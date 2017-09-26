---
title: "catalog.operations (SSISDB 데이터베이스) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- operations view [Integration Services]
- catalog.operations view [Integration Services]
ms.assetid: 9455c5b1-60ff-45fc-8599-cc3abbd6daf5
caps.latest.revision: 29
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: f9d1969e9fe7bcb2104003cfab057effcd35da5d
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="catalogoperations-ssisdb-database"></a>catalog.operations(SSISDB 데이터베이스)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 카탈로그에 있는 모든 작업에 대한 자세한 정보를 표시합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|operation_id|**bigint**|작업의 고유 식별자(ID)입니다.|  
|operation_type|**smallint**|작업의 유형입니다.|  
|created_time|**datetimeoffset**|작업이 생성된 시간입니다.|  
|object_type|**smallint**|작업의 영향을 받는 개체의 유형입니다. 개체는 폴더(`10`), 프로젝트(`20`), 패키지(`30`), 환경(`40`) 또는 실행 인스턴스(`50`)일 수 있습니다.|  
|object_id|**bigint**|작업의 영향을 받는 개체의 ID입니다.|  
|object_name|**nvarchar (260)**|개체 이름입니다.|  
|상태|**int**|작업의 상태입니다. 가능한 값은 생성됨(`1`), 실행 중(`2`), 취소됨(`3`), 실패(`4`), 보류 중(`5`), 갑자기 종료됨(`6`), 성공(`7`), 중지 중(`8`) 및 완료(`9`)입니다.|  
|start_time|**datetimeoffset**|작업이 시작된 시간입니다.|  
|end_time|**datetimeoffsset**|작업이 종료된 시간입니다.|  
|caller_sid|**varbinary(85)**|Windows 인증을 사용하여 로그온한 사용자의 보안 ID(SID)입니다.|  
|caller_name|**nvarchar (128)**|작업을 수행한 계정의 이름입니다.|  
|process_id|**int**|외부 프로세스의 프로세스 ID입니다(해당되는 경우).|  
|stopped_by_sid|**varbinary(85)**|작업을 중지한 사용자의 SID입니다.|  
|stopped_by_name|**nvarchar (128)**|작업을 중지한 사용자의 이름입니다.|  
|server_name|**nvarchar (128)**|Windows 서버 및 지정된 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스에 대한 인스턴스 정보입니다.|  
|machine_name|**nvarchar (128)**|서버 인스턴스가 실행 중인 컴퓨터 이름입니다.|  
  
## <a name="remarks"></a>주의  
 이 뷰는 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 카탈로그에 있는 각 작업에 대한 하나의 행을 표시합니다. 이를 통해 관리자는 프로젝트 배포 또는 패키지 실행과 같은 서버에서 수행된 모든 논리적 작업을 열거할 수 있습니다.  
  
 이 보기에 나열 된 다음 작업 유형을 표시는 **operation_type** 열:  
  
|**operation_type** 값|**operation_type** 설명|**object_id** 설명|**object_name** 설명|  
|-------------------------------|-------------------------------------|--------------------------------|----------------------------------|  
|`1`|[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 초기화|**NULL**|**NULL**|  
|`2`|보존 기간<br /><br /> (SQL 에이전트 작업)|**NULL**|**NULL**|  
|`3`|MaxProjectVersion<br /><br /> (SQL 에이전트 작업)|**NULL**|**NULL**|  
|`101`|**deploy_project**<br /><br /> (저장 프로시저)|프로젝트 ID|프로젝트 이름|  
|`106`|**restore_project**<br /><br /> (저장 프로시저)|프로젝트 ID|프로젝트 이름|  
|`200`|**create_execution** 및 **start_execution**<br /><br /> (저장 프로시저)|프로젝트 ID|**NULL**|  
|`202`|**stop_operation**<br /><br /> (저장 프로시저)|프로젝트 ID|**NULL**|  
|`300`|**validate_project**<br /><br /> (저장 프로시저)|프로젝트 ID|프로젝트 이름|  
|`301`|**validate_package**<br /><br /> (저장 프로시저)|프로젝트 ID|패키지 이름|  
|`1000`|**configure_catalog**<br /><br /> (저장 프로시저)|**NULL**|**NULL**||  
  
## <a name="permissions"></a>Permissions  
 이 뷰를 보려면 다음 권한 중 하나가 필요합니다.  
  
-   작업에 대한 READ 권한  
  
-   멤버 자격에는 **ssis_admin** 데이터베이스 역할  
  
-   멤버 자격에는 **sysadmin** 서버 역할  
  
> [!NOTE]  
>  서버에서 작업을 수행할 권한이 있으면 작업에 대한 정보를 볼 수 있는 권한도 있습니다. 행 수준 보안이 적용됩니다. 따라서 볼 수 있는 권한이 있는 행만 표시됩니다.  
  
  