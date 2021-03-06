---
title: Ordinal (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 83036ec2ee0fa69c9ebb8cc2a905361eeae0aafa
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34742672"
---
# <a name="ordinal-mdx"></a>Ordinal(MDX)


  수준과 관련된 서수 값(0부터 시작)을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Level_Expression.Ordinal   
```  
  
## <a name="arguments"></a>인수  
 *Level_Expression*  
 수준을 반환하는 유효한 MDX 식입니다.  
  
## <a name="remarks"></a>Remarks  
 **서 수** 함수와 함께에서 자주 사용 되는 **IIF** 및 **CurrentMember** 쿼리 결과 있는 각 특정 셀의 서 수 위치에 따라 조건부로 각 계층 수준 서로 다른 값을 표시 하는 함수입니다. 예를 들어, 사용할 수는 **서** 특정 수준에서 계산을 수행 하 고 다른 수준의 기본값은 "n/A"를 표시 하는 함수입니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 Calendar 계층에 있는 Calendar Quarter 수준의 서수를 반환합니다.  
  
```  
WITH MEMBER Measures.x AS [Date].[Calendar].[Calendar Quarter].Ordinal  
SELECT Measures.x on 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>관련 항목  
 [MDX 함수 참조 &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
