---
title: (SSAS 테이블 형식)는 데이터 피드에서 가져오기 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
ms.assetid: 0686e519-67c2-4f9b-8cd2-84a4871499ee
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 27c22caf9c3b6dfebede60cd795496496562c19b
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48099843"
---
# <a name="import-from-a-data-feed-ssas-tabular"></a>데이터 피드에서 가져오기(SSAS 테이블 형식)
  데이터 피드는 온라인 데이터 원본에서 생성되어 대상 문서 또는 애플리케이션으로 스트리밍되는 하나 이상의 XML 데이터 스트림입니다. 테이블 가져오기 마법사를 사용하여 데이터 피드의 데이터를 모델로 가져올 수 있습니다.  
  
 이 항목에는 다음과 같은 섹션이 포함되어 있습니다.  
  
-   [데이터 피드에서 가져오기 이해](#prereq)  
  
-   [Azure DataMarket 데이터 집합에서 데이터 가져오기](#azure)  
  
-   [공용 또는 회사 데이터 원본에서 데이터 피드 가져오기](#importdata)  
  
-   [SharePoint 목록에서 데이터 피드 가져오기](#importlist)  
  
-   [Reporting Services 보고서에서 데이터 피드 가져오기](#importreport)  
  
##  <a name="prereq"></a> 데이터 피드에서 가져오기 이해  
 다음 유형의 데이터 피드에서 테이블 형식 모델로 데이터를 가져올 수 있습니다.  
  
 **Reporting Services 보고서**  
 SharePoint 사이트나 보고서 서버에 게시한 Reporting Services 보고서를 모델에서 데이터 원본으로 사용할 수 있습니다. Reporting Services 보고서에서 데이터를 가져올 경우 보고서 정의(.rdl) 파일을 데이터 원본으로 지정해야 합니다.  
  
 **하늘색 DataMarket 데이터 집합**  
 Azure DataMarket은 단일 마켓플레이스와 정보 배달 채널을 클라우드 서비스로 제공하는 서비스입니다. Azure DataMarket 데이터 세트에는 Windows 사용자 계정 대신 계정 키가 필요합니다.  
  
 **Atom 피드**  
 피드는 ATOM 피드여야 합니다. RSS 피드는 지원되지 않습니다. 누구나 사용할 수 있도록 피드가 공개되어 있거나 피드 연결에 필요한 권한이 현재 로그인에 사용한 Windows 계정에 있어야 합니다.  
  
 가져오는 동안 데이터 피드의 데이터가 모델에 한 번 추가됩니다. 피드에서 업데이트된 데이터를 가져오려면 모델 디자이너에서 데이터를 새로 고치거나, 모델이 Analysis Services의 프로덕션 인스턴스에 배포된 후 이 모델에 대해 데이터 새로 고침 일정을 구성할 수 있습니다. 자세한 내용은 [데이터 처리&#40;SSAS 테이블 형식&#41;](process-data-ssas-tabular.md)를 참조하세요.  
  
##  <a name="azure"></a> Azure DataMarket 데이터 집합에서 데이터 가져오기  
 Azure DataMarket의 데이터를 모델에 테이블로 가져올 수 있습니다.  
  
#### <a name="to-import-data-from-an-azure-datamarket-dataset"></a>Azure DataMarket 데이터 세트에서 데이터를 가져오려면  
  
1.  [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]에서 **모델** 메뉴를 클릭한 다음 **데이터 원본에서 가져오기**를 클릭합니다. 테이블 가져오기 마법사가 열립니다.  
  
2.  **데이터 원본에 연결** 페이지의 **데이터 피드**에서 **Azure DataMarket 데이터 집합**을 선택한 다음 **다음**을 클릭합니다.  
  
3.  **Azure DataMarket 데이터 집합에 연결** 페이지의 **이름**에 액세스하는 피드를 설명하는 이름을 입력합니다. 피드 또는 데이터 원본을 여러 개 가져오는 경우 연결을 설명하는 이름을 사용하면 연결이 사용되는 방식을 기억하는 데 도움이 됩니다.  
  
4.  **데이터 피드 URL**에 데이터 피드의 주소를 입력합니다.  
  
5.  **보안 설정**의 **계정 키**에 계정 키를 입력합니다. 계정 키는 Analysis Services가 DataMarket 구독에 액세스할 때 사용됩니다.  
  
6.  **연결 테스트** 를 클릭하여 피드를 사용할 수 있는지 확인합니다. 또는 **고급** 을 클릭하여 기본 URL이나 서비스 문서 URL에 피드를 제공하는 쿼리 또는 서비스 문서가 포함되어 있는지 확인할 수도 있습니다.  
  
7.  **다음** 을 클릭하여 가져오기 작업을 계속합니다.  
  
8.  **가장 정보** 페이지에서 데이터를 새로 고칠 때 Analysis Services가 데이터 원본에 연결하는 데 사용할 자격 증명을 지정하고 **다음**을 클릭합니다. 이러한 자격 증명은 계정 키와 다릅니다.  
  
9. 마법사의 **테이블 및 뷰 선택** 페이지에 있는 **이름** 필드에 가져온 데이터가 포함될 테이블을 설명하는 이름을 입력합니다.  
  
10. **미리 보기 및 필터** 를 클릭하여 데이터를 검토하고 열 선택을 변경합니다. 보고서 데이터 피드로 가져오는 행을 제한할 수는 없지만 해당 확인란의 선택을 취소하여 열을 제거할 수 있습니다. **확인**을 클릭합니다.  
  
11. **테이블 및 뷰 선택** 페이지에서 **마침**을 클릭합니다.  
  
##  <a name="importdata"></a> 공용 또는 회사 데이터 원본에서 데이터 피드 가져오기  
 공용 피드에 액세스하거나, 소유 또는 레거시 데이터베이스 시스템에서 ATOM 피드를 생성하는 사용자 지정 데이터 서비스를 작성할 수 있습니다.  
  
#### <a name="to-import-data-from-public-or-corporate-data-feeds"></a>공용 또는 회사 데이터 피드에서 데이터를 가져오려면  
  
1.  [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]에서 **모델** 메뉴를 클릭한 다음 **데이터 원본에서 가져오기**를 클릭합니다. 테이블 가져오기 마법사가 열립니다.  
  
2.  **데이터 원본에 연결** 페이지의 **데이터 피드**에서 **다른 피드**를 선택하고 **다음**을 클릭합니다.  
  
3.  **데이터 피드에 연결** 페이지에서 액세스하는 피드를 설명하는 이름을 입력합니다. 피드 또는 데이터 원본을 여러 개 가져오는 경우 연결을 설명하는 이름을 사용하면 연결이 사용되는 방식을 기억하는 데 도움이 됩니다.  
  
4.  **데이터 피드 URL**에 데이터 피드의 주소를 입력합니다. 유효한 값은 다음과 같습니다.  
  
    1.  ATOM 데이터가 포함된 XML 문서. 예를 들어 다음 URL은 Open Government Data Initiative 웹 사이트의 공용 피드를 가리킵니다.  
  
        ```  
        http://ogdi.cloudapp.net/v1/dc/banklocations/  
        ```  
  
    2.  하나 이상의 피드를 지정하는 .atomsvc 문서. .atomsvc 문서는 하나 이상의 피드를 제공하는 서비스 또는 애플리케이션을 가리킵니다. 각 피드는 결과 집합을 반환하는 기본 쿼리로 지정됩니다.  
  
         웹 서버에 있는 .atomsvc 문서의 URL 주소를 지정하거나 컴퓨터의 공유 또는 로컬 폴더에서 파일을 열 수 있습니다. Reporting Services 보고서를 내보내는 동안 컴퓨터에 .atomsvc 문서를 저장한 경우 해당 문서가 있거나, 다른 사용자가 SharePoint 사이트에 대해 만든 .atomsvc 문서가 데이터 피드 라이브러리에 있을 수도 있습니다.  
  
        > [!NOTE]  
        >  URL 주소나 공유 폴더를 통해 액세스할 수 있는 .atomsvc 문서를 지정하는 것이 좋습니다. 그러면 통합 문서가 SharePoint에 게시된 후 나중에 통합 문서에 대해 데이터 자동 새로 고침을 구성할 수 있습니다. 컴퓨터의 로컬 위치가 아닌 위치를 지정하면 서버에서 동일한 URL 주소나 네트워크 폴더를 다시 사용하여 데이터를 새로 고칠 수 있습니다.  
  
5.  **연결 테스트** 를 클릭하여 피드를 사용할 수 있는지 확인합니다. 또는 **고급** 을 클릭하여 기본 URL이나 서비스 문서 URL에 피드를 제공하는 쿼리 또는 서비스 문서가 포함되어 있는지 확인할 수도 있습니다.  
  
6.  **다음** 을 클릭하여 가져오기 작업을 계속합니다.  
  
7.  **가장 정보** 페이지에서 데이터를 새로 고칠 때 Analysis Services가 데이터 원본에 연결하는 데 사용할 자격 증명을 지정하고 **다음**을 클릭합니다.  
  
8.  마법사의 **테이블 및 뷰 선택** 페이지에 있는 **이름** 필드에서 데이터 피드 내용을 가져온 데이터가 포함될 테이블을 설명하는 이름으로 바꿉니다.  
  
9. **미리 보기 및 필터** 를 클릭하여 데이터를 검토하고 열 선택을 변경합니다. 보고서 데이터 피드로 가져오는 행을 제한할 수는 없지만 해당 확인란의 선택을 취소하여 열을 제거할 수 있습니다. **확인**을 클릭합니다.  
  
10. **테이블 및 뷰 선택** 페이지에서 **마침**을 클릭합니다.  
  
##  <a name="importlist"></a> SharePoint 목록에서 데이터 피드 가져오기  
 (SharePoint) 리본에 **데이터 피드로 내보내기** 단추가 있는 모든 SharePoint 목록을 가져올 수 있습니다. 이 단추를 클릭하여 목록을 피드로 내보낼 수 있습니다.  
  
#### <a name="to-import-data-feeds-from-a-sharepoint-list"></a>SharePoint 목록에서 데이터 피드를 가져오려면  
  
1.  [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]에서 **모델** 메뉴를 클릭한 다음 **데이터 원본에서 가져오기**를 클릭합니다.  
  
2.  **데이터 원본에 연결** 페이지의 **데이터 피드**에서 **다른 데이터 피드**를 선택하고 **다음**을 클릭합니다.  
  
3.  **데이터 피드에 연결** 페이지에서 액세스하는 피드를 설명하는 이름을 입력합니다. 피드 또는 데이터 원본을 여러 개 가져오는 경우 연결을 설명하는 이름을 사용하면 연결이 사용되는 방식을 기억하는 데 도움이 됩니다.  
  
4.  데이터 피드 URL에 목록 데이터 서비스 주소를 입력 합니다. 대체 \<서버 이름 > SharePoint 서버의 실제 이름으로:  
  
    ```  
    http://<server-name>/_vti_bin/listdata.svc  
    ```  
  
5.  **연결 테스트** 를 클릭하여 피드를 사용할 수 있는지 확인합니다. 또는 **고급** 을 클릭하여 서비스 문서 URL에 목록 데이터 서비스의 주소가 포함되어 있는지 확인할 수도 있습니다.  
  
6.  **다음** 을 클릭하여 가져오기 작업을 계속합니다.  
  
7.  **가장 정보** 페이지에서 데이터를 새로 고칠 때 Analysis Services가 데이터 원본에 연결하는 데 사용할 자격 증명을 지정하고 **다음**을 클릭합니다.  
  
8.  마법사의 **테이블 및 뷰 선택** 페이지에서 가져올 목록을 선택합니다.  
  
    > [!NOTE]  
    >  열이 포함된 목록만 가져올 수 있습니다.  
  
9. **미리 보기 및 필터** 를 클릭하여 데이터를 검토하고 열 선택을 변경합니다. 보고서 데이터 피드로 가져오는 행을 제한할 수는 없지만 해당 확인란의 선택을 취소하여 열을 제거할 수 있습니다. **확인**을 클릭합니다.  
  
10. **테이블 및 뷰 선택** 페이지에서 **마침**을 클릭합니다.  
  
##  <a name="importreport"></a> Reporting Services 보고서에서 데이터 피드 가져오기  
 [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] Reporting Services가 배포되어 있는 경우 Atom 렌더링 확장 프로그램을 사용하여 기존 보고서에서 데이터 피드를 생성할 수 있습니다.  
  
#### <a name="to-import-report-data-from-a-published-reporting-services-report"></a>게시된 Reporting Services 보고서에서 보고서 데이터를 가져오려면  
  
1.  [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]에서 **모델** 메뉴를 클릭한 다음 **데이터 원본에서 가져오기**를 클릭합니다.  
  
2.  **데이터 원본에 연결** 페이지의 **데이터 피드**에서 **보고서**를 선택하고 **다음**을 클릭합니다.  
  
3.  Microsoft SQL Server Reporting Services 보고서에 연결 페이지의 연결 이름에 액세스하는 피드를 설명하는 이름을 입력합니다. 데이터 원본을 여러 개 가져오는 경우 연결을 설명하는 이름을 사용하면 연결이 사용되는 방식을 기억하는 데 도움이 됩니다.  
  
4.  **찾아보기** 를 클릭하고 보고서 서버를 선택합니다.  
  
     보고서 서버에서 보고서를 정기적으로 사용하는 경우 해당 서버가 **최근에 사용한 사이트 및 서버**에 나열되어 있을 수 있습니다. 그렇지 않으면 이름에 보고서 서버의 주소를 입력하고 **열기** 를 클릭하여 보고서 서버 사이트에서 폴더를 찾습니다. 보고서 서버에 대 한 주소는 http:// 않을\<컴퓨터 이름 > / reportserver입니다.  
  
5.  보고서를 선택하고 **열기**를 클릭합니다. 또는 **이름** 입력란에 전체 경로와 보고서 이름을 포함하여 보고서 링크를 붙여 넣을 수 있습니다. 테이블 가져오기 마법사를 통해 보고서에 연결되고 미리 보기 영역에서 보고서가 렌더링됩니다.  
  
     보고서에서 매개 변수를 사용하는 경우 매개 변수를 지정해야 하며, 그렇지 않으면 보고서 연결을 만들 수 없습니다. 이렇게 하면 매개 변수 값과 관련된 행만 데이터 피드로 가져옵니다.  
  
    1.  보고서에 제공된 목록 상자나 콤보 상자를 사용하여 매개 변수를 선택합니다.  
  
    2.  **보고서 보기** 를 클릭하여 데이터를 업데이트합니다.  
  
        > [!NOTE]  
        >  보고서를 보면 선택한 매개 변수가 데이터 피드 정의와 함께 저장됩니다.  
  
     필요에 따라 **고급** 을 클릭하여 보고서의 공급자별 속성을 설정합니다.  
  
6.  **연결 테스트** 를 클릭하여 보고서를 데이터 피드로 사용할 수 있는지 확인합니다. 또는 **고급** 을 클릭하여 데이터 피드 연결을 지정하는 포함 XML이 **인라인 서비스 문서** 속성에 들어 있는지 확인할 수도 있습니다.  
  
7.  **다음** 을 클릭하여 가져오기 작업을 계속합니다.  
  
8.  **가장 정보** 페이지에서 데이터를 새로 고칠 때 Analysis Services가 데이터 원본에 연결하는 데 사용할 자격 증명을 지정하고 **다음**을 클릭합니다.  
  
9. 마법사의 **테이블 및 뷰 선택** 페이지에서 데이터로 가져올 보고서 파트 옆의 확인란을 선택합니다.  
  
     일부 보고서에는 테이블, 목록 또는 그래프를 비롯한 여러 파트가 포함될 수 있습니다.  
  
10. **이름** 상자에 모델에서 데이터 피드를 저장할 테이블의 이름을 입력합니다.  
  
     이름을 할당하지 않은 경우 Reporting Services 컨트롤의 이름(예: Tablix1, Tablix2)이 기본적으로 사용됩니다. 가져온 데이터 피드의 원본을 보다 쉽게 식별할 수 있도록 가져올 때 이 이름을 변경하는 것이 좋습니다.  
  
11. **미리 보기 및 필터** 를 클릭하여 데이터를 검토하고 열 선택을 변경합니다. 보고서 데이터 피드로 가져오는 행을 제한할 수는 없지만 해당 확인란의 선택을 취소하여 열을 제거할 수 있습니다. **확인**을 클릭합니다.  
  
12. **테이블 및 뷰 선택** 페이지에서 **마침**을 클릭합니다.  
  
## <a name="see-also"></a>관련 항목  
 [지원 되는 데이터 원본 &#40;&AMP;#40;SSAS 테이블 형식&#41;](tabular-models/data-sources-supported-ssas-tabular.md)   
 [지원 되는 데이터 형식 &#40;&AMP;#40;SSAS 테이블 형식&#41;](tabular-models/data-types-supported-ssas-tabular.md)   
 [가장 &#40;&AMP;#40;SSAS 테이블 형식&#41;](tabular-models/impersonation-ssas-tabular.md)   
 [데이터 처리 &#40;&AMP;#40;SSAS 테이블 형식&#41;](process-data-ssas-tabular.md)   
 [데이터 가져오기 &#40;&AMP;#40;SSAS 테이블 형식&#41;](import-data-ssas-tabular.md)  
  
  
