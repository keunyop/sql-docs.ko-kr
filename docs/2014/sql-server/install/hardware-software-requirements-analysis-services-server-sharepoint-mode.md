---
title: 하드웨어 및 소프트웨어 요구 사항 (SQL Server 2014) SharePoint 모드로 Analysis Services 서버에 대 한 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
ms.assetid: fb86ca0a-518c-4c61-ae78-7680c57fae1f
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 72888a9896502c09480ae682981e4031ea01751c
ms.sourcegitcommit: aa4f594ec6d3e85d0a1da6e69fa0c2070d42e1d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59241591"
---
# <a name="hardware-and-software-requirements-for-analysis-services-server-in-sharepoint-mode-sql-server-2014"></a>SharePoint 모드의 Analysis Services 서버 하드웨어 및 소프트웨어 요구 사항(SQL Server 2014)
  [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)] SharePoint 2010 및 SharePoint 2013을 모두 지원합니다. [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)] 2013은 SharePoint 서버에 설치할 수 있지만 SharePoint 팜 외부에서 실행 합니다. [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)] 2010은 SharePoint 2010 팜의 응용 프로그램 서버에서 실행 되 고 SharePoint 기능과 인프라를 사용 하 여 서버 작업을 지원 합니다. 두 SharePoint 버전에 해당하는 [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)]를 설치하려면 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 설치 마법사를 사용합니다. 설치 후 다음을 완료합니다.  
  
-   SharePoint 버전에 대한 [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)] 구성 도구의 해당 버전을 실행합니다.  
  
-   SharePoint 2013을 설치 합니다 [설치 하거나 SharePoint 추가 기능에 대 한 PowerPivot을 제거 &#40;SharePoint 2013&#41;](../../analysis-services/instances/install-windows/install-or-uninstall-the-power-pivot-for-sharepoint-add-in-sharepoint-2013.md)합니다.  

  
##  <a name="bkmk_sqleditions"></a> SQL Server 버전 요구 사항  
 비즈니스 인텔리전스 기능은 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]의 일부 버전에서만 사용할 수 있습니다. 세부 정보를 참조 하세요 [SQL Server 2014 버전에서 지 원하는 기능](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md) 하 고 [Edition 및 SQL Server 2014 구성 요소](../editions-and-components-of-sql-server-2016.md)합니다.  
  
 현재 릴리스 정보에서 찾을 수 있습니다 [Microsoft SQL Server 2014 릴리스 정보](https://go.microsoft.com/fwlink/?LinkID=296445)합니다.  
  

  
##  <a name="bkmk_sqllicense"></a> SQL Server 라이선스  
 SQL Server 사용권 계약에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [SQL Server 2014 라이선스 데이터 시트](https://download.microsoft.com/download/6/6/F/66FF3259-1466-4BBA-A505-2E3DA5B2B1FA/SQL_Server_2014_Licensing_Datasheet.pdf) (https://download.microsoft.com/download/6/6/F/66FF3259-1466-4BBA-A505-2E3DA5B2B1FA/SQL_Server_2014_Licensing_Datasheet.pdf)합니다.  
  
-   [구입 방법: SQL Server 라이선스 모델 지원](https://www.microsoft.com/licensing/product-licensing/sql-server-2014?activetab=sql-server-2014-pivot%3aprimaryr2) (https://www.microsoft.com/licensing/product-licensing/sql-server-2014?activetab=sql-server-2014-pivot%3aprimaryr2)합니다.  
  

  
##  <a name="bkmk_ssas__sharepoint_2013"></a> SharePoint 2013에 설치 된 analysis Services  
 서버에 SharePoint 모드의 Analysis Services 서버만 설치할 경우 최소 시스템 요구 사항은 SharePoint Server 요구 사항이 아닌 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]를 기준으로 합니다.  
  
 [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md)  
  
 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 차세대 비즈니스 서버에서 모범 SharePoint 실행에 대 한 높은 RAM 임계값과 더 많은 처리 기능을 제공 하는 합니다. 메모리에 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 데이터를 저장하는 데는 많은 양의 RAM이 사용됩니다. RAM은 구조 변경에 맞게 변경되는 기능을 지원합니다. 추가 프로세서는 집계되지 않은 원시 데이터에 대한 장기 실행 검색을 지원합니다. 데이터 구조는 동적 환경에서 Excel 클라이언트 또는 프런트 엔드 인터페이스를 통해 시작된 사용자 기반 데이터 분석에 응답하는 것으로 가정됩니다.  
  
> [!TIP]  
>  [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] SharePoint에 대 한 L2 및 L3 캐시를 활용합니다. 성능을 향상시키려면 더 큰 L2 및 L3 캐시가 있는 프로세서를 사용해 보십시오.  
  
 다음 표에서는 SharePoint 팜의 일부가 아닌 독립 실행형 [!INCLUDE[ssGeminiShortvnext](../../includes/ssgeminishortvnext-md.md)] 서버의 최소 및 권장 하드웨어 구성에 대해 설명합니다.  
  
|구성 요소|최소|권장|  
|---------------|-------------|-----------------|  
|프로세서|64비트 듀얼 코어 프로세서, 3GHz|코어 16개|  
|RAM|8GB의 RAM|64GB의 RAM|  
|스토리지|80GB 저장소|80GB 이상|  
  
 SharePoint 팜 서버에 SharePoint 모드의 Analysis Services 서버를 설치할 경우 다음 링크에서 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]와 SharePoint Server에 대한 최소 시스템 요구 사항을 검토하십시오.  
  
-   [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md)  
  
-   [SharePoint 2013 하드웨어 및 소프트웨어 요구 사항](https://technet.microsoft.com/library/cc262485\(office.15\).aspx)합니다.  
  
 표준 SharePoint 2013 하드웨어 및 소프트웨어 권장 사항은 작업 그룹 또는 팀에 대한 웹 기반 문서 관리 솔루션에 대한 것입니다. [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 처리는 데이터를 많이 사용하기 때문에 전체 작업량이 적을 경우에만(예: 100명 미만의 사용자나 100개 미만의 통합 문서) 표준 권장 사항이 충분합니다. 대규모 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 배포에는 추가 컴퓨팅 기능이 필요합니다.  
  

  
##  <a name="bkmk_ssas__sharepoint_2010"></a> SharePoint 2010 서버에 설치 된 analysis Services  
 [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)] 2010은 SharePoint 2010 팜의 응용 프로그램 서버에서 실행 되 고 SharePoint 기능과 인프라를 사용 하 여 서버 작업을 지원 합니다. 다음 표에서는 SharePoint 2010 배포와 관련된 요구 사항을 요약해서 보여 줍니다.  
  
|구성 요소|요구 사항|  
|---------------|-----------------|  
|SharePoint 버전|Excel Services, 보안 저장소 서비스 및 Windows 토큰 서비스에 대한 클레임을 포함하고 동일한 서버 팜에서 구성된 SharePoint 2010<br /><br /> SharePoint는 SharePoint 설치의 서버 팜 옵션을 사용하여 설치해야 합니다(SharePoint의 독립 실행형 설치 옵션은 지원 안 됨). [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 데이터 액세스 및 관리를 지원 하기 위해 서버 팜 인프라가 필요 합니다. 독립 실행형 설치에서는 이러한 서비스를 제공하지 않습니다.<br /><br /> Windows 7 또는 Windows Vista에서 실행되는 Developer 버전에서는 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 서버를 설치할 수 없습니다.|  
|서비스 팩|SharePoint Server 2010 SP1(서비스 팩 1)은 필수입니다.<br /><br /> [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)][!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)] 기능을 사용하려면 SharePoint 2010 서비스 팩 1을 설치해야 합니다.<br /><br /> 이전 버전의 [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)]에서 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]로 업그레이드할 때는 SharePoint 2010 2010년 8월 누적 업데이트 이상이 필요합니다. SharePoint 서비스 팩 1을 설치한 후 2010년 8월 누적 업데이트 이상을 설치해야 합니다. 새로 설치 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)] 누적 업데이트가 필요 하지 않습니다. 자세한 내용은 [2010 SharePoint에 대 한 누적 업데이트가 출시 된 년 8 월](http://blogs.technet.com/b/stefan_gossner/archive/2010/09/02/august-2010-cumulative-update-for-sharepoint-has-been-released.aspx)합니다.|  
|SharePoint 웹 응용 프로그램|[!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] SharePoint 2010에 클래식 모드 인증에 대해 구성 된 SharePoint 웹 응용 프로그램을 지원 합니다. SharePoint용 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)]을 기존 팜에 추가할 경우 함께 사용하려는 웹 응용 프로그램이 클래식 모드 인증에 대해 구성되어 있어야 합니다. 인증 모드를 확인, 섹션을 참조 하는 방법에 대 한 지침은 "확인 웹 응용 프로그램에서는 클래식 모드 인증" [SharePoint에 PowerPivot 솔루션 배포](../../analysis-services/power-pivot-sharepoint/deploy-power-pivot-solutions-to-sharepoint.md)합니다.|  
|[!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 서버 쪽 데이터 새로 고침에 필요한 데이터 공급자|서버 쪽 데이터 새로 고침은 원래 데이터를 가져오기 위해 사용된 것과 동일한 데이터 검색 단계를 반복해서 수행합니다. 즉, 클라이언트 워크스테이션에서 데이터를 가져오기 위해 사용된 데이터 공급자는 SharePoint용 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 서버에도 제공되어야 합니다.<br /><br /> 또한 SharePoint 서버에서 데이터 피드를 사용하려면 ADO.NET Data Services가 필요합니다. SharePoint 필수 구성 요소 설치 관리자 프로그램은 이 소프트웨어를 설치하지 않습니다. 다음 소프트웨어는 수동으로 설치해야 합니다.<br /><br /> SharePoint 목록을 데이터 피드로 내보내는 데 사용되는 ADO.NET Data Services 3.5 SP1 런타임 어셈블리. 운영 체제와 일치하는 버전을 다운로드하여 설치합니다.<br /><br /> Windows Server 2008 r2를 사용 하 여 [.NET Framework 3.5 SP1에 대 한 Windows 7 및 windows Server 2008 R2 용 ADO.NET Data Services 업데이트 (https://go.microsoft.com/fwlink/?LinkId=182557)](https://go.microsoft.com/fwlink/?LinkId=182557)합니다. Windows Server 2008 R2 **SP1** 이미 업데이트 된 공급자를 포함 합니다.<br /><br /> Windows Server 2008을 사용 하 여 [.NET Framework 3.5 SP1에 대 한 Windows 2000, Windows Server 2003, Windows XP, Windows Vista 및 Windows Server 2008 용 ADO.NET Data Services 업데이트 (https://go.microsoft.com/fwlink/?LinkId=158125)](https://go.microsoft.com/fwlink/?LinkId=158125)합니다.|  
  
 [하드웨어 및 소프트웨어 확인 요구 사항 (SharePoint 2010) (https://go.microsoft.com/fwlink/?LinkId=169734)](https://go.microsoft.com/fwlink/?LinkId=169734)  
  
 
  
## <a name="additional-information"></a>추가 정보  
 SharePoint 변경에 대 한 정보를 참조 하세요 [SharePoint 2010에서 SharePoint 2013으로 변경](https://technet.microsoft.com/library/ff607742\(office.15\).aspx) (https://technet.microsoft.com/library/ff607742(office.15).aspx)합니다.  
  

  
  
