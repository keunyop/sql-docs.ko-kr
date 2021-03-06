---
title: sp_helparticledts (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_helparticledts
- sp_helparticledts_TSQL
helpviewer_keywords:
- sp_helparticledts
ms.assetid: cd1aed60-e056-4ff3-86ee-62b19433d890
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: cac631425a43870395fa0adceb0bb041d70e1932
ms.sourcegitcommit: c44014af4d3f821e5d7923c69e8b9fb27aeb1afd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58530555"
---
# <a name="sphelparticledts-transact-sql"></a>sp_helparticledts(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic을 사용하여 변환 구독을 만들 때 사용할 정확한 사용자 지정 태스크 이름에 대한 정보를 가져오는 데 사용합니다. 이 저장 프로시저는 게시 데이터베이스의 게시자에서 실행됩니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_helparticledts [ @publication = ] 'publication', [ @article = ] 'article'  
```  
  
## <a name="arguments"></a>인수  
`[ @publication = ] 'publication'` 게시의 이름이입니다. *게시* 됩니다 **sysname**, 기본값은 없습니다.  
  
`[ @article = ] 'article'` 게시에서 아티클의 이름이입니다. *문서* 됩니다 **sysname**, 기본값은 없습니다.  
  
## <a name="result-sets"></a>결과 집합  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**pre_script_ignore_error_task_name**|**sysname**|스냅숏 데이터가 복사되기 전에 수행되는 프로그래밍 작업의 태스크 이름입니다. 스크립트 오류가 발생해도 프로그램 실행은 계속됩니다.|  
|**pre_script_task_name**|**sysname**|스냅숏 데이터가 복사되기 전에 수행되는 프로그래밍 작업의 태스크 이름입니다. 오류가 발생하면 프로그램 실행을 중단합니다.|  
|**transformation_task_name**|**sysname**|데이터 기반 쿼리 작업을 사용하는 경우 프로그래밍 작업의 태스크 이름입니다.|  
|**post_script_ignore_error_task_name**|**sysname**|스냅숏 데이터가 복사된 후에 수행되는 프로그래밍 작업의 태스크 이름입니다. 스크립트 오류가 발생해도 프로그램 실행은 계속됩니다.|  
|**post_script_task_name**|**sysname**|스냅숏 데이터가 복사된 후에 수행되는 프로그래밍 작업의 태스크 이름입니다. 오류가 발생하면 프로그램 실행을 중단합니다.|  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="remarks"></a>Remarks  
 **sp_helparticledts** 스냅숏 복제 및 트랜잭션 복제에 사용 됩니다.  
  
 복제 DTS(데이터 변환 서비스) 프로그램에서 태스크를 명명할 때 복제 에이전트가 요구하는 명명 규칙을 따라야 합니다. Execute SQL 작업 등 사용자 지정 태스크의 경우 이름은 아티클 이름, 접두사 및 선택적 부분으로 이루어진 연결 문자열입니다. 코드를 쓰는 경우 사용할 작업 이름이 확실치 않으면 결과 집합이 지정하는 태스크 이름을 사용해야 합니다.  
  
## <a name="permissions"></a>사용 권한  
 멤버는 **sysadmin** 고정된 서버 역할 및 **db_owner** 고정된 데이터베이스 역할을 실행할 수 있습니다 **sp_helparticledts**합니다.  
  
  
