---
title: 모델 열의 별칭 만들기 | Microsoft Docs
ms.date: 05/01/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: data-mining
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: e051c454223fc7fc710f45b97a1a76ecceb10f2b
ms.sourcegitcommit: 7fe14c61083684dc576d88377e32e2fc315b7107
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2018
ms.locfileid: "50147448"
---
# <a name="create-an-alias-for-a-model-column"></a>모델 열의 별칭 만들기
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]에서 모델 열의 별칭을 만들 수 있습니다. 이것은 마이닝 구조 이름이 너무 길어서 쉽게 사용할 수 없거나 모델에서 열의 내용과 사용을 잘 설명하도록 열 이름을 변경할 경우에 유용합니다. 예를 들어 구조 열의 복사본을 만든 다음 특정 모델과 다르게 열을 불연속화한 경우 내용을 보다 정확하게 나타내도록 열의 이름을 바꿀 수 있습니다.  
  
 모델 열의 별칭을 만들려면 **속성** 창을 사용하여 열의 [Name](https://docs.microsoft.com/bi-reference/assl/properties/name-element-assl) 속성을 설정합니다.  
  
 데이터 마이닝 디자이너의 **마이닝 모델** 탭에서 별칭은 열 사용 레이블 옆 괄호 안에 표시됩니다.  
  
 마이닝 모델의 속성을 설정하는 방법은 [마이닝 모델 열](../../analysis-services/data-mining/mining-model-columns.md)을 참조하세요.  
  
### <a name="to-add-an-alias-to-a-mining-model-column"></a>마이닝 모델 열에 별칭을 추가하려면  
  
1.  데이터 마이닝 디자이너의 **마이닝 모델** 탭에서 변경할 마이닝 열의 마이닝 모델에 있는 셀을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 선택합니다.  
  
2.  화면 오른쪽의 **속성** 창에서 이름 속성 옆의 셀을 클릭하고 현재 값을 삭제합니다. 열의 새 이름을 입력합니다.  
  
## <a name="see-also"></a>관련 항목  
 [마이닝 모델 태스크 및 방법](../../analysis-services/data-mining/mining-model-tasks-and-how-tos.md)   
 [마이닝 모델 속성](../../analysis-services/data-mining/mining-model-properties.md)  
  
  
