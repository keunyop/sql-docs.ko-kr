---
title: "GetReparentedValue (데이터베이스 엔진) | Microsoft Docs"
ms.custom: 
ms.date: 07/22/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Reparent_TSQL
- Reparent
dev_langs:
- TSQL
helpviewer_keywords:
- Reparent [Database Engine]
ms.assetid: f47f8e25-08ef-498b-84f4-a317aca1f358
caps.latest.revision: 25
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 57f565258c7fd95347d7d9bd36b2dd2034712efe
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="getreparentedvalue-database-engine"></a>GetReparentedValue(데이터베이스 엔진)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

경로가 루트에서 노드를 반환 하려면 *newRoot*에서 경로 *oldRoot* 를 *이*합니다.
  
## <a name="syntax"></a>구문  
  
```sql
-- Transact-SQL syntax  
node. GetReparentedValue ( oldRoot, newRoot )  
```  
  
```sql
-- CLR syntax  
SqlHierarchyId GetReparentedValue ( SqlHierarchyId oldRoot , SqlHierarchyId newRoot )  
```  
  
## <a name="arguments"></a>인수  
*oldRoot*  
A **hierarchyid** 노드 수정할 계층의 수준을 나타내는입니다.
  
*newRoot*  
A **hierarchyid** 를 대체 하는 노드를 나타내는 *oldRoot* 노드를 이동 하기 위해 현재 노드의 섹션.
  
## <a name="return-types"></a>반환 형식  
**SQL Server 반환 형식: hierarchyid**
  
**CLR 반환 형식: SqlHierarchyId**
  
## <a name="remarks"></a>주의  
노드를 이동 하 여 트리를 수정 하는 데 사용 될 *oldRoot* 를 *newRoot*합니다. GetReparentedValue를 사용하면 계층에서 노드를 새 위치로 이동할 수 있습니다. **hierarchyid** 데이터 형식을 나타내지 않으며 계층 구조를 적용 하지 않습니다. 사용자는 hierarchyid가 새 위치에 대해 적절히 구성되어 있는지 확인해야 합니다. 에 고유 인덱스는 **hierarchyid** 데이터 형식은 중복 항목을 방지할 수 있습니다. 전체 하위 트리를 이동 하는 예제를 보려면 [계층적 데이터 &#40; SQL Server &#41; ](../../relational-databases/hierarchical-data-sql-server.md).
  
## <a name="examples"></a>예  
  
### <a name="a-comparing-two-node-locations"></a>1. 두 노드 위치 비교  
다음 예에서는 노드의 현재 hierarchyid를 보여 줍니다. 또한 어떤 표시는 **hierarchyid** 노드의 것 노드 하위 항목 이동 된 경우는  **@NewParent**  노드. 이 예에서는 `ToString()` 메서드를 사용하여 계층 관계를 보여 줍니다.
  
```sql
DECLARE @SubjectEmployee hierarchyid , @OldParent hierarchyid, @NewParent hierarchyid  
SELECT @SubjectEmployee = OrgNode FROM HumanResources.EmployeeDemo  
  WHERE LoginID = 'adventure-works\gail0' ;  
SELECT @OldParent = OrgNode FROM HumanResources.EmployeeDemo  
  WHERE LoginID = 'adventure-works\roberto0' ; -- who is /1/1/  
SELECT @NewParent = OrgNode FROM HumanResources.EmployeeDemo  
  WHERE LoginID = 'adventure-works\wanida0' ; -- who is /2/3/  
  
SELECT OrgNode.ToString() AS Current_OrgNode_AS_Text,   
(@SubjectEmployee. GetReparentedValue(@OldParent, @NewParent) ).ToString() AS Proposed_OrgNode_AS_Text,  
OrgNode AS Current_OrgNode,  
@SubjectEmployee. GetReparentedValue(@OldParent, @NewParent) AS Proposed_OrgNode,  
*  
FROM HumanResources.EmployeeDemo  
WHERE OrgNode = @SubjectEmployee ;  
GO  
```  
  
### <a name="b-updating-a-node-to-a-new-location"></a>2. 새 위치로 노드 업데이트  
다음 예에서는 UPDATE 문의 `GetReparentedValue()`를 사용하여 계층에서 노드를 이전 위치에서 새 위치로 이동합니다.
  
```sql
DECLARE @SubjectEmployee hierarchyid , @OldParent hierarchyid, @NewParent hierarchyid  
SELECT @SubjectEmployee = OrgNode FROM HumanResources.EmployeeDemo  
  WHERE LoginID = 'adventure-works\gail0' ; -- Node /1/1/2/  
SELECT @OldParent = OrgNode FROM HumanResources.EmployeeDemo  
  WHERE LoginID = 'adventure-works\roberto0' ; -- Node /1/1/  
SELECT @NewParent = OrgNode FROM HumanResources.EmployeeDemo  
  WHERE LoginID = 'adventure-works\wanida0' ; -- Node /2/3/  
  
UPDATE HumanResources.EmployeeDemo  
SET OrgNode = @SubjectEmployee. GetReparentedValue(@OldParent, @NewParent)   
WHERE OrgNode = @SubjectEmployee ;  
  
SELECT OrgNode.ToString() AS Current_OrgNode_AS_Text,   
*  
FROM HumanResources.EmployeeDemo  
WHERE LoginID = 'adventure-works\gail0' ; -- Now node /2/3/2/  
```  
  
### <a name="c-clr-example"></a>3. CLR 예  
다음 코드 조각 GetReparentedValue () 메서드를 호출합니다.
  
```sql
this. GetReparentedValue(oldParent, newParent)  
```  
  
## <a name="see-also"></a>참고 항목
[hierarchyid 데이터 형식 메서드 참조](http://msdn.microsoft.com/library/01a050f5-7580-4d5f-807c-7f11423cbb06)  
[계층적 데이터&#40;SQL Server&#41;](../../relational-databases/hierarchical-data-sql-server.md)  
[hierarchyid&#40;Transact-SQL&#41;](../../t-sql/data-types/hierarchyid-data-type-method-reference.md)
  
  
