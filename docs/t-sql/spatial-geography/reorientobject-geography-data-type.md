---
title: ReorientObject(geography 데이터 형식) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- ReorientObject
- ReorientObject_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- ReorientObject method (geography)
ms.assetid: e2a1a4f1-211b-4e82-abed-03fc7140a83c
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: cda6f09124127d04c8ded1773feab4e9ffbf2ba9
ms.sourcegitcommit: 01e17c5f1710e7058bad8227c8011985a9888d36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2019
ms.locfileid: "56265230"
---
# <a name="reorientobject-geography-data-type"></a>ReorientObject(geography 데이터 형식)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

내부 영역과 외부 영역이 서로 바뀐 **geography** 인스턴스를 반환합니다.  
  
이 **geography** 데이터 형식 메서드는 **FullGlobe** 인스턴스 또는 반구보다 큰 공간 인스턴스를 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
.ReorientObject (geography)  
```  
  
## <a name="arguments"></a>인수  
_geography_  
`ReorientObject()`를 호출할 다른 **geography** 인스턴스입니다.  
  
## <a name="return-value"></a>반환 값  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 반환 형식: **geography**  
  
CLR 반환 형식: **SqlGeography**  
  
## <a name="remarks"></a>Remarks  
이 메서드는 **GeometryCollection**에 있는 모든 **Polygons**의 링 방향을 변경하지만 지정된 컬렉션에서 **Points** 또는 **LineStrings**를 제거하거나 변경하지는 않습니다.  
  
**GeometryCollection**을 이 메서드에 전달하면 그 결과로 컬렉션에 포함된 각 인스턴스의 방향이 다시 지정되지만 전체 컬렉션의 방향은 다시 지정되지 않습니다.  
  
## <a name="examples"></a>예  
  
```  
DECLARE @R GEOGRAPHY = GEOGRAPHY::Parse('Polygon((-10 -10, -10 10, 10 10, 10 -10, -10 -10))');  
SELECT @R.ReorientObject().STAsText();  
--Result: POLYGON ((10 10, -10 10, -10 -10, 10 -10, 10 10))  
```  
  
## <a name="see-also"></a>참고 항목  
[지리 인스턴스의 확장 메서드](../../t-sql/spatial-geography/extended-methods-on-geography-instances.md)  
  
