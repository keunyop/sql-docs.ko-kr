---
title: '5단원: 보고서 서식 지정(Reporting Services) | Microsoft Docs'
ms.date: 05/23/2016
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: reporting-services
ms.topic: conceptual
ms.assetid: ae46efa9-6e04-48ec-afb4-5a2314dcb05a
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 1c5a41b39b5c22c05ac4b13a9e57606110b60a2b
ms.sourcegitcommit: 31800ba0bb0af09476e38f6b4d155b136764c06c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56291111"
---
# <a name="lesson-5-formatting-a-report-reporting-services"></a>5단원: 보고서 서식 지정(Reporting Services)
이제 Sales Orders 보고서에 데이터 영역과 일부 필드를 추가했으므로 날짜 및 통화 필드와 열 머리글의 서식을 지정할 수 있습니다.  
  
## <a name="bkmk_format_date"></a>날짜 서식 지정  
기본적으로 Date 필드에 날짜 및 시간 정보가 표시됩니다. 날짜만 표시되도록 서식을 지정할 수 있습니다.  
  
#### <a name="to-format-a-date-field"></a>날짜 필드의 서식을 지정하려면  
  
1.  **디자인** 탭을 클릭합니다.  
  
2.  `[Date]` 필드 식이 있는 셀을 마우스 오른쪽 단추로 클릭한 다음 **입력란 속성**을 클릭합니다.  
  
3.  **숫자**를 클릭한 다음 **범주** 필드에서 **날짜**를 클릭합니다.  
  
4.  **형식** 상자에서 **January 31, 2000**을 선택합니다.  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  보고서를 미리 보기하여 `[Date]` 필드의 변경 내용을 확인하고 다시 디자인 보기로 변경합니다.  
  
## <a name="bkmk_format_currency"></a>통화 서식 지정  
**LineTotal** 필드에는 일반 숫자가 표시됩니다. 서식을 지정하여 숫자가 통화로 표시되도록 합니다.  
  
#### <a name="to-format-a-currency-field"></a>통화 필드의 서식을 지정하려면  
  
1.  `[LineTotal]` 필드 식이 있는 셀을 마우스 오른쪽 단추로 클릭한 다음 **입력란 속성**을 클릭합니다.  
  
2.  **숫자**를 클릭한 다음 **범주** 필드에서 **통화**를 클릭합니다.  
  
3.  국가별 설정이 영어(미국)인 경우 기본값은 다음과 같아야 합니다.  
  
    -   **소수 자릿수: 2**  
  
    -   **음수: ($12345.00)**  
  
    -   **기호: $ 영어(미국)**  
  
4.  **천 단위 구분 기호(,) 사용**을 선택합니다.  
  
    샘플 텍스트가 **$12,345.00**이면 설정이 올바른 것입니다.  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  보고서를 미리 보기하여 `[LineTotal]` 필드의 변경 내용을 확인하고 다시 디자인 보기로 변경합니다.  
  
## <a name="bkmk_change_textstyle"></a>텍스트 스타일 및 열 너비 변경  
보고서 데이터의 행과 구분하기 위해 머리글 행의 서식 지정을 변경할 수 있습니다. 마지막으로 열의 너비를 조정합니다.  
  
#### <a name="to-format-header-rows-and-table-columns"></a>머리글 행 및 테이블 너비의 서식을 지정하려면  
  
1.  테이블을 클릭하여 열 핸들과 행 핸들이 테이블 위와 옆에 표시되도록 합니다. 테이블 위쪽 및 옆쪽을 따라 표시되는 회색 막대는 행 및 열 핸들입니다.  
       
  
2.  열 핸들 사이의 선에 커서를 두면 커서가 양방향 화살표로 바뀝니다. 이 상태에서 열을 끌어 크기를 원하는 대로 조정합니다.
 ![rs_BasicTableDetailsDesign](../reporting-services/media/rs-basictabledetailsdesign.png)   
  
3.  열 머리글 레이블이 있는 행을 선택하고 **서식** 메뉴에서 **글꼴** 을 가리킨 다음 **굵게**를 클릭합니다.  
  
4.  보고서를 미리 보려면 **미리 보기** 탭을 클릭합니다. 다음과 비슷합니다.  
  
    ![열 헤더가 굵게 설정된 테이블의 미리 보기](../reporting-services/media/rs-basictabledetailsformattedpreview.png "열 헤더가 굵게 설정된 테이블의 미리 보기")  
  
5.  **파일** 메뉴에서 **모두 저장** 을 클릭하여 보고서를 저장합니다.  
  
## <a name="next-steps"></a>Next Steps  
열 머리글과 날짜 및 통화 값의 서식을 성공적으로 지정했습니다. 그 다음은 보고서에 그룹화 및 합계를 추가하는 단계입니다. [6단원: 그룹화 및 합계 추가&#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
[숫자 및 날짜 서식 지정&#40;보고서 작성기 및 SSRS&#41;](../reporting-services/report-design/formatting-numbers-and-dates-report-builder-and-ssrs.md)  
[렌더링 동작&#40;보고서 작성기 및 SSRS&#41;](../reporting-services/report-design/rendering-behaviors-report-builder-and-ssrs.md)  
  
  
  

