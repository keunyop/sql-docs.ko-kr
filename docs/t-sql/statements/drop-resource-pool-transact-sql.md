---
title: "삭제할 리소스 풀 (Transact SQL) | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DROP RESOURCE POOL
- DROP_RESOURCE_POOL_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- DROP RESOURCE POOL
ms.assetid: 18cd6dd9-7a6d-4a08-b9d5-649af23583d5
caps.latest.revision: 21
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 72d609a56d8d0327d72a74f173445f666b78f09c
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="drop-resource-pool-transact-sql"></a>DROP RESOURCE POOL(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  사용자 정의 리소스 관리자 리소스 풀을 삭제합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [TRANSACT-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
DROP RESOURCE POOL pool_name  
[ ; ]  
```  
  
## <a name="arguments"></a>인수  
 *pool_name 이라*  
 기존 사용자 정의 리소스 풀의 이름입니다.  
  
## <a name="remarks"></a>주의  
 작업 그룹이 들어 있으면 해당 리소스 풀을 삭제할 수 없습니다.  
  
 리소스 관리자 기본 풀 또는 내부 풀을 삭제할 수 없습니다.  
  
 DDL 문을 실행할 경우 리소스 관리자 상태에 대해 잘 알고 있는 것이 좋습니다. 자세한 내용은 참조 [리소스 관리자](../../relational-databases/resource-governor/resource-governor.md)합니다.  
  
## <a name="permissions"></a>Permissions  
 CONTROL SERVER 권한이 필요합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 `big_pool`라는 리소스 풀을 삭제합니다.  
  
```  
DROP RESOURCE POOL big_pool;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a>관련 항목:  
 [리소스 관리자](../../relational-databases/resource-governor/resource-governor.md)   
 [CREATE RESOURCE POOL&#40;Transact-SQL&#41;](../../t-sql/statements/create-resource-pool-transact-sql.md)   
 [ALTER RESOURCE POOL&#40;Transact-SQL&#41;](../../t-sql/statements/alter-resource-pool-transact-sql.md)   
 [CREATE WORKLOAD GROUP&#40;Transact-SQL&#41;](../../t-sql/statements/create-workload-group-transact-sql.md)   
 [ALTER WORKLOAD GROUP&#40;Transact-SQL&#41;](../../t-sql/statements/alter-workload-group-transact-sql.md)   
 [DROP WORKLOAD GROUP&#40;Transact-SQL&#41;](../../t-sql/statements/drop-workload-group-transact-sql.md)   
 [ALTER RESOURCE GOVERNOR&#40;Transact-SQL&#41;](../../t-sql/statements/alter-resource-governor-transact-sql.md)  
  
  