---
title: "순위 함수 (Transact SQL) | Microsoft Docs"
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- ranking functions
- row ranking [SQL Server]
- functions [SQL Server], ranking
- ranking rows
ms.assetid: e7f917ba-bf4a-4fe0-b342-a91bcf88a71b
caps.latest.revision: 31
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 4865abf5682586cab26ca9dbb78afee04f11c590
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="ranking-functions-transact-sql"></a>순위 함수(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  순위 함수는 파티션에서 각 행의 순위 값을 반환합니다. 사용하는 함수에 따라 어떤 행은 다른 행과 동일한 값을 받을 수 있습니다. 순위 함수는 확정적이지 않습니다.  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)]은 다음과 같은 순위 함수를 제공합니다.  
  
|||  
|-|-|  
|[순위](../../t-sql/functions/rank-transact-sql.md)|[NTILE](../../t-sql/functions/ntile-transact-sql.md)|  
|[DENSE_RANK](../../t-sql/functions/dense-rank-transact-sql.md)|[ROW_NUMBER](../../t-sql/functions/row-number-transact-sql.md)|  
  
## <a name="examples"></a>예  
 다음은 동일한 쿼리에 사용된 4가지 순위 함수를 보여 줍니다. 함수별 예에 대한 자세한 내용은 각 순위 함수를 참조하십시오.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT p.FirstName, p.LastName  
    ,ROW_NUMBER() OVER (ORDER BY a.PostalCode) AS "Row Number"  
    ,RANK() OVER (ORDER BY a.PostalCode) AS Rank  
    ,DENSE_RANK() OVER (ORDER BY a.PostalCode) AS "Dense Rank"  
    ,NTILE(4) OVER (ORDER BY a.PostalCode) AS Quartile  
    ,s.SalesYTD  
    ,a.PostalCode  
FROM Sales.SalesPerson AS s   
    INNER JOIN Person.Person AS p   
        ON s.BusinessEntityID = p.BusinessEntityID  
    INNER JOIN Person.Address AS a   
        ON a.AddressID = p.BusinessEntityID  
WHERE TerritoryID IS NOT NULL AND SalesYTD <> 0;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
|FirstName|LastName|Row Number|Rank|Dense Rank|Quartile|SalesYTD|PostalCode|  
|---------------|--------------|----------------|----------|----------------|--------------|--------------|----------------|  
|Michael|Blythe|1.|1|1|1.|4557045.0459|98027|  
|Linda|Mitchell|2|1|1|1.|5200475.2313|98027|  
|Jillian|Carson|3|1|1|1.|3857163.6332|98027|  
|Garrett|Vargas|4|1|1|1.|1764938.9859|98027|  
|Tsvi|Reiter|5|1.|1|2|2811012.7151|98027|  
|Shu|Ito|6|6|2|2|3018725.4858|98055|  
|José|Saraiva|7|6|2|2|3189356.2465|98055|  
|David|Campbell|8|6|2|3|3587378.4257|98055|  
|Tete|Mensa-Annan|9|6|2|3|1931620.1835|98055|  
|Lynn|Tsoflias|10|6|2|3|1758385.926|98055|  
|Rachel|Valdez|11|6|2|4|2241204.0424|98055|  
|Jae|Pak|12|6|2|4|5015682.3752|98055|  
|Ranjit|Varkey Chudukatil|13|6|2|4|3827950.238|98055|  
  
## <a name="see-also"></a>관련 항목:  
 [기본 제공 함수s&#40;Transact-SQL&#41;](~/t-sql/functions/functions.md)   
 [절 &#40; 조치 Transact SQL &#41;](../../t-sql/queries/select-over-clause-transact-sql.md)  
  
  
