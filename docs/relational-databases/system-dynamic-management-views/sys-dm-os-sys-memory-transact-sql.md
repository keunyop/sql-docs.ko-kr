---
title: sys.dm_os_sys_memory (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dm_os_sys_memory
- sys.dm_os_sys_memory_TSQL
- sys.dm_os_sys_memory
- dm_os_sys_memory_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_os_sys_memory dynamic management view
ms.assetid: 1ca58814-1caa-44c1-b307-ff0bdcbbef62
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>=aps-pdw-2016||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 4cea000b63948207626298c1f0c977ba22ec3865
ms.sourcegitcommit: 9c6a37175296144464ffea815f371c024fce7032
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51677312"
---
# <a name="sysdmossysmemory-transact-sql"></a>sys.dm_os_sys_memory(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-pdw-md.md)]

  운영 체제의 메모리 정보를 반환합니다.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에 의해 제한 됩니다 하 고 운영 체제 수준 및 기본 하드웨어의 물리적 제한에서 외부 메모리 상태에 응답 합니다. 전체 시스템 상태 파악은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 메모리 사용량 평가에서 중요한 부분입니다.  
  
> [!NOTE]  
>  이를 호출 하 [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] 나 [!INCLUDE[ssPDW](../../includes/sspdw-md.md)], 이름을 사용 하 여 **sys.dm_pdw_nodes_os_sys_memory**합니다.  
  
|열 이름|데이터 형식|설명|  
|-----------------|---------------|-----------------|  
|**total_physical_memory_kb**|**bigint**|운영 체제에서 사용할 수 있는 실제 메모리의 총 크기(KB)입니다.|  
|**available_physical_memory_kb**|**bigint**|사용할 수 있는 실제 메모리의 크기(KB)입니다.|  
|**total_page_file_kb**|**bigint**|운영 체제에서 보고한 커밋 제한 크기(KB)입니다.|  
|**available_page_file_kb**|**bigint**|사용 중이 아닌 페이지 파일의 총 공간(KB)입니다.|  
|**system_cache_kb**|**bigint**|시스템 캐시 메모리의 총 공간(KB)입니다.|  
|**kernel_paged_pool_kb**|**bigint**|페이징된 커널 풀의 총 공간(KB)입니다.|  
|**kernel_nonpaged_pool_kb**|**bigint**|페이징되지 않은 커널 풀의 총 공간(KB)입니다.|  
|**system_high_memory_signal_state**|**bit**|시스템 고용량 메모리 리소스 상태 알림입니다. 값이 1이면 Windows에서 고용량 메모리 신호가 설정된 것입니다. 자세한 내용은 [CreateMemoryResourceNotification](https://go.microsoft.com/fwlink/?LinkId=82427) MSDN 라이브러리에서.|  
|**system_low_memory_signal_state**|**bit**|시스템 저용량 메모리 리소스 상태 알림입니다. 값이 1이면 Windows에서 저용량 메모리 신호가 설정된 것입니다. 자세한 내용은 [CreateMemoryResourceNotification](https://go.microsoft.com/fwlink/?LinkId=82427) MSDN 라이브러리에서.|  
|**system_memory_state_desc**|**nvarchar(256)**|메모리 상태에 대한 설명입니다. 아래 표를 참조하세요.|  
|**pdw_node_id**|**int**|**적용 대상**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)], [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> 이 배포에 있는 노드에 대 한 식별자입니다.|  
  
|조건|값|  
|---------------|-----------|  
|system_high_memory_signal_state = 1<br /><br /> 및<br /><br /> system_low_memory_signal_state = 0|사용 가능한 실제 메모리가 높은 수준입니다.|  
|system_high_memory_signal_state = 0<br /><br /> 및<br /><br /> system_low_memory_signal_state = 1|사용 가능한 실제 메모리가 낮은 수준입니다.|  
|system_high_memory_signal_state = 0<br /><br /> 및<br /><br /> system_low_memory_signal_state = 0|실제 메모리 사용률이 안정적입니다.|  
|system_high_memory_signal_state = 1<br /><br /> 및<br /><br /> system_low_memory_signal_state = 1|실제 메모리 상태가 전환되는 중입니다.<br /><br /> 높음 신호와 낮음 신호는 동시에 설정될 수 없습니다. 하지만 운영 체제 수준에서 상태가 빠르게 변경되면 사용자 모드 응용 프로그램에 두 값이 동시에 나타날 수 있습니다. 두 신호가 동시에 설정된 것으로 나타나면 전환 상태로 해석됩니다.|  
  
## <a name="permissions"></a>사용 권한  
 을 실행하려면 서버에 대해 VIEW SERVER STATE 권한이 필요합니다.  
  
## <a name="see-also"></a>관련 항목  
 [동적 관리 뷰 및 함수&#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [SQL Server 운영 체제 관련 동적 관리 뷰 &#40;TRANSACT-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-server-operating-system-related-dynamic-management-views-transact-sql.md)  
  
  


