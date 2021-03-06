---
title: 보고서 관리자 URL (SSRS 기본 모드) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
f1_keywords:
- sql12.rsconfigtool.reportmanagervirtualdirectory.f1
ms.assetid: 45768952-23a6-45a5-b541-e7bf192b4a78
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: f5e472f0cb8cb1a2fc8ed9d85b73622617a3a70a
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48210523"
---
# <a name="report-manager-url-ssrs-native-mode"></a>보고서 관리자 URL(SSRS 기본 모드)
  보고서 관리자 URL 페이지를 사용하여 보고서 관리자에 액세스하는 데 사용되는 URL을 구성하거나 수정할 수 있습니다. 기본적으로 보고서 관리자 URL은 보고서 서버 웹 서비스 URL의 접두사, IP 주소 및 포트를 상속합니다. 보고서 관리자가 동일한 보고서 서버 서비스 내에서 실행되는 웹 서비스에 대한 프런트 엔드 액세스를 제공하기 때문입니다. 서비스 애플리케이션을 격리하고 보고서 관리자를 사용하여 다른 컴퓨터의 보고서 서버 웹 서비스에 액세스하는 경우 보고서 관리자가 다른 인스턴스를 가리키도록 RSReportServer.config 파일을 편집해야 합니다. 원격 보고서 서버에 연결 하는 보고서 관리자를 구성 하는 방법에 대 한 자세한 내용은 참조 하세요. [Reporting Services 구성 관리자 &#40;기본 모드&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md)합니다.  
  
 [!INCLUDE[applies](../../includes/applies-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 기본 모드입니다.  
  
 SharePoint 통합 모드로 실행되도록 보고서 서버를 구성하는 경우에는 보고서 관리자 URL을 만들지 마십시오. SharePoint 통합 모드에서 실행되는 보고서 서버에서는 보고서 관리자가 지원되지 않습니다. 보고서 관리자에 대한 URL이 이미 있는 경우 SharePoint 통합 모드에서 실행되도록 보고서 서버를 구성한 후에는 이 URL을 사용할 수 없습니다.  
  
 이 페이지를 열려면 시작 합니다 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager 및 클릭 **보고서 관리자 URL** 탐색 창에서. 구성 관리자를 시작 하는 방법에 대 한 자세한 내용은 참조 하세요. [Reporting Services 구성 관리자 &#40;기본 모드&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md)합니다.  
  
> [!NOTE]  
>  보고서 관리자가 활성화되어 있지 않으면 이 페이지에서 옵션을 설정할 수 없습니다. 보고서 관리자를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 참조 하십시오 [Reporting Services 구성 관리자 &#40;기본 모드&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md)합니다.  
  
## <a name="options"></a>변수  
 **가상 디렉터리**  
 보고서 관리자의 가상 디렉터리 이름을 지정합니다. 같은 컴퓨터의 각 보고서 관리자 인스턴스에 대해 가상 디렉터리 이름은 하나만 지정할 수 있습니다.  
  
 **Url**  
 현재 보고서 관리자 인스턴스에 정의된 URL을 표시합니다.  
  
 **고급**  
 현재 보고서 관리자 인스턴스에 대해 다른 URL을 추가합니다.  
  
## <a name="see-also"></a>관련 항목  
 [URL 구성&#40;SSRS 구성 관리자&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md)   
 [구성 파일의 Url &#40;SSRS 구성 관리자&#41;](../../reporting-services/install-windows/urls-in-configuration-files-ssrs-configuration-manager.md)   
 [보고서 서버 URL 구성&#40;SSRS 구성 관리자&#41;](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
  
  
