---
title: "설명자 레코드 바인딩된 | Microsoft Docs"
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
- bound descriptor records [ODBC]
- descriptors [ODBC], bound descriptor records
ms.assetid: 55d09344-6682-40f6-b634-036b134ff650
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: d1ecc435a6b62d75527292ab8dc098e8cb121627
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="bound-descriptor-records"></a>바인딩된 설명자 레코드
Null 값을 더 이상 포함 되도록 한 설명자 레코드의 SQL_DESC_DATA_PTR 필드가 설정 하는 응용 프로그램, 레코드 수를 라고 *바인딩된*합니다.  
  
 설명자는 APD 이면 바인딩된 각 레코드는 바인딩된 매개 변수를 구성 합니다. 입력된 매개 변수에 대 한 응용 프로그램에서 문을 실행 하기 전에 SQL 문을 각 동적 매개 변수 표식에 대 한 매개 변수를 바인딩해야 합니다. 출력 매개 변수에 대 한 응용 프로그램 매개 변수를 바인딩하지 필요 합니다.  
  
 설명자가는 카드가 데이터베이스 데이터의 행을 설명 하는 경우 바인딩된 각 레코드는 바인딩된 열을 구성 합니다.