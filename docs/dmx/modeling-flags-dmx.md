---
title: "모델링 플래그 (DMX) | Microsoft Docs"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- DMX
helpviewer_keywords:
- REGRESSOR flag
- DMX [Analysis Services], modeling flags
- MODEL_EXISTENCE_ONLY flag
- modeling flags [DMX]
- Data Mining Extensions [Analysis Services], modeling flags
- flags [DMX]
- NOT NULL flag
ms.assetid: 498d25f7-9597-47ae-8717-61ddd1d2fd15
caps.latest.revision: 35
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: ce032085f10db22608aee69b886724309e83506b
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="modeling-flags-dmx"></a>모델링 플래그(DMX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]에서는 모델링 플래그를 사용하여 사례 테이블에 정의되어 있는 데이터에 대한 추가 정보를 데이터 마이닝 알고리즘에 제공할 수 있습니다. 데이터 마이닝 알고리즘은 이 정보를 토대로 더욱 정확한 데이터 마이닝 모델을 만들 수 있습니다. 마이닝 구조 열과 마이닝 모델 열에서 모델링 플래그를 정의할 수 있습니다.  
  
 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]에서는 다음과 같은 모델링 플래그를 지원합니다.  
  
 **NOT NULL**  
 특성 열 값에는 Null 값을 포함할 수 없습니다. [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] 의 모델 학습 프로세스 중 이 특성 열에 Null 값이 있는 경우에는 오류가 발생합니다. 이 플래그는 마이닝 구조 열에 정의됩니다.  
  
 **회귀 변수**  
 회귀 알고리즘의 회귀 수식에 지정된 열을 사용할 수 있음을 나타냅니다. 이 플래그는 [!INCLUDE[msCoName](../includes/msconame-md.md)] 선형 회귀 알고리즘 및 [!INCLUDE[msCoName](../includes/msconame-md.md)] 의사 결정 트리 알고리즘에서 사용할 수 있으며 마이닝 모델 열에 정의됩니다.  
  
 **MODEL_EXISTENCE_ONLY**  
 특성 열의 값은 특성 자체보다는 중요도가 낮습니다. 이 플래그는 마이닝 모델 열에 정의됩니다.  
  
 타사 알고리즘에서 추가 모델링 플래그를 지원할 수도 있습니다. 지 원하는 모델링 플래그를 확인 하는 알고리즘을 사용 하 여는 **SUPPORTED_MODELING_FLAGS** 스키마 행 집합입니다. 서버의 마이닝 서비스를 쿼리하여 특정 알고리즘에 지원되는 모델링 플래그를 확인할 수도 있습니다. 예를 들어 다음 쿼리는 현재 서버에서 Microsoft 선형 회귀 알고리즘에 대해 지원되는 모델링 플래그를 반환합니다.  
  
```  
SELECT SUPPORTED_MODELING_FLAGS  
FROM $SYSTEM.DMSCHEMA_MINING_SERVICES  
WHERE SERVICE_NAME = 'Microsoft_Linear_Regression'  
```  
  
 예상 결과:  
  
 NOT NULL,REGRESSOR  
  
## <a name="specifying-modeling-flags-on-a-mining-model"></a>마이닝 모델에 모델링 플래그 지정  
 구문에 대 한 예제는 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] 마이닝 구조 열에 플래그를 지정 하는 데 지원 참조 [마이닝 구조 만들기 &#40; DMX &#41;](../dmx/create-mining-structure-dmx.md)합니다.  
  
 예를 보려면 마이닝 모델 열에 모델링 플래그를 지정 하는 구문은 참조 [ALTER MINING STRUCTURE &#40; DMX &#41;](../dmx/alter-mining-structure-dmx.md)합니다.  
  
 마이닝 모델 열 사용에 대 한 자세한 내용은 참조 [마이닝 모델 열](../analysis-services/data-mining/mining-model-columns.md)합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [데이터 마이닝 알고리즘&#40;Analysis Services - 데이터 마이닝&#41;](../analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md)   
 [Data Mining Extensions &#40; DMX &#41; 참조](../dmx/data-mining-extensions-dmx-reference.md)   
 [Data Mining Extensions &#40; DMX &#41; 구문 요소](../dmx/data-mining-extensions-dmx-syntax-elements.md)   
 [Data Mining Extensions &#40; DMX &#41; 함수 참조](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Data Mining Extensions &#40; DMX &#41; 연산자 참조](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [Data Mining Extensions &#40; DMX &#41; 문 참조](../dmx/data-mining-extensions-dmx-statements.md)   
 [Data Mining Extensions &#40; DMX &#41; 구문 표기 규칙](../dmx/data-mining-extensions-dmx-syntax-conventions.md)   
 [일반 예측 함수 &#40; DMX &#41;](../dmx/general-prediction-functions-dmx.md)   
 [구조 및 DMX 예측 쿼리 사용](../dmx/structure-and-usage-of-dmx-prediction-queries.md)   
 [DMX Select 문 이해](../dmx/understanding-the-dmx-select-statement.md)  
  
  
