---
title: "Write 요소 (ASSL) | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- Write Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- Write element
ms.assetid: d8f7a367-d7bf-4b40-acb4-19c8bc8c6c20
caps.latest.revision: 12
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: d5f72e90c9975f0cf0dd1d16eeaabdb6eb378781
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="write-element-assl"></a>Write 요소(ASSL)
  데이터 또는 메타 데이터를 쓸 수 있는지 여부를 결정 한 주어진 [CubeDimensionPermission](../../../analysis-services/scripting/data-type/cubedimensionpermission-data-type-assl.md) 또는 [권한](../../../analysis-services/scripting/data-type/permission-data-type-assl.md) 요소입니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<CubeDimensionPermission> <!-- or Permission -->  
   ...  
   <Write>...</Write>  
   ...  
</CubeDimensionPermission>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|설명|  
|--------------------|-----------------|  
|데이터 형식 및 길이|String(열거형)|  
|기본값|*없음*|  
|카디널리티|0-1: 한 번만 나타날 수 있는 선택적 요소입니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|-------------|  
|부모 요소|[CubeDimensionPermission](../../../analysis-services/scripting/objects/cubepermission-element-assl.md), [사용 권한](../../../analysis-services/scripting/data-type/permission-data-type-assl.md)|  
|자식 요소|없음|  
  
## <a name="remarks"></a>주의  
 이 요소의 값은 다음 표에 나열된 문자열 중 하나로 제한됩니다.  
  
|값|Description|  
|-----------|-----------------|  
|*없음*|부모 개체의 데이터 또는 메타데이터에 대한 액세스가 허용되지 않습니다.|  
|*허용*|부모 개체의 데이터 및 메타데이터에 대한 쓰기 액세스가 허용됩니다.|  
  
## <a name="remarks"></a>주의  
 부모에 해당 하는 요소 **쓰기** Analysis Management Objects (AMO) 개체 모델은 <xref:Microsoft.AnalysisServices.CubeDimensionPermission> 및 <xref:Microsoft.AnalysisServices.Permission>합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [Cube 요소 &#40; ASSL &#41;](../../../analysis-services/scripting/objects/cube-element-assl.md)   
 [Dimension 요소 &#40; ASSL &#41;](../../../analysis-services/scripting/objects/dimension-element-assl.md)   
 [속성 &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  