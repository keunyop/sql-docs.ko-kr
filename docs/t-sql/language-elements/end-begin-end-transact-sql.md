---
title: "END (BEGIN... 끝) (Transact SQL) | Microsoft Docs"
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- END
- END_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- enclosing statements [SQL Server]
- END keyword
- BEGIN...END keyword
- END (BEGIN...END) keyword
ms.assetid: 354c4935-1375-4141-8195-61326662f4d2
caps.latest.revision: 34
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: f7a3c01fd0a038d226edcf605774c3a75f49b4f1
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="end-beginend-transact-sql"></a>END(BEGIN...END)(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  그룹으로 실행되는 일련의 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문을 묶습니다. BEGIN...END 블록은 중첩될 수 있습니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
BEGIN   
     { sql_statement | statement_block }   
END   
```  
  
## <a name="arguments"></a>인수  
 { *sql_statement*| *statement_block*}  
 문 블록에 정의된 유효한 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문이나 문 그룹입니다. 문 블록(일괄 처리)을 정의하려면 흐름 제어 언어 키워드인 BEGIN과 END를 사용합니다. BEGIN...END 블록 내의 모든 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문이 유효해도 특정 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문을 동일한 일괄 처리(문 블록) 내에서 그룹화할 수 없습니다.  
  
## <a name="result-types"></a>결과 형식  
 **Boolean**  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>예: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] 및[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 다음 예에서 `BEGIN` 및 `END` 일련의 정의 [!INCLUDE[DWsql](../../includes/dwsql-md.md)] 함께 실행 되는 문입니다. 경우는 `BEGIN...END` 블록 포함 되지 않은 경우, 다음 예제에서는 연속 반복에 포함 됩니다.  
  
```  
-- Uses AdventureWorks  
  
DECLARE @Iteration Integer = 0  
WHILE @Iteration <10  
BEGIN  
    SELECT FirstName, MiddleName   
    FROM dbo.DimCustomer WHERE LastName = 'Adams';  
SET @Iteration += 1  
END;  
  
```  
  
## <a name="see-also"></a>관련 항목:  
 [ALTER TRIGGER&#40;Transact-SQL&#41;](../../t-sql/statements/alter-trigger-transact-sql.md)   
 [시작 중... 최종 &#40; Transact SQL &#41;](../../t-sql/language-elements/begin-end-transact-sql.md)   
 [흐름 제어 언어 &#40; Transact SQL &#41;](~/t-sql/language-elements/control-of-flow.md)   
 [CREATE TRIGGER&#40;Transact-SQL&#41;](../../t-sql/statements/create-trigger-transact-sql.md)   
 [다른 &#40; 덮어쓰려는 경우... 다른 &#41; &#40; Transact SQL &#41;](../../t-sql/language-elements/else-if-else-transact-sql.md)   
 [다음과 같은 경우... 다른 &#40; Transact SQL &#41;](../../t-sql/language-elements/if-else-transact-sql.md)   
 [WHILE&#40;Transact-SQL&#41;](../../t-sql/language-elements/while-transact-sql.md)  
  
  


