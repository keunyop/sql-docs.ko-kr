---
title: 차원 쓰기 저장을 사용 하도록 설정 | Microsoft Docs
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 561dc878302afe7636a2660a9e194ac14a35c7f1
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "34020320"
---
# <a name="bi-wizard---enable-dimension-writeback"></a>BI 마법사-Enable 차원 쓰기 저장
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  큐브나 차원에 차원 쓰기 저장 기능을 추가하면 수동으로 차원 구조와 멤버를 수정할 수 있습니다. 쓰기 가능 차원에 대한 업데이트는 차원 테이블에 직접 기록됩니다. 이 기능은 차원의 **WriteEnabled** 속성 설정을 변경합니다.  
  
 차원에 쓰기 저장 기능을 추가하려면 비즈니스 인텔리전스 마법사의 **기능 선택** 페이지에서 **차원 쓰기 저장(writeback) 설정** 옵션을 선택합니다. 그런 다음 마법사의 안내를 따라 차원 쓰기 저장을 적용할 차원을 선택하고 선택한 차원에 대해 이 옵션을 설정합니다.  
  
> [!NOTE]  
>  쓰기 저장은 SQL Server 관계형 데이터베이스 및 데이터 마트에 대해서만 지원됩니다.  
  
## <a name="selecting-a-dimension"></a>차원 선택  
 마법사의 첫 번째 **차원 쓰기 저장(writeback) 설정** 페이지에서 차원 쓰기 저장을 적용할 차원을 지정합니다. 선택한 차원에 차원 쓰기 저장 기능을 추가하면 차원이 변경됩니다. 이러한 변경 내용은 선택된 차원을 포함하는 모든 큐브에 상속됩니다.  
  
## <a name="setting-dimension-writeback-capability"></a>차원 쓰기 저장(Writeback) 기능 설정  
 마법사의 두 번째 **차원 쓰기 저장(writeback) 설정** 페이지에서 실제로 **차원에 쓰기 저장(writeback) 설정** 옵션을 설정합니다. 이 옵션을 선택하면 자동으로 차원의 **WriteEnabled** 속성이 **True**로 설정됩니다. 이 옵션의 선택을 취소하면 자동으로 속성이 **False**로 설정됩니다.  
  
## <a name="remarks"></a>주의  
 새 멤버를 만들 때 차원에 모든 특성을 포함해야 합니다. 차원의 키 특성 값을 지정하지 않고 멤버를 삽입할 수 없습니다. 따라서 멤버를 만들 때는 차원 테이블에 정의된 모든 제약 조건(예: Null이 아닌 키 값)이 적용됩니다. **CustomRollupColumn**, **CustomRollupPropertiesColumn** 또는 **UnaryOperatorColumn** 과 같은 차원 속성에 의해 선택적으로 지정된 열도 고려해야 합니다.  
  
> [!WARNING]  
>  SQL Azure를 데이터 원본으로 사용하여 Analysis Services에 쓰기 저장(writeback)을 수행할 경우 작업이 실패합니다. MARS(Multiple Active Result Set)를 활성화하는 공급자 옵션이 기본적으로 설정되어 있지 않기 때문에 이 작업이 실패하는 것입니다.  
>   
>  이 문제를 해결하려면 연결 문자열에 MARS를 지원하고 쓰기 저장(writeback)을 활성화하는 다음 설정을 추가합니다.  
>   
>  `"MultipleActiveResultSets=True"`  
>   
>  자세한 내용은 [MARS&#40;Multiple Active Result Sets&#41; 사용](../../relational-databases/native-client/features/using-multiple-active-result-sets-mars.md)을 참조하세요.  
  
## <a name="see-also"></a>관련 항목:  
 [쓰기 가능 차원](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md)  
  
  
