---
title: DATEFROMPARTS (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/29/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DATEFROMPARTS_TSQL
- DATEFROMPARTS
dev_langs:
- TSQL
helpviewer_keywords:
- DATEFROMPARTS function
ms.assetid: 5b885376-87aa-41f1-9e18-04987aead250
caps.latest.revision: 16
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 3365c40b5bc4fb57a8e09cc97e706a16fbd709ec
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="datefromparts-transact-sql"></a>DATEFROMPARTS(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-all_md](../../includes/tsql-appliesto-ss2012-all-md.md)]

반환 된 **날짜** 지정 된 연도, 월 및 일에 대 한 값입니다.
  
![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>구문  
  
```sql
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
DATEFROMPARTS ( year, month, day )  
```  
  
## <a name="arguments"></a>인수  
*연도*  
연도를 지정하는 정수 식입니다.
  
*월*  
1에서 12까지의 숫자로 월을 지정하는 정수 식입니다.
  
*일*  
일을 지정하는 정수 식입니다.
  
## <a name="return-types"></a>반환 형식
**date**
  
## <a name="remarks"></a>주의  
**DATEFROMPARTS** 반환는 **날짜** 값과 지정 된 연도, 월 및 일을로 설정 날짜 부분과 시간 부분이 기본값으로 설정 합니다. 인수가 유효하지 않으면 오류가 발생합니다. 필수 인수가 Null일 경우에는 Null이 반환됩니다.
  
이 함수는 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] 이상 서버에 대해서는 원격으로 실행할 수 있지만 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] 이전 버전의 서버에 대해서는 원격으로 실행할 수 없습니다.
  
## <a name="examples"></a>예  
다음 예제는 **DATEFROMPARTS** 함수입니다.
  
```sql
SELECT DATEFROMPARTS ( 2010, 12, 31 ) AS Result;  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
Result  
----------------------------------  
2010-12-31  
  
(1 row(s) affected)  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>예: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] 및[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
다음 예제는 **DATEFROMPARTS** 함수입니다.
  
```sql
SELECT DATEFROMPARTS ( 2010, 12, 31 ) AS Result;  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
Result  
----------------------------------  
2010-12-31  
  
(1 row(s) affected)  
```  
  
## <a name="see-also"></a>참고 항목
[date&#40;Transact-SQL&#41;](../../t-sql/data-types/date-transact-sql.md)
  
  

