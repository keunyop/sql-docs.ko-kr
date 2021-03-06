---
title: SQLColAttribute | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLColAttribute function
ms.assetid: a5387d9e-a243-4cfe-b786-7fad5842b1d6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 706d08eb3c140571460f4ebccb541ac24a71160a
ms.sourcegitcommit: 334cae1925fa5ac6c140e0b2c38c844c477e3ffb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/13/2018
ms.locfileid: "53361275"
---
# <a name="sqlcolattribute"></a>SQLColAttribute
  사용할 수 있습니다 `SQLColAttribute` 준비 되거나 실행 ODBC 문에 대 한 결과 집합 열의 특성을 검색 하려면. 호출 `SQLColAttribute` 에서 준비 된 문을 원인에 대 한 왕복 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]합니다. 합니다 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 드라이버는 문 실행을 호출 하므로의 일부로 결과 집합 열 데이터를 받는 `SQLColAttribute` 완료 되 면 **SQLExecute** 하거나 **SQLExecDirect** 않습니다 서버 왕복은 포함 되지 않습니다.  
  
> [!NOTE]  
>  일부 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 결과 집합에는 ODBC 열 식별자 특성을 사용할 수 없습니다.  
  
|필드 식별자|Description|  
|----------------------|-----------------|  
|SQL_COLUMN_TABLE_NAME|서버 커서를 생성하는 문에서 검색된 결과 집합 또는 FOR BROWSE 절을 포함하는 실행된 SELECT 문에서 사용할 수 있습니다.|  
|SQL_DESC_BASE_COLUMN_NAME|서버 커서를 생성하는 문에서 검색된 결과 집합 또는 FOR BROWSE 절을 포함하는 실행된 SELECT 문에서 사용할 수 있습니다.|  
|SQL_DESC_BASE_TABLE_NAME|서버 커서를 생성하는 문에서 검색된 결과 집합 또는 FOR BROWSE 절을 포함하는 실행된 SELECT 문에서 사용할 수 있습니다.|  
|SQL_DESC_CATALOG_NAME|데이터베이스 이름입니다. 서버 커서를 생성하는 문에서 검색된 결과 집합 또는 FOR BROWSE 절을 포함하는 실행된 SELECT 문에서 사용할 수 있습니다.|  
|SQL_DESC_LABEL|모든 결과 집합에서 사용할 수 있습니다. 값은 SQL_DESC_NAME 필드의 값과 동일합니다.<br /><br /> 열이 레이블 할당이 포함되지 않은 식의 결과이면 필드 길이가 0입니다.|  
|SQL_DESC_NAME|모든 결과 집합에서 사용할 수 있습니다. 값은 SQL_DESC_LABEL 필드의 값과 동일합니다.<br /><br /> 열이 레이블 할당이 포함되지 않은 식의 결과이면 필드 길이가 0입니다.|  
|SQL_DESC_SCHEMA_NAME|소유자 이름입니다. 서버 커서를 생성하는 문에서 검색된 결과 집합 또는 FOR BROWSE 절을 포함하는 실행된 SELECT 문에서 사용할 수 있습니다.<br /><br /> SELECT 문에서 열에 대해 소유자 이름이 지정된 경우에만 사용할 수 있습니다.|  
|SQL_DESC_TABLE_NAME|서버 커서를 생성하는 문에서 검색된 결과 집합 또는 FOR BROWSE 절을 포함하는 실행된 SELECT 문에서 사용할 수 있습니다.|  
|SQL_DESC_UNNAMED|열이 레이블 할당이 포함되지 않은 식의 결과인 경우를 제외하고는 결과 집합의 모든 열에 대해 SQL_NAMED입니다. SQL_DESC_UNNAMED가 SQL_UNNAMED를 반환하면 모든 ODBC 열 식별자 특성이 열에 대해 길이가 0인 문자열을 포함함을 나타냅니다.|  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 드라이버는 SET FMTONLY 문을 사용 하 여 서버 오버 헤드를 줄일 때 `SQLColAttribute` 되었지만 실행 되지 않은 문 준비에 대해 호출 됩니다.  
  
 큰 값 형식에 대 한 `SQLColAttribute` 다음 값이 반환 됩니다.  
  
|필드 식별자|변경 내용 설명|  
|----------------------|---------------------------|  
|SQL_DESC_DISPLAY_SIZE|열의 데이터를 표시하는 데 필요한 최대 문자 수입니다. 큰 값 유형 열에 대해서는 SQL_SS_LENGTH_UNLIMITED 값을 반환합니다.|  
|SQL_DESC_LENGTH|결과 집합에 있는 열의 실제 길이를 반환합니다. 큰 값 유형 열에 대해서는 SQL_SS_LENGTH_UNLIMITED 값을 반환합니다.|  
|SQL_DESC_OCTET_LENGTH|큰 값 유형 열의 최대 길이를 반환합니다. 크기가 무제한임을 나타낼 때는 SQL_SS_LENGTH_UNLIMITED를 사용합니다.|  
|SQL_DESC_PRECISION|큰 값 유형 열에 대해 SQL_SS_LENGTH_UNLIMITED 값을 반환합니다.|  
|SQL_DESC_TYPE|큰 값 유형에 대해 SQL_VARCHAR, SQL_WVARCHAR 및 SQL_VARBINARY를 반환합니다.|  
|SQL_DESC_TYPE_NAME|큰 값 유형에 대해 "varchar", "varbinary", "nvarchar"를 반환합니다.|  
  
 버전에 관계없이, 준비된 SQL 문의 일괄 처리에서 여러 개의 결과 집합이 생성될 경우 첫 번째 결과 집합에 대해서만 열 특성이 보고됩니다.  
  
 다음 열 특성을 제공 하는 확장 된 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 드라이버. 합니다 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 드라이버에서 모든 값을 반환 합니다 *NumericAttrPtr* 매개 변수입니다. WORD 배열에 대한 포인터인 SQL_CA_SS_COMPUTE_BYLIST를 제외하고는 SDWORD(signed long) 값을 반환합니다.  
  
|필드 식별자|반환 값|  
|----------------------|--------------------|  
|SQL_CA_SS_COLUMN_HIDDEN*|참조된 열이 FOR BROWSE가 포함된 Transact-SQL SELECT 문을 지원하기 위해 생성된 숨겨진 기본 키의 일부인 경우 TRUE입니다.|  
|SQL_CA_SS_COLUMN_ID|현재 Transact-SQL SELECT 문 내 COMPUTE 절 결과 열의 서수 위치입니다.|  
|SQL_CA_SS_COLUMN_KEY*|참조된 열이 행 기본 키의 일부이고 Transact-SQL SELECT 문에 FOR BROWSE가 포함된 경우 TRUE입니다.|  
|SQL_CA_SS_COLUMN_OP|COMPUTE 절 열의 값에 대한 집계 연산자를 지정하는 정수입니다. 정수 값에 대한 정의는 sqlncli.h에 있습니다.|  
|SQL_CA_SS_COLUMN_ORDER|ODBC 또는 Transact-SQL SELECT 문의 ORDER BY 절 내 열의 서수 위치입니다.|  
|SQL_CA_SS_COLUMN_SIZE|열에서 검색된 데이터 값을 SQL_C_BINARY 변수에 바인딩하는 데 필요한 최대 길이(바이트)입니다.|  
|SQL_CA_SS_COLUMN_SSTYPE|SQL Server 열에 저장된 데이터의 네이티브 데이터 형식입니다. 형식 값에 대한 정의는 sqlncli.h에 있습니다.|  
|SQL_CA_SS_COLUMN_UTYPE|SQL Server 열의 사용자 정의 데이터 형식에 대한 기본 데이터 형식입니다. 형식 값에 대한 정의는 sqlncli.h에 있습니다.|  
|SQL_CA_SS_COLUMN_VARYLEN|열의 데이터 길이가 가변적인 경우 TRUE이고, 그렇지 않으면 FALSE입니다.|  
|SQL_CA_SS_COMPUTE_BYLIST|COMPUTE 절의 BY 구에 사용되는 열을 지정하는 WORD(unsigned short) 배열에 대한 포인터입니다. COMPUTE 절에 BY 구가 지정되어 있지 않으면 NULL 포인터를 반환합니다.<br /><br /> 배열의 첫 번째 요소는 BY 목록 열의 개수를 포함하고 나머지 요소는 열 서수입니다.|  
|SQL_CA_SS_COMPUTE_ID|*computeid* 현재 TRANSACT-SQL SELECT 문에 COMPUTE 절 결과 나타내는 행의 합니다.|  
|SQL_CA_SS_NUM_COMPUTES|현재 Transact-SQL SELECT 문에 지정된 COMPUTE 절의 수입니다.|  
|SQL_CA_SS_NUM_ORDERS|ODBC 또는 Transact-SQL SELECT 문의 ORDER BY 절에 지정된 열의 수입니다.|  
  
 \*   문 특성 SQL_SOPT_SS_HIDDEN_COLUMNS가 SQL_HC_ON로 설정 된 경우에 사용할 수 있습니다.  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] 각각 XML 스키마 컬렉션 이름, 스키마 이름 및 카탈로그 이름을 나타내는 추가 정보를 제공 하는 드라이버별 설명자 필드를 도입 합니다. 이러한 속성에는 영숫자가 아닌 문자가 포함된 경우 따옴표나 이스케이프 문자가 필요하지 않습니다. 다음 표에는 새로 도입된 설명자 필드가 나와 있습니다.  
  
|열 이름|형식|Description|  
|-----------------|----------|-----------------|  
|SQL_CA_SS_XML_SCHEMACOLLECTION_CATALOG_NAME|CharacterAttributePtr|XML 스키마 컬렉션 이름이 정의된 카탈로그의 이름입니다. 카탈로그 이름을 찾을 수 없는 경우 이 변수에는 빈 문자열이 포함됩니다.<br /><br /> 이 정보는 읽기/쓰기 필드인 IRD의 SQL_DESC_SS_XML_SCHEMACOLLECTION_CATALOG_NAME 레코드 필드에서 반환됩니다.|  
|SQL_CA_SS_XML_SCHEMACOLLECTION_SCHEMA_NAME|CharacterAttributePtr|XML 스키마 컬렉션 이름이 정의된 스키마의 이름입니다. 스키마 이름을 찾을 수 없는 경우 이 변수에는 빈 문자열이 포함됩니다.<br /><br /> 이 정보는 읽기/쓰기 필드인 IRD의 SQL_DESC_SS_XML_SCHEMACOLLECTION_SCHEMA_NAME 레코드 필드에서 반환됩니다.|  
|SQL_CA_SS_XML_SCHEMACOLLECTION_NAME|CharacterAttributePtr|XML 스키마 컬렉션의 이름입니다. 이름을 찾을 수 없는 경우 이 변수에는 빈 문자열이 포함됩니다.<br /><br /> 이 정보는 읽기/쓰기 필드인 IRD의 SQL_DESC_SS_XML_SCHEMACOLLECTION_NAME 레코드 필드에서 반환됩니다.|  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]에는 결과 집합의 UDT(사용자 정의 형식) 열 또는 저장 프로시저나 매개 변수가 있는 쿼리의 UDT 매개 변수에 대한 추가 정보를 제공하기 위한 새 드라이버 관련 설명자 필드도 도입되었습니다. 이러한 속성에는 영숫자가 아닌 문자가 포함된 경우 따옴표나 이스케이프 문자가 필요하지 않습니다. 다음 표에는 새로 도입된 설명자 필드가 나와 있습니다.  
  
|열 이름|형식|Description|  
|-----------------|----------|-----------------|  
|SQL_CA_SS_UDT_CATALOG_NAME|CharacterAttributePtr|UDT가 포함된 카탈로그의 이름입니다.|  
|SQL_CA_SS_UDT_SCHEMA_NAME|CharacterAttributePtr|UDT가 포함된 스키마의 이름입니다.|  
|SQL_CA_SS_UDT_TYPE_NAME|CharacterAttributePtr|UDT의 이름입니다.|  
|SQL_CA_SS_UDT_ASSEMBLY_TYPE_NAME|CharacterAttributePtr|UDT의 정규화된 어셈블리 이름입니다.|  
  
 기존 설명자 필드 식별자인 SQL_DESC_TYPE_NAME은 UDT의 이름을 나타내는 데 사용됩니다. UDT 형식 열에 대한 SQL_DESC_TYPE 필드는 SQL_SS_UDT입니다.  
  
## <a name="sqlcolattribute-support-for-enhanced-date-and-time-features"></a>향상된 날짜 및 시간 기능에 대한 SQLColAttribute 지원  
 날짜/시간 형식에 대 한 반환 값을 "정보 반환 IRD 필드에서" 섹션을 참조 하세요 [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md)합니다.  
  
 자세한 내용은 [날짜 및 시간 기능 향상 &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md)합니다.  
  
## <a name="sqlcolattribute-support-for-large-clr-udts"></a>큰 CLR UDT에 대한 SQLColAttribute 지원  
 `SQLColAttribute`는 큰 CLR UDT(사용자 정의 형식)를 지원합니다. 자세한 내용은 [Large CLR User-Defined 형식 &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md)합니다.  
  
## <a name="sqlcolattribute-support-for-sparse-columns"></a>스파스 열에 대한 SQLColAttribute 지원  
 SQLColAttribute 새 구현 행 IRD (설명자) 필드를 열 경우 확인 SQL_CA_SS_IS_COLUMN_SET을 쿼리하여를 `column_set` 열입니다.  
  
 자세한 내용은 [Sparse Columns Support &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md)합니다.  
  
## <a name="see-also"></a>관련 항목  
 [SQLColAttribute 함수](https://go.microsoft.com/fwlink/?LinkId=59334)   
 [ODBC API 구현 정보](odbc-api-implementation-details.md)   
 [SQLSetStmtAttr](sqlsetstmtattr.md)  
  
  
