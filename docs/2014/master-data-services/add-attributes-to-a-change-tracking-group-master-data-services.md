---
title: 변경 내용 추적 그룹에 특성 추가(Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- change tracking groups [Master Data Services]
- attributes [Master Data Services], change tracking groups
- change tracking groups [Master Data Services], adding attributes
ms.assetid: e153eb5f-70ca-4c6f-89d8-1f937ed3917d
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 6d215fe6a1b0c41868816e09e64927b8f736f8c9
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52772551"
---
# <a name="add-attributes-to-a-change-tracking-group-master-data-services"></a>변경 내용 추적 그룹에 특성 추가(Master Data Services)
  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]에서 특성 값의 변경 내용을 추적하려는 경우 변경 내용 추적 그룹에 특성을 추가합니다.  
  
> [!NOTE]  
>  변경 내용 추적 그룹에 특성을 추가한 후에는 특성이 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 데이터베이스에서 변경될 때 특성에 플래그가 지정됩니다. 변경 내용에 따라 동작을 수행할 비즈니스 규칙을 만듭니다.  
  
## <a name="prerequisites"></a>사전 요구 사항  
 이 절차를 수행하려면  
  
-   **시스템 관리** 기능 영역에 액세스할 수 있는 권한이 있어야 합니다.  
  
-   모델 관리자여야 합니다. 자세한 내용은 [관리자&#40;Master Data Services&#41;](administrators-master-data-services.md)를 참조하세요.  
  
-   변경 내용 추적 그룹에 추가할 특성이 있어야 합니다. 자세한 내용은 [텍스트 특성 만들기&#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md)를 참조하세요.  
  
### <a name="to-add-attributes-to-a-change-tracking-group"></a>변경 내용 추적 그룹에 특성을 추가하려면  
  
1.  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]에서 **시스템 관리**를 클릭합니다.  
  
2.  **모델 탐색기** 페이지의 메뉴 모음에서 **관리** 를 가리키고 **엔터티**를 클릭합니다.  
  
3.  **엔터티 유지 관리** 페이지의 **모델** 목록에서 모델을 선택합니다.  
  
4.  특성 값을 추적하려는 엔터티의 행을 선택합니다.  
  
5.  **선택한 엔터티 편집**을 클릭합니다.  
  
6.  **엔터티 편집** 페이지에서  
  
    -   리프 멤버에 대 한 일 경우 합니다 **리프 특성** 창에 특성을 선택 하 고 클릭 **리프 특성 편집**합니다.  
  
    -   특성에 대 한 경우 통합된 멤버에는 **통합 특성** 창에 특성을 선택 하 고 클릭 **통합 특성 편집**합니다.  
  
    -   특성의 경우 컬렉션의 경우에 **컬렉션 특성** 창에 특성을 선택 하 고 클릭 **컬렉션 특성 편집**합니다.  
  
7.  **변경 내용 추적 설정** 확인란을 선택합니다.  
  
8.  **변경 내용 추적 그룹** 상자에 그룹의 번호를 입력합니다.  
  
9. **특성 저장**을 클릭합니다.  
  
10. **엔터티 유지 관리** 페이지에서 **엔터티 저장**을 클릭합니다.  
  
11. 그룹에 포함할 모든 특성에 대해 이 절차를 반복합니다. 그룹의 각 특성에 대해 동일한 변경 내용 추적 그룹 번호를 사용합니다.  
  
## <a name="next-steps"></a>다음 단계  
  
-   [특성 값 변경 기반 동작 시작&#40;Master Data Services&#41;](../../2014/master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)  
  
## <a name="see-also"></a>관련 항목:  
 [텍스트 특성 만들기&#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md)   
 [도메인 기반 특성 만들기&#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
  
