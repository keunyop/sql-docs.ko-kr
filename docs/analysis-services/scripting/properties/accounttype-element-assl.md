---
title: "AccountType 요소 (ASSL) | Microsoft Docs"
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
- AccountType Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- AccountType
helpviewer_keywords:
- AccountType element
ms.assetid: 4fdf17d3-cd84-4bf6-9baf-21e15d4bf71e
caps.latest.revision: 39
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: cdb339861e5b12a9f020af51fe96847fe8ca9b36
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="accounttype-element-assl"></a>AccountType 요소(ASSL)
  에 정의 된 계정 유형의 이름을 포함 한 [데이터베이스](../../../analysis-services/scripting/objects/database-element-assl.md) 요소입니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<Account>  
   ...  
   <AccountType>...</AccountType>  
   ...  
</Account>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|설명|  
|--------------------|-----------------|  
|데이터 형식 및 길이|String(열거형)|  
|기본값|없음|  
|카디널리티|1-1: 한 번만 나타나는 필수 요소입니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|-------------|  
|부모 요소|[계정](../../../analysis-services/scripting/objects/account-element-assl.md)|  
|자식 요소|없음|  
  
## <a name="remarks"></a>주의  
 이 요소의 값은 다음 표에 있는 문자열 중 하나로 제한됩니다.  
  
|값|Description|  
|-----------|-----------------|  
|*수입*|수입 계정입니다.|  
|*비용*|지출 계정입니다.|  
|*흐름*|현금 흐름 계정입니다.|  
|*잔액*|잔액 계정입니다.|  
|*자산*|자산 계정입니다.|  
|*책임*|부채 계정입니다.|  
|*통계*|통계 계정입니다.|  
  
 에 대 한 허용된 된 값에 해당 하는 열거 **AccountType** Analysis Management Objects (AMO) 개체 모델은 <xref:Microsoft.AnalysisServices.AccountTypes>합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [Accounts 요소 &#40; ASSL &#41;](../../../analysis-services/scripting/collections/accounts-element-assl.md)   
 [속성 &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  