---
title: "진단 레코드 | Microsoft Docs"
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
- diagnostic information [ODBC], diagnostic records
- handles [ODBC], diagnostic records
- header records [ODBC]
- status records [ODBC]
- diagnostic records [ODBC]
ms.assetid: 92c73f9b-3ed7-410d-9cec-2771004aae60
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 598f047d1ae18e2c37587df270001b49d1b15831
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="diagnostic-records"></a>진단 레코드
환경에 연결 된 각, 연결, 문 및 설명자 핸들은 *진단 레코드*합니다. 이러한 레코드는 특정 핸들을 사용 하는 마지막 함수 호출에 대 한 진단 정보를 포함 합니다. 레코드는이 핸들을 사용 하 여 다른 함수를 호출할 경우에 대체 됩니다. 한 번에 저장할 수 있는 진단 레코드의 수 제한은 없습니다.  
  
 진단 레코드의 두 가지:는 *헤더 레코드* 및 0 개 이상의 *상태 레코드*합니다. 헤더 레코드는 레코드 0; 상태 레코드는 레코드 1 이상입니다. 진단 레코드는 여러 다른 헤더 레코드 및 상태 레코드에 대 한 별도 필드 구성 됩니다. 또한 ODBC 구성 요소 자체 진단 레코드 필드를 정의할 수 있습니다.  
  
 진단 레코드는 구조로 생각할 수 있습니다 하지만 실제로 구조; 수에 대 한 요구 사항은 없습니다. 드라이버 진단 정보를 저장 하는 방법을 드라이버 관련 됩니다.  
  
 진단 레코드의 필드를 통해 검색 됩니다 **SQLGetDiagField**합니다. SQLSTATE, 원시 오류 번호 및 상태 레코드의 진단 메시지 필드와 한 번의 호출에서 검색할 수 있는 **SQLGetDiagRec**합니다.  
  
 이 섹션에서는 다음 항목을 다룹니다.  
  
-   [헤더 레코드](../../../odbc/reference/develop-app/header-record.md)  
  
-   [상태 레코드](../../../odbc/reference/develop-app/status-records.md)