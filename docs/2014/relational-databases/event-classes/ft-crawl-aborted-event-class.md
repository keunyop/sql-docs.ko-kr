---
title: FT:Crawl Aborted 이벤트 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Crawl Aborted event class
ms.assetid: eead8ea6-5051-4689-ab30-4dfbfda01fb9
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: ba7914456e4ffcf19a52c6e7f7206a390147cc2f
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52772685"
---
# <a name="ftcrawl-aborted-event-class"></a>FT:Crawl Aborted 이벤트 클래스
  **FT:Crawl Aborted** 이벤트 클래스는 전체 텍스트 탐색 도중 예외가 발생했음을 나타냅니다. 오류가 발생하면 보통 전체 텍스트 탐색이 중지됩니다. 자세한 오류 정보는 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 이벤트 로그 또는 탐색 로그를 참조하십시오.  
  
## <a name="ftcrawl-aborted-event-class-data-columns"></a>FT:Crawl Aborted 이벤트 클래스 데이터 열  
  
|데이터 열 이름|데이터 형식|Description|열 ID|필터 가능|  
|----------------------|---------------|-----------------|---------------|----------------|  
|**DatabaseID**|**int**|전체 텍스트 탐색이 실행되는 데이터베이스의 ID입니다. DB_ID 함수를 사용하여 데이터베이스의 값을 확인할 수 있습니다.|3|사용자 계정 컨트롤|  
|**오류**|**int**|지정된 이벤트의 오류 번호입니다. 종종 **sysmessages** 테이블에 저장된 오류 번호를 나타냅니다.|31|사용자 계정 컨트롤|  
|**EventClass**|**int**|이벤트 유형 = 157|27|아니요|  
|**EventSequence**|**int**|요청 내에 지정된 이벤트 시퀀스입니다.|51|아니요|  
|**IsSystem**|**int**|이벤트가 시스템 프로세스에서 발생했는지 아니면 사용자 프로세스에서 발생했는지를 나타냅니다. 1 = 시스템, 0 = 사용자|60|사용자 계정 컨트롤|  
|**Exchange Spill**|**int**|오류가 발생했을 때 전체 텍스트 탐색이 실행되는 개체의 시스템 할당 ID입니다.|22|사용자 계정 컨트롤|  
|**SessionLoginName**|**nvarchar**|세션을 시작한 사용자의 로그인 이름입니다. 예를 들어 Login1을 사용하여 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에 연결하고 Login2로 문을 실행할 경우 **SessionLoginName** 은 Login1을 표시하고 **LoginName** 은 Login2를 표시합니다. 이 열은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 및 Windows 로그인을 모두 표시합니다.|64|사용자 계정 컨트롤|  
|**SPID**|**int**|이벤트가 발생한 세션의 ID입니다.|12|사용자 계정 컨트롤|  
|**StartTime**|**datetime**|이벤트가 시작된 시간입니다(사용 가능한 경우).|14|사용자 계정 컨트롤|  
|**State**|**int**|오류 상태 코드입니다.|30|사용자 계정 컨트롤|  
|**TransactionID**|**bigint**|시스템이 할당한 트랜잭션의 ID입니다.|4|사용자 계정 컨트롤|  
  
## <a name="see-also"></a>관련 항목  
 [sp_trace_setevent&#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
