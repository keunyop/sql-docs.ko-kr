---
title: getUser 메서드(SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDataSource.getUser
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 3513dd7f-6ae5-4010-bde0-454ac4365bce
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 34d7c710372114d9c11d9a4f8278fa041482f0bf
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47597168"
---
# <a name="getuser-method-sqlserverdatasource"></a>getUser 메서드(SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  데이터 원본에 연결하는 데 사용되는 사용자 이름을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public java.lang.String getUser()  
```  
  
## <a name="return-value"></a>반환 값  
 사용자 이름을 포함하는 **문자열**입니다.  
  
## <a name="remarks"></a>Remarks  
 [setUser](../../../connect/jdbc/reference/setuser-method-sqlserverdatasource.md) 메서드는 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]의 인스턴스에 연결할 때 사용할 사용자 이름을 설정합니다. 사용자 이름 값이 설정되어 있지 않으면 getUser 메서드는 기본값인 null을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerDataSource 멤버](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 클래스](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
