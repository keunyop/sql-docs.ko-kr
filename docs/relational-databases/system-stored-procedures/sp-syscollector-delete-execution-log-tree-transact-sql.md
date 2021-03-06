---
title: sp_syscollector_delete_execution_log_tree (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_syscollector_delete_execution_log_tree_TSQL
- sp_syscollector_delete_execution_log_tree
dev_langs:
- TSQL
helpviewer_keywords:
- sp_syscollector_delete_execution_log_tree
- data collector [SQL Server], stored procedures
ms.assetid: 0a9a7c5b-c3cc-40ca-b524-e948a8cce4e4
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: be3f468db321f1e8ba7af3d7b5b80c97803a0b4b
ms.sourcegitcommit: c44014af4d3f821e5d7923c69e8b9fb27aeb1afd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58531245"
---
# <a name="spsyscollectordeleteexecutionlogtree-transact-sql"></a>sp_syscollector_delete_execution_log_tree(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  하나의 컬렉션 집합 실행에 대한 모든 로그 항목을 삭제합니다. 또한 이러한 실행에 대한 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 테이블의 로그 항목도 삭제합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_syscollector_delete_execution_log_tree[ @log_id = ] log_id  
          , [ @from_collection_set = ] from_collection_set  
```  
  
## <a name="arguments"></a>인수  
`[ @log_id = ] log_id` 컬렉션에 대 한 고유 식별자를 로그를 설정 됩니다. *log_id* 됩니다 **int**합니다.  
  
`[ @from_collection_set = ] from_collection_set` 컬렉션 집합에 대 한 식별자가입니다. *from_collection_set* 됩니다 **bit 1 =** 합니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="permissions"></a>사용 권한  
 멤버 자격이 필요 합니다 **dc_operator** (EXECUTE 권한 있음)와이 프로시저를 실행 하려면 고정된 데이터베이스 역할.  
  
## <a name="see-also"></a>관련 항목  
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
