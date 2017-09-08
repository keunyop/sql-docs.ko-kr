---
title: LEN (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 09/03/2015
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- LEN
- LEN_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- LEN function
- characters [SQL Server], number of
- number of characters
ms.assetid: fa20fee4-884d-4301-891a-c03e901345ae
caps.latest.revision: 47
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 532b996c23a8f9746a52434d78783da2a24d1add
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="len-transact-sql"></a>LEN(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  지정한 문자열 식의 후행 공백을 제외한 문자 수를 반환합니다.  
  
> [!NOTE]  
>  식을 표시 하는 데 사용 되는 바이트 수를 반환 하려면 사용 하 여는 [DATALENGTH](../../t-sql/functions/datalength-transact-sql.md) 함수입니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
LEN ( string_expression )  
```  
  
## <a name="arguments"></a>인수  
 *string_expression*  
 문자열은 [식](../../t-sql/language-elements/expressions-transact-sql.md) 계산 되도록 합니다. *string_expression* 상수, 변수 또는 문자 또는 이진 데이터의 열 수 있습니다.  
  
## <a name="return-types"></a>반환 형식  
 **bigint** 경우 *식* 입니다는 **varchar (max)**, **nvarchar (max)** 또는 **varbinary (max)** 데이터 형식입니다. 그렇지 않으면 **int**합니다.  
  
 SC 데이터 정렬을 사용하는 경우 반환되는 정수 값에서는 UTF-16 서로게이트 쌍이 단일 문자로 계산됩니다. 자세한 내용은 [Collation and Unicode Support](../../relational-databases/collations/collation-and-unicode-support.md)을 참조하세요.  
  
## <a name="remarks"></a>주의  
 LEN 후행 공백을 제외합니다. 문제가 있는 경우에 사용 하 여 여는 [DATALENGTH &#40; Transact SQL &#41; ](../../t-sql/functions/datalength-transact-sql.md) 함수에 문자열을 트리밍 하지 않습니다. 유니코드 문자열을 처리 하는 경우 DATALENGTH 두 배 문자 수를 반환 합니다. 다음 예제에서는 후행 공백이 있는 LEN 및 DATALENGTH을 보여 줍니다.  
  
```  
DECLARE @v1 varchar(40),  
    @v2 nvarchar(40);  
SELECT   
@v1 = 'Test of 22 characters ',   
@v2 = 'Test of 22 characters ';  
SELECT LEN(@v1) AS [varchar LEN] , DATALENGTH(@v1) AS [varchar DATALENGTH];  
SELECT LEN(@v2) AS [nvarchar LEN], DATALENGTH(@v2) AS [nvarchar DATALENGTH];  
  
```  
  
## <a name="examples"></a>예  
 다음 예에서는 `FirstName`에 있는 사람의 `Australia` 데이터 및 문자 수를 선택합니다. 다음 예에서는 [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] 데이터베이스를 사용합니다.  
  
```  
SELECT LEN(FirstName) AS Length, FirstName, LastName   
FROM Sales.vIndividualCustomer  
WHERE CountryRegionName = 'Australia';  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>예: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] 및[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 다음 예에서는 열에 있는 문자의 수를 반환 `FirstName` 에 있는 직원의 성과 이름 및 `Australia`합니다.  
  
```  
-- Uses AdventureWorks  
  
SELECT DISTINCT LEN(FirstName) AS FNameLength, FirstName, LastName   
FROM dbo.DimEmployee AS e  
INNER JOIN dbo.DimGeography AS g   
    ON e.SalesTerritoryKey = g.SalesTerritoryKey   
WHERE EnglishCountryRegionName = 'Australia';  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `FNameLength  FirstName  LastName`  
  
 `-----------  ---------  ---------------`  
  
 `4            Lynn       Tsoflias`  
  
## <a name="see-also"></a>관련 항목:  
 [데이터 형식&#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)   
 [문자열 함수 &#40; Transact SQL &#41;](../../t-sql/functions/string-functions-transact-sql.md)   
 [DATALENGTH &#40; Transact SQL &#41;](../../t-sql/functions/datalength-transact-sql.md)   
 [왼쪽 &#40; Transact SQL &#41;](../../t-sql/functions/left-transact-sql.md)   
 [오른쪽 &#40; Transact SQL &#41;](../../t-sql/functions/right-transact-sql.md)  
  
  


