---
title: getURL 메서드(java.lang.String)(SQLServerResultSet) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.getURL (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 105a5319-0f4c-4d08-964b-cc52f8e28ec1
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 49f586249657b2f10a166c975608fd2b539d67ea
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47740871"
---
# <a name="geturl-method-javalangstring-sqlserverresultset"></a>getURL 메서드(java.lang.String)(SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 개체의 현재 행에서 지정된 열 이름의 값을 검색하여 URL 개체로 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public java.net.URL getURL(java.lang.String sColumn)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *sColumn*  
  
 열 이름이 포함된 **문자열**입니다.  
  
## <a name="return-value"></a>반환 값  
 URL 개체입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 이 getURL 메서드는 java.sql.ResultSet 인터페이스의 getURL 메서드에 의해 지정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [getURL 메서드 &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/geturl-method-sqlserverresultset.md)   
 [SQLServerResultSet 멤버](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 클래스](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
