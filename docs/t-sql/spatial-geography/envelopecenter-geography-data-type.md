---
title: "EnvelopeCenter (geography 데이터 형식) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- EnvelopeCenter
- EnvelopeCenter_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- EnvelopeCenter method
ms.assetid: dee9d807-faad-45b8-b3f3-7e8aa7d07147
caps.latest.revision: 17
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 0638e8793c75ad78aafa12bec1d1f8a3061022c2
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="envelopecenter-geography-data-type-"></a>EnvelopeCenter(geography 데이터 형식)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  에 대 한 경계 원의 중심으로 사용할 수 있는 지점을 반환 된 **geography** 인스턴스.  
  
 경계 원을 결정하기 위해 이 인스턴스의 각 지점은 지구 중심에서 지구 표면에 있는 해당 지점까지의 벡터로 표시됩니다. 경계 원의 중심점은 모든 벡터의 평균을 구하여 계산합니다. 폐쇄형 루프는 **다각형** 인스턴스 또는 **linestring** 인스턴스를 첫 번째 및 마지막 지점이 한 번만 사용 됩니다.  
  
 이 **geography** 데이터 형식 메서드 지원 **FullGlobe** 인스턴스 또는 반구 보다 큰 공간 인스턴스.  
  
## <a name="syntax"></a>구문  
  
```  
  
EnvelopeCenter( )  
```  
  
## <a name="return-types"></a>반환 형식  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]반환 형식: **geography**  
  
 CLR 반환 형식: **SqlGeography**  
  
## <a name="remarks"></a>주의  
 이 메서드는 반환 된 **가리킨**합니다. 와 함께 사용할 경우 `EnvelopeAngle()`, `EnvelopeCenter()` 의 경계 원을 반환는 **geography** 인스턴스.  
  
> [!NOTE]  
>  `EnvelopeCenter()`에 대 한 경계 원을 반환는 **geography** 인스턴스 중 하나로 결과 가장 작은 경계 원이 되려면 보장 되지 합니다. 반면,는 **geometry** 데이터 형식 메서드에 `STEnvelope()` 에 적용 되는 최소 경계 상자를 반환 하는 **geometry** 인스턴스.  
  
 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] 이상으로이 인스턴스의 봉투를 나타내는 원의 중심을 반환 하 고는 **가리킨**합니다. `EnvelopeAngle()` = 180으로 정의된 모든 큰 개체의 경우 `EnvelopeCenter()`는 (90,0)을 반환합니다.  
  
 이 메서드는 정확하지 않습니다.  
  
## <a name="examples"></a>예  
  
```  
DECLARE @g geography = 'LINESTRING(-120 45, -120 0, -90 0)';  
SELECT @g.EnvelopeCenter().ToString();  
```  
  
## <a name="see-also"></a>관련 항목:  
 [Geography 인스턴스의 확장된 메서드](../../t-sql/spatial-geography/extended-methods-on-geography-instances.md)   
 [EnvelopeAngle &#40; geography 데이터 형식 &#41;](../../t-sql/spatial-geography/envelopeangle-geography-data-type.md)  
  
  