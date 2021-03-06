---
title: Optimize 속성-동적 (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- Optimize property [ADO]
ms.assetid: a491c4ce-2b04-4c84-be83-3846bde8d16b
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d461d0fad834dfc3c3c6f22ec64cc4987eca6fa5
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47662281"
---
# <a name="optimize-property-dynamic-ado"></a>Optimize 속성-동적(ADO)
인덱스를 만들어야 하는지 여부를 지정 된 [필드](../../../ado/reference/ado-api/field-object.md)합니다.  
  
## <a name="settings-and-return-values"></a>설정 및 반환 값  
 설정 하거나 반환 된 **부울** 인덱스를 만들어야 하는지 여부를 나타내는 값입니다.  
  
## <a name="remarks"></a>Remarks  
 인덱스를 찾거나 값이 정렬 하는 작업의 성능을 향상 시킬 수 있습니다는 [레코드 집합](../../../ado/reference/ado-api/recordset-object-ado.md)합니다. 인덱스는 ADO; 내부 명시적으로 액세스 하거나 응용 프로그램에서 사용할 수 없습니다.  
  
 인덱스를 만들려면 필드를 설정 합니다 **최적화** 속성을 **True**합니다. 인덱스를 삭제 하려면이 속성을 설정 **False**합니다.  
  
 **최적화** 에 추가 하는 동적 속성을 [필드](../../../ado/reference/ado-api/field-object.md) 개체 [속성](../../../ado/reference/ado-api/properties-collection-ado.md) 컬렉션 때 합니다 [CursorLocation](../../../ado/reference/ado-api/cursorlocation-property-ado.md) 속성이**adUseClient**합니다.  
  
## <a name="usage"></a>사용법  
  
```  
Dim rs As New Recordset  
Dim fld As Field  
rs.CursorLocation = adUseClient      'Enable index creation  
rs.Fields.Append "Field1", adChar, 35, adFldIsNullable  
rs.Open  
Set fld = rs.Fields(0)  
fld.Properties("Optimize") = True    'Create an index  
fld.Properties("Optimize") = False   'Delete an index  
```  
  
## <a name="applies-to"></a>적용 대상  
 [Field 개체](../../../ado/reference/ado-api/field-object.md)  
  
## <a name="see-also"></a>관련 항목  
 [Optimize 속성 예제 (VB)](../../../ado/reference/ado-api/optimize-property-example-vb.md)   
 [Optimize 속성 예제 (VC + +)](../../../ado/reference/ado-api/optimize-property-example-vc.md)   
 [필터 속성](../../../ado/reference/ado-api/filter-property.md)   
 [Find 메서드 (ADO)](../../../ado/reference/ado-api/find-method-ado.md)   
 [Sort 속성](../../../ado/reference/ado-api/sort-property.md)
