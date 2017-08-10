---
title: "영향을 받는 개체 (SybaseToSQL) 선택 하 고 구성 | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
helpviewer_keywords:
- Tester Component,Affected Objects
ms.assetid: a219df74-543a-4aec-aeeb-79f90ac3e2ee
caps.latest.revision: 8
author: sabotta
ms.author: carlasab
manager: lonnyb
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 8e5f4fcb5af81da2b78520542e2b57bd66bc4fd1
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="selecting-and-configuring-affected-objects-sybasetosql"></a>영향을 받는 개체 (SybaseToSQL) 선택 및 구성
이 페이지에서 테이블을 선택할 수 있습니다 및 SSMA 이전 단계에서 선택한 개체에 대 한 실행의 결과 확인 하는 경우 비교 외래 키를 변경 해야 합니다. 또한 확인 매개 변수를 사용자 지정할 수 있습니다.  
  
## <a name="selection-of-affected-objects"></a>영향을 받는 개체 선택  
Sybase 개체 트리에서 창의 왼쪽에 있는 테이블과 외래 키를 확인 중인 변경 내용이 동일한 것에 대 한 비교 해야 합니다.  
  
레이블이 링크 표시는 SSMA 테스터는 이러한 개체 중 하나를 확인할 수 없는, **일부 선택 된 개체에 오류가 포함 되어** 개체 트리 아래 합니다. 이러한 개체를 비교할 수 없는 이유는 이유를 표시 하 고 잘못 된 개체의 선택을 취소 하려면이 링크를 클릭 합니다.  
  
## <a name="table"></a>테이블  
테이블 탭 선택한 테이블의 표 뷰를 포함 합니다. 표에서 선택한 테이블에 대 한 다음과 같은 정보가 포함 되어 있습니다.  
  
-   열 이름  
  
-   데이터 형식  
  
-   전체 자릿수  
  
-   소수 자릿수  
  
-   규칙  
  
-   기본값  
  
-   ID  
  
-   Null 허용  
  
## <a name="sql"></a>Sql  
SQL 탭에 "Create table" 선택한 테이블의 SQL 합니다.  
  
## <a name="data"></a>Data  
데이터 탭에는 선택한 테이블에 데이터가 표시 됩니다.  
  
## <a name="properties"></a>속성  
속성 탭에 선택한 표 속성이 표시 됩니다. 다음 필드 속성 탭에서 제공 됩니다.  
  
-   만들었거나 마지막으로 수정한  
  
-   Object Name  
  
## <a name="table-comparison-settings"></a>테이블 비교 설정  
테이블에 대 한 비교 규칙에 설정 **테이블 비교** 페이지. 다음 설정을 만들 수 있습니다.  
  
### <a name="comparison-mode"></a>비교 모드  
테이블 내용을 정의 비교를 수행 합니다.  
  
-   선택 하는 경우 **변경 내용만**, 테이블 행의 전체 비교 수행 됩니다.  
  
-   선택 하는 경우 **전체**, 변경 된 행만 비교가 수행 됩니다.  
  
## <a name="column-comparison-settings"></a>열 비교 설정  
테이블 열에 대 한 비교 규칙에 설정 **열 비교** 페이지. 다음 설정을 만들 수 있습니다.  
  
### <a name="use-during-test-comparisons"></a>테스트 비교 중에 사용  
이 열은 테스트 결과 확인에 참여 하는 경우를 결정 합니다.  
  
-   선택 하면 **True**, SSMA는 Sybase에서 SQL Server에 있는 열의 내용으로 테스트를 실행 한 후이 열의 내용을 비교 합니다.
  
-   선택 하면 **False**, 열 결과 확인에서 제외 됩니다.  
  
### <a name="use-custom-scale"></a>사용자 지정 배율이 사용  
숫자 데이터 형식의 열에 대 한 비교에 대 한 사용자 지정 배율이 설정할 수 있습니다.  
  
-   선택 하면 **True**, 숫자 값에 따라 반올림 됩니다는 **비교 눈금** 비교 하기 전에 값입니다.  
  
-   선택 하면 **False**, 숫자 비교를 정확 하 게 됩니다.  
  
### <a name="comparing-scale"></a>소수 자릿수를 비교합니다.  
  
-   경우에만 사용할 수는 **사용 하 여 사용자 지정 배율** 옵션이로 설정 되어 **True**합니다. 숫자 비교에 대 한 전체 자릿수입니다.  
  
### <a name="date-time-comparing"></a>날짜 시간 비교  
정의 방법: 날짜/시간 값을 비교 합니다.  
  
-   선택 하는 경우 **전체 날짜 비교**, 두 플랫폼 모두에서 값의 전체 비교 수행 됩니다.  
  
-   선택 하는 경우 **날짜만 비교**, 시간 부분 무시 됩니다.  
  
-   선택 하는 경우 **시간만 비교**, 날짜 부분 무시 됩니다.  
  
-   선택 하는 경우 **무시 밀리초**, 초까지 결과 비교 합니다.  
  
-   선택 하는 경우 **무시 날짜 및 시간 (밀리초)**, 결과 초의 소수 부분 시간 부분에만 비교 하 고 무시 됩니다.  
  
### <a name="ignore-strings-case"></a>문자열의 대/소문자 무시  
비교의 대/소문자 구분을 제어합니다.  
  
-   선택 하면 **True**, 비교 시 대/소문자 구분 하지 것입니다.  
  
-   선택 하면 **False**, 대/소문자 비교를 고려 합니다.  
  
## <a name="comparing-sql"></a>SQL 비교  
SSMA 테스터에서 생성 된 SELECT 문의 볼 수는 **비교 SQL** 페이지. 테스터-행 단위에서 이러한 문의 결과 집합을 비교 합니다. Sybase 결과 집합의 다음 각 행은 결과에서 생성 된 집합의 다음 행으로 동일 해야 합니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]합니다.  
  
사용자 지정 확인 기능을 제공 하는 SELECT 문을 편집할 수 있습니다. Sybase 및 변경 내용을 저장 하려면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 문을 사용 하 여는 **적용** 원본 및 대상 SQL, 아래까지 단추입니다.  
  
## <a name="next-step"></a>다음 단계  
[호출 순서 &#40; 사용자 지정 SybaseToSQL &#41;](../../ssma/sybase/customizing-calls-order-sybasetosql.md)  
  
## <a name="see-also"></a>관련 항목:  
[테스트 사례 &#40; 실행 SybaseToSQL &#41;](../../ssma/sybase/running-test-cases-sybasetosql.md)  
[데이터베이스 개체 &#40; 마이그레이션 테스트 SybaseToSQL &#41;](../../ssma/sybase/testing-migrated-database-objects-sybasetosql.md)  
  
