---
title: "catalog.extended_operation_info (SSISDB 데이터베이스) | Microsoft Docs"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: db299b45-557d-4c62-8e14-355cdb051f63
caps.latest.revision: 13
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 4d89a9adbf89dcc89715832664dcca176cd7f2ff
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="catalogextendedoperationinfo-ssisdb-database"></a>catalog.extended_operation_info(SSISDB 데이터베이스)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 카탈로그에 있는 모든 작업에 대한 확장 정보를 표시합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|info_id|**bigint**|확장 정보의 고유 식별자(ID)입니다.|  
|operation_id|**bigint**|확장 정보에 해당하는 작업의 고유 ID입니다.|  
|object_name|**nvarchar (260)**|개체 이름입니다.|  
|object_type|**smallint**|작업의 영향을 받는 개체의 유형입니다. 개체는 폴더(`10`), 프로젝트(`20`), 패키지(`30`), 환경(`40`) 또는 실행 인스턴스(`50`)일 수 있습니다.|  
|reference_id|**bigint**|작업에 사용된 참조의 고유 ID입니다.|  
|상태|**int**|작업의 상태입니다. 가능한 값은 생성됨(`1`), 실행 중(`2`), 취소됨(`3`), 실패(`4`), 보류 중(`5`), 갑자기 종료됨(`6`), 성공(`7`), 중지 중(`8`) 및 완료(`9`)입니다.|  
|start_time|**(7)**|작업이 시작된 날짜 및 시간입니다.|  
|end_time|**(7)**|작업이 종료된 날짜 및 시간입니다.|  
  
## <a name="remarks"></a>주의  
 한 작업에 여러 확장 정보 행이 있을 수 있습니다.  
  
## <a name="permissions"></a>Permissions  
 이 뷰를 보려면 다음 권한 중 하나가 필요합니다.  
  
-   작업에 대한 READ 권한  
  
-   멤버 자격에는 **ssis_admin** 데이터베이스 역할  
  
-   멤버 자격에는 **sysadmin** 서버 역할  
  
> [!NOTE]  
>  서버에서 작업을 수행할 권한이 있으면 작업에 대한 정보를 볼 수 있는 권한도 있습니다. 행 수준 보안이 적용됩니다. 따라서 볼 수 있는 권한이 있는 행만 표시됩니다.  
  
  