---
title: 일반 예측 함수 (DMX) | Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: c8de92033c58f2583fc7ba93e6c326d4a406c90a
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "37985435"
---
# <a name="general-prediction-functions-dmx"></a>일반 예측 함수(DMX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  사용할 수는 **선택** 에서 확장 DMX (Data Mining) 다양 한 유형의 쿼리를 만드는 문입니다. 쿼리는 마이닝 모델 자체에 대한 정보를 반환하거나, 새 예측을 만들거나, 새 데이터로 모델을 학습시켜 모델을 변경하기 위해 사용할 수 있습니다. [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] 다양 한 쿼리에서 반환 되는 정보의 유형을 제어 하는 특수 한 기능을 제공 합니다. 이러한 함수를 DMX 쿼리에 추가하면 추가 통계 또는 데이터 열을 검색할 수 있습니다. 그러나 쿼리 유형과 모델 유형마다 지원되는 함수가 다릅니다.  
  
## <a name="common-functions"></a>일반 함수  
 함수를 사용하여 마이닝 모델이 반환하는 결과를 확장할 수 있습니다. 에 대 한 다음 함수를 사용할 수 있습니다 **선택** 테이블 식을 반환 하는 문:  
  
|||  
|-|-|  
|[BottomCount &#40;DMX&#41;](../dmx/bottomcount-dmx.md)|[RangeMin &#40;DMX&#41;](../dmx/rangemin-dmx.md)|  
|[BottomPercent &#40;DMX&#41;](../dmx/bottompercent-dmx.md)|[TopCount &#40;DMX&#41;](../dmx/topcount-dmx.md)|  
|[예측 &#40;DMX&#41;](../dmx/predict-dmx.md)|[TopPercent &#40;DMX&#41;](../dmx/toppercent-dmx.md)|  
|[RangeMax &#40;DMX&#41;](../dmx/rangemax-dmx.md)|[TopSum &#40;DMX&#41;](../dmx/topsum-dmx.md)|  
|[RangeMid &#40;DMX&#41;](../dmx/rangemid-dmx.md)||  
  
 다음 함수도 거의 모든 모델 유형에 대해 지원됩니다.  
  
-   [존재 &#40;DMX&#41;](../dmx/exists-dmx.md)  
  
-   [IsDescendant &#40;DMX&#41;](../dmx/isdescendant-dmx.md)  
  
-   [IsTestCase &#40;DMX&#41;](../dmx/istestcase-dmx.md)  
  
-   [IsTrainingCase &#40;DMX&#41;](../dmx/istrainingcase-dmx.md)  
  
-   [예측 &#40;DMX&#41;](../dmx/predict-dmx.md)  
  
-   [RangeMax &#40;DMX&#41;](../dmx/rangemax-dmx.md)  
  
-   [RangeMid &#40;DMX&#41;](../dmx/rangemid-dmx.md)  
  
-   [RangeMin &#40;DMX&#41;](../dmx/rangemin-dmx.md)  
  
-   [StructureColumn &#40;DMX&#41;](../dmx/structurecolumn-dmx.md)  
  
 개별 알고리즘에서 추가 함수를 지원할 수 있습니다. 각 모델 유형에 서 지원 되는 함수의 목록을 참조 하세요 [데이터 마이닝 쿼리](../analysis-services/data-mining/data-mining-queries.md)합니다.  
  
## <a name="functions-specific-to-select-syntax"></a>SELECT 구문용 함수  
 다음 표에서 각 유형에 대해 사용할 수 있는 함수 **선택** 문입니다.  
  
 DMX 함수에에서 대 한 일반적인 내용은 참조 하세요. [Data Mining Extensions &#40;DMX&#41; 함수 참조](../dmx/data-mining-extensions-dmx-function-reference.md)합니다.  
  
|쿼리 유형|지원되는 함수|Remarks|  
|----------------|-------------------------|-------------|  
|[SELECT DISTINCT FROM \<모델 >](../dmx/select-distinct-from-model-dmx.md)|[RangeMin &#40;DMX&#41;](../dmx/rangemin-dmx.md)<br /><br /> [RangeMid &#40;DMX&#41;](../dmx/rangemid-dmx.md)<br /><br /> [RangeMax &#40;DMX&#41;](../dmx/rangemax-dmx.md)|이러한 함수는 숫자 데이터 형식을 포함하는 열이 연속 열인지 아니면 불연속화된 열인지에 관계없이 해당 열의 최소값, 최대값 및 평균을 제공하는 데 사용할 수 있습니다.|  
|[SELECT FROM \<모델 >. 콘텐츠](../dmx/select-from-model-content-dmx.md)<br /><br /> 로 구분하거나 여러<br /><br /> [SELECT FROM \<모델 >. DIMENSION_CONTENT](../dmx/select-from-model-dimension-content-dmx.md)|[IsDescendant &#40;DMX&#41;](../dmx/isdescendant-dmx.md)|이 함수는 모델의 지정된 노드에 대한 자식 노드를 검색하며 마이닝 모델 콘텐츠의 노드를 반복하는 데 사용할 수 있습니다. 마이닝 모델 콘텐츠에 포함된 노드 배열은 모델 유형에 따라 달라집니다. 구조에 마이닝 모델 유형에 대 한 자세한 내용은 [마이닝 모델 콘텐츠 &#40;Analysis Services-데이터 마이닝&#41;](../analysis-services/data-mining/mining-model-content-analysis-services-data-mining.md)합니다.<br /><br /> 마이닝 모델 콘텐츠를 차원으로 저장한 경우 특성 계층을 쿼리하는 데 사용할 수 있는 다른 MDX(Multidimensional Expressions) 함수도 사용할 수 있습니다.|  
|[SELECT FROM \<모델 >. 경우](../dmx/select-from-model-cases-dmx.md)|[IsInNode &#40;DMX&#41;](../dmx/isinnode-dmx.md)<br /><br /> [ClientSettingsGeneralFlag 클래스](../relational-databases/wmi-provider-configuration-classes/clientsettingsgeneralflag-class/clientsettingsgeneralflag-class.md)<br /><br /> [IsTrainingCase &#40;DMX&#41;](../dmx/istrainingcase-dmx.md)<br /><br /> [IsTestCase &#40;DMX&#41;](../dmx/istestcase-dmx.md)|Lag 함수는 시계열 모델에만 지원 됩니다.<br /><br /> IsTestCase 함수는 홀드 아웃 옵션을 사용 하 여 테스트 데이터 집합을 만들려면 생성 된 구조를 기반으로 하는 모델에서 지원 됩니다. 모델이 홀드아웃 테스트 집합이 포함된 구조를 기반으로 하지 않을 경우 모든 사례는 학습 사례로 간주됩니다.|  
|[SELECT FROM \<모델 >. SAMPLE_CASES](../dmx/select-from-model-sample-cases-dmx.md)|[IsInNode &#40;DMX&#41;](../dmx/isinnode-dmx.md)|이 컨텍스트에서 IsInNode 함수는 이상적인된 샘플 사례 집합에 속하는 사례를 반환 합니다.|  
|SELECT FROM \<모델 >. PMML|이 오류에는 이 작업을 적용할 수 없습니다. 대신 XML 쿼리 함수 사용|PMML 표현은 다음 모델 유형에 대해서만 지원됩니다.<br /><br /> [!INCLUDE[msCoName](../includes/msconame-md.md)] 의사 결정 트리<br /><br /> [!INCLUDE[msCoName](../includes/msconame-md.md)] 클러스터링|  
|[SELECT FROM \<모델 > PREDICTION JOIN](../dmx/select-from-model-prediction-join-dmx.md)|모델을 만드는 데 사용하는 알고리즘과 관련된 예측 함수|각 모델 유형에 예측 함수 목록은 참조 하세요 [데이터 마이닝 쿼리](../analysis-services/data-mining/data-mining-queries.md)합니다.|  
|[SELECT FROM \<모델 >](../dmx/select-from-model-dmx.md)|모델을 만드는 데 사용하는 알고리즘과 관련된 예측 함수|각 모델 유형에 예측 함수 목록은 참조 하세요 [데이터 마이닝 쿼리](../analysis-services/data-mining/data-mining-queries.md)합니다.|  
  
## <a name="see-also"></a>관련 항목  
 [Data Mining Extensions &#40;DMX&#41; 참조](../dmx/data-mining-extensions-dmx-reference.md)   
 [Data Mining Extensions &#40;DMX&#41; 함수 참조](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Data Mining Extensions &#40;DMX&#41; 연산자 참조](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [Data Mining Extensions &#40;DMX&#41; 문 참조](../dmx/data-mining-extensions-dmx-statements.md)   
 [Data Mining Extensions &#40;DMX&#41; 구문 표기 규칙](../dmx/data-mining-extensions-dmx-syntax-conventions.md)   
 [Data Mining Extensions &#40;DMX&#41; 구문 요소](../dmx/data-mining-extensions-dmx-syntax-elements.md)   
 [구조 및 사용법 DMX 예측 쿼리](../dmx/structure-and-usage-of-dmx-prediction-queries.md)   
 [DMX Select 문 이해](../dmx/understanding-the-dmx-select-statement.md)  
  
  
