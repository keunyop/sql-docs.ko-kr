---
title: "setMaxFieldSize 메서드 (SQLServerStatement) | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- SQLServerStatement.setMaxFieldSize
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 38f7fc1d-acad-4d10-9fc8-3c0669d93b07
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 79a7cd17e2d28fde42bfad8c82fdc4bcde3ef00f
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="setmaxfieldsize-method-sqlserverstatement"></a>setMaxFieldSize 메서드 (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  바이트의 최대 수에 대 한 제한을 설정 하는 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 문자 또는 이진 값을 지정 된 바이트 수를 저장 하는 열입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public final void setMaxFieldSize(int max)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *max*  
  
 **int** 최대 바이트 수를 나타내는입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>주의  
 이 setMaxFieldSize 메서드는 java.sql.Statement 인터페이스의 setMaxFieldSize 메서드에 의해 지정 됩니다.  
  
## <a name="see-also"></a>관련 항목:  
 [SQLServerStatement 멤버](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement 클래스](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  