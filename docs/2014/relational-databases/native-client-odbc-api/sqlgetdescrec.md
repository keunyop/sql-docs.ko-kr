---
title: SQLGetDescRec | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLGetDescRec function
ms.assetid: f3389ff2-f3be-4035-9fb5-c9ebc2f15025
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 41bd489752dc1b4084d9c012cad97413c6ff98b5
ms.sourcegitcommit: 334cae1925fa5ac6c140e0b2c38c844c477e3ffb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/13/2018
ms.locfileid: "53368595"
---
# <a name="sqlgetdescrec"></a>SQLGetDescRec
  이 항목에서는 관련 된 SQLGetDescRec 기능 설명 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client입니다.  
  
## <a name="sqlgetdescrec-and-table-valued-parameters"></a>SQLGetDescRec 및 테이블 반환 매개 변수  
 SQLGetDescRec는 테이블 반환 매개 변수 및 테이블 반환 매개 변수 열의 특성에 대 한 값을 가져오는 데 사용할 수 있습니다. 합니다 *RecNumber* SQLGetDescRec 매개 변수에 해당 하는 *상태로* SQLBindParameter의 매개 변수입니다.  
  
 테이블 반환 매개 변수 열은 설명자 헤더 필드 SQL_SOPT_SS_PARAM_FOCUS가 SQL_DESC_TYPE이 SQL_SS_TABLE로 설정된 레코드의 서수로 설정된 경우에만 사용할 수 있습니다. SQL_SOPT_SS_PARAM_FOCUS에 대 한 자세한 내용은 참조 하세요. [SQLSetStmtAttr](sqlsetstmtattr.md)합니다.  
  
 SQLGetDescRec 다음 데이터를 반환합니다.  
  
|매개 변수|테이블 반환 매개 변수|테이블 반환 매개 변수 열 및 기타 매개 변수|  
|---------------|-----------------------------|----------------------------------------------------------|  
|*이름*|저장 프로시저 호출의 경우 형식 매개 변수 이름, 다른 경우 길이가 0인 문자열|테이블 반환 매개 변수 열 이름|  
|*TypePtr*|SQL_DESC_TYPE 테이블 반환 매개 변수의 경우 SQL_SS_TABLE|SQL_DESC_TYPE|  
|*SubTypePtr*|정의되지 않음|SQL_DESC_DATETIME_INTERVAL_CODE(형식이 SQL_DATETIME 또는 SQL_INTERVAL인 레코드의 경우)|  
|*LengthPtr*|0|SQL_DESC_OCTET_LENGTH|  
|*PrecisionPtr*|0|SQL_DESC_PRECISION|  
|*ScalePtr*|0|SQL_DESC_SCALE|  
|*NullablePtr*|1|SQL_DESC_NULLABLE|  
  
 테이블 반환 매개 변수에 대 한 자세한 내용은 참조 하세요. [테이블 반환 매개 변수 &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md)합니다.  
  
## <a name="sqlgetdescrec-support-for-enhanced-date-and-time-features"></a>향상된 날짜 및 시간 기능에 대한 SQLGetDescRec 지원  
 날짜/시간 형식에 대해 반환되는 값은 다음과 같습니다.  
  
||*TypePtr*|*SubTypePtr*|*LengthPtr*|*PrecisionPtr*|*ScalePtr*|  
|-|---------------|------------------|-----------------|--------------------|----------------|  
|DATETIME|SQL_DATETIME|SQL_CODE_TIMESTAMP|4|3|3|  
|smalldatetime|SQL_DATETIME|SQL_CODE_TIMESTAMP|8|0|0|  
|date|SQL_DATETIME|SQL_CODE_DATE|6|0|0|  
|Time|SQL_SS_TIME2|0|10|0..7|0..7|  
|Datetime2|SQL_DATETIME|SQL_CODE_TIMESTAMP|16|0..7|0..7|  
|datetimeoffset|SQL_SS_TIMESTAMPOFFSET|0|20|0..7|0..7|  
  
 자세한 내용은 [날짜 및 시간 기능 향상 &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md)합니다.  
  
## <a name="sqlgetdescrec-support-for-large-clr-udts"></a>큰 CLR UDT에 대한 SQLGetDescRec 지원  
 `SQLGetDescRec`는 큰 CLR UDT(사용자 정의 형식)를 지원합니다. 자세한 내용은 [Large CLR User-Defined 형식 &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md)합니다.  
  
## <a name="see-also"></a>관련 항목  
 [SQLGetDescRec](https://go.microsoft.com/fwlink/?LinkId=80707)   
 [ODBC API 구현 정보](odbc-api-implementation-details.md)  
  
  
