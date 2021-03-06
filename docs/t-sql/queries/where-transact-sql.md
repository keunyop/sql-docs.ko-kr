---
title: WHERE(Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 08/09/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- WHERE_TSQL
- WHERE
dev_langs:
- TSQL
helpviewer_keywords:
- retrieving rows
- clauses [SQL Server], WHERE
- WHERE clause, about WHERE clause
- row retrieval [SQL Server], WHERE clause
- WHERE clause
ms.assetid: a8430421-7bce-4fab-a2d2-56c00a3c6fa4
author: VanMSFT
ms.author: vanto
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: d43fc27fc3536f296f49f40bb6233e961c4b9f12
ms.sourcegitcommit: 670082cb47f7d3d82e987b549b6f8e3a8968b5db
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57334420"
---
# <a name="where-transact-sql"></a>WHERE(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  쿼리가 반환하는 행에 대한 검색 조건을 지정합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
[ WHERE <search_condition> ]  
```  
  
## <a name="arguments"></a>인수  
\< *search_condition* > 행을 반환 하기 위해 충족될 조건을 정의합니다. 검색 조건에 포함시킬 수 있는 조건자의 개수에는 제한이 없습니다. 검색 조건 및 조건자에 대한 자세한 내용은 [검색 조건&#40;Transact-SQL&#41;](../../t-sql/queries/search-condition-transact-sql.md)을 참조하세요.  
  
## <a name="examples"></a>예  
 다음 예에서는 `WHERE` 절에서 일부 일반 검색 조건을 사용하는 방법을 보여 줍니다.  
  
### <a name="a-finding-a-row-by-using-a-simple-equality"></a>1. 간단 비교를 사용하여 행 찾기  
  
```  
-- Uses AdventureWorksDW  
  
SELECT EmployeeKey, LastName  
FROM DimEmployee  
WHERE LastName = 'Smith' ;  
```  
  
### <a name="b-finding-rows-that-contain-a-value-as-part-of-a-string"></a>2. 값을 문자열의 일부로 포함하는 행 찾기  
  
```  
-- Uses AdventureWorksDW  
  
SELECT EmployeeKey, LastName  
FROM DimEmployee  
WHERE LastName LIKE ('%Smi%');  
```  
  
### <a name="c-finding-rows-by-using-a-comparison-operator"></a>C. 비교 연산자를 사용하여 행 찾기  
  
```  
-- Uses AdventureWorksDW  
  
SELECT EmployeeKey, LastName  
FROM DimEmployee  
WHERE EmployeeKey  <= 500;  
```  
  
### <a name="d-finding-rows-that-meet-any-of-three-conditions"></a>D. 세 가지 조건 중 하나를 충족하는 행 찾기  
  
```  
-- Uses AdventureWorksDW  
  
SELECT EmployeeKey, LastName  
FROM DimEmployee  
WHERE EmployeeKey = 1 OR EmployeeKey = 8 OR EmployeeKey = 12;  
```  
  
### <a name="e-finding-rows-that-must-meet-several-conditions"></a>E. 여러 조건을 모두 충족하는 행 찾기  
  
```  
-- Uses AdventureWorksDW  
  
SELECT EmployeeKey, LastName  
FROM DimEmployee  
WHERE EmployeeKey <= 500 AND LastName LIKE '%Smi%' AND FirstName LIKE '%A%';  
```  
  
### <a name="f-finding-rows-that-are-in-a-list-of-values"></a>F. 값 목록에 있는 행 찾기  
  
```  
-- Uses AdventureWorksDW  
  
SELECT EmployeeKey, LastName  
FROM DimEmployee  
WHERE LastName IN ('Smith', 'Godfrey', 'Johnson');  
```  
  
### <a name="g-finding-rows-that-have-a-value-between-two-values"></a>G. 두 값 사이의 값을 가진 행 찾기  
  
```  
-- Uses AdventureWorksDW  
  
SELECT EmployeeKey, LastName  
FROM DimEmployee  
WHERE EmployeeKey Between 100 AND 200;  
```  
  
## <a name="see-also"></a>참고 항목  
 [DELETE&#40;Transact-SQL&#41;](../../t-sql/statements/delete-transact-sql.md)   
 [조건자&#40;Transact-SQL&#41;](~/t-sql/queries/predicates.md)   
 [검색 조건&#40;Transact-SQL&#41;](../../t-sql/queries/search-condition-transact-sql.md)   
 [SELECT&#40;Transact-SQL&#41;](../../t-sql/queries/select-transact-sql.md)   
 [UPDATE&#40;Transact-SQL&#41;](../../t-sql/queries/update-transact-sql.md)   
 [MERGE&#40;Transact-SQL&#41;](../../t-sql/statements/merge-transact-sql.md)  
  
  


