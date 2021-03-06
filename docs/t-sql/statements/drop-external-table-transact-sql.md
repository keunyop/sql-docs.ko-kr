---
title: DROP EXTERNAL TABLE(Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: sql-data-warehouse, pdw, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 02a6a236-0756-4570-abfa-6f677a7df042
author: CarlRabeler
ms.author: carlrab
manager: craigg
monikerRange: '>=aps-pdw-2016||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 3260abf50bf46a703a925f8ad0a7829d2d1c1315
ms.sourcegitcommit: 3cfedfeba377560d460ca3e42af1e18824988c07
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59042352"
---
# <a name="drop-external-table-transact-sql"></a>DROP EXTERNAL TABLE(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2016-xxxx-asdw-pdw-md.md)]

  데이터베이스에서 PolyBase 외부 테이블을 제거하지만, 외부 데이터는 삭제하지 않습니다.  
  
 ![문서 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "문서 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
DROP EXTERNAL TABLE [ database_name . [schema_name ] . | schema_name . ] table_name   
[;]  
```  
  

## <a name="arguments"></a>인수  
 `[ database_name . [schema_name] . | schema_name . ] table_name`  
 제거할 외부 테이블의 한 부분에서 세 부분으로 이루어진 이름입니다. 테이블 이름은 선택적으로 스키마 또는 데이터베이스와 스키마를 포함할 수 있습니다.  
  
## <a name="permissions"></a>사용 권한  
  
-   테이블이 속한 스키마에 대한 **ALTER** 권한이 필요합니다.  
  
## <a name="general-remarks"></a>일반적인 주의 사항  
 외부 테이블을 삭제하면 모든 테이블 관련 메타데이터가 제거됩니다. 외부 데이터는 삭제되지 않습니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-using-basic-syntax"></a>1. 기본 구문 사용  
  
```  
DROP EXTERNAL TABLE SalesPerson;  
DROP EXTERNAL TABLE dbo.SalesPerson;  
DROP EXTERNAL TABLE EasternDivision.dbo.SalesPerson;  
```  
  
### <a name="b-dropping-an-external-table-from-the-current-database"></a>2. 현재 데이터베이스에서 외부 테이블 삭제  
 다음 예제에서는 현재 데이터베이스에서 `ProductVendor1` 테이블, 해당 데이터, 인덱스 및 종속된 뷰를 제거합니다.  
  
```  
DROP EXTERNAL TABLE ProductVendor1;  
```  
  
### <a name="c-dropping-a-table-from-another-database"></a>C. 다른 데이터베이스에서 테이블 삭제  
 다음 예에서는 `EasternDivision` 데이터베이스에서 `SalesPerson` 테이블을 삭제합니다.  
  
```  
DROP EXTERNAL TABLE EasternDivision.dbo.SalesPerson;  
```  
  
## <a name="see-also"></a>참고 항목  
 [CREATE EXTERNAL TABLE&#40;Transact-SQL&#41;](../../t-sql/statements/create-external-table-transact-sql.md)  
  
