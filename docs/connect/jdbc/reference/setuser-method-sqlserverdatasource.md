---
title: setUser 메서드(SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDataSource.setUser
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: d2ea7906-2d10-438d-aa51-f576eea923c7
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 3f3953763dc1b8a0d24e4c335b5b465c49707174
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47784161"
---
# <a name="setuser-method-sqlserverdatasource"></a>setUser 메서드(SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  데이터 원본에 연결하는 데 사용되는 사용자 이름을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public void setUser(java.lang.String user)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *user*  
  
 사용자 이름을 포함하는 **문자열**입니다.  
  
## <a name="remarks"></a>Remarks  
 setUser 메서드는 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]에 연결하는 데 사용될 사용자 이름을 설정합니다. 사용자 이름 값이 설정되어 있지 않으면 [getUser](../../../connect/jdbc/reference/getuser-method-sqlserverdatasource.md) 메서드는 기본값인 null을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerDataSource 멤버](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 클래스](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
