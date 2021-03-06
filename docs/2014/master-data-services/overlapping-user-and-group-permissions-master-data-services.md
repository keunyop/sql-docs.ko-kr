---
title: 겹치는 사용자 및 그룹 권한(Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- users [Master Data Services], resolving permissions
- permissions [Master Data Services], user and group overlaps
- groups [Master Data Services], resolving permissions
ms.assetid: 31c3cf7d-17d4-4474-b6a7-ffcb9fc45b37
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 3f68f367f782a28f062ea807fb0b7680df15c69d
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52799265"
---
# <a name="overlapping-user-and-group-permissions-master-data-services"></a>겹치는 사용자 및 그룹 권한(Master Data Services)
  사용자의 사용 권한은 다음 요소에 따라 결정됩니다.  
  
-   그룹 멤버 자격의 사용 권한  
  
-   사용자에게 명시적으로 할당된 사용 권한  
  
 사용자가 여러 그룹의 멤버이며 이러한 그룹에 마스터 데이터 관리자에 대한 액세스 권한이 있는 경우 다음 규칙이 적용됩니다.  
  
-   **거부** 는 다른 모든 사용 권한을 무시합니다.  
  
-   **업데이트** 재정의 **읽기 전용**합니다.  
  
 이러한 규칙은 **모델** 탭과 **계층 멤버** 탭 모두에 적용됩니다. 각 탭의 사용 권한이 확인된 후 결합됩니다. 자세한 내용은 [사용 권한이 결정되는 방식&#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md)을 참조하세요.  
  
> [!NOTE]  
>  겹치는 사용자 및 그룹 권한은 사용자 인터페이스에서 확인할 수 있습니다. **모델** 탭과 **계층 멤버** 탭 둘 다에 **유효** 를 선택하여 유효 사용 권한을 볼 수 있는 드롭다운 목록이 있습니다.  
  
## <a name="example-1"></a>예제 1  
 ![mds_conc_user_group_ex_1](../../2014/master-data-services/media/mds-conc-user-group-ex-1.gif "mds_conc_user_group_ex_1")  
  
 사용자가 그룹 1 및 그룹 2에 속합니다.  
  
 사용자에 게 **읽기 전용** Product 엔터티에 대 한 사용 권한.  
  
 그룹 1은 Product 엔터티에 대한 **업데이트** 권한을 가지고 있습니다.  
  
 그룹 2에 **읽기 전용** Product 엔터티에 대 한 사용 권한.  
  
 결과: 사용자의 유효 권한은 **업데이트** Product 엔터티에 합니다.  
  
## <a name="example-2"></a>예제 2  
 ![mds_conc_user_group_ex_2](../../2014/master-data-services/media/mds-conc-user-group-ex-2.gif "mds_conc_user_group_ex_2")  
  
 사용자가 그룹 1 및 그룹 2에 속합니다.  
  
 사용자에 게 **읽기 전용** Product 엔터티에 대 한 사용 권한.  
  
 그룹 1은 Product 엔터티에 대한 **업데이트** 권한을 가지고 있습니다.  
  
 그룹 2는 Product 엔터티에 대한 **거부** 권한을 가지고 있습니다.  
  
 결과: 사용자의 유효 권한은 **Deny** Product 엔터티에 합니다.  
  
## <a name="example-3"></a>예 3  
 ![mds_conc_user_group_ex_3](../../2014/master-data-services/media/mds-conc-user-group-ex-3.gif "mds_conc_user_group_ex_3")  
  
 사용자가 그룹 1 및 그룹 2에 속합니다.  
  
 사용자가 계층 노드의 멤버 그룹에 대한 **업데이트** 권한을 가지고 있습니다.  
  
 그룹 1에 **읽기 전용** 계층 노드의 멤버 그룹에 대 한 사용 권한.  
  
 그룹 2에 **읽기 전용** 계층 노드의 멤버 그룹에 대 한 사용 권한.  
  
 결과: 사용자의 유효 권한은 **업데이트** 멤버입니다.  
  
## <a name="see-also"></a>관련 항목:  
 [사용 권한이 결정되는 방식&#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md)   
 [겹치는 모델 및 멤버 권한&#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)  
  
  
