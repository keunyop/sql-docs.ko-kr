---
title: "UnknownMember 요소 (ASSL) | Microsoft Docs"
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
- UnknownMember Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- UnknownMember
helpviewer_keywords:
- UnknownMember element
ms.assetid: 5558961e-e3c6-4f4e-817d-5b12b0734c03
caps.latest.revision: 35
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 5da9cdc237512a47a27b21691864b3da523ce70a
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="unknownmember-element-assl"></a>UnknownMember 요소(ASSL)
  알 수 없는 멤버의 표시 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<Dimension>  
      ...  
   <UnknownMember>...</UnknownMember>  
   ...  
</Dimension>  
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
|부모 요소|[Dimension](../../../analysis-services/scripting/objects/dimension-element-assl.md)|  
|자식 요소|없음|  
  
## <a name="remarks"></a>주의  
 이 요소의 값은 다음 표에 나열된 문자열 중 하나로 제한됩니다.  
  
|값|Description|  
|-----------|-----------------|  
|*표시*|알 수 없는 멤버가 있고 표시됩니다.|  
|*숨김*|알 수 없는 멤버가 있지만 표시되지 않습니다.|  
|*없음*|알 수 없는 멤버가 사용되지 않습니다.|  
  
 에 대 한 허용된 된 값에 해당 하는 열거형 **UnknownMember** Analysis Management Objects (AMO) 개체 모델은 <xref:Microsoft.AnalysisServices.UnknownMemberBehavior>합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [UnknownMemberName 요소 &#40; ASSL &#41;](../../../analysis-services/scripting/properties/unknownmembername-element-assl.md)   
 [UnknownMemberTranslation 요소 &#40; ASSL &#41;](../../../analysis-services/scripting/objects/unknownmembertranslation-element-assl.md)   
 [속성 &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  