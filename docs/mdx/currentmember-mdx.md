---
title: CurrentMember (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: f7d47e12b95a92930bbdfceaba5cc8997c286eec
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34739952"
---
# <a name="currentmember-mdx"></a>CurrentMember(MDX)


  반복하는 동안 지정된 계층을 따라 현재 멤버를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Hierarchy_Expression.CurrentMember  
```  
  
## <a name="arguments"></a>인수  
 *Hierarchy_Expression*  
 계층을 반환하는 유효한 MDX 식입니다.  
  
## <a name="remarks"></a>Remarks  
 계층 멤버 집합에서 반복하는 동안 반복의 각 단계에서 작업이 수행되는 대상 멤버가 현재 멤버입니다. **CurrentMember** 함수 해당 멤버를 반환 합니다.  
  
> [!IMPORTANT]  
>  차원에 표시 가능한 계층이 하나만 있는 경우 해당 차원 이름은 표시 가능한 유일한 계층으로 확인되므로 해당 계층을 차원 이름이나 계층 이름 중 하나로 참조할 수 있습니다. 예를 들어 `Measures.CurrentMember`는 Measures 차원의 유일한 계층으로 확인되므로 유효한 MDX 식입니다.  
  
## <a name="examples"></a>예  
 다음 쿼리 표시 방법을 **Currentmember** 열, 행 및 분할 영역 축의 계층에서 현재 멤버를 찾는 데 사용할 수 있습니다.  
  
 `WITH MEMBER MEASURES.CURRENTDATE AS`  
  
 `[Date].[Calendar].CURRENTMEMBER.NAME`  
  
 `MEMBER MEASURES.CURRENTPRODUCT AS`  
  
 `[Product].[Product Categories].CURRENTMEMBER.NAME`  
  
 `MEMBER MEASURES.CURRENTMEASURE AS`  
  
 `MEASURES.CURRENTMEMBER.NAME`  
  
 `MEMBER MEASURES.CURRENTCUSTOMER AS`  
  
 `[Customer].[Customer Geography].CURRENTMEMBER.NAME`  
  
 `SELECT`  
  
 `[Product].[Product Categories].[Category].MEMBERS`  
  
 `*`  
  
 `{MEASURES.CURRENTDATE, MEASURES.CURRENTPRODUCT,MEASURES.CURRENTMEASURE, MEASURES.CURRENTCUSTOMER}`  
  
 `ON 0,`  
  
 `[Date].[Calendar].MEMBERS`  
  
 `ON 1`  
  
 `FROM [Adventure Works]`  
  
 `WHERE([Customer].[Customer Geography].[Country].&[Australia])`  
  
 현재 멤버는 쿼리의 축에 사용된 계층에서 변경됩니다. 따라서 축에 사용 되지 않는 동일한 차원의 다른 계층에 있는 현재 멤버가 변경할 수도 있습니다. 이 문제를 ' autoexist ' 라고 하며 자세한 내용은에서 확인할 수 있습니다 [MDX의 주요 개념 &#40;Analysis Services&#41;](../analysis-services/multidimensional-models/mdx/key-concepts-in-mdx-analysis-services.md)합니다. 예를 들어 아래 쿼리에서는 Date 차원의 Calendar Year 계층에 있는 현재 멤버가 Rows 축에 표시되는 Calendar 계층의 현재 멤버와 함께 변경되는 방법을 보여 줍니다.  
  
 `WITH MEMBER MEASURES.CURRENTYEAR AS`  
  
 `[Date].[Calendar Year].CURRENTMEMBER.NAME`  
  
 `SELECT`  
  
 `{MEASURES.CURRENTYEAR}`  
  
 `ON 0,`  
  
 `[Date].[Calendar].MEMBERS`  
  
 `ON 1`  
  
 `FROM [Adventure Works]`  
  
 **CurrentMember** 계산에서 사용 하는 쿼리의 컨텍스트를 인식 하도록 하는 것이 매우 중요 합니다. 다음 예제에서는 경우에서 범주 및 모델별 주문 수량의 비율 및 각 제품의 주문 수량과 반환 된 **Adventure Works** 큐브. **CurrentMember** 함수는 해당 주문 수량이 계산 시 사용 될 제품을 식별 합니다.  
  
```  
WITH   
   MEMBER [Measures].[Order Percent by Category] AS  
   CoalesceEmpty  
(   
      ([Product].[Product Categories].CurrentMember,  
        Measures.[Order Quantity]) /   
          (  
           Ancestor  
           ( [Product].[Product Categories].CurrentMember,   
             [Product].[Product Categories].[Category]  
           ), Measures.[Order Quantity]  
       ), 0  
   ), FORMAT_STRING='Percent'  
SELECT   
   {Measures.[Order Quantity],  
      [Measures].[Order Percent by Category]} ON COLUMNS,  
{[Product].[Product].Members} ON ROWS  
FROM [Adventure Works]  
WHERE {[Date].[Calendar Year].[Calendar Year].&[2003]}  
```  
  
## <a name="see-also"></a>관련 항목  
 [MDX 함수 참조 &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
