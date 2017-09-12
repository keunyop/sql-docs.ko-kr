---
title: SET DATEFORMAT (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DATEFORMAT
- SET DATEFORMAT
- SET_DATEFORMAT_TSQL
- DATEFORMAT_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- dates [SQL Server], formats
- dates [SQL Server], ordering date parts
- SET DATEFORMAT option [SQL Server]
- DATEFORMAT option [SQL Server]
- date and time [SQL Server], SET DATEFORMAT
- options [SQL Server], date
- date and time [SQL Server], DATEFORMAT
- dateparts [SQL Server], dateformat
ms.assetid: da217878-7ec4-477e-aa13-604073c948f8
caps.latest.revision: 49
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: eba2bdb31a805c61b92a88ce5699c05dfa7fe09f
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="set-dateformat-transact-sql"></a>SET DATEFORMAT(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  이해를 돕기 위해 월, 일 및 연도 날짜 부분의 순서를 설정 **날짜**, **smalldatetime**, **datetime**, **datetime2** 및 **datetimeoffset** 문자열입니다.  
  
 모든 개요 [!INCLUDE[tsql](../../includes/tsql-md.md)] 날짜 및 시간 데이터 형식 및 함수, 참조 [날짜 및 시간 데이터 형식 및 함수 &#40; Transact SQL &#41; ](../../t-sql/functions/date-and-time-data-types-and-functions-transact-sql.md).  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
SET DATEFORMAT { format | @format_var }   
```  
  
## <a name="arguments"></a>인수  
 *형식* | **@***format_var*  
 날짜 부분의 순서입니다. 유효한 매개 변수는 **mdy**, **dmy**, **ymd**, **ydm**, **myd**, 및 **dym**. 유니코드나 유니코드로 변환된 DBCS(더블바이트 문자 집합) 중 하나가 될 수 있습니다. 미국 영어 기본값은 **mdy**합니다. 모든 기본 DATEFORMAT에 대 한 언어 지원, 참조 [sp_helplanguage &#40; Transact SQL &#41; ](../../relational-databases/system-stored-procedures/sp-helplanguage-transact-sql.md).  
  
## <a name="remarks"></a>주의  
 DATEFORMAT **ydm** 에 지원 되지 않습니다 **날짜**, **datetime2** 및 **datetimeoffset** 데이터 형식입니다.  
  
 문자열의 해석에 DATEFORMAT 설정의 효과 다를 수 있습니다 **datetime** 및 **smalldatetime** 에 대 한 값 보다 **날짜**, **datetime2** 및 **datetimeoffset** 문자열 형식에 따라 값입니다. 이 설정은 문자열이 데이터베이스 저장을 위해 날짜 값으로 변환될 때 문자열의 해석에 영향을 미칩니다. 데이터베이스에 저장되는 날짜 데이터 형식의 값 표시 및 저장소 형식에는 영향을 주지 않습니다.  
  
 ISO 8601과 같은 일부 문자열 형식의 경우 DATEFORMAT 설정과 관계없이 해석됩니다.  
  
 SET DATEFORMAT 옵션은 실행 시간 또는 런타임에 설정되며, 구문 분석 시에는 설정되지 않습니다.  
  
 SET DATEFORMAT 재정의 암시적 날짜 형식 설정의 [SET LANGUAGE](../../t-sql/statements/set-language-transact-sql.md)합니다.  
  
## <a name="permissions"></a>Permissions  
 **public** 역할의 멤버 자격이 필요합니다.  
  
## <a name="examples"></a>예  
 다음 예제에서는 입력으로 동일한 세션에서 서로 다른 날짜 문자열을 사용 `DATEFORMAT` 설정 합니다.  
  
```  
-- Set date format to day/month/year.  
SET DATEFORMAT dmy;  
GO  
DECLARE @datevar datetime2 = '31/12/2008 09:01:01.1234567';  
SELECT @datevar;  
GO  
-- Result: 2008-12-31 09:01:01.123  
SET DATEFORMAT dmy;  
GO  
DECLARE @datevar datetime2 = '12/31/2008 09:01:01.1234567';  
SELECT @datevar;  
GO  
-- Result: Msg 241: Conversion failed when converting date and/or time -- from character string.  
  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>예: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] 및[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
```  
-- Set date format to month/day/year.  
SET DATEFORMAT mdy;  
DECLARE @datevar datetime2 = '12/31/2012 09:01:01.1234567';  
SELECT @datevar;  
  
```  
  
## <a name="see-also"></a>관련 항목:  
 [SET 문&#40;Transact-SQL&#41;](../../t-sql/statements/set-statements-transact-sql.md)  
  
  

