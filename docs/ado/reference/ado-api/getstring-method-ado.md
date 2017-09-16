---
title: "GetString 메서드 (ADO) | Microsoft Docs"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- Recordset20::raw_GetString
- Recordset20::GetString
helpviewer_keywords:
- GetString method [ADO]
ms.assetid: 92452940-b2a7-456e-94fc-3780c71da33c
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: d146c1cdd2ebb4f069afef7163ce998cbb149ef6
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="getstring-method-ado"></a>GetString 메서드 (ADO)
반환 된 [레코드 집합](../../../ado/reference/ado-api/recordset-object-ado.md) 문자열입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Variant = recordset.GetString(StringFormat, NumRows, ColumnDelimiter, RowDelimiter, NullExpr)  
```  
  
## <a name="return-value"></a>반환 값  
 반환 된 **레코드 집합** 문자열 값으로 **Variant** (BSTR).  
  
#### <a name="parameters"></a>매개 변수  
 *StringFormat*  
 A [StringFormatEnum](../../../ado/reference/ado-api/stringformatenum.md) 값을 지정 하는 방법을 **레코드 집합** 문자열로 변환 해야 합니다. *RowDelimiter*, *ColumnDelimiter*, 및 *NullExpr* 매개 변수 에서만 사용 되는 *StringFormat* 의 ** adClipString**합니다.  
  
 *NumRows*  
 (선택 사항) 식을 변환할 수는 행 개수는 **레코드 집합**합니다. 경우 *NumRows* 를 지정 하지 않으면에 있는 행의 총 개수 보다 큰 경우 또는 **레코드 집합**, 다음의 모든 행은 **레코드 집합** 변환 됩니다.  
  
 *ColumnDelimiter*  
 (선택 사항) 그렇지 않으면 탭 문자를 지정 하는 경우 열 간에 사용 되는 구분 기호입니다.  
  
 *RowDelimiter*  
 (선택 사항) 행을 캐리지 리턴 문자를 다르게 지정 하는 경우 간에 사용 되는 구분 기호입니다.  
  
 *NullExpr*  
 (선택 사항) 그렇지 않으면 빈 문자열을 지정 하는 경우 null 값을 대신 사용 하는 식입니다.  
  
## <a name="remarks"></a>주의  
 스키마 데이터가 아니라 행 데이터를 문자열에 저장 됩니다. 따라서 한 **레코드 집합** 이 문자열을 사용 하 여 다시 열 수 없습니다.  
  
 이 메서드는 해당 하는 RDO **GetClipString** 메서드.  
  
## <a name="applies-to"></a>적용 대상  
 [레코드 집합 개체(ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>관련 항목:  
 [GetString 메서드 예제(VB)](../../../ado/reference/ado-api/getstring-method-example-vb.md)