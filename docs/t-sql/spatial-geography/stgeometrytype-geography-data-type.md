---
title: STGeometryType(geography 데이터 형식) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- STGeometryType (geography Data Type)
- STGeometryType_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- STGeometryType method
ms.assetid: 3e169ead-a98e-44af-8d33-fd59a955cae4
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: d4f721d552f40fcbb1fe2ae8daac8031c437d35c
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47765381"
---
# <a name="stgeometrytype-geography-data-type"></a>STGeometryType(geography 데이터 형식)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  **geography** 인스턴스로 표현된 OGC(Open Geospatial Consortium) 형식 이름을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
.STGeometryType ( )  
```  
  
## <a name="return-types"></a>반환 형식  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 반환 형식: **nvarchar(4000)**  
  
 CLR 반환 형식: **SqlString**  
  
## <a name="remarks"></a>Remarks  
 `STGeometryType()`에 의해 반환될 수 있는 OGC 형식 이름은 **Point**, **LineString**, **CircularString**, **CompoundCurve**, **Polygon**, **CurvePolygon**, **GeometryCollection**, **MultiPoint**, **MultiLineString**, **MultiPolygon** 및 **FullGlobe**입니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 `Polygon` 인스턴스를 만들고 `STGeometryType()`을 사용하여 이 인스턴스가 다각형인지 확인합니다.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POLYGON((-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))', 4326);  
SELECT @g.STGeometryType();  
```  
  
## <a name="see-also"></a>참고 항목  
 [지리 인스턴스의 OGC 메서드](../../t-sql/spatial-geography/ogc-methods-on-geography-instances.md)  
  
  
