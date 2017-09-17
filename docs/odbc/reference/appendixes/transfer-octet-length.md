---
title: "8 진수 길이 전송 | Microsoft Docs"
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
- transfer octet length of data types [ODBC]
- size of data types [ODBC]
- SQL data types [ODBC], column characteristics
- data types [ODBC], transfer octet length
ms.assetid: 9fdc9762-e203-4cff-9212-54f450bf18d9
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 763f6fdd2790de695e1e2307cbcac4e0ed3018ae
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="transfer-octet-length"></a>8 진수 길이 전송 합니다.
열의 전송 8 진수 길이의 기본 C 데이터 형식에 데이터를 전송할 때 응용 프로그램에 반환 된 바이트의 최대 수입니다. 문자 데이터에 대 한 전송 8 진수 길이 null 종결 문자에 대 한 공간이 포함 되지 않습니다. 열의 전송 8 진수 길이 보다 데이터 원본에 데이터를 저장 하는 데 필요한 바이트 수가 달라질 수 있습니다.  
  
 각 ODBC SQL 데이터 형식에 대해 정의 된 전송 8 진수 길이 다음 표에 표시 됩니다.  
  
|SQL 유형 식별자|길이|  
|-------------------------|------------|  
|모든 문자 형식 [a]|정의 된 또는 바이트의 열 (변수 형식)에 대 한 최대 길이입니다. SQL_DESC_OCTET_LENGTH 설명자 필드와 동일한 값입니다.|  
|SQL_DECIMAL<br />SQL_NUMERIC|문자 집합은 유니코드 경우이 번호를 두 번이 고 문자 집합은 ANSI 하는 경우이 데이터의 문자 표시를 보유 하는 데 필요한 바이트 수입니다. 데이터를 문자열로 반환 되 고 숫자, 기호, 및 소수점에 필요한 문자 때문에 이것이 자리 + 2, 최대 수입니다. 예를 들어 전송 길이의 NUMERIC(10,3)로 정의 된 열은 12입니다.|  
|SQL_TINYINT|1.|  
|SQL_SMALLINT|2|  
|SQL_INTEGER|4|  
|SQL_BIGINT|경우 기본적으로이 데이터 형식은 문자열로 반환 되기 때문에 문자 집합은 유니코드,이 번호를 두 번이 고 문자 집합은 ANSI 하는 경우이 데이터의 문자 표시를 보유 하는 데 필요한 바이트 수입니다. 문자 표현이 20 자의: 19 자리 숫자 및 기호를 서명 하는 경우 또는 20 자리 숫자로, 서명 되지 않은 경우에 대 한 합니다. 따라서 길이 20입니다.|  
|SQL_REAL|4|  
|SQL_FLOAT|8|  
|SQL_DOUBLE|8|  
|SQL_BIT|1.|  
|모든 이진 형식 [a]|변수 형식의 최대 문자 수 또는 고정된 유형에 대해 정의 된 유지 하는 데 필요한 바이트 수입니다.|  
|SQL_TYPE_DATE<br />SQL_TYPE_TIME|6 (SQL_DATE_STRUCT 또는 SQL_TIME_STRUCT 구조체의 크기).|  
|SQL_TYPE_TIMESTAMP|16 (SQL_TIMESTAMP_STRUCT 구조체의 크기).|  
|모든 interval 데이터 형식|34 (간격 구조체의 크기).|  
|SQL_GUID|16 (GUID 구조체의 크기).|  
  
 [a] 드라이버 변수 형식에 대 한 열 또는 매개 변수 길이 확인할 수 없습니다, SQL_NO_TOTAL을 반환 합니다.