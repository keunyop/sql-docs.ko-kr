---
title: sp_changedynamicsnapshot_job (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_changedynamicsnapshot_job
- sp_changedynamicsnapshot_job_TSQL
helpviewer_keywords:
- sp_changedynamicsnapshot_job
ms.assetid: ea0dacd2-a5fd-42f4-88dd-7d289b0ae017
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 8ab11ccb8853c00439583162f33e76d0e14622a1
ms.sourcegitcommit: 2db83830514d23691b914466a314dfeb49094b3c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58493145"
---
# <a name="spchangedynamicsnapshotjob-transact-sql"></a>sp_changedynamicsnapshot_job(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  매개 변수가 있는 행 필터를 사용하여 구독에 대한 스냅숏을 생성하는 에이전트 작업을 게시로 수정합니다. 이 저장 프로시저는 게시 데이터베이스의 게시자에서 실행됩니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_changedynamicsnapshot_job [ @publication = ] 'publication'  
    [ , [ @dynamic_snapshot_jobname = ] 'dynamic_snapshot_jobname' ]  
    [ , [ @dynamic_snapshot_jobid = ] 'dynamic_snapshot_jobid' ]  
    [ , [ @frequency_type = ] frequency_type ]   
    [ , [ @frequency_interval = ] frequency_interval ]   
    [ , [ @frequency_subday = ] frequency_subday ]   
    [ , [ @frequency_subday_interval = ] frequency_subday_interval ]   
    [ , [ @frequency_relative_interval = ] frequency_relative_interval ]   
    [ , [ @frequency_recurrence_factor = ] frequency_recurrence_factor ]   
    [ , [ @active_start_date = ] active_start_date ]   
    [ , [ @active_end_date = ] active_end_date ]   
    [ , [ @active_start_time_of_day = ] active_start_time_of_day ]   
    [ , [ @active_end_time_of_day = ] active_end_time_of_day ]   
    [ , [ @job_login = ] 'job_login' ]   
    [ , [ @job_password = ] 'job_password' ]   
```  
  
## <a name="arguments"></a>인수  
`[ @publication = ] 'publication'` 게시의 이름이입니다. *게시* 됩니다 **sysname**, 기본값은 없습니다.  
  
`[ @dynamic_snapshot_jobname = ] 'dynamic_snapshot_jobname'` 변경 될 스냅숏 작업의 이름입니다. *dynamic_snapshot_jobname*됩니다 **sysname**, 기본값은 N '%'. 하는 경우 *dynamic_snapshot_jobid* 를 지정 하면 기본 값을 사용 해야 *dynamic_snapshot_jobname*합니다.  
  
`[ @dynamic_snapshot_jobid = ] 'dynamic_snapshot_jobid'` 변경 될 스냅숏 작업의 ID입니다. *dynamic_snapshot_jobid* 됩니다 **uniqueidentifier**, 기본값은 NULL입니다. 하는 경우 *dynamic_snapshot_jobname*를 지정 하면 기본 값을 사용 해야 *dynamic_snapshot_jobid*합니다.  
  
`[ @frequency_type = ] frequency_type` 에이전트를 예약 하는 빈도입니다. *frequency_type* 됩니다 **int**, 이며 다음 값 중 하나일 수 있습니다.  
  
|값|Description|  
|-----------|-----------------|  
|**1**|한 번|  
|**2**|요청 시|  
|**4**|일별|  
|**8**|매주|  
|**16**|매월|  
|**32**|매월 상대적|  
|**64**|자동 시작|  
|**128**|되풀이|  
|NULL(기본값)||  
  
`[ @frequency_interval = ] frequency_interval` 에이전트가 실행 되는 요일입니다. *frequency_interval* 됩니다 **int**, 이며 다음 값 중 하나일 수 있습니다.  
  
|값|Description|  
|-----------|-----------------|  
|**1**|일요일|  
|**2**|월요일|  
|**3**|화요일|  
|**4**|수요일|  
|**5**|목요일|  
|**6**|금요일|  
|**7**|토요일|  
|**8**|Day|  
|**9**|평일|  
|**10**|주말|  
|NULL(기본값)||  
  
`[ @frequency_subday = ] frequency_subday` 정의 된 기간 동안 다시 예약 하는 빈도 방법이입니다. *frequency_subday* 됩니다 **int**, 이며 다음 값 중 하나일 수 있습니다.  
  
|값|Description|  
|-----------|-----------------|  
|**1**|한 번|  
|**2**|Second|  
|**4**|Minute|  
|**8**|Hour|  
|NULL(기본값)||  
  
`[ @frequency_subday_interval = ] frequency_subday_interval` 에 대 한 간격인 *frequency_subday*합니다. *frequency_subday_interval* 됩니다 **int**, 기본값은 NULL입니다.  
  
`[ @frequency_relative_interval = ] frequency_relative_interval` 병합 에이전트가 실행 되는 날짜가입니다. 이 매개 변수를 사용 하면 *frequency_type* 로 설정 된 **32** (매월 상대적)입니다. *frequency_relative_interval* 됩니다 **int**, 이며 다음 값 중 하나일 수 있습니다.  
  
|값|Description|  
|-----------|-----------------|  
|**1**|첫째|  
|**2**|Second|  
|**4**|셋째|  
|**8**|넷째|  
|**16**|마지막|  
|NULL(기본값)||  
  
`[ @frequency_recurrence_factor = ] frequency_recurrence_factor` 사용 하는 되풀이 비율 *frequency_type*합니다. *frequency_recurrence_factor* 됩니다 **int**, 기본값은 NULL입니다.  
  
`[ @active_start_date = ] active_start_date` 가 경우 병합 에이전트 첫 번째 예약 된 날짜 이며 YYYYMMDD 형식으로 합니다. *active_start_date* 됩니다 **int**, 기본값은 NULL입니다.  
  
`[ @active_end_date = ] active_end_date` 병합 에이전트가 중지 되 면 날짜 예약 된 형식은 YYYYMMDD입니다. *active_end_date* 됩니다 **int**, 기본값은 NULL입니다.  
  
`[ @active_start_time_of_day = ] active_start_time_of_day` 병합 에이전트가 처음 하루 중 시간 예약 된 hhmmss입니다. *active_start_time_of_day* 됩니다 **int**, 기본값은 NULL입니다.  
  
`[ @active_end_time_of_day = ] active_end_time_of_day` 하루 중에서 병합 에이전트에 예약 된 형식은 HHMMSS입니다. *active_end_time_of_day* 됩니다 **int**, 기본값은 NULL입니다.  
  
`[ @job_login = ] 'job_login'` 가 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 매개 변수가 있는 행 필터를 사용 하 여 구독에 대 한 스냅숏을 생성할 때 스냅숏 에이전트가 실행 되는 Windows 계정입니다. *job_login* 됩니다 **nvarchar(257)**, 기본값은 NULL입니다.  
  
`[ @job_password = ] 'job_password'` 매개 변수가 있는 행 필터를 사용 하는 구독에 대 한 스냅숏을 생성할 때 스냅숏 에이전트가 실행 되는 Windows 계정의 암호입니다. *job_password* 됩니다 **nvarchar(257)**, 기본값은 NULL입니다.  
  
> [!IMPORTANT]  
>  가능한 경우 런타임 시 사용자에게 보안 자격 증명을 입력하라는 메시지가 표시됩니다. 자격 증명을 스크립트 파일에 저장해야 하는 경우에는 파일에 무단으로 액세스하지 못하도록 보안을 설정해야 합니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="remarks"></a>Remarks  
 **sp_changedynamicsnapshot_job** 매개 변수가 있는 행 필터로 게시에 대 한 병합 복제에 사용 됩니다.  
  
 에이전트 로그인 또는 암호를 변경한 후 에이전트를 중지하고 다시 시작해야 변경 내용이 적용됩니다.  
  
## <a name="permissions"></a>사용 권한  
 멤버는 **sysadmin** 고정된 서버 역할 또는 **db_owner** 고정된 데이터베이스 역할을 실행할 수 있습니다 **sp_changedynamicsnapshot_job**합니다.  
  
## <a name="see-also"></a>관련 항목  
 [복제 보안 설정 보기 및 수정](../../relational-databases/replication/security/view-and-modify-replication-security-settings.md)   
 [Snapshots for Merge Publications with Parameterized Filters](../../relational-databases/replication/create-a-snapshot-for-a-merge-publication-with-parameterized-filters.md)  
  
  
