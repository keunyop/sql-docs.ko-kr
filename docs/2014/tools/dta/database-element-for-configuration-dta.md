---
title: Database 요소 (DTA) 구성 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database element
ms.assetid: e91ba243-6cc9-457a-8f5a-134f3c71ae69
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: fbca62a5d32ed6b7ec30eb5d6dba6a82a2b80c64
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52747285"
---
# <a name="database-element-for-configuration-dta"></a>Configuration의 Database 요소(DTA)
  데이터베이스 엔진 튜닝 관리자가 가상 구성(`Configuration` 요소에 의해 지정됨)을 평가하게 하려는 데이터베이스를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|Description|  
|--------------------|-----------------|  
|**데이터 형식 및 길이**|없음|  
|**기본값**|없음|  
|**발생 빈도**|`Server` 요소마다 한 번 이상 지정해야 합니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|--------------|  
|**부모 요소**|[Configuration의 Server 요소&#40;DTA&#41;](server-element-for-configuration-dta.md)|  
|**자식 요소**|[Database의 Name 요소&#40;DTA&#41;](name-element-for-database-dta.md)<br /><br /> [Database의 Schema 요소&#40;DTA&#41;](schema-element-for-database-dta.md)<br /><br /> [Recommendation 요소&#40;DTA&#41;](recommendation-element-dta.md)|  
  
## <a name="remarks"></a>Remarks  
 데이터베이스 엔진 튜닝 관리자 XML 스키마에서 이 요소의 이름은 **DatabaseTypecomplexType** 입니다. 이 `Database` 요소와 XML 입력 파일의 맨 위에서 발생하는 `Server` 요소가 루트 부모인 요소를 혼동하지 마십시오. 자세한 내용은 [Server의 Database 요소&#40;DTA&#41;](database-element-for-server-dta.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 이 사용 예 `Database` 요소를 참조 합니다 [사용자 지정 구성이 포함 된 XML 입력 파일 샘플 &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md)합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [XML 입력 파일 참조&#40;데이터베이스 엔진 튜닝 관리자&#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
