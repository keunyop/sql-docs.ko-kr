---
title: XOR (MDX) | Microsoft Docs
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- XOR
dev_langs:
- kbMDX
helpviewer_keywords:
- XOR operator
ms.assetid: 17280f36-df0e-477e-9342-e8129ed5cc3c
caps.latest.revision: 27
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: b3cc1c76865fe61cd819649e3a8e92031d17b444
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="xor-mdx"></a>XOR(MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  두 숫자 식에 대해 논리 제외를 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Expression1 XOR Expression2  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 *Expression1*  
 숫자 값을 반환하는 유효한 MDX 식입니다.  
  
 *Expression2*  
 숫자 값을 반환하는 유효한 MDX 식입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 하는 부울 값 **true** 에 단 하나의 인수가 계산 되 면 **true**, 그렇지 않으면 **false**합니다.  
  
## <a name="remarks"></a>주의  
 **XOR** 연산자는 매개 변수가 모두 부울 값으로 취급 (0, 0으로 **false**, 그렇지 않으면 **true**) 연산자는 논리 제외를 수행 하기 전에. 다음 표에서 설명 방법을 **XOR** 연산자로 논리 제외를 수행 합니다.  
  
|*Expression1*|*Expression2*|반환 값|  
|-------------------|-------------------|------------------|  
|**true**|**true**|**false**|  
|**true**|**false**|**true**|  
|**false**|**true**|**true**|  
|**false**|**false**|**false**|  
  
## <a name="see-also"></a>참고 항목  
 [MDX 연산자 참조 &#40; Mdx&#41;](../mdx/mdx-operator-reference-mdx.md)  
  
  
