---
title: "버전 요소 (ASSL) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- Version Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- Version
helpviewer_keywords:
- Version element
ms.assetid: fb26fe5d-de40-443b-a8bc-031c950552e6
caps.latest.revision: 39
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: da0d8a1b101dd16fe9e7b94a0538a8b73c732e64
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="version-element-assl"></a>Version 요소(ASSL)
  인스턴스의 읽기 전용 버전 번호를 포함 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] 나타내는 [서버](../../../analysis-services/scripting/objects/server-element-assl.md) 요소입니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<Server>  
      ...  
      <Version>...</Version>  
   ...  
</Server>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|설명|  
|--------------------|-----------------|  
|데이터 형식 및 길이|문자열|  
|기본값|없음|  
|카디널리티|0-1: 한 번만 나타날 수 있는 선택적 요소입니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|-------------|  
|부모 요소|[Server](../../../analysis-services/scripting/objects/server-element-assl.md)|  
|자식 요소|없음|  
  
## <a name="remarks"></a>주의  
 **버전** 요소 설명의 버전 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] 가 설치 되어 있습니다.  
  
 부모에 해당 하는 요소 **버전** Analysis Management Objects (AMO) 개체 모델은 <xref:Microsoft.AnalysisServices.Server>합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [Edition 요소 &#40; ASSL &#41;](../../../analysis-services/scripting/properties/edition-element-assl.md)   
 [속성 &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  