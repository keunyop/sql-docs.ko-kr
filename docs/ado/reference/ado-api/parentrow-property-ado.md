---
title: ParentRow 속성 (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- ADORecordConstruction::put_ParentRow
- ADORecordConstruction::ParentRow
- ADORecordConstruction::putParentRow
helpviewer_keywords:
- ParentRow property [ADO]
ms.assetid: 5ea8029b-eda4-490b-ae84-2ad036fb582f
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 9ea31baf4b215a6a516c13b438b526b8e9d8b612
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47606581"
---
# <a name="parentrow-property-ado"></a>ParentRow 속성(ADO)
OLE DB의 컨테이너를 설정 **행** 에서 개체를 **ADORecordConstruction** 개체를 부모 행의 ADO에 켜져 있도록 **레코드** 개체입니다.  
  
 쓰기 전용입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT put_ParentRow([in] IUnknown* pParent);  
```  
  
## <a name="parameters"></a>매개 변수  
 *pParent*  
 행의 컨테이너입니다.  
  
## <a name="return-values"></a>반환 값  
 이 속성 메서드는 S_OK와 E_FAIL을 비롯 한 표준 HRESULT 값을 반환 합니다.  
  
## <a name="applies-to"></a>적용 대상  
 [ADORecordConstruction 인터페이스](../../../ado/reference/ado-api/adorecordconstruction-interface.md)
