---
title: "명령 (ADO-WFC 구문) | Microsoft Docs"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
helpviewer_keywords:
- Command collection [ADO], ADO/WFC syntax
ms.assetid: 39d0aa06-03ac-4c9a-8400-83947756ef99
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 867ebe5a6eec1d340c0d02f77d8f5b687766ee89
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="command-ado---wfc-syntax"></a>명령 (ADO-WFC 구문)
## <a name="package-commswfcdata"></a>패키지 com.ms.wfc.data  
  
### <a name="constructor"></a>생성자  
  
```  
public Command()  
public Command(String commandtext)  
```  
  
### <a name="methods"></a>메서드  
  
```  
public void cancel()  
public com.ms.wfc.data.Parameter createParameter(String  
    Name, int Type, int Direction, int Size, Object Value)  
public Recordset execute()  
public Recordset execute(Object[] parameters)  
public Recordset execute(Object[] parameters, int options)  
public int executeUpdate(Object[] parameters)  
public int executeUpdate(Object[] parameters, int options)  
public int executeUpdate()  
```  
  
 **executeUpdate** 메서드는 내부 ADO를 호출 하는 특수 한 사례 방법이 **실행** 특정 매개 변수와 함께 메서드. **executeUpdate** 방법은의 반환을 지원 하지 않습니다는 **레코드 집합** 개체 이므로 **실행** 메서드의 *옵션* 매개 변수는 로 수정 **AdoEnums.ExecuteOptions.NORECORDS**합니다. 이후에 **실행** 메서드가 완료 되 면 해당 업데이트 된 *RecordsAffected* 로 다시 전달 될 매개 변수는 **executeUpdate** 는 로마지막으로반환되는메서드**int**합니다.  
  
### <a name="properties"></a>속성  
  
```  
public com.ms.wfc.data.Connection getActiveConnection()  
public void setActiveConnection(com.ms.wfc.data.Connection con)  
public void setActiveConnection(String conString)  
public String getCommandText()  
public void setCommandText(String command)  
public int getCommandTimeout()  
public void setCommandTimeout(int timeout)  
public int getCommandType()  
public void setCommandType(int type)  
public String getName()  
public void setName(String name)  
public boolean getPrepared()  
public void setPrepared(boolean prepared)  
public int getState()  
public com.ms.wfc.data.Parameter getParameter(int n)  
public com.ms.wfc.data.Parameter getParameter(String n)  
public com.ms.wfc.data.Parameters getParameters()  
public AdoProperties getProperties()  
```  
  
## <a name="see-also"></a>관련 항목:  
 [명령 개체(ADO)](../../../ado/reference/ado-api/command-object-ado.md)