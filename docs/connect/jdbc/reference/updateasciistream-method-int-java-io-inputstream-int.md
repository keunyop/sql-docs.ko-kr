---
title: "updateAsciiStream 메서드 (int, java.io.InputStream) | Microsoft Docs"
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
- SQLServerResultSet.updateAsciiStream (int, java.io.InputStream.int)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: d07944b8-7001-49b5-b3b3-0676f71e17cf
caps.latest.revision: 27
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: e60544cf133d302d4b2ec329b7bc648d543035f2
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="updateasciistream-method-int-javaioinputstream-int"></a>updateAsciiStream 메서드(int, java.io.InputStream, int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  지정된 열을 지정된 바이트 수를 포함하는 ASCII 스트림 값으로 업데이트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public void updateAsciiStream(int index,  
                              java.io.InputStream x,  
                              int length)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *인덱스*  
  
 **int** 열 인덱스를 나타내는입니다.  
  
 *x*  
  
 InputStream 개체입니다.  
  
 *length*  
  
 **int** 스트림의 길이 나타내는입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>주의  
 이 updateAsciiStream 메서드는 java.sql.ResultSet 인터페이스의 updateAsciiStream 메서드에 의해 지정 됩니다.  
  
 이 메서드는 InputStream 개체에서 ASCII 범위는 변환 가능한 문자 열에 ASCII 문자 (바이트)를 전달 [0x00 – 0x7F] 유니코드, 및 874, 932, 936, 949, 950, 1250-1258 코드 페이지입니다. 이 메서드는 대상 데이터 정렬 페이지에 대한 변환을 수행합니다. 변환할 수 없는 대상 열을 업데이트하려고 하면 예외가 발생합니다. 이진 열의 경우 원시 바이트가 전달됩니다.  
  
 스트림의 길이에 지정 된 것 보다 다른 경우는 *길이* 매개 변수를 JDBC 드라이버는 경우 예외를 throw 행이 업데이트 되거나 삽입 합니다.  
  
 스트림의 길이 알 수 없으면는 *길이* 드라이버의 길이 상관 없이 스트림을 수락 해야 함을 나타내려면 매개 변수를-1로 설정할 수 있습니다. Sqljdbc4.jar을 JDBC 4.0 메서드를 사용 하면 권장 [updateAsciiStream 메서드 &#40; int, java.io.InputStream &#41;](../../../connect/jdbc/reference/updateasciistream-method-int-java-io-inputstream.md) 응용 프로그램에서 길이 알 수 없는 스트림에서 열을 업데이트 하려는 경우.  
  
## <a name="see-also"></a>관련 항목:  
 [updateAsciiStream 메서드 &#40; SQLServerResultSet &#41;](../../../connect/jdbc/reference/updateasciistream-method-sqlserverresultset.md)   
 [SQLServerResultSet 멤버](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 클래스](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  