---
title: "논리 식 (XQuery) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
dev_langs:
- XML
helpviewer_keywords:
- logical operators [SQL Server], XQuery
- effective Boolean value [XQuery]
- logical expressions [XQuery]
- EBV
- expressions [XQuery], logical
ms.assetid: de94cd2e-2d48-49fb-9ebd-a2d90c79bf62
caps.latest.revision: 26
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: e6a7c65f0c5758bdc8f50582d6d2288f9918677b
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="logical-expressions-xquery"></a>논리 식(XQuery)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  XQuery 지원 논리 **및** 및 **또는** 연산자입니다.  
  
```  
expression1 and expression2  
expression1 or expression2  
```  
  
 테스트 식 `expression1,``expression2`에 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 빈 시퀀스, 하나 이상의 노드 시퀀스 또는 단일 부울 값에서 발생할 수 있습니다. 결과를 바탕으로 유효한 해당 부울 값은 다음 방식으로 결정됩니다.  
  
-   테스트 식 결과 빈 시퀀스가 생성되면 식의 결과는 False입니다.  
  
-   테스트 식의 결과로 단일 부울 값이 생성되면 이 값이 식의 결과입니다.  
  
-   테스트 식의 결과로 하나 이상의 노드 시퀀스가 생성되면 식의 결과는 True입니다.  
  
-   위의 경우 중 하나에 해당하지 않으면 정적 오류가 발생합니다.  
  
 논리 **및** 및 **또는** 연산자는 표준 논리적 의미 체계가 있는 식의 결과 부울 값에 적용 됩니다.  
  
 다음 쿼리는 제품 카탈로그에서 특정 제품 모델에 대해 전면 각도의 크기가 작은 사진인 <`Picture`> 요소를 검색합니다. 각 제품 설명 문서에 대해 카탈로그에 크기 및 각도와 같은 다른 특성을 가진 하나 이상의 제품 사진을 저장할 수 있습니다.  
  
```  
SELECT CatalogDescription.query('  
     declare namespace PD="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
     for $F in /PD:ProductDescription/PD:Picture[PD:Size="small"   
                                                 and PD:Angle="front"]  
     return   
         $F   
    ') as Result  
FROM  Production.ProductModel  
where ProductModelID=19  
```  
  
 다음은 결과입니다.  
  
```  
<PD:Picture   
  xmlns:PD="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">  
  <PD:Angle>front</PD:Angle>  
  <PD:Size>small</PD:Size>  
  <PD:ProductPhotoID>31</PD:ProductPhotoID>  
</PD:Picture>  
  
```  
  
## <a name="see-also"></a>관련 항목:  
 [XQuery 식](../xquery/xquery-expressions.md)  
  
  