---
title: 모양 변경 | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- reshaping previously shaped Recordset [ADO]
- data shaping [ADO], reshaping
ms.assetid: b1c965b7-3dad-4de6-9e0e-502ca8785be3
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 324801cbfc97db4e2a1137fa04df0c74dc1897a1
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47714531"
---
# <a name="reshaping"></a>다시 셰이핑
A **레코드 집합** 생성 셰이프 절로 명령을 할당할 수 있습니다는 *별칭* (일반적으로 사용 하 여 AS 키워드) 이름입니다. 별칭을 모양의 **레코드 집합** 완전히 다른 명령에서 참조할 수 있습니다. 재사용할 수, 또는 *변형*, 이전에 모양의 **레코드 집합** 새 셰이프 명령에서입니다. 이 기능을 지원 하려면 ADO에는 속성을 제공 [이름은 변형](../../../ado/reference/ado-api/reshape-name-property-dynamic-ado.md)합니다.  
  
 모양 변경에 두 개의 main 함수가 있습니다. 첫 번째는 기존 연결 **Recordset** 새 부모와 함께 **레코드 집합**합니다.  
  
## <a name="example"></a>예제  
  
```  
rs1.Open "SHAPE {select * from Customers} " & _  
         "APPEND ({select * from Orders} AS chapOrders " & _  
         "RELATE CustomerID to CustomerID)", cn  
  
rs2.Open "SHAPE {select * from Employees} " & _  
         "APPEND (chapOrders RELATE EmployeeID to EmployeeID)", cn  
```  
  
 두 번째 기능은 기존 자식에 대 한 장으로 구성 된 비 액세스를 사용 하도록 설정 하는 것 **레코드 집합** 개체는 구문을 사용 하 여 "셰이프 \<레코드 집합 이름 변형 >"입니다.  
  
> [!NOTE]
>  기존 열을 추가할 수 없습니다 **Recordset**, 매개 변수가 있는 변형 **레코드 집합** 또는 **레코드 집합** 모든 중간 COMPUTE 절에서 개체 또는 수행 작업을 집계 **레코드 집합** 의 하위 합니다 **레코드 집합** 원들은 되 고 합니다. **Recordset** 원들은 되 고 새 셰이프 명령을 사용 해야 합니다 둘 다 동일한 [연결](../../../ado/reference/ado-api/connection-object-ado.md)합니다.  
  
## <a name="see-also"></a>관련 항목  
 [데이터 셰이핑 예제](../../../ado/guide/data/data-shaping-example.md)
