---
title: "^ (거듭제곱) (MDX) | Microsoft Docs"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- kbMDX
helpviewer_keywords:
- functions [MDX], ^ (Power)
ms.assetid: be2becd7-5683-4891-9b8a-6e795fc9e47d
caps.latest.revision: 7
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 229544cc06737bfc61e5781fb7cf3014f86ae681
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="-power-mdx"></a>^ (거듭제곱)(MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  한 수에 다른 수를 제곱하는 산술 연산을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Numeric_Expression ^ Numeric_Expression  
```  
  
#### <a name="parameters"></a>매개 변수  
 *Numeric_Expression*  
 숫자 값을 반환하는 유효한 MDX 식입니다.  
  
## <a name="return-value"></a>반환 값  
 우선 순위가 더 높은 매개 변수의 데이터 형식을 갖는 값입니다.  
  
## <a name="remarks"></a>주의  
 두 식이 모두 동일한 데이터 형식으로 되어 있거나 식 하나가 암시적으로 다른 식의 데이터 형식으로 변환될 수 있어야 합니다. 식 하나가 Null 값으로 계산되는 경우 연산자는 Null 값을 반환합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [MDX 연산자 참조 &#40; Mdx&#41;](../mdx/mdx-operator-reference-mdx.md)  
  
  
