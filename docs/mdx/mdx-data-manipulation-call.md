---
title: "CALL 문 (MDX) | Microsoft Docs"
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
- CALL
dev_langs:
- kbMDX
helpviewer_keywords:
- voids [MDX]
- stored procedures [MDX]
- CALL statement
ms.assetid: b534a20b-924c-43b8-832d-24e57d50425c
caps.latest.revision: 35
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 3d5bc0d9875d602135fd92722b73c07176a1df59
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="mdx-data-manipulation---call"></a>MDX 데이터 조작-호출
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  현재 범위 또는 지정된 큐브에서 void를 반환하는 저장 프로시저를 실행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
CALL SP_Name   
   [ (SP_Argument   
      [, SP_Argument ,...n]  
      ) ]   
[ONCube_Expression]  
```  
  
## <a name="arguments"></a>인수  
 *SP_Name*  
 저장 프로시저의 이름을 지정하는 유효한 문자열 식입니다.  
  
 *SP_Argument*  
 호출된 저장 프로시저에 인수를 지정하는 유효한 문자열 식입니다.  
  
 *Cube_Expression*  
 큐브의 이름을 지정하는 유효한 문자열 큐브 식입니다.  
  
## <a name="remarks"></a>주의  
 **호출** 문을 필요에 따라 지정 된 저장된 프로시저에 대 한 하나 이상의 인수를 포함 하 여 지정 된 등록 된 저장된 프로시저를 실행 합니다. **호출** 문은 void를 반환 하는 저장된 프로시저에만 사용 됩니다. 이 문은 MDX 식 내의 다른 함수 또는 연산자와 조합될 수 없습니다. 값을 반환하는 등록된 저장 프로시저는 MDX 식 내에서 직접 호출될 수 있으며 다른 MDX 함수 및 연산자와 조합될 수 있습니다.  
  
 큐브가 지정되지 않은 경우 이 문은 현재 큐브에서 저장 프로시저를 실행합니다.  
  
> [!NOTE]  
>  저장된 프로시저가 클라이언트에 등록 되지 않은 경우는 **호출** 문에서의 인스턴스에서 저장된 프로시저를 호출 하려고 [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MDX 데이터 조작 문 &#40; Mdx&#41;](../mdx/mdx-data-manipulation-statements-mdx.md)   
 [저장된 프로시저 &#40;를 사용 하 여 Mdx&#41;](../mdx/using-stored-procedures-mdx.md)  
  
  
