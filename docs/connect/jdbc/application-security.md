---
title: "응용 프로그램 보안 | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 940879b4-aa0f-41ce-a369-6cfc0e78e01d
caps.latest.revision: 23
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: e608d2181520284be87dbdaa078ff261a2a7d878
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="application-security"></a>응용 프로그램 보안
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  사용 하는 경우는 [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)], 응용 프로그램의 보안을 유지 하려면 예방 조치를 수행 해야 합니다. 다음 섹션에서는 응용 프로그램의 보안을 확보하기 위해 수행할 수 있는 단계에 관한 정보를 제공합니다.  
  
## <a name="using-java-policy-permissions"></a>Java 정책 권한 사용  
 사용 하는 경우는 [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)], JDBC 드라이버에서 요구 하는 필수 Java 정책 권한을 지정 해야 합니다. JRE(Java Runtime Environment)는 런타임에 사용하여 스레드가 리소스에 액세스할 수 있는지 여부를 확인할 수 있는 다양한 보안 모델을 제공합니다. 이러한 액세스는 보안 정책 파일을 통해 제어할 수 있습니다. 또한 이 정책 파일은 배포자와 컨테이너의 sysadmin을 통해 관리되지만 이 항목에 나열된 권한은 JDBC 드라이버의 기능에 영향을 주는 권한입니다.  
  
 정책 파일의 일반적인 권한은 다음과 같습니다.  
  
```  
// Example policy file entry.  
grant [signedBy <signer>,] [codeBase <code source>] {  
   permission  <class>  [<name> [, <action list>]];  
};  
```  
  
 다음 코드베이스는 최소한의 권한을 부여하도록 JDBC 드라이버 코드베이스로 제한해야 합니다.  
  
```  
grant codeBase "file:/install_dir/lib/-" {  
  
// Grant access to data source.  
permission java.util.PropertyPermission "java.naming.*", "read,write";  
  
// Specify which hosts can be connected to.  
permission java.net.socketPermission "host:port", "connect";  
  
// Logger permission to take advantage of logging.  
permission java.util.logging.LoggingPermission;  
  
// Grant listen/connect/accept permissions to the driver if   
// connecting to a named instance as the client driver.   
// This connects to a udp service and listens for a response.  
permission java.net.SocketPermission "*", "listen, connect, accept";   
};   
```  
  
> [!NOTE]  
>  "file:/install_dir/lib/-" 코드는 JDBC 드라이버의 설치 디렉터리를 나타냅니다.  
  
## <a name="protecting-server-communication"></a>서버 통신 보호  
 와 통신 하려면 JDBC 드라이버를 사용 하는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 데이터베이스 인터넷 프로토콜 보안 (IPSEC) 또는 SSL Secure Sockets Layer ();를 사용 하 여 통신 채널을 보호할 수 있습니다 또는 둘 다 사용할 수 있습니다.  
  
 SSL 지원을 사용하여 IPSec 외에 추가 수준의 보호 기능을 제공할 수 있습니다. SSL을 사용 하는 방법에 대 한 자세한 내용은 참조 [SSL 암호화를 사용 하 여](../../connect/jdbc/using-ssl-encryption.md)합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [JDBC 드라이버 응용 프로그램 보안](../../connect/jdbc/securing-jdbc-driver-applications.md)  
  
  