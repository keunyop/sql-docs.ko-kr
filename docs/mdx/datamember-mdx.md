---
title: DataMember (MDX) | Microsoft Docs
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
- DATAMEMBER
dev_langs:
- kbMDX
helpviewer_keywords:
- DataMember function
ms.assetid: 65bf21e8-1cb2-4ae8-bfbe-bb4d72589557
caps.latest.revision: 30
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: b6be9e31f666eafaba1ec7ad346a7e5bb28da9b0
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="datamember-mdx"></a>DataMember(MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  차원의 리프가 아닌 멤버에 관련된 시스템 생성 데이터 멤버를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Member_Expression.DataMember  
```  
  
## <a name="arguments"></a>인수  
 *Member_Expression*  
 멤버를 반환하는 유효한 MDX 식입니다.  
  
## <a name="remarks"></a>주의  
 이 함수는 계층의 리프가 아닌 멤버에 작동 하며에서 사용할 수는 [UPDATE CUBE 문 (MDX)](../mdx/mdx-data-manipulation-update-cube.md) 리프 멤버의 하위 항목 대신 리프가 아닌 멤버를 직접에 쓰기 저장 데이터에 명령 합니다.  
  
> [!NOTE]  
>  지정된 멤버가 리프 멤버인 경우나 리프가 아닌 멤버에 관련 데이터 멤버가 없는 경우에는 지정된 멤버를 반환합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **DataMember** 각 개별 직원에 대 한 판매 할당량을 표시 하는 계산된 측정값에서 함수:  
  
```  
WITH MEMBER measures.InvidualQuota AS   
([Employee].[Employees].currentmember.datamember, [Measures].[Sales Amount Quota])  
,FORMAT_STRING='Currency'  
SELECT {[Measures].[Sales Amount Quota],[Measures].InvidualQuota} ON COLUMNS,  
[Employee].[Employees].MEMBERS ON ROWS  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>참고 항목  
 [MDX 함수 참조 &#40; Mdx&#41;](../mdx/mdx-function-reference-mdx.md)   
 [MDX &#40;의 주요 개념 Analysis Services &#41;](../analysis-services/multidimensional-models/mdx/key-concepts-in-mdx-analysis-services.md)  
  
  
