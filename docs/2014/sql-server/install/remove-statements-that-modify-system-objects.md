---
title: 시스템 개체를 수정 하는 문을 제거 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- direct system catalog updates [SQL Server]
- system catalogs [SQL Server]
ms.assetid: 221b46c2-c27e-4df8-bd8c-8b990d6d5e98
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: ebc7288bd7c72ce76df69d11c7a9fb0771764fca
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48079953"
---
# <a name="remove-statements-that-modify-system-objects"></a>시스템 개체를 수정하는 문을 제거합니다.
  업그레이드 관리자가 시스템 카탈로그를 업데이트하는 문을 검색했습니다. 직접 시스템 카탈로그 업데이트가 허용되지 않습니다. SQL 스크립트에서 문서화된 공식 API를 사용하도록 수정합니다.  
  
## <a name="component"></a>구성 요소  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a>Description  
 직접 시스템 카탈로그 업데이트가 허용되지 않습니다. 직접 시스템 카탈로그 업데이트를 시도하면 다음 오류가 발생합니다.  
  
 `Server: Msg 259, Level 16, State 1, Line 1`  
  
 `Ad hoc updates to system catalogs are not allowed.`  
  
## <a name="corrective-action"></a>수정 동작  
 SQL 스크립트에서 문서화된 공식 API를 사용하도록 수정합니다. 예를 들어 *sysdatabases* 시스템 테이블에 대해 UPDATE 문을 실행하는 대신 ALTER DATABASE **database_name** SET EMERGENCY를 사용합니다.  
  
## <a name="see-also"></a>관련 항목  
 [데이터베이스 엔진 업그레이드 문제](../../../2014/sql-server/install/database-engine-upgrade-issues.md)   
 [SQL Server 2014 업그레이드 관리자 &#91;새로 만들기&#93;](/sql/2014/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
