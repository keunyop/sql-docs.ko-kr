---
title: sys.dm_exec_connections (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dm_exec_connections_TSQL
- sys.dm_exec_connections_TSQL
- sys.dm_exec_connections
- dm_exec_connections
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_exec_connections dynamic management view
ms.assetid: 6bd46fe1-417d-452d-a9e6-5375ee8690d8
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 305f544bf34b4f5e9ab4132dc2ffb45ff89cf0df
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47774231"
---
# <a name="sysdmexecconnections-transact-sql"></a>sys.dm_exec_connections(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]의 이 인스턴스에 대해 설정된 연결에 대한 정보와 각 연결에 대한 세부 정보를 반환합니다. SQL Server에 대 한 서버 단위 연결 정보를 반환합니다. SQL Database에 대 한 현재 데이터베이스 연결 정보를 반환합니다.  
  
> [!NOTE]
> 이를 호출 하 [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] 나 [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]를 사용 하 여 [sys.dm_pdw_exec_connections &#40;TRANSACT-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-connections-transact-sql.md).  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|session_id|**int**|이 연결과 연관된 세션을 식별합니다. Null을 허용합니다.|  
|most_recent_session_id|**int**|이 연결과 연관된 가장 최근 요청의 세션 ID를 나타냅니다. SOAP 연결은 다른 세션에서 다시 사용될 수 있습니다. Null을 허용합니다.|  
|connect_time|**datetime**|연결이 설정된 타임스탬프입니다. Null을 허용하지 않습니다.|  
|net_transport|**nvarchar(40)**|항상 반환 **세션** 경우 연결에 사용할 수 있는 여러 활성 결과 집합 (MARS).<br /><br /> **참고:** 이 연결에서 사용 되는 물리적 전송 프로토콜을 설명 합니다. Null을 허용하지 않습니다.|  
|protocol_type|**nvarchar(40)**|페이로드의 프로토콜 유형을 지정합니다. 현재 TDS(TSQL)와 SOAP을 구분합니다. Null을 허용합니다.|  
|protocol_version|**int**|이 연결과 연관된 데이터 액세스 프로토콜의 버전입니다. Null을 허용합니다.|  
|endpoint_id|**int**|연결 유형을 설명하는 식별자입니다. 이 endpoint_id를 사용하여 sys.endpoints 뷰를 쿼리할 수 있습니다. Null을 허용합니다.|  
|encrypt_option|**nvarchar(40)**|이 연결에 대해 암호화가 설정되었는지 여부를 설명하는 부울 값입니다. Null을 허용하지 않습니다.|  
|auth_scheme|**nvarchar(40)**|이 연결에 사용된 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]/Windows 인증 체계를 지정합니다. Null을 허용하지 않습니다.|  
|node_affinity|**smallint**|이 연결에서 선호도가 설정된 메모리 노드를 식별합니다. Null을 허용하지 않습니다.|  
|num_reads|**int**|이 연결을 통해 발생 한 바이트 읽기 수입니다. Null을 허용합니다.|  
|num_writes|**int**|이 연결을 통해 발생 한 쓰기 바이트 수입니다. Null을 허용합니다.|  
|last_read|**datetime**|이 연결 중에 마지막 읽기가 발생한 타임스탬프입니다. Null을 허용합니다.|  
|last_write|**datetime**|이 연결 중에 마지막 쓰기가 발생한 타임스탬프입니다. Null을 허용하지 않습니다.|  
|net_packet_size|**int**|정보 및 데이터 전송에 사용되는 네트워크 패킷 크기입니다. Null을 허용합니다.|  
|client_net_address|**varchar(48)**|이 서버에 연결되는 클라이언트의 호스트 주소입니다. Null을 허용합니다.<br /><br /> V12 이전 [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)],이 열은 항상 NULL을 반환 합니다.|  
|client_tcp_port|**int**|이 연결과 연관된 클라이언트 컴퓨터의 포트 번호입니다. Null을 허용합니다.<br /><br /> [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]에서 이 열은 항상 NULL을 반환합니다.|  
|local_net_address|**varchar(48)**|이 연결이 대상으로 하는 서버의 IP 주소를 나타냅니다. TCP 전송 공급자를 사용하여 연결한 경우에만 사용할 수 있습니다. Null을 허용합니다.<br /><br /> [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]에서 이 열은 항상 NULL을 반환합니다.|  
|local_tcp_port|**int**|TCP 전송을 사용하는 연결인 경우 이 연결이 대상으로 하는 서버 TCP 포트를 나타냅니다. Null을 허용합니다.<br /><br /> [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]에서 이 열은 항상 NULL을 반환합니다.|  
|connection_id|**uniqueidentifier**|각 연결을 고유하게 식별합니다. Null을 허용하지 않습니다.|  
|parent_connection_id|**uniqueidentifier**|MARS 세션이 사용하고 있는 주 연결을 식별합니다. Null을 허용합니다.|  
|most_recent_sql_handle|**varbinary(64)**|이 연결에서 실행된 마지막 요청의 SQL 핸들입니다. most_recent_sql_handle 열은 항상 most_recent_session_id 열과 동기화됩니다. Null을 허용합니다.|  
|pdw_node_id|**int**|**적용 대상**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)], [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> 이 배포에 있는 노드에 대 한 식별자입니다.|  
  
## <a name="permissions"></a>사용 권한

온 [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)], 필요한 `VIEW SERVER STATE` 권한.   
온 [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)], 필요를 `VIEW DATABASE STATE` 데이터베이스의 권한.   

## <a name="physical-joins"></a>물리적 조인  
 ![Sys.dm_exec_connections에 대 한 조인](../../relational-databases/system-dynamic-management-views/media/join-dm-exec-connections-1.gif "sys.dm_exec_connections에 대 한 조인")  
  
## <a name="relationship-cardinalities"></a>관계 카디널리티  
  
||||  
|-|-|-|  
|dm_exec_sessions.session_id|dm_exec_connections.session_id|일 대 일|  
|dm_exec_requests.connection_id|dm_exec_connections.connection_id|다 대 일|  
|dm_broker_connections.connection_id|dm_exec_connections.connection_id|일 대 일|  
  
## <a name="examples"></a>예  
 쿼리 자체 연결에 대한 정보를 수집하는 일반 쿼리입니다.  
  
```sql  
SELECT   
    c.session_id, c.net_transport, c.encrypt_option,   
    c.auth_scheme, s.host_name, s.program_name,   
    s.client_interface_name, s.login_name, s.nt_domain,   
    s.nt_user_name, s.original_login_name, c.connect_time,   
    s.login_time   
FROM sys.dm_exec_connections AS c  
JOIN sys.dm_exec_sessions AS s  
    ON c.session_id = s.session_id  
WHERE c.session_id = @@SPID;  
```  
  
## <a name="see-also"></a>관련 항목  

 [실행 관련 동적 관리 뷰 및 함수&#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/execution-related-dynamic-management-views-and-functions-transact-sql.md)  
  
  


