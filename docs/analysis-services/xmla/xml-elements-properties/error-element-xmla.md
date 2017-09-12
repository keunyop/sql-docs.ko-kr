---
title: "Error 요소 (XMLA) | Microsoft Docs"
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- Error Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- microsoft.xml.analysis.error
- http://schemas.microsoft.com/analysisservices/2003/engine#Error
- urn:schemas-microsoft-com:xml-analysis#Error
helpviewer_keywords:
- Error element
ms.assetid: add670cb-cab2-42be-91a3-d0c385f29d16
caps.latest.revision: 13
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 214dc93af2f02f4bd47ac9d0199b0254fe2ab024
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="error-element-xmla"></a>Error 요소(XMLA)
  인스턴스에서 반환 된 오류에 대 한 정보를 포함 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<Message>  
   <Error   
      ErrorCode="unsignedint"   
      Severity="string"   
      Description="string"  
      Source="string"  
      HelpFile="string"  
   />  
</Message>  
<!-- or -->  
<Cell><!-- or row -->  
   <!-- A child element -->  
      <Error xmlns="urn:schemas-microsoft-com:xml-analysis:exception"  
         < ErrorCode>...</ErrorCode>  
         < Description>...</Description>  
         < Source>...</Source>  
         < HelpFile>...</HelpFile>  
      </Error>  
   <!-- /A child element -- >  
</Cell>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|설명|  
|--------------------|-----------------|  
|데이터 형식 및 길이|없음|  
|기본값|없음|  
|카디널리티|0-1: 한 번만 나타날 수 있는 선택적 요소입니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|-------------|  
|부모 요소|[메시지](../../../analysis-services/xmla/xml-elements-properties/message-element-xmla.md)|  
|자식 요소|아래 표를 참조 합니다.|  
  
|상위 항목|자식 요소|  
|--------------|--------------------|  
|[메시지](../../../analysis-services/xmla/xml-elements-properties/message-element-xmla.md)|없음|  
|[셀](../../../analysis-services/xmla/xml-elements-properties/cell-element-mddataset-xmla.md), [행](../../../analysis-services/xmla/xml-elements-properties/message-element-xmla.md)|[설명](../../../analysis-services/xmla/xml-elements-properties/description-element-xmla.md), [ErrorCode](../../../analysis-services/xmla/xml-elements-properties/errorcode-element-xmla.md), [HelpFile](../../../analysis-services/xmla/xml-elements-properties/helpfile-element-xmla.md), [소스](../../../analysis-services/xmla/xml-elements-properties/source-element-error-xmla.md)|  
  
## <a name="attributes"></a>특성  
  
|Attribute|설명|  
|---------------|-----------------|  
|ErrorCode|필요한 **UnsignedInt** 특성 (경우에만 **메시지** 부모 요소입니다.) 오류의 숫자 반환 코드를 포함합니다.|  
|Severity|선택적 **문자열** 특성 (경우에만 **메시지** 부모 요소입니다.) 오류의 심각도를 포함합니다.|  
|Description|선택적 **문자열** 특성 (경우에만 **메시지** 부모 요소입니다.) 오류에 대한 설명 텍스트를 포함합니다.|  
|원본|선택적 **문자열** 특성 (경우에만 **메시지** 부모 요소입니다.) 오류를 발생시킨 구성 요소 이름을 포함합니다.|  
|HelpFile|선택적 **문자열** 특성 (경우에만 **메시지** 부모 요소입니다.) 오류를 설명하는 도움말 파일 또는 항목의 경로 및 URL을 포함합니다.|  
  
## <a name="remarks"></a>주의  
  
## <a name="see-also"></a>관련 항목:  
 [Warning 요소 &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/warning-element-xmla.md)   
 [속성 &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  