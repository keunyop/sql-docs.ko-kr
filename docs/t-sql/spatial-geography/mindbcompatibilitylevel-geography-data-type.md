---
title: MinDbCompatibilityLevel(geography 데이터 형식) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- MinDbCompatibilityLevel
- MinDbCompatibilityLevel_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MinDbCompatibilityLevel method (geography)
ms.assetid: a9e44748-4a9e-4179-abc4-7631597be5a7
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 2fbd22febcadf49726a4c2c4891db85417cbf787
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47744211"
---
# <a name="mindbcompatibilitylevel-geography-data-type"></a>MinDbCompatibilityLevel(geography 데이터 형식)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

  **geography** 데이터 형식을 인식하는 최소 데이터베이스 호환성을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
. MinDbCompatibilityLevel ( )  
```  
  
## <a name="return-types"></a>반환 형식  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 반환 형식: **int**  
  
 CLR 반환 형식: **int**  
  
## <a name="remarks"></a>Remarks  
 데이터베이스의 호환성 수준을 변경하기 전에 `MinDbCompatibilityLevel()`을 사용하여 공간 개체의 호환성을 테스트할 수 있습니다. 잘못된 **geography** 형식은 110을 반환합니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-testing-circularstring-type-for-compatibility-with-compatibility-level-110"></a>1. 호환성 수준 110으로 CircularString 형식의 호환성 테스트  
 다음 예에서는 `CircularString` 인스턴스에 대해 이전 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 버전과의 호환성을 테스트합니다.  
  
```  
DECLARE @g geometry = 'CIRCULARSTRING(-120.533 46.566, -118.283 46.1, -122.3 47.45)';  
IF @g.MinDbCompatibilityLevel() <= 110  
BEGIN  
    SELECT @g.ToString();  
END  
  
```  
  
### <a name="b-testing-linestring-type-for-compatibility-with-compatibility-level-100"></a>2. 호환성 수준 100으로 LineString 형식의 호환성 테스트  
 다음 예에서는 `LineString` 인스턴스에 대해 [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]과의 호환성을 테스트합니다.  
  
```  
DECLARE @g geometry = 'LINESTRING(-120.533 46.566, -118.283 46.1, -122.3 47.45)';  
IF @g.MinDbCompatibilityLevel() <= 100  
BEGIN  
    SELECT @g.ToString();  
END  
  
```  
  
### <a name="c-testing-the-value-of-a-geography-instance-for-compatibility"></a>3. Geography 인스턴스 값의 호환성 테스트  
 다음 예에서는 두 `geography` 인스턴스의 호환성 수준을 보여 줍니다. 한 인스턴스는 반구보다 작고 다른 인스턴스는 반구보다 큽니다.  
  
```  
DECLARE @g geography = geography::Parse('POLYGON((0 -10, 120 -10, 240 -10, 0 -10))');  
DECLARE @h geography = geography::Parse('POLYGON((0 10, 120 10, 240 10, 0 10))');  
IF (@g.EnvelopeAngle() >= 90)  
BEGIN  
SELECT @g.MinDbCompatibilityLevel();  
END     
IF (@h.EnvelopeAngle() < 90)  
BEGIN  
SELECT @h.MinDbCompatibilityLevel();  
END  
  
```  
  
 첫 번째 SELECT 문은 110을 반환하고 두 번째 SELECT 문은 100을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ALTER DATABASE 호환성 수준&#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql-compatibility-level.md)   
 [SQL Server 데이터베이스 엔진의 이전 버전과의 호환성](../../database-engine/sql-server-database-engine-backward-compatibility.md)  
  
  
