---
title: "SilenceOverrideInterval 요소 (ASSL) | Microsoft Docs"
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
- SilenceOverrideInterval Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- SilenceOverrideInterval
helpviewer_keywords:
- SilenceOverrideInterval element
ms.assetid: 0dcd2db4-9bc0-4460-b1dd-def0b38c4617
caps.latest.revision: 32
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: c84c6f51a727620094aa21206da7d01187bbd6c2
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="silenceoverrideinterval-element-assl"></a>SilenceOverrideInterval 요소(ASSL)
  MOLAP(다차원 OLAP) 이미징을 무조건 시작하기 전에 초기 알림을 받은 후 경과해야 하는 시간을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<ProactiveCaching>  
   ...  
   <SilenceOverrideInterval>...</SilenceOverrideInterval>  
   ...  
</ProactiveCaching>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|설명|  
|--------------------|-----------------|  
|데이터 형식 및 길이|duration|  
|기본값|P0|  
|카디널리티|0-1: 한 번만 나타날 수 있는 선택적 요소입니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|-------------|  
|부모 요소|[ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md)|  
|자식 요소|없음|  
  
## <a name="remarks"></a>주의  
 대기 기간 중에 알림을 받은 경우 **SilenceOverrideInterval** 의 값으로 **SilenceInterval** 의 값이 재정의됩니다.  
  
 부모에 해당 하는 요소 **SilenceOverrideInterval** Analysis Management Objects (AMO) 개체 모델은 <xref:Microsoft.AnalysisServices.ProactiveCaching>합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [속성 &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  