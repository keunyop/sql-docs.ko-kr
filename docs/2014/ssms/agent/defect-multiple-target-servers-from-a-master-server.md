---
title: 마스터 서버에서 여러 대상 서버 제거 | Microsoft 문서
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], defecting
- SQL Server Agent jobs, master servers
- master servers [SQL Server], defecting target servers
- defecting target servers
- multiple target server defections
ms.assetid: 61a3713b-403a-4806-bfc4-66db72ca1156
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 0123027ac9aa87d616b52ac5cc26f36a20f7e1e3
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52757482"
---
# <a name="defect-multiple-target-servers-from-a-master-server"></a>Defect Multiple Target Servers from a Master Server
  이 항목에서는 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 에서 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]를 사용하여 다중 서버 관리 구성에서 여러 대상 서버를 제거하는 방법에 대해 설명합니다. 이 절차는 마스터 서버에서 실행하십시오.  
  
##  <a name="SSMSProcedure"></a> SQL Server Management Studio 사용  
  
#### <a name="to-defect-multiple-target-servers-from-a-master-server"></a>마스터 서버에서 다중 대상 서버를 제거하려면  
  
1.  **개체 탐색기**에서 마스터 서버로 구성된 서버를 확장합니다.  
  
2.  **SQL Server 에이전트**를 마우스 오른쪽 단추로 클릭하고 **다중 서버 관리**를 가리킨 다음 **대상 서버 관리**를 클릭합니다.  
  
3.  **명령 게시**를 클릭하고 **명령 유형** 목록에서 **제거**를 선택합니다.  
  
4.  **받는 사람**에서 다음 중 하나를 수행합니다.  
  
    -   이 마스터 서버의 모든 대상 서버를 제거하려면 **모든 대상 서버** 를 클릭합니다. 현재 다중 서버 관리 구성을 완전히 제거하려면 이 옵션을 사용합니다.  
  
    -   이 마스터 서버의 모든 대상 서버가 아닌 일부 대상 서버를 제거하려면 **대상 서버 지정**을 클릭한 다음 해당 **선택** 상자를 클릭합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [다중 서버 환경 만들기](create-a-multiserver-environment.md)   
 [기업 내 관리 자동화](automated-administration-across-an-enterprise.md)   
 [Defect a Target Server from a Master Server](defect-a-target-server-from-a-master-server.md)  
  
  
