---
title: 새 OLAP 마이닝 구조 만들기 | Microsoft Docs
ms.date: 05/01/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: data-mining
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: d0a12d7fad2deb138d2dac445492ffce55f1493a
ms.sourcegitcommit: 1ab115a906117966c07d89cc2becb1bf690e8c78
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2018
ms.locfileid: "52390717"
---
# <a name="create-a-new-olap-mining-structure"></a>새 OLAP 마이닝 구조 만들기
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
   [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 의 데이터 마이닝 마법사를 사용하여 다차원 모델의 데이터를 사용하는 마이닝 구조를 만들 수 있습니다. OLAP 큐브를 기반으로 하는 마이닝 모델은 팩트 테이블의 열과 값, 차원 및 측정값 그룹을 분석 특성으로 사용할 수 있습니다.  
  
### <a name="to-create-a-new-olap-mining-structure"></a>새 OLAP 마이닝 구조를 만들려면  
  
1.  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]의 솔루션 탐색기에서 **프로젝트의** 마이닝 구조 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 폴더를 마우스 오른쪽 단추로 클릭하고 **새 마이닝 구조** 를 클릭하여 데이터 마이닝 마법사를 엽니다.  
  
2.  **데이터 마이닝 마법사 시작** 페이지에서 **다음**을 클릭합니다.  
  
3.  **정의 방법 선택** 페이지에서 **기존 큐브 사용**을 선택하고 **다음**을 클릭합니다.  
  
     지원되는 데이터 마이닝 알고리즘 목록을 검색할 수 없습니다.라는 오류 메시지가 나타나면 **프로젝트 속성** 대화 상자를 열고 다차원 모델을 지원하는 Analysis Services 인스턴스 이름을 지정했는지 확인합니다. 테이블 형식 모델링을 지원하는 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 인스턴스에는 마이닝 모델을 만들 수 없습니다.  
  
4.  **데이터 마이닝 구조 만들기** 페이지에서 마이닝 구조만 만들지 아니면 마이닝 구조와 관련 마이닝 모델 하나를 함께 만들지 결정합니다. 일반적으로 필요한 열을 포함할지 묻는 메시지가 나타나도록 동시에 마이닝 모델을 만드는 편이 더 쉽습니다.  
  
     마이닝 모델을 만들려면 사용할 데이터 마이닝 알고리즘을 선택한 후 **다음**을 클릭합니다. 알고리즘을 선택하는 방법에 대한 자세한 내용은 [데이터 마이닝 알고리즘&#40;Analysis Services - 데이터 마이닝&#41;](../../analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md)을 참조하세요.  
  
5.  **원본 큐브 차원 선택** 페이지의 **원본 큐브 차원 선택**에서 대부분의 사례 데이터가 포함된 차원을 찾습니다.  
  
     예를 들어 고객 그룹화를 식별하려는 경우 Customer 차원을 선택할 수 있고, 트랜잭션 간 구매를 분석하려는 경우 Internet Sales Order Details 차원을 선택할 수 있습니다. 이 차원의 데이터만 사용하도록 제한되지는 않지만 해당 차원은 분석에 사용할 중요 특성을 포함해야 합니다.  
  
     **다음**을 클릭합니다.  
  
6.  **사례 키 선택** 페이지의 **특성**에서 마이닝 구조의 키로 사용할 특성을 선택하고 **다음**을 클릭합니다.  
  
     일반적으로 마이닝 구조의 키로 사용하는 특성은 차원의 키이기도 하며 미리 선택됩니다.  
  
7.  **사례 수준 열 선택** 페이지의 **관련 특성 및 측정값**에서 마이닝 구조에 추가할 값이 들어 있는 특성과 측정값을 사례 데이터로 선택합니다. **다음**을 클릭합니다.  
  
8.  **마이닝 모델 열 사용법 지정** 페이지의 **마이닝 모델 구조**에서 먼저 예측 가능한 열을 설정한 다음 입력으로 사용할 열을 선택합니다.  
  
    -   마이닝 구조의 데이터를 포함할 맨 왼쪽 열의 확인란을 선택합니다. 구조의 열 중에서 분석에 사용할 열이 아닌 참조에 사용할 열을 포함할 수 있습니다.  
  
    -   **입력** 열의 확인란을 선택하여 특성을 분석의 변수로 사용합니다.  
  
    -   예측 가능한 특성에 대해서만 **예측** 열의 확인란을 선택합니다.  
  
     키로 지정한 열은 입력이나 예측에 사용할 수 없습니다.  
  
     **다음**을 클릭합니다.  
  
9. **마이닝 모델 열 사용법 지정** 페이지에서는 **중첩 테이블 추가** 및 **중첩 테이블**을 사용하여 중첩 테이블을 마이닝 구조에 추가하거나 제거할 수도 있습니다.  
  
     OLAP 마이닝 구조에서 중첩 테이블은 케이스 특성을 나타내는 차원을 가진 일 대 다 관계가 포함된 큐브 내의 또 다른 데이터 집합입니다. 따라서 대화 상자를 열면 케이스 테이블로 선택한 차원과 이미 관련되어 있는 측정값 그룹이 미리 선택됩니다. 이때 분석에 유용한 추가 정보가 포함되어 있는 다른 차원을 선택합니다.  
  
     예를 들어 고객을 분석하는 경우 [Customer] 차원을 케이스 테이블로 사용합니다. 중첩 테이블의 경우 고객이 구매할 때 제시한 이유를 추가할 수 있습니다. 이 이유는 [Sales Reason] 차원에 포함되어 있습니다.  
  
     중첩된 데이터를 추가하는 경우 다음과 같은 두 개의 추가 열을 지정해야 합니다.  
  
    -   중첩 테이블의 키: 이 페이지에서 미리 선택 되어야 합니다 **중첩 테이블 키 선택**합니다.  
  
    -   분석에 사용할 특성: 페이지 **중첩 테이블 열 선택**중첩된 테이블 선택 항목의 특성 및 측정값 목록을 제공 합니다.  
  
        -   모델에 포함하는 각 특성에 대해 왼쪽 열의 상자를 선택합니다.  
  
        -   특성을 분석에만 사용하려는 경우 **입력**을 선택합니다.  
  
        -   열을 모델의 예측 가능한 특성 중 하나로만 포함하려는 경우 **예측**을 선택합니다.  
  
        -   구조에 포함하되 입력 또는 예측 가능한 특성으로 지정하지 않는 항목은 모두 **Ignore**플래그와 함께 구조에 추가됩니다. 이는 모델을 작성할 때 데이터가 처리되지만 해당 데이터는 분석에 사용되지 않으며 드릴스루용으로만 사용 가능함을 의미합니다. 이 기능은 고객 이름과 같은 세부 정보를 포함 하려고 하지만 분석에서 사용 하지 않으려는 경우에 유용할 수 있습니다.  
  
     **마침** 를 클릭하여 중첩 테이블을 사용하는 마법사 부분을 닫습니다. 프로세스를 반복하여 여러 중첩 열을 추가할 수 있습니다.  
  
10. **열 내용 및 데이터 형식 지정** 페이지의 **마이닝 모델 구조**에서 각 열의 내용 유형과 데이터 형식을 설정합니다.  
  
    > [!NOTE]  
    >  OLAP 마이닝 모델에서는 **검색** 기능을 사용하여 열에 연속 데이터나 불연속 데이터가 있는지 자동으로 검색할 수 없습니다.  
  
     **다음**을 클릭합니다.  
  
11. **원본 큐브 조각화** 페이지에서 마이닝 구조를 만드는 데 사용되는 데이터를 필터링할 수 있습니다.  
  
     큐브를 조각화하면 모델을 작성하는 데 사용되는 데이터를 제한할 수 있습니다. 예를 들어 Geography 계층을 조각화하여 각 지역에 대해 별도의 모델을 작성할 수 있습니다.  
  
    -   **차원**: 드롭다운 목록에서 관련된 차원을 선택합니다.  
  
    -   **계층**:  필터를 적용하려는 차원 계층의 수준을 선택합니다. 예를 들어 [Geography] 차원을 기준으로 조각화하는 경우에는 [Region Country Name]과 같은 계층 수준을 선택합니다.  
  
    -   **연산자**: 목록에서 연산자를 선택합니다.  
  
    -   **필터 식**: 필터 조건으로 사용할 값 또는 식을 입력하거나 드롭다운 목록을 사용하여 지정된 계층 수준의 멤버 목록에서 값을 선택합니다.  
  
         예를 들어 [Geography]를 차원으로 선택하고 [Region Country Name]을 계층 수준으로 선택한 경우 드롭다운 목록에는 필터 조건으로 사용할 수 있는 모든 유효한 국가가 포함되어 있습니다. 여러 항목을 선택 할 수 있습니다. 결과적으로 마이닝 구조의 데이터가 이러한 지리적인 영역의 큐브 데이터로 제한됩니다.  
  
    -   **매개 변수**: 이 확인란을 무시합니다. 이 대화 상자에서는 여러 큐브 필터링 시나리오를 지원하며 이 옵션은 마이닝 구조 작성과 관련되어 있지 않습니다.  
  
     **다음**을 클릭합니다.  
  
12. **학습 및 테스트 집합으로 데이터 분할** 페이지에서 테스트용으로 예약할 마이닝 구조 데이터의 비율을 지정하거나 테스트 사례의 최대 수를 지정합니다. **다음**을 클릭합니다.  
  
     두 값을 모두 지정하면 더 낮은 쪽을 사용하도록 두 제한이 결합됩니다.  
  
13. **마법사 완료** 페이지에서 새 OLAP 마이닝 구조의 이름과 초기 마이닝 모델을 지정합니다.  
  
14. **마침**을 클릭합니다.  
  
15. **마법사 완료** 페이지에는 마이닝 모델 차원을 사용하여 마이닝 모델 차원이나 큐브를 만들 수 있는 옵션도 있습니다. 이러한 옵션은 다음 알고리즘을 사용하여 작성된 모델에 대해서만 지원됩니다.  
  
    -   Microsoft 클러스터링 알고리즘  
  
    -   Microsoft 의사 결정 트리 알고리즘  
  
    -   Microsoft 연결 규칙 알고리즘  
  
     **마이닝 모델 차원 만들기**: 이 확인란을 선택하고 마이닝 모델 차원의 형식 이름을 제공합니다. 이 옵션을 사용하면 마이닝 구조를 작성하는 데 사용된 원본 큐브 내에 새 차원이 만들어집니다. 이 차원을 사용하여 드릴다운 및 추가 분석을 수행할 수 있습니다. 차원은 큐브 내에 있으므로 사례 데이터 차원에 자동으로 매핑됩니다.  
  
     **마이닝 모델 차원을 사용 하 여 큐브 만들기**: 이 확인란을 선택하고 새 큐브의 이름을 제공합니다. 이 옵션을 사용하면 구조를 작성하는 데 사용된 기존 차원과 모델의 결과가 포함된 새 데이터 마이닝 차원이 모두 포함된 새 큐브가 만들어집니다.  
  
## <a name="see-also"></a>관련 항목  
 [마이닝 구조 태스크 및 방법](../../analysis-services/data-mining/mining-structure-tasks-and-how-tos.md)  
  
  
