---
title: SMO 네임 스페이스 | Microsoft Docs
ms.custom: ''
ms.date: 08/02/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- object models [SMO]
- SMO [SQL Server], namespaces
- namespaces [SMO]
- SQL Server Management Objects, namespaces
ms.assetid: 7bfabe4d-9f4c-4bc9-b998-93bd2b50ee8a
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 717b2171b535405cc0bc075ceafd50107fb68bed
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47632651"
---
# <a name="smo-object-model-namespaces"></a>SMO 개체 모델 네임스페이스
[!INCLUDE[appliesto-ss-asdb-asdw-xxx-md](../../includes/appliesto-ss-asdb-asdw-xxx-md.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects(SMO)에는 다양한 네임스페이스가 있습니다. 각 네임스페이스는 SMO의 서로 다른 기능 영역을 나타냅니다.  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], SMO 어셈블리는 C:\Program Files\Microsoft SQL Server\130\SDK\Assemblies\ 폴더에 있습니다.  
  
## <a name="namespaces"></a>네임스페이스  
 SMO 네임스페이스는 다음과 같습니다.  
  
|클래스|기능|  
|-----------|--------------|  
|<xref:Microsoft.SqlServer.Management.Smo>|인스턴스 클래스, 유틸리티 클래스 및 프로그래밍 방식으로 조작 하는 데 사용 되는 열거형을 포함 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]합니다.|  
|<xref:Microsoft.SqlServer.Management.Common>|연결 클래스와 같이 RMO(복제 관리 개체)와 SMO에 공통되는 클래스를 포함합니다.|  
|<xref:Microsoft.SqlServer.Management.Smo.Agent>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트를 나타내는 클래스를 포함합니다.|  
|<xref:Microsoft.SqlServer.Management.Smo.Wmi>|WMI 공급자를 나타내는 클래스를 포함합니다.|  
|<xref:Microsoft.SqlServer.Management.Smo.RegisteredServers>|등록된 서버를 나타내는 클래스를 포함합니다.|  
|<xref:Microsoft.SqlServer.Management.Smo.Mail>|데이터베이스 메일을 나타내는 클래스를 포함합니다.|  
|<xref:Microsoft.SqlServer.Management.Smo.Broker>|[!INCLUDE[ssSB](../../includes/sssb-md.md)]를 나타내는 클래스를 포함합니다.|  
  
  
