---
title: "파일 또는 Microsoft 데이터 액세스 서비스 어셈블리를 로드할 수 없습니다 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 81ed0f44-8782-462d-af8f-0ba5b975df27
caps.latest.revision: 7
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 653e99076ed3b4aec45b116e02c20cccdde53c21
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="could-not-load-file-or-assembly-microsoft-data-services"></a>파일 또는 Microsoft 데이터 액세스 서비스 어셈블리를 로드할 수 없습니다.
  SharePoint용 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 이 설치된 SharePoint 2010 환경에서는 데이터 피드 내보내기를 시도할 때 시스템에 필요한 Microsoft ADO.NET Data Services 버전이 없으면 이 오류가 발생합니다.  
  
## <a name="details"></a>세부 정보  
  
|||  
|-|-|  
|적용 대상|[!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] for SharePoint|  
|제품 버전|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|  
|원인|ADO.NET Data Services 3.5 SP1이 없습니다.|  
|메시지 텍스트|파일이나 어셈블리 'Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' 또는 여기에 종속되어 있는 파일이나 어셈블리 중 하나를 로드할 수 없습니다.. 시스템에서 지정한 파일을 찾을 수 없습니다.|  
  
## <a name="explanation"></a>설명  
 SharePoint 2010에는 SharePoint 목록을 XML 데이터 피드로 내보내는 데 사용할 수 있는 데이터 피드로 내보내기 단추가 포함되어 있습니다. 또한 SharePoint 모드의 Reporting Services와 SharePoint용 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 은 모두 ADO.NET Data Services가 필요한 데이터 피드 기능을 지원합니다.  
  
 ADO.NET Data Services가 설치되어 있지 않으면 데이터 피드를 요청할 때 이 오류가 발생합니다.  
  
## <a name="user-action"></a>사용자 동작  
  
1.  SharePoint 2010의 하드웨어 및 소프트웨어 요구 사항 설명서 [하드웨어 및 소프트웨어 요구 사항 확인(SharePoint 2010)](http://go.microsoft.com/fwlink/?LinkId=169734) (http://go.microsoft.com/fwlink/?LinkId=169734)으로 이동합니다.  
  
2.  **소프트웨어 필수 구성 요소 설치**에서 현재 사용 중인 운영 체제(Windows Server 2008 SP2 또는 Windows Server 2008 R2)에 맞는 ADO.NET Data Services 3.5의 링크를 찾습니다.  
  
3.  링크를 클릭하여 서비스를 설치하는 설치 프로그램을 실행합니다.  
  
## <a name="see-also"></a>관련 항목  
 [SharePoint에 PowerPivot 솔루션 배포](../../analysis-services/power-pivot-sharepoint/deploy-power-pivot-solutions-to-sharepoint.md)  
  
  