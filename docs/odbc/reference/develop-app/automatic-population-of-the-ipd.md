---
title: "IPD의 자동 채우기를 | Microsoft Docs"
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
- automatically populating ipd [ODBC]
- descriptors [ODBC], automatically populating ipd
- descriptors [ODBC], allocating and freeing
- ipd [ODBC]
- allocating and freeing descriptors [ODBC]
ms.assetid: 1184a7d8-d557-4140-843b-6633ae6deacc
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: d637ddfebc0563ed2591740498d519f91e34321e
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="automatic-population-of-the-ipd"></a>IPD의 자동 채우기
일부 드라이버 매개 변수가 있는 쿼리를 준비한 후은 IPD 필드를 설정할 수 있습니다. 설명자 필드 데이터 형식, 정밀도, 배율, 및 기타 특성을 포함 하 여 매개 변수에 대 한 정보로 자동으로 채워집니다. 지 원하는 동일 **SQLDescribeParam**합니다. 이 정보를 응용 프로그램에 대해 알지 못하는 하는 매개 변수는 임시 쿼리 수행 될 때와 같은 검색할 수 있는 다른 방법이 때 응용 프로그램에 특히 유용 수 있습니다.  
  
 응용 프로그램이 드라이버를 호출 하 여 자동 채우기를 지원 하는지 여부를 확인 **SQLGetConnectAttr** 와 *특성* SQL_ATTR_AUTO_IPD입니다. SQL_TRUE 반환 되 면 드라이버에서 지 원하는 및 응용 프로그램 SQL_ATTR_ENABLE_AUTO_IPD 문 특성 SQL_TRUE로 설정 하 여 설정할 수 있습니다.  
  
 매개 변수 표식이 포함 하는 SQL 문을 호출 하 여 준비 된 후 드라이버는 IPD의 필드를 채웁니다 자동 채우기를 지원 하 고 사용 **SQLPrepare**합니다. 응용 프로그램 호출 하 여이 정보를 검색할 수 **SQLGetDescField** 또는 **SQLGetDescRec**, 또는 **SQLDescribeParam**합니다. 매개 변수에 대해 가장 적합 한 응용 프로그램 버퍼를 바인딩할 또는 데이터 변환에 대 한 지정 하려면 응용 프로그램 정보를 사용할 수 있습니다.  
  
 IPD의 자동 채우기를 성능 저하를 발생할 수 있습니다. 응용 프로그램 해제할 수 (기본값) SQL_FALSE를 SQL_ATTR_ENABLE_AUTO_IPD 문 특성을 설정 하 여 합니다.