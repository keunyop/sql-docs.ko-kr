---
title: '태스크 1(필수): MDS에서 공급자 데이터 제거 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6f0a4287-7fd4-4f18-b7e4-a5191a9d4a3c
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 19e402f1b74f72ce962aaa95f5f48794ffb7c154
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56018125"
---
# <a name="task-1-prerequisite-removing-supplier-data-in-mds"></a>태스크 1(필수): MDS에서 공급자 데이터 제거
  이 작업에서는 MDS에 저장된 공급자 데이터를 제거합니다. 이전 단원에서는 **MDS Excel 추가 기능** 을 사용하여 데이터를 수동으로 업로드했습니다. 이 단원에서 만드는 SSIS 패키지는 데이터를 MDS에 자동으로 업로드합니다. 따라서 SSIS 패키지를 테스트하기 전에 MDS에서 공급자 데이터를 제거하고, 파생 계층을 제거하고, 공급자 및 상태 엔터티를 제거하고 포함된 데이터 없이 공급자 엔터티를 만들어야 합니다.  
  
1.  시작할 **마스터 데이터 관리자** 로 이동 하 여 **http://localhost/MDS** 또는 MDS를 구성할 때 지정한 응용 프로그램 및 웹 사이트입니다. **마스터 데이터 관리자** 가 열려 있으면 상단에서 **SQL Server 2012 Master Data Services** 를 클릭하여 **홈 페이지**로 전환합니다.  
  
2.  **관리 작업** 섹션에서 **시스템 관리** 를 클릭합니다.  
  
3.  메뉴의 **관리** 위로 마우스를 가져가고 **파생 계층**을 클릭합니다. **Suppliers** 모델에서 엔터티를 삭제하려면 먼저 **SuppliersInState** 파생 계층을 삭제해야 합니다.  
  
4.  **파생 계층** 목록에서 **SuppliersInState** 를 선택하고 도구 모음에서 **X(삭제)** 단추를 클릭합니다.  
  
5.  **확인** 을 클릭하여 삭제를 확인합니다.  
  
6.  메뉴에서 **관리** 위로 마우스를 가져가고 **엔터티**를 클릭합니다.  
  
7.  **Supplier** 를 클릭하고 도구 모음에서 **삭제(X)** 단추를 클릭하여 엔터티를 삭제합니다. 메시지 상자에서 **확인** 을 클릭합니다.  
  
8.  이전 단계를 반복하여 **State** 엔터티를 삭제합니다.  
  
9. 닫지 마세요 **마스터 데이터 관리자**합니다.  
  
10. **Cleansed and Matched Suppliers.xls** 파일이 열려 있는 Excel 창으로 전환합니다. 하단에서 **Sheet1** 탭으로 전환합니다.  
  
11. **첫 번째 머리글 행**만 선택합니다. 다른 행을 선택 하지 마십시오. Excel 열을 기반으로 엔터티를 만듭니다. 하지만 모든 데이터를 업로드 하지. 따라서 첫 번째 머리글 행만 선택합니다.  
  
12. 메뉴 모음에서 **마스터 데이터** 를 클릭합니다.  
  
13. 리본에서 **엔터티 만들기** 를 클릭합니다.  
  
14. **연결 관리** 대화 상자에서 **기존 연결** 아래에 **로컬 MDS 서버**에 대한 연결이 표시되지 않으면 다음을 수행합니다.  
  
    1.  **새 연결 만들기**를 선택하고 **새로 만들기** 단추를 클릭합니다.  
  
    2.  새 연결 추가 대화 상자에서 입력 **Local MDS Server** 에 대 한 **설명** 하 고 **http://localhost/MDS** 에 대 한 **MDS 서버 주소**, 클릭 **확인** 대화 상자를 닫습니다.  
  
15. **연결 관리** 대화 상자에서 **Local MDS Server** (http://localhost/MDS), 클릭 **테스트** 연결을 테스트 합니다. 메시지 상자에서 **확인** 을 클릭합니다.  
  
16. **연결** 을 클릭하여 MDS 서버에 대한 연결을 설정합니다.  
  
17. **엔터티 만들기** 대화 상자에서 다음 작업을 수행합니다.  
  
    1.  **범위** 가 **$1:$1**로 설정되었는지 확인합니다.  
  
    2.  **모델** 에 대해 **Suppliers**를 선택합니다.  
  
    3.  **버전** 에 대해 **VERSION_1**을 선택합니다.  
  
    4.  **새 엔터티 이름** 에 **Supplier**를 입력합니다.  
  
    5.  **코드** 에 대해 **SupplierID**를 선택합니다.  
  
    6.  **이름** 에 대해 **Supplier Name**을 선택합니다.  
  
    7.  **확인** 을 클릭하여 엔터티를 만들고 대화 상자를 닫습니다.  
  
18. **Excel** 을 닫고 파일을 **저장하지는 않습니다** .  
  
19. **마스터 데이터 관리자**에서 인터넷 브라우저를 새로 고치고 **Supplier** 엔터티가 목록에 표시되는지 확인합니다.  
  
20. 상단에서 **SQL Server 2012 Master Data Services** 를 클릭하여 **홈 페이지** 로 전환합니다.  
  
21. **모델** 에 대해 **Suppliers** 모델이 선택되었고 **버전** 으로 **VERSION_1**이 선택되었는지 확인합니다.  
  
22. **탐색기**를 클릭합니다. 모든 특성이 포함된 **Supplier** 엔터티가 **값 없음**으로 만들어졌는지 확인합니다.  
  
## <a name="next-step"></a>다음 단계  
 [작업 2 &#40;선택적&#41;: 마스터 데이터 관리자를 사용 하 여 MDS 구독 뷰 만들기](../../2014/tutorials/task-2-optional-creating-a-mds-subscription-view-using-master-data-manager.md)  
  
  
