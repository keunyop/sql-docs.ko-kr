---
title: updateAsciiStream 메서드(java.io.InputStream, int) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.updateAsciiStream (java.lang.String, java.io.InputStream, int)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 4e2997a0-c18e-4114-bce9-0ab4b2b9f92c
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: a548e0b6beb1815052167d28d67d1228c0bf6dfc
ms.sourcegitcommit: 2429fbcdb751211313bd655a4825ffb33354bda3
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "52517306"
---
# <a name="updateasciistream-method-javalangstring-javaioinputstream-int"></a>updateAsciiStream 메서드(java.lang.String, java.io.InputStream, int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  지정된 열 이름을 지정된 바이트 수를 포함하는 ASCII 스트림 값으로 업데이트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public void updateAsciiStream(java.lang.String columnName,  
                              java.io.InputStream x,  
                              int length)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *columnName*  
  
 열 이름이 포함된 **문자열**입니다.  
  
 *x*  
  
 InputStream 개체입니다.  
  
 *length*  
  
 스트림의 길이를 나타내는 **int**입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 이 updateAsciiStream 메서드는 java.sql.ResultSet 인터페이스의 updateAsciiStream 메서드에 의해 지정 됩니다.  
  
 이 메서드는 InputStream 개체의 ASCII 문자(바이트)를 변환 가능한 문자 열에 전달합니다. 이러한 열은 유니코드의 ASCII 범위 [0x00 – 0x7F]와 874, 932, 936, 949, 950, 1250-1258 코드 페이지입니다. 이 메서드는 대상 데이터 정렬 페이지에 대한 변환을 수행합니다. 변환할 수 없는 대상 열을 업데이트하려고 하면 예외가 발생합니다. 이진 열의 경우 원시 바이트가 전달됩니다.  
  
 스트림의 길이가 *length* 매개 변수에 지정된 길이와 다르면 행이 업데이트되거나 삽입될 때 JDBC 드라이버에서 예외가 발생합니다.  
  
 스트림의 길이를 알 수 없으면 *length* 매개 변수는 드라이버에서 스트림의 길이에 상관없이 스트림을 허용해야 함을 나타내는 -1로 설정될 수 있습니다. sqljdbc4.jar을 사용하는 경우에는 응용 프로그램에서 길이를 알 수 없는 스트림에서 열을 업데이트하려고 할 때 JDBC 4.0 메서드 [updateAsciiStream 메서드(java.lang.String, java.io.InputStream)](../../../connect/jdbc/reference/updateasciistream-method-java-lang-string-java-io-inputstream.md)를 사용하는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
 [updateAsciiStream 메서드&#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/updateasciistream-method-sqlserverresultset.md)   
 [SQLServerResultSet 멤버](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 클래스](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
