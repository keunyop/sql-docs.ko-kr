---
title: DROP USER (TRANSACT-SQL) | Microsoft Docs
ms.custom:
- SQL2016_New_Updated
ms.date: 05/12/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DROP_USER_TSQL
- DROP USER
dev_langs:
- TSQL
helpviewer_keywords:
- dropping users
- DROP USER statement
- deleting users
- database user removal [SQL Server]
- removing users
- users [SQL Server], removing
ms.assetid: d6e0e21a-7568-4321-b6d6-bcfba183a719
caps.latest.revision: 43
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 7d1af03b517cbef82d0ed1c9f7affb6b7d6eda21
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="drop-user-transact-sql"></a>DROP USER(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  현재 데이터베이스에서 사용자를 제거합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
-- Syntax for SQL Server and Azure SQL Database  
  
DROP USER [ IF EXISTS ] user_name  
```  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
DROP USER user_name  
```  
  
## <a name="arguments"></a>인수  
 *경우에 존재*  
 **적용 대상**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] 통해 [현재 버전](http://go.microsoft.com/fwlink/p/?LinkId=299658), [!INCLUDE[sssds](../../includes/sssds-md.md)]).  
  
 조건에 따라 이미 있는 경우에 사용자를 삭제 합니다.  
  
 *user_name*  
 이 데이터베이스 내에서 사용자를 식별하는 이름을 지정합니다.  
  
## <a name="remarks"></a>주의  
 보안 개체를 소유하는 사용자는 데이터베이스에서 삭제할 수 없습니다. 보안 개체를 소유하는 데이터베이스 사용자를 삭제하려면 먼저 해당 보안 개체의 소유권을 삭제하거나 이전해야 합니다.  
  
 게스트 사용자는 삭제할 수 없지만 master 또는 tempdb 이외의 데이터베이스 내에서 REVOKE CONNECT FROM GUEST를 실행하면 게스트 사용자의 CONNECT 권한이 취소되므로 사용할 수 없게 됩니다.  
  
> [!CAUTION]  
>  [!INCLUDE[ssCautionUserSchema](../../includes/sscautionuserschema-md.md)]  
  
## <a name="permissions"></a>Permissions  
 데이터베이스에 대한 ALTER ANY USER 권한이 필요합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 `AbolrousHazem` 데이터베이스에서 `AdventureWorks2012` 데이터베이스 사용자를 제거합니다.  
  
```  
DROP USER AbolrousHazem;  
GO  
```  
  
## <a name="see-also"></a>관련 항목:  
 [CREATE USER&#40;Transact-SQL&#41;](../../t-sql/statements/create-user-transact-sql.md)   
 [ALTER USER&#40;Transact-SQL&#41;](../../t-sql/statements/alter-user-transact-sql.md)   
 [EVENTDATA&#40;Transact-SQL&#41;](../../t-sql/functions/eventdata-transact-sql.md)  
  
