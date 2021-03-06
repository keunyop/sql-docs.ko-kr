---
title: setTrustStore 메서드(SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- setTrustStore Method (SQLServerDataSource)
apilocation:
- setTrustStore Method (SQLServerDataSource)
apitype: Assembly
ms.assetid: bab5485d-4547-426c-adbe-44e2b5702d1d
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 8deaaf006698018764eb67dc27e3f7cdb372e04a
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47687771"
---
# <a name="settruststore-method-sqlserverdatasource"></a>setTrustStore 메서드(SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  인증서 trustStore 파일의 경로(파일 이름 포함)를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public void setTrustStore(java.lang.String trustStore)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *trustStore*  
  
 인증서 trustStore 파일의 경로(파일 이름 포함)가 들어 있는 **문자열**입니다.  
  
## <a name="remarks"></a>Remarks  
 trustStore 속성이 지정되어 있지 않거나 null로 설정되어 있으면 [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]에서는 트러스트 관리자 팩터리의 조회 규칙에 따라 사용할 인증서 저장소를 결정합니다. 기본 SunX509 TrustManagerFactory에서는 다음 위치의 순서에 따라 트러스트 자료를 찾으려고 합니다.  
  
-   1. "javax.net.ssl.trustStore" JVM(Java Virtual Machine) 시스템 속성에 지정된 파일  
  
-   2. "\<java 홈 >/lib/security/jssecacerts" 파일입니다.  
  
-   3. "\<java 홈 >/lib/security/cacerts" 파일입니다.  
  
 자세한 내용은 Sun Microsystems 웹 사이트에서 SunX509 TrustManager 인터페이스 설명서를 참조하십시오.  
  
 trustStore 속성이 문자열이나 빈 문자열 ""로 설정되어 있으면 드라이버에서는 해당 값으로 trustStore 파일을 찾아서 서버 SSL 인증서의 유효성을 검사합니다.  
  
 trustStorePassword 속성은 trustStore 속성과 함께 지정할 수 있으며 해당 값을 사용하여 trustStore 파일을 엽니다. 자세한 내용은 [setTrustStorePassword](../../../connect/jdbc/reference/settruststorepassword-method-sqlserverdatasource.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerDataSource 멤버](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 클래스](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
