---
title: 분류표 (SQL Server 데이터 마이닝 추가 기능) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, validating
- classification matrix
- confusion table
- mining models, testing
ms.assetid: d6f620f4-39af-4714-9628-28ce3c361fca
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 5f2f1f055974edc3625ed66a8d803358b8345494
ms.sourcegitcommit: 2429fbcdb751211313bd655a4825ffb33354bda3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "52522168"
---
# <a name="classification-matrix-sql-server-data-mining-add-ins"></a>분류표(SQL Server 데이터 마이닝 추가 기능)
  ![데이터 마이닝 리본, 분류표 단추](media/dmc-cmatrix.gif "데이터 마이닝 리본, 분류표 단추")  
  
 분류표를 사용하여 예측에 대한 모델의 정확도를 평가할 수 있습니다. 분류표를 생성하려면 모델을 통해 테스트 데이터 집합을 실행해야 합니다. 분류표 도구는 테스트 집합의 실제 값과 모델로 산출된 예측을 비교합니다. 분류표를 확인하여 모델이 올바르게 예측한 빈도와 잘못 예측한 빈도를 한눈에 볼 수 있습니다.  
  
 이러한 추가 기능을 사용 합니다 **분류표** , 모델을 선택 하 고, 테스트 데이터를 지정 하 고, 다음 결과 분류표를 생성 하는 마법사.  
  
## <a name="how-to-read-a-classification-matrix"></a>분류표를 읽는 방법  
 적절 한 수준의 인센티브를 사용 하 여 제공할 수 있도록 목표가 고객 충성도 프로그램을 디자인 한 다음 적절 한 범주에 고객을 할당 하는 경우를 가정해 봅니다. 수행 된 이러한 고객에 게 시험 단계에서 서-동, silver 및 gold-보상 프로그램에 대 한 세 가지 수준 구현 했습니다. 또한 고객을 분석하고 올바른 범주를 예측하는 모델을 설계했습니다. 이제 시험 데이터에 대한 분류표를 사용하여 모델이 모든 고객에 대한 올바른 보상을 얼마나 정확하게 예측했는지를 확인할 것입니다.  
  
 분류표의 표에서는 모델을 기반으로 각 범주에 할당될 고객 수를 알려주고 이 결과를 각 보상 수준에 실제로 등록한 고객 수와 비교합니다.  
  
||동(실제)|금(실제)|은(실제)|  
|-|-----------------------|---------------------|-----------------------|  
|동|**94.45%**|15.18%|1.70%|  
|금|2.72%|**84.82%**|0.00%|  
|Silver|1.84%|0.00%|**93.80%**|  
|*올바름*|*95.45%*|*84.82%*|*98.30%*|  
|*오 분류*|*4.55%*|*15.18%*|*1.70%*|  
  
-   각 열에는 테스트 데이터 집합의 실제 값이 표시됩니다.  
  
-   각 행에는 예측된 값이 표시됩니다.  
  
-   분류표의 왼쪽 위 모퉁이에서 오른쪽 아래 모퉁이까지 대각선 방향으로 굵게 표시된 값은 모델이 올바르게 예측한 값을 보여 줍니다.  
  
-   대각선 밖의 다른 모든 값은 오류를 나타냅니다. 일부 오류는 거짓 긍정입니다. 즉, 모델은 고객이 금 프로그램에 참여할 것으로 예측했지만 틀린 경우입니다.  분야에 따라 거짓 긍정은 비용이 매우 많이 들 수 있습니다.  
  
     다른 오류는 거짓 부정입니다. 즉, 모델은 고객이 관심이 없을 것이라고 예측했지만 고객은 프로그램에 참여한 경우입니다. 마찬가지로 문제 분야에 따라 이 손실된 기회 비용은 상당히 클 수 있습니다.  
  
## <a name="using-the-classification-matrix-wizard"></a>분류표 마법사 사용  
  
1.  예측의 기반이 될 마이닝 모델을 선택합니다.  
  
2.  새 테스트 데이터의 원본을 선택하거나 구조와 함께 저장된 테스트 데이터를 사용합니다.  
  
3.  정확도를 평가하려는 열을 선택합니다. 분류표를 만들 때 열을 하나만 선택할 수 있지만 열의 값이 여러 개일 수 있습니다.  
  
     팁:  예측 가능한 열에 비교할 여러 열이 있는 경우 분류표를 해석하기가 어려울 수 있습니다.  
  
     에 **예측할 열 선택** 페이지를 지정할 수 있습니다도 올바르지 않은 값의 개수를 표시 하거나 백분율을 표시할 것인지 여부를 합니다.  
  
4.  원본 데이터 선택 페이지에서 외부 테스트 데이터를 사용할지, 아니면 모델과 함께 저장된 테스트 데이터를 사용할지를 나타냅니다.  
  
5.  외부 테스트 데이터를 사용 하는 경우 모델 입력된 열을 매핑합니다 해야 합니다 **관계 지정** 마법사의 페이지입니다.  
  
     포함된 테스트 데이터 집합을 사용하는 경우 매핑이 자동으로 수행됩니다.  
  
6.  클릭 **완료** 모델에 대해 예측을 실행 하 고 분류표를 생성 합니다.  
  
     마법사가 분류표 및 분석에 대한 기타 세부 사항이 포함된 보고서를 만듭니다. 이 보고서는 Excel에서 테이블로 저장되며 보고서 위에는 올바르게 예측된 경우의 수와 잘못된 예측의 수를 나타내는 요약이 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  
-   분류표를 만들려면 정확도 측정을 지원하는 기존 마이닝 모델에 액세스할 수 있어야 합니다. 예측 모델과 연결 모델은 이 도구를 사용하여 측정될 수 없습니다.  
  
-   측정할 모델은 불연속 값이거나 이미 불연속화된 값을 예측해야 합니다.  
  
-   구조 나 모델과 함께 테스트 집합을 저장 하는 옵션을 사용 하지 않은 경우에 동일한 개수의 열을 모델에 사용 되는 데이터 형식이 일치 기본적으로 입력된 데이터 집합을 가져올 해야 합니다.  
  
-   데이터 마이닝 모델과 테스트에 사용할 새 데이터에는 예측 가능한 열이 한 개 이상 있어야 하며 열은 반드시 동일한 종류의 데이터를 포함해야 합니다.  
  
### <a name="known-issues"></a>알려진 문제  
 SQL Server 2012 및 SQL Server 2014에서는 내부 테스트 데이터 집합을 모델에 매핑할 수에서 작동 하지 않습니다 합니다 **분류표** 도구입니다. 그러나 외부 데이터 집합을 지정한 다음 학습 집합을 입력으로 선택하여 원래 데이터 집합에 대한 오류를 확인할 수 있습니다.  
  
## <a name="see-also"></a>관련 항목:  
 [모델 유효성 검사 및 예측 용 모델 사용 &#40;Excel 용 데이터 마이닝 추가 기능&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md)   
 [데이터 탐색 &#40;SQL Server 데이터 마이닝 추가 기능&#41;](explore-data-sql-server-data-mining-add-ins.md)   
 [범주 검색 &#40;Excel 용 테이블 분석 도구&#41;](detect-categories-table-analysis-tools-for-excel.md)  
  
  
