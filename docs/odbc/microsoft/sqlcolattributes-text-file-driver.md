---
title: "SQLColAttributes (텍스트 파일 드라이버) | Microsoft Docs"
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
- text file driver [ODBC], SQLColAttributes
- SQLColAttribute function [ODBC], Text File Driver
ms.assetid: 132fd1c0-1921-4a7d-910e-aedf1bff5453
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 811ccdff731e006d1ee112674b47531573778354
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="sqlcolattributes-text-file-driver"></a>SQLColAttributes (텍스트 파일 드라이버)
> [!NOTE]  
>  이 항목에서는 텍스트 파일 드라이버 관련 정보를 제공 합니다. 이 함수에 대 한 일반 정보에서 해당 항목을 참조 하십시오. [ODBC API 참조](../../odbc/reference/syntax/odbc-api-reference.md)합니다.  
  
|Attribute|설명|  
|---------------|--------------|  
|SQL_COLUMN_DISPLAY_SIZE|LONGVARBINARY 데이터 SQL_COLUMN_DISPLAY_SIZE 하지 2 시간 열의 최대 길이 열의 최대 길이입니다.|  
|SQL_OWNER_NAME|빈 문자열 ("") 소유자 이름입니다. 지원 되지 않으므로이 열에 반환 합니다.|  
|SQL_QUALIFIER_NAME|디렉터리 경로가 반환 됩니다.|  
|SQL_COLUMN_SEARCHABLE|LONGVARCHAR 및 LONGVARBINARY 열 SQL_UNSEARCHABLE로 보고 됩니다.<br /><br /> 고정 길이 및 가변 길이 이진 및 문자 데이터 형식 LONGVARCHAR 및 LONGVARBINARY 없는 있지만 검색할 수 있는는.|