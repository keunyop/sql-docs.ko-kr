---
title: 알림(Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- notifications [Master Data Services]
- notifications [Master Data Services], about notifications
- e-mail [Master Data Services]
- e-mail [Master Data Services], about e-mail notifications
ms.assetid: d7ad32d5-9fe5-48fd-8c61-0b00c0aff082
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: b255b5e0d82b70237bd9933f49c6b3b247560be2
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52819225"
---
# <a name="notifications-master-data-services"></a>알림(Master Data Services)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 에서 전자 메일 알림을 보내도록 구성할 수 있습니다.  
  
## <a name="how-notifications-are-sent"></a>알림 전송 방법  
 [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)]에서 알림을 구성합니다. 알림은 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 데이터베이스를 호스트하는 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../includes/ssde-md.md)] 인스턴스에서 데이터베이스 메일을 사용하여 메일 메시지를 보냅니다. 데이터베이스 메일에 대한 자세한 내용은 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 온라인 설명서에서 [데이터베이스 메일 구성 개체](../relational-databases/database-mail/database-mail-configuration-objects.md)를 참조하세요.  
  
## <a name="when-notifications-are-sent"></a>알림을 보내는 경우  
 알림이 구성된 후 다음 인스턴스에 자동화된 전자 메일 알림을 보낼 수 있습니다.  
  
|인스턴스|설명|  
|--------------|-----------------|  
|데이터가 비즈니스 규칙 유효성 검사를 통과하지 못할 경우|특성 값이 비즈니스 규칙 유효성 검사를 통과하지 못하는 경우 전자 메일을 보내도록 개별 비즈니스 규칙을 구성해야 합니다. 이 알림에는 다음과 같은 정보가 포함되어 있습니다.<br /><br /> Model<br /><br /> 버전 옵션<br /><br /> 엔터티<br /><br /> 멤버 코드<br /><br /> 비즈니스 규칙 실패<br /><br /> 비즈니스 규칙이 실패하는 특성 값의 멤버에 연결<br /><br /> 알림 발급 시간<br /><br /> 자세한 내용은 [알림을 보내도록 비즈니스 규칙 구성&#40;Master Data Services&#41;](../master-data-services/configure-business-rules-to-send-notifications-master-data-services.md)에서 알림을 구성합니다.|  
|모델 버전 상태가 변경될 경우|모델 버전의 상태가 변경될 때마다 모델 관리자인 사용자가 알림을 자동으로 받습니다. 이 알림에는 다음과 같은 정보가 포함되어 있습니다.<br /><br /> Model<br /><br /> 버전 옵션<br /><br /> 버전의 이전 및 새 상태<br /><br /> 알림 발급 시간<br /><br /> 자세한 내용은 [관리자&#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md)에 액세스하지 않고 그룹에서 사용자를 추가하고 제거할 수 있습니다.|  
|변경 집합 상태 변경|승인이 필요한 엔터티에 대해 변경 집합 상태가 변경될 때마다 엔터티 관리자 및/또는 변경 집합 소유자는 자동으로 알림을 받습니다. 이 알림에는 다음과 같은 정보가 포함되어 있습니다.<br /><br /> Model<br /><br /> 버전 옵션<br /><br /> 변경 집합 이름<br /><br /> 이전 상태<br /><br /> 새 상태<br /><br /> 보류 중인 변경 내용을 보고 수정하기 위해 변경 집합을 적용하려면 연결합니다.<br /><br /> 자세한 내용은 [변경 집합&#40;Master Data Services&#41;](../master-data-services/changesets-master-data-services.md)을 참조하세요.|  
  
## <a name="system-settings"></a>시스템 설정  
 [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] 에는 알림에 영향을 주는 설정이 있습니다. 이러한 설정은 [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] 에서 조정하거나 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 데이터베이스의 시스템 설정 테이블에서 직접 조정할 수 있습니다. 자세한 내용은 [시스템 설정&#40;Master Data Services&#41;](../master-data-services/system-settings-master-data-services.md)을 참조하세요.  
  
## <a name="related-tasks"></a>관련 작업  
  
|태스크 설명|항목|  
|----------------------|-----------|  
|[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 에서 전자 메일을 알림을 보내도록 구성합니다.|[메일 알림 구성&#40;Master Data Services&#41;](../master-data-services/configure-email-notifications-master-data-services.md)|  
|특성 값 변경 시 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 에서 알림을 보내도록 구성합니다.|[알림을 보내도록 비즈니스 규칙 구성&#40;Master Data Services&#41;](../master-data-services/configure-business-rules-to-send-notifications-master-data-services.md)|  
  
## <a name="related-content"></a>관련 내용  
  
-   [비즈니스 규칙&#40;Master Data Services&#41;](../master-data-services/business-rules-master-data-services.md)  
  
-   [버전&#40;Master Data Services&#41;](../master-data-services/versions-master-data-services.md)  
  
-   [전자 메일 알림 문제 해결(Master Data Services)](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx)  
  
  
