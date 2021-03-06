---
title: sp_dbmmonitorresults (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_dbmmonitorresults
- sp_dbmmonitorresults_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_dbmmonitorresults
- database mirroring [SQL Server], monitoring
ms.assetid: d575e624-7d30-4eae-b94f-5a7b9fa5427e
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 54cf9a13396674c2ac9dd43845c94d7ac657f008
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47702751"
---
# <a name="spdbmmonitorresults-transact-sql"></a>sp_dbmmonitorresults(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  데이터베이스 미러링 모니터링 기록이 저장된 상태 테이블에서 모니터링된 데이터베이스에 대한 상태 행을 반환하고 프로시저에서 최신 상태를 미리 가져올지 여부를 선택할 수 있도록 합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_dbmmonitorresults database_name   
   , rows_to_return  
    , update_status   
```  
  
## <a name="arguments"></a>인수  
 *database_name*  
 미러링 상태를 반환할 데이터베이스를 지정합니다.  
  
 *rows_to_return*  
 반환되는 행 수를 지정합니다.  
  
 0 = 마지막 행  
  
 1 = 마지막 2시간 동안의 행  
  
 2 = 마지막 4시간 동안의 행  
  
 3 = 마지막 8시간 동안의 행  
  
 4 = 마지막 1일 동안의 행  
  
 5 = 마지막 2일 동안의 행  
  
 6 = 마지막 100 개 행  
  
 7 = 마지막 500 행  
  
 8 = 마지막 1,000 행  
  
 9 = 마지막 1,000,000개의 행  
  
 *update_status*  
 결과를 반환하기 전의 프로시저 동작을 지정합니다.  
  
 0 = 데이터베이스의 상태를 업데이트하지 않습니다. 결과는 마지막 두 개의 행만 사용하여 계산되고 두 행의 사용 기간은 상태 테이블의 새로 고침 시기에 따라 달라집니다.  
  
 1 = 호출 하 여 데이터베이스에 대 한 상태를 업데이트 **sp_dbmmonitorupdate** 결과 계산 하기 전에 합니다. 그러나 상태 테이블이 이전 15 초, 또는 사용자 내에 업데이트 된 없으면의 멤버는 **sysadmin** 고정 서버 역할 **sp_dbmmonitorresults** 상태를 업데이트 하지 않고 실행 합니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 없음  
  
## <a name="result-sets"></a>결과 집합  
 지정한 데이터베이스에 대해 요청된 개수의 기록 상태 행을 반환합니다. 각 행에는 다음 정보가 들어 있습니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**database_name**|**sysname**|미러된 데이터베이스의 이름입니다.|  
|**role**|**int**|서버 인스턴스의 현재 미러링 역할입니다.<br /><br /> 1 = 주 서버<br /><br /> 2 = 미러 서버|  
|**mirroring_state**|**int**|데이터베이스의 상태입니다.<br /><br /> 0 = 일시 중지됨<br /><br /> 1 = 연결 끊김<br /><br /> 2 = 동기화 중<br /><br /> 3 = 장애 조치(Failover) 보류 중<br /><br /> 4 = 동기화됨|  
|**witness_status**|**int**|데이터베이스의 데이터베이스 미러링 세션에서 미러링 모니터 서버의 연결 상태로, 다음 값을 가질 수 있습니다.<br /><br /> 0 = 알 수 없음<br /><br /> 1 = 연결됨<br /><br /> 2 = 연결 끊김|  
|**log_generation_rate**|**int**|이 데이터베이스의 이전 미러링 상태 업데이트 이후 생성된 로그의 양(KB/초)입니다.|  
|**unsent_log**|**int**|주 서버의 Send Queue에 있는 보내지 않은 로그의 크기(KB)입니다.|  
|**send_rate**|**int**|주 서버에서 미러 서버로의 로그 전송 속도(KB/초)입니다.|  
|**unrestored_log**|**int**|미러 서버에 있는 Redo Queue의 크기(KB)입니다.|  
|**recovery_rate**|**int**|미러 서버의 다시 실행 속도(KB/초)입니다.|  
|**transaction_delay**|**int**|모든 트랜잭션의 총 지연(밀리초)입니다.|  
|**transactions_per_sec**|**int**|주 서버 인스턴스에서 초당 수행되는 트랜잭션 수입니다.|  
|**average_delay**|**int**|데이터베이스 미러링 때문에 주 서버 인스턴스에서 각 트랜잭션에 대해 발생하는 평균 지연 시간입니다. 성능 우선 모드에서(SAFETY 속성이 OFF로 설정된 경우) 이 값은 일반적으로 0입니다.|  
|**time_recorded**|**datetime**|데이터베이스 미러링 모니터에서 행을 기록한 시간입니다. 주 서버의 시스템 클럭 시간입니다.|  
|**time_behind**|**datetime**|미러 데이터베이스가 현재 동기화되는 주 서버의 대략적인 시스템 클럭 시간입니다. 이 값은 주 서버 인스턴스에서만 의미가 있습니다.|  
|**local_time**|**datetime**|이 행이 업데이트된 로컬 서버 인스턴스의 시스템 클럭 시간입니다.|  
  
## <a name="remarks"></a>Remarks  
 **sp_dbmmonitorresults** 의 컨텍스트에서만 실행할 수 있습니다 합니다 **msdb** 데이터베이스입니다.  
  
## <a name="permissions"></a>사용 권한  
 멤버 자격이 필요 합니다 **sysadmin** 고정된 서버 역할 또는 **dbm_monitor** 고정된 데이터베이스 역할을 **msdb** 데이터베이스. 합니다 **dbm_monitor** 역할에 해당 멤버 데이터베이스 미러링 상태를 보고 하지만 하지 업데이트 하지만 하지 보기 또는 구성 데이터베이스 미러링 이벤트를 사용 하도록 설정 합니다.  
  
> [!NOTE]  
>  처음 **sp_dbmmonitorupdate** 실행 만듭니다 합니다 **dbm_monitor** 고정된 데이터베이스 역할에는 **msdb** 데이터베이스. 멤버는 **sysadmin** 고정된 서버 역할에 임의의 사용자를 추가할 수는 **dbm_monitor** 고정된 데이터베이스 역할.  
  
## <a name="examples"></a>예  
 다음 예에서는 데이터베이스의 상태를 업데이트하지 않고 이전 2시간 동안 기록된 행을 반환합니다.  
  
```  
USE msdb;  
EXEC sp_dbmmonitorresults AdventureWorks2012, 2, 0;  
```  
  
## <a name="see-also"></a>관련 항목  
 [데이터베이스 미러링 모니터링&#40;SQL Server&#41;](../../database-engine/database-mirroring/monitoring-database-mirroring-sql-server.md)   
 [sp_dbmmonitorchangemonitoring &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitorchangemonitoring-transact-sql.md)   
 [sp_dbmmonitoraddmonitoring &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitoraddmonitoring-transact-sql.md)   
 [sp_dbmmonitordropmonitoring &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitordropmonitoring-transact-sql.md)   
 [sp_dbmmonitorhelpmonitoring &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitorhelpmonitoring-transact-sql.md)   
 [sp_dbmmonitorupdate&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitorupdate-transact-sql.md)  
  
  
