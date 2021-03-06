---
title: Oracle CDC 인스턴스 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ed71e8c4-e013-4bf2-8b6c-1e833ff2a41d
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: 0152594c213196860e80ff5d5267356977404b7d
ms.sourcegitcommit: 5a8678bf85f65be590676745a7fe4fcbcc47e83d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58393051"
---
# <a name="the-oracle-cdc-instance"></a>Oracle CDC 인스턴스
  Oracle CDC 인스턴스는 단일 Oracle 원본 데이터베이스에서 캡처된 변경 내용을 처리하기 위해 Oracle CDC Service에서 만든 프로세스입니다. Oracle CDC 인스턴스는 **cdc.xdbcdc_config** 테이블에서 구성을 검색하고 **cdc.xdbcdc_state** 테이블에서 상태를 유지 관리합니다. 이러한 테이블은 Oracle CDC 인스턴스를 정의하는 CDC 데이터베이스의 일부입니다. xdbcdc 데이터베이스 및 테이블에 대한 자세한 내용은 [The CDC Databases](the-oracle-cdc-service.md)를 참조하십시오.  
  
 다음은 Oracle CDC 인스턴스에 의해 수행되는 태스크에 대한 설명입니다.  
  
-   **서비스 시작 확인 처리**: CDC 인스턴스에에서 구성을 로드 시작 되 면 합니다 **xdbcdc_config** 테이블과 일련 수행 상태 확인 있는지 CDC 인스턴스 지속된 상태가 일관 되 고 처리를 시작할 수 있습니다 변경 내용입니다.  
  
-   **변경 캡처 준비**: 확인에 통과하면 Oracle CDC 인스턴스는 현재 정의된 모든 캡처 인스턴스를 검색하고 변경 캡처에 필요한 Oracle LogMiner 쿼리와 다른 지원 구조를 준비합니다. 또한 Oracle 인스턴스는 Oracle CDC 인스턴스를 마지막으로 실행할 때 저장된 내부 캡처 상태를 다시 로드합니다.  
  
-   **Oracle에서 변경 내용 캡처**: Oracle CDC 인스턴스는 Oracle LogMiner 기능을 사용하여 Oracle에서 변경 내용을 풀링하여 트랜잭션 커밋에 따라 정렬한 다음 트랜잭션 시간을 변경하여 CDC 데이터베이스의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 변경 테이블에 기록합니다.  
  
-   **서비스 종료 처리**: Oracle CDC 인스턴스의 수명 주기는 Oracle CDC Service에 의해 관리 됩니다. Oracle CDC 인스턴스는 종료하도록 요청되면 다음 태스크를 수행합니다.  
  
    -   Oracle 트랜잭션 로그 읽기를 중지합니다.  
  
    -   CDC 데이터베이스에 완료된 Oracle 트랜잭션 쓰기를 중지합니다.  
  
    -   필요한 경우 현재 트랜잭션이 CDC 데이터베이스에 기록될 때까지 30초까지 대기합니다. 30초가 초과되면 쓰기가 취소되고 트랜잭션이 롤백됩니다(CDC 인스턴스를 다시 시작하면 다시 시도됨).  
  
    -   별도의 스레드에서 최대 30초 동안 메모리에 캐시된 레코드를 준비된 트랜잭션 테이블에 최대한 많이 기록한 다음(오래된 트랜잭션부터 순서대로) **xdbcdc_state** 테이블을 업데이트하고 모든 변경 내용을 커밋합니다.  
  
-   **구성 변경 처리**: 새 버전을 검색 하거나 CDC Service를 통해 구성 변경 내용을 통지 하는 Oracle CDC 인스턴스를 **cdc.xdbcdc_config** 테이블입니다. 대부분의 변경(예: 캡처 인스턴스 추가 또는 제거)은 Oracle CDC 인스턴스를 다시 시작할 필요가 없습니다. 일부 변경(예: Oracle 연결 문자열 또는 액세스 자격 증명 변경)은 CDC 인스턴스를 다시 시작해야 합니다.  
  
-   **복구 처리**: 내부 상태에서 복원 된 Oracle CDC 인스턴스가 시작 될 때 합니다 **xdbcdc_state** 하며 **xdbcdc_staged_transactions** 테이블입니다. 상태가 복원되면 CDC 인스턴스가 평소와 같이 진행됩니다.  
  
## <a name="see-also"></a>관련 항목  
 [오류 처리](error-handling.md)  
  
  
