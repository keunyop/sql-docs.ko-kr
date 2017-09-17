---
title: "Oracle에 대 한 ODBC 드라이버 구성 | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring ODBC driver for Oracle [ODBC]
- ODBC driver for Oracle [ODBC], configuring
ms.assetid: 0a5f827c-0b80-4627-85cb-f10292b9fb33
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 64e6dfe9f31eb983170f08e9fcd3e0705ba9ae62
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="configuring-the-odbc-driver-for-oracle"></a>Oracle에 대 한 ODBC 드라이버 구성
> [!IMPORTANT]  
>  이 기능은 나중 버전의 Windows에서 제거 됩니다. 새 개발 작업에서는 이 기능을 사용하지 않도록 하고, 현재 이 기능을 사용하는 응용 프로그램은 수정하세요. Oracle에서 제공 하는 ODBC 드라이버를 사용 하십시오.  
  
 Oracle에 대 한 ODBC 드라이버의 성능 데이터 환경 알면 올바르게를 통해 데이터 원본 연결의 매개 변수를 설정 하 여 제어할 수 있습니다는 [ODBC 데이터 원본 관리자](../../odbc/admin/odbc-data-source-administrator.md) 대화 상자 또는 연결 문자열 매개 변수입니다. 대화 상자에서는 대화 상자를 사용 하 여 데이터 원본에 연결 하기 위한 다음과 같은 컨트롤을 제공 하거나 문자열을 사용 하 여 연결 합니다.  
  
-   **사용자 DSN 탭** 로컬 컴퓨터에 있는 데이터 원본 이름을 나열 합니다.  
  
-   **시스템 DSN 탭** 추가 또는 시스템 데이터 소스를 제거할 수 있습니다. 시스템 데이터 원본은 로컬 컴퓨터의 모든 사용자가 액세스할 수 있습니다.  
  
-   **파일 DSN 탭** 추가 하거나 로컬 컴퓨터에서 파일 데이터 소스를 제거할 수 있습니다. 파일 데이터 원본은 동일한 드라이버가 설치 되어 있는 모든 사용자가 공유할 수 있습니다.  
  
-   **드라이버 탭** 설치 된 ODBC 드라이버를 나열 합니다.  
  
-   **추적 탭** ODBC 드라이버 관리자 ODBC 함수 호출을 추적 하는 방법을 지정할 수 있습니다. 별도로 설치 된 각 ODBC 응용 프로그램에 대 한 추적을 구성할 수 있습니다.  
  
-   **연결 풀링은 탭** 설치 된 각 드라이버에 대 한 연결 옵션을 선택할 수 있습니다.  
  
-   **탭에 대 한** 설치 된 ODBC 구성 요소 파일을 나열 합니다.  
  
 데이터 소스를 추가한 후 사용할 수 있습니다는 **ODBC 데이터 원본 관리자** 대화 상자를 데이터 원본에 대 한 액세스를 구성할 수 있습니다. 데이터 소스를 선택 하 고 편집 하거나 정보를 검토 하는 탭 중 하나를 클릭 합니다.