---
title: sys.dm_external_script_execution_stats | Microsoft Docs
ms.custom: ''
ms.date: 10/28/2018
ms.prod: sql
ms.reviewer: ''
ms.technology: ''
ms.topic: language-reference
f1_keywords:
- sys.dm_external_script_execution_stats
- sys.dm_external_script_execution_stats_TSQL
- dm_external_script_execution_stats
- dm_external_script_execution_stats_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_external_script_execution_stats dynamic management view
ms.assetid: 2e99f026-ceb2-42a2-a549-c71d31ed0cf4
author: HeidiSteen
ms.author: heidist
manager: cgronlund
ms.openlocfilehash: 8bdbaf1fdb0fb0c27127611ace0fac00d861838f
ms.sourcegitcommit: c2322c1a1dca33b47601eb06c4b2331b603829f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2018
ms.locfileid: "50743138"
---
# <a name="sysdmexternalscriptexecutionstats"></a>sys.dm_external_script_execution_stats
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

외부 스크립트 요청의 각 유형에 대해 하나의 행을 반환합니다. 외부 스크립트 요청이 지원되는 외부 스크립트 언어로 그룹화됩니다. 각 등록된 외부 스크립트 함수에 대해 행이 하나씩 생성됩니다. 임의의 외부 스크립트 함수는 `rxExec`같은 부모 프로세스에 의해 전송되지 않는 한 기록되지 않습니다.
  
> [!NOTE]  
> 이 동적 관리 뷰 (DMV)는 설치 하 고 외부 스크립트 실행을 지 원하는 기능을 사용 하도록 설정 하는 경우에 사용할 수 있습니다. 자세한 내용은 [SQL Server 2016에서 R Services](../../advanced-analytics/r/sql-server-r-services.md) 하 고 [Machine Learning 서비스 (R, Python) SQL Server 2017의](../../advanced-analytics/what-is-sql-server-machine-learning.md)합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|language|**nvarchar**|등록된 외부 스크립트 언어의 이름입니다. 각 외부 스크립트에서 연결된 실행 프로그램을 시작하려면 스크립트 요청에서 언어를 지정 해야 합니다. |  
|counter_name|**nvarchar**|등록된 외부 스크립트 함수의 이름입니다. Null을 허용하지 않습니다.|  
|counter_value|**integer**|서버에서 등록된 외부 스크립트 함수를 호출한 총 인스턴스 수입니다. 이 값은 누적되며, 인스턴스에 기능이 설치된 시간부터 시작되어 다시 설정할 수 없습니다.|  

  
## <a name="permissions"></a>사용 권한  
 서버에 대한 VIEW SERVER STATE 권한이 필요합니다.  
  
> [!NOTE]  
>  외부 스크립트를 실행하는 사용자에게는 추가 권한 EXECUTE ANY EXTERNAL SCRIPT가 있어야 합니다. 하지만 이 DMV는 이 권한이 없는 관리자가 사용할 수 있습니다. 
  
## <a name="remarks"></a>Remarks  
  이 DMV는 내부 원격 분석용으로 제공되어 [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)]에서 제공되는 새로운 외부 스크립트 실행 기능의 전반적인 사용을 모니터링합니다. 원격 분석 서비스는 LaunchPad가 실행될 때 시작되고, 등록된 외부 스크립트 함수를 호출할 때마다 디스크 기반 카운터를 늘립니다.

일반적으로 생성된 프로세스가 활성 상태인 경우에만 성능 카운터가 유효합니다. 따라서 DMV에서 쿼리는 실행이 중지된 서비스의 데이터 세부 정보를 표시할 수 없습니다. 예를 들어 시작 관리자 외부 스크립트를 실행 하 고 아직 매우 빠르게 완료 하는 경우 기존의 DMV 데이터가 표시 되지 않을 수 있습니다.

따라서 이 DMV에서 추적하는 카운터는 계속 실행 중 상태로 인스턴스가 종료되더라도 디스크에 쓰기를 사용하여 sys.dm_external_script_requests의 상태를 유지합니다.

   
  
### <a name="counter-values"></a>카운터 값
SQL Server 2016에서 지원 되는 유일한 외부 언어는 R 및 외부 스크립트 요청에서 처리 됩니다 [!INCLUDE[rsql_productname_md](../../includes/rsql-productname-md.md)]합니다. SQL Server 2017에서는 R 및 Python 모두 지원 되는 외부 언어 이며 외부 스크립트 요청에서 처리 됩니다 [!INCLUDE[rsql_productname_md](../../includes/rsql-productnamenew-md.md)]합니다.

R에 대 한이 DMV는 인스턴스에서 실행 된 R 호출 수를 추적 합니다. 예를 들어 `rxLinMod` 가 호출되어 병렬로 실행될 때 카운터는 1씩 증가합니다.
 
R 언어에서 *counter_name* 필드에 표시되는 카운터 값은 등록된 ScaleR 함수 이름을 나타냅니다. *counter_value* 필드 값은 특정 ScaleR 함수의 누적 인스턴스 수를 나타냅니다. 

Python의 경우이 DMV는 인스턴스에서 Python 호출 된 횟수를 추적 합니다.

수는 인스턴스에서 기능을 설치하고 사용하도록 설정되면 시작되며 상태를 유지 관리하는 파일이 관리자에 의해 삭제되거나 덮어쓸 때까지 누적됩니다. 따라서 일반적으로 *counter_value*에서는 값을 다시 설정할 수 없습니다. 세션, 일정 시간 또는 기타 시간 간격을 기준으로 사용량을 모니터링하려면 개수를 테이블에 캡처하는 것이 좋습니다.

### <a name="registration-of-external-script-functions-in-r"></a>R의 외부 스크립트 함수 등록

R에서 임의 스크립트를 지원 하 고 R 커뮤니티는 고유한 함수 및 메서드를 사용 하 여 각 많은 천 패키지를 제공 합니다. 그러나 이 DMV는 SQL Server R Services에 설치된 ScaleR 함수만 모니터링합니다.

이러한 함수는 기능이 설치될 때 등록되며 등록된 함수는 추가하거나 삭제할 수 없습니다.

## <a name="examples"></a>예  
  
### <a name="viewing-the-number-of-r-scripts-run-on-the-server"></a>서버에서 실행되는 R 스크립트 수 보기  
 다음 예제에서는 R 언어에 대해 누적된 외부 스크립트 실행 수를 표시합니다.  
  
```  
SELECT counter_name, counter_value   
FROM sys.dm_external_script_execution_stats   
WHERE language = 'R';
```  

### <a name="viewing-the-number-of-python-scripts-run-on-the-server"></a>서버에서 스크립트 실행 Python 수 보기  
 다음 예제에서는 Python 언어에 대 한 외부 스크립트 실행의 누적 수를 표시 합니다.  
  
```  
SELECT counter_name, counter_value   
FROM sys.dm_external_script_execution_stats   
WHERE language = 'Python';
```  

  
## <a name="see-also"></a>관련 항목  
 [동적 관리 뷰 및 함수&#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [실행 관련 동적 관리 뷰 및 함수&#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/execution-related-dynamic-management-views-and-functions-transact-sql.md) 
[sys.dm_external_script_requests](../../relational-databases/system-dynamic-management-views/sys-dm-external-script-requests.md)  
[sp_execute_external_script](../../relational-databases/system-stored-procedures/sp-execute-external-script-transact-sql.md)  
  

