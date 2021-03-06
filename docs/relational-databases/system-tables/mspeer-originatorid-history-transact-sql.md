---
title: MSpeer_originatorid_history (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSpeer_originatorid_history_TSQL
- MSpeer_originatorid_history
dev_langs:
- TSQL
helpviewer_keywords:
- MSpeer_originatorid_history
ms.assetid: c1f53d0f-4080-43ff-be38-2b10395c68c9
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 3dff36fb672d7d94d9716f0c8eaefbb6132f9536
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52810505"
---
# <a name="mspeeroriginatoridhistory-transact-sql"></a>MSpeer_originatorid_history(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  토폴로지에 정의된 각 송신자 ID에 대한 행을 하나씩 포함합니다. 여기에는 더 이상 활성화되지 않는 노드의 ID도 포함됩니다. 이 테이블은 지정된 송신자 ID가 아직 사용되지 않았는지 확인하기 위해 충돌 감지를 수행할 노드를 새로 구성할 때 사용됩니다. 이 테이블은 게시 데이터베이스에 저장됩니다. 충돌 검색에 대 한 자세한 내용은 참조 하세요. [피어 투 피어 복제에서 충돌 검색](../../relational-databases/replication/transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md)합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|originator_publication|**sysname**|송신자 ID가 지정된 게시입니다.|  
|originator_id|**int**|충돌 감지를 위해 토폴로지의 각 노드를 식별하는 번호입니다.|  
|originator_node|**sysname**|송신자 ID가 지정된 서버 인스턴스입니다.|  
|originator_db|**sysname**|송신자 ID가 지정된 게시 데이터베이스입니다.|  
|originator_db_version|**int**|원래 데이터베이스의 버전 번호를 식별합니다.|  
|originator_version|**int**|게시자의 버전 번호를 식별합니다.|  
|inserted_date|**datetime**|송신자 ID의 행이 이 테이블에 삽입된 날짜와 시간입니다.|  
  
## <a name="see-also"></a>관련 항목:  
 [복제 테이블 &#40;TRANSACT-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [복제 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
