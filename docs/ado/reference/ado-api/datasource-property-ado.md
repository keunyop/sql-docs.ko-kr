---
title: 데이터 원본 속성 (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset20::DataSource
helpviewer_keywords:
- DataSource property [ADO]
ms.assetid: 300a702a-3544-48c5-b759-83b511fe97e0
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: ad42ea14e58e28bf5eee0e5aac66c5a8fc309f2f
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47801281"
---
# <a name="datasource-property-ado"></a>DataSource 속성(ADO)
로 나타낼 수 있는 데이터가 포함 된 개체를 나타냅니다는 [레코드 집합](../../../ado/reference/ado-api/recordset-object-ado.md) 개체입니다.  
  
## <a name="remarks"></a>Remarks  
 이 속성은 데이터 환경을 사용 하 여 데이터 바인딩된 컨트롤을 만드는 데 사용 됩니다. 데이터 환경 데이터 (데이터 원본)가 포함 된 컬렉션으로 표현 되는 개체 (데이터 멤버) 라는 유지 관리를 **Recordset** 개체*합니다.*  
  
 합니다 [DataMember](../../../ado/reference/ado-api/datamember-property.md) 하 고 **DataSource** 속성을 함께에서 사용 해야 합니다.  
  
 참조 된 개체를 구현 해야 합니다 **IDataSource** 인터페이스를 포함 해야 합니다는 **IRowset** 인터페이스입니다.  
  
## <a name="usage"></a>사용법  
  
```  
Dim rs as New ADODB.Recordset  
rs.DataMember = "Command"     'Name of the rowset to bind to.  
Set rs.DataSource = myDE      'Name of the object containing an IRowset.  
```  
  
## <a name="applies-to"></a>적용 대상  
 [레코드 집합 개체(ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>관련 항목  
 [DataMember 속성](../../../ado/reference/ado-api/datamember-property.md)
