---
title: 필터 추가(보고서 작성기 및 SSRS) | Microsoft Docs
ms.date: 03/07/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.technology: report-design
ms.topic: conceptual
ms.assetid: 10ae54e7-0e8a-4dff-995d-05516c51d076
author: markingmyname
ms.author: maghan
ms.openlocfilehash: dfc6115dbda5bbdeeac2ca629c5e7adb4d4a1fd8
ms.sourcegitcommit: 31800ba0bb0af09476e38f6b4d155b136764c06c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56296201"
---
# <a name="add-a-filter-report-builder-and-ssrs"></a>필터 추가(보고서 작성기 및 SSRS)
  계산 또는 표시 내용에 특정 값을 포함하거나 제외하려는 경우 데이터 세트, 데이터 영역 또는 그룹에 필터를 추가할 수 있습니다. 필터는 런타임에 데이터 세트에 대해 가장 먼저 적용된 다음 데이터 영역과 그룹(그룹 계층 구조에 대해 하향식으로)에 차례로 적용됩니다. 테이블, 행렬 또는 목록에서 행 그룹, 열 그룹 및 인접 그룹의 필터는 독립적으로 적용됩니다. 또한 차트에서 범주 그룹 및 계열 그룹의 필터는 독립적으로 적용됩니다.  
  
 필터를 추가하려면 하나 이상의 필터 수식을 지정해야 합니다. 필터 수식은 필터링할 데이터를 식별하는 식, 연산자 및 비교할 값으로 구성됩니다. 필터링된 데이터와 값의 데이터 형식은 일치해야 합니다. 데이터 세트나 데이터 영역에는 집계 값에 대한 필터링이 지원되지 않습니다.  
  
 차트에서 데이터 요소를 필터링하려면 범주 그룹이나 계열 그룹에 대해 필터를 설정하면 됩니다. 기본적으로 차트에서는 기본 제공 함수 Sum을 사용하여 동일한 그룹에 속하는 값을 계열의 개별 데이터 요소로 집계합니다. 계열의 집계 함수를 변경할 경우에는 필터 식의 집계 함수를 변경해야 합니다.  
  
 포함된 데이터 세트 및 공유 데이터 세트 필터링에 대한 자세한 내용은 [데이터 세트에 필터 추가&amp;#40;보고서 작성기 및 SSRS&amp;#41;](../../reporting-services/report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md)을 참조하세요.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-a-filter-on-a-data-region"></a>데이터 영역에 대해 필터를 설정하려면  
  
1.  **디자인** 뷰에서 보고서를 엽니다.  
  
2.  디자인 화면에서 데이터 영역을 선택한 다음 _\<data region>_**속성**을 마우스 오른쪽 단추로 클릭합니다. 계기의 경우 **계기 패널 속성**을 선택합니다. _\<data region>_**속성** 대화 상자가 열립니다.  
  
    > [!NOTE]  
    >  테이블릭스 데이터 영역에서 모퉁이 셀이나 행 또는 열 핸들을 마우스 오른쪽 단추로 클릭한 다음 **테이블릭스 속성**을 클릭합니다.  
  
3.  **필터**를 클릭합니다. 그러면 현재 필터 수식 목록이 표시됩니다. 기본적으로 이 목록은 비어 있습니다.  
  
4.  **추가**를 클릭합니다. 새로운 빈 필터 수식이 나타납니다.  
  
5.  **식**에서 필터링할 필드에 대한 식을 입력하거나 선택합니다. 식을 편집하려면 식(*fx*) 단추를 클릭합니다.  
  
6.  5단계에서 만든 식의 데이터 형식과 일치하는 데이터 형식을 드롭다운 상자에서 선택합니다.  
  
7.  **연산자** 상자에서 해당 필터로 **식** 상자와 **값** 상자의 값을 비교하는 데 사용할 연산자를 선택합니다. 선택한 연산자에 따라 다음 단계에서 사용하는 값의 수가 결정됩니다.  
  
8.  **값** 상자에 해당 필터로 **식**의 값을 계산하는 데 기준이 되는 식 또는 값을 입력합니다.  
  
     필터 수식의 예는 [필터 수식 예&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/filter-equation-examples-report-builder-and-ssrs.md)를 참조하세요.  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-tablix-row-or-column-group"></a>테이블릭스 행 또는 열 그룹에 대해 필터를 설정하려면  
  
1.  **디자인** 뷰에서 보고서를 엽니다.  
  
2.  디자인 화면의 테이블, 행렬 또는 목록 데이터 영역을 마우스 오른쪽 단추로 클릭하여 선택합니다. 그룹화 창에 선택한 항목에 대한 그룹이 표시됩니다.  
  
3.  그룹화 창에서 그룹을 마우스 오른쪽 단추로 클릭한 다음 **그룹 편집**을 클릭합니다. **테이블릭스 그룹** 대화 상자가 열립니다.  
  
4.  **필터**를 클릭합니다. 그러면 현재 필터 수식 목록이 표시됩니다. 기본적으로 이 목록은 비어 있습니다.  
  
5.  **추가**를 클릭합니다. 새로운 빈 필터 수식이 나타납니다.  
  
6.  **식**에서 필터링할 필드에 대한 식을 입력하거나 선택합니다. 식을 편집하려면 식(*fx*) 단추를 클릭합니다.  
  
7.  5단계에서 만든 식의 데이터 형식과 일치하는 데이터 형식을 드롭다운 상자에서 선택합니다.  
  
8.  **연산자** 상자에서 해당 필터로 **식** 상자와 **값** 상자의 값을 비교하는 데 사용할 연산자를 선택합니다. 선택한 연산자에 따라 다음 단계에서 사용하는 값의 수가 결정됩니다.  
  
9. **값** 상자에 해당 필터로 **식**의 값을 계산하는 데 기준이 되는 식 또는 값을 입력합니다.  
  
     필터 수식의 예는 [필터 수식 예&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/filter-equation-examples-report-builder-and-ssrs.md)를 참조하세요.  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-chart-category-group"></a>차트 범주 그룹에 대해 필터를 설정하려면  
  
1.  **디자인** 뷰에서 보고서를 엽니다.  
  
2.  디자인 화면에서 차트를 두 번 클릭하여 데이터, 계열 및 범주 필드 끌어 놓기 영역을 표시합니다.  
  
3.  범주 필드 끌어 놓기 영역에 포함된 필드를 마우스 오른쪽 단추로 클릭하고 **범주 그룹 속성**을 선택합니다.  
  
4.  **필터**를 클릭합니다. 그러면 현재 필터 수식 목록이 표시됩니다. 기본적으로 이 목록은 비어 있습니다.  
  
5.  **추가**를 클릭합니다. 새로운 빈 필터 수식이 나타납니다.  
  
6.  **식**에서 필터링할 필드에 대한 식을 입력하거나 선택합니다. 식을 편집하려면 식(*fx*) 단추를 클릭합니다.  
  
7.  5단계에서 만든 식의 데이터 형식과 일치하는 데이터 형식을 드롭다운 상자에서 선택합니다.  
  
8.  **연산자** 상자에서 해당 필터로 **식** 상자와 **값** 상자의 값을 비교하는 데 사용할 연산자를 선택합니다. 선택한 연산자에 따라 다음 단계에서 사용하는 값의 수가 결정됩니다.  
  
9. **값** 상자에 해당 필터로 **식**의 값을 계산하는 데 기준이 되는 식 또는 값을 입력합니다.  
  
     필터 수식의 예는 [필터 수식 예&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/filter-equation-examples-report-builder-and-ssrs.md)를 참조하세요.  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-chart-series-group"></a>차트 계열 그룹에 대해 필터를 설정하려면  
  
1.  **디자인** 뷰에서 보고서를 엽니다.  
  
2.  디자인 화면에서 차트를 두 번 클릭하여 데이터, 계열 및 범주 필드 끌어 놓기 영역을 표시합니다.  
  
3.  계열 필드 끌어 놓기 영역에 포함된 필드를 마우스 오른쪽 단추로 클릭하고 **계열 그룹 속성**을 선택합니다.  
  
4.  **필터**를 클릭합니다. 그러면 현재 필터 수식 목록이 표시됩니다. 기본적으로 이 목록은 비어 있습니다.  
  
5.  **추가**를 클릭합니다. 새로운 빈 필터 수식이 나타납니다.  
  
6.  **식**에서 필터링할 필드에 대한 식을 입력하거나 선택합니다. 식을 편집하려면 식(*fx*) 단추를 클릭합니다.  
  
7.  5단계에서 만든 식의 데이터 형식과 일치하는 데이터 형식을 드롭다운 상자에서 선택합니다.  
  
8.  **연산자** 상자에서 해당 필터로 **식** 상자와 **값** 상자의 값을 비교하는 데 사용할 연산자를 선택합니다. 선택한 연산자에 따라 다음 단계에서 사용하는 값의 수가 결정됩니다.  
  
9. **값** 상자에 해당 필터로 **식**의 값을 계산하는 데 기준이 되는 식 또는 값을 입력합니다.  
  
     필터 수식의 예는 [필터 수식 예&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/filter-equation-examples-report-builder-and-ssrs.md)를 참조하세요.  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [데이터 세트 필터, 데이터 영역 필터 및 그룹 필터 추가&amp;#40;보고서 작성기 및 SSRS&amp;#41;](../../reporting-services/report-design/add-dataset-filters-data-region-filters-and-group-filters.md)   
 [식 예&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/expression-examples-report-builder-and-ssrs.md)   
 [계기&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/gauges-report-builder-and-ssrs.md)   
 [테이블, 행렬 및 목록&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/tables-matrices-and-lists-report-builder-and-ssrs.md)   
 [차트&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)  
  
  
