---
title: sp_helpdatatypemap (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_helpdatatypemap
- sp_helpdatatypemap_TSQL
helpviewer_keywords:
- sp_helpdatatypemap
ms.assetid: 800c9c65-723e-4961-a63d-327987f129f0
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: bf42231158f646e34c63bd148ba66c9780b14785
ms.sourcegitcommit: c44014af4d3f821e5d7923c69e8b9fb27aeb1afd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58529595"
---
# <a name="sphelpdatatypemap-transact-sql"></a>sp_helpdatatypemap(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  간의 정의 된 데이터 형식 매핑에 대 한 정보 반환 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 및 비- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] DBMS (데이터베이스 관리 시스템). 이 저장 프로시저는 모든 데이터베이스의 배포자에서 실행됩니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_helpdatatypemap [ @source_dbms = ] 'source_dbms'   
    [ , [ @source_version = ] 'source_version' ]  
    [ , [ @source_type = ] 'source_type' ]   
    [ , [ @destination_dbms = ] 'destination_dbms' ]  
    [ , [ @destination_version = ] 'destination_version' ]  
    [ , [ @destination_type = ] 'destination_type' ]  
    [ , [ @defaults_only = ] defaults_only ]  
```  
  
## <a name="arguments"></a>인수  
`[ @source_dbms = ] 'source_dbms'` 데이터 형식이 매핑된 DBMS의 이름이입니다. *source_dbms* 됩니다 **sysname**, 이며 다음 값 중 하나일 수 있습니다.  
  
|값|Description|  
|-----------|-----------------|  
|**MSSQLSERVER**|원본은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스입니다.|  
|**ORACLE**|원본은 Oracle 데이터베이스입니다.|  
  
`[ @source_version = ] 'source_version'` 원본 DBMS의 제품 버전이입니다. *source_version*됩니다 **varchar(10)**, 데이터 형식 원본 DBMS에서 반환 되는 모든 버전에 대 한 매핑을 지정 하지 않으면. 결과 집합을 DBMS 원본 버전으로 필터링하도록 설정합니다.  
  
`[ @source_type = ] 'source_type'` 원본 DBMS에에서 나열 된 데이터 형식입니다. *source_type* 됩니다 **sysname**를 지정 하지 않으면 하는 경우 원본 DBMS의에서 모든 데이터 형식에 대 한 매핑이 반환 됩니다. 결과 집합을 원본 DBMS의 데이터 형식으로 필터링하도록 설정합니다.  
  
`[ @destination_dbms = ] 'destination_dbms'` 대상 DBMS의 이름이입니다. *destination_dbms* 됩니다 **sysname**, 이며 다음 값 중 하나일 수 있습니다.  
  
|값|Description|  
|-----------|-----------------|  
|**MSSQLSERVER**|대상은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스입니다.|  
|**ORACLE**|대상은 Oracle 데이터베이스입니다.|  
|**DB2**|대상은 IBM DB2 데이터베이스입니다.|  
|**SYBASE**|대상은 Sybase 데이터베이스입니다.|  
  
`[ @destination_version = ] 'destination_version'` 대상 DBMS의 제품 버전이입니다. *destination_version*됩니다 **varchar(10)** 를 지정 하지 않으면 하는 경우 대상 DBMS의 모든 버전에 대 한 매핑이 반환 됩니다. 결과 집합을 DBMS 대상 버전으로 필터링하도록 설정합니다.  
  
`[ @destination_type = ] 'destination_type'` 대상 DBMS에에서 나열 된 데이터 형식입니다. *destination_type*됩니다 **sysname**를 지정 하지 않으면 하는 경우 대상 DBMS의에서 모든 데이터 형식에 대 한 매핑이 반환 됩니다. 결과 집합을 대상 DBMS의 데이터 형식으로 필터링하도록 설정합니다.  
  
`[ @defaults_only = ] defaults_only` 기본 데이터 형식 매핑만 반환 되는지만 됩니다. *defaults_only* 됩니다 **비트**, 기본값은 **0**합니다. **1** 의미는 기본 데이터 형식 매핑이 반환 됩니다. **0** 반환 되는 기본 및 사용자 정의 데이터 형식 매핑 의미 합니다.  
  
## <a name="result-sets"></a>결과 집합  
  
|열 이름|Description|  
|-----------------|-----------------|  
|**mapping_id**|데이터 형식 매핑을 식별합니다.|  
|**source_dbms**|원본 DBMS의 이름 및 버전 번호입니다.|  
|**source_type**|원본 DBMS의 데이터 형식입니다.|  
|**destination_dbms**|대상 DBMS의 이름입니다.|  
|**destination_type**|대상 DBMS의 데이터 형식입니다.|  
|**is_default**|매핑이 기본값인지 또는 대체 매핑인지 여부를 나타냅니다. 값이 **0** 이 매핑이 사용자 정의 임을 나타냅니다.|  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="remarks"></a>Remarks  
 **sp_helpdatatypemap** 에서 SQL Server 이외 게시자와의 데이터 형식 매핑을 정의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 이외 게시자 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 구독자입니다.  
  
 원본 및 대상 DBMS의 지정 된 조합을 지원 하지 않는 경우 **sp_helpdatatypemap** 빈 결과 집합을 반환 합니다.  
  
## <a name="permissions"></a>사용 권한  
 멤버만 합니다 **sysadmin** 고정된 서버 역할의 멤버나 배포자 합니다 **db_owner** 고정된 데이터베이스 역할의 배포 데이터베이스를 실행할 수 있습니다 **sp_helpdatatypemap**.  
  
## <a name="see-also"></a>관련 항목  
 [sp_getdefaultdatatypemapping &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-getdefaultdatatypemapping-transact-sql.md)   
 [sp_setdefaultdatatypemapping &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-setdefaultdatatypemapping-transact-sql.md)  
  
  
