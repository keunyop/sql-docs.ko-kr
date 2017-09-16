---
title: "C: GUID로 SQL | Microsoft Docs"
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
- converting data from SQL to C types [ODBC], GUID
- data conversions from SQL to C types [ODBC], guid
- GUID data type [ODBC]
ms.assetid: cf56c684-c261-4b89-994a-db14ab2241d6
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 0d60ca76d44f443c564bd354535833ab6c7b407f
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="sql-to-c-guid"></a>C: GUID로 SQL
다음은 GUID ODBC SQL 데이터 형식에 대 한 식별자가입니다.  
  
 SQL_GUID  
  
 다음 표에서 ODBC C 데이터 형식에 GUID SQL 데이터를 변환 될 수 있습니다를 보여 줍니다. 참조에 대 한 열과 테이블의 용어 설명은 [SQL에서 C 데이터 형식 변환 데이터](../../../odbc/reference/appendixes/converting-data-from-sql-to-c-data-types.md)합니다.  
  
|C 형식 식별자|테스트|**TargetValuePtr*|**StrLen_or_IndPtr*|SQLSTATE|  
|-----------------------|----------|------------------------|----------------------------|--------------|  
|SQL_C_CHAR|*BufferLength* > 문자 바이트 길이|data|36|n/a|  
||*BufferLength* < 37|정의되지 않음|정의되지 않음|22003|  
|SQL_C_WCHAR|*BufferLength* > 문자 길이|data|36|n/a|  
||*BufferLength* < 37|정의되지 않음|정의되지 않음|22003|  
|SQL_C_BINARY|데이터의 바이트 길이 \< =  *BufferLength*|data|데이터의 바이트 길이|n/a|  
||데이터의 바이트 길이 > *BufferLength*|정의되지 않음|정의되지 않음|22003|  
|SQL_C_GUID|[A] 없음|data|16 [b]|n/a|  
  
 [a]의 값 *BufferLength* 이 변환에 대해 무시 됩니다. 드라이버를 가정 하는 크기 **TargetValuePtr* C 데이터 형식 크기입니다.  
  
 [b] C 데이터 형식에 해당 크기입니다.
