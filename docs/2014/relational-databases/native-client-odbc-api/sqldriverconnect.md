---
title: SQLDriverConnect | Microsoft 문서
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLDriverConnect function
ms.assetid: a1e38e2c-3a97-42d1-9c45-a0ca3282ffd1
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 22d560c8a65d5b9a7cebc4062ddd2d1ce936d5a2
ms.sourcegitcommit: 334cae1925fa5ac6c140e0b2c38c844c477e3ffb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/13/2018
ms.locfileid: "53372064"
---
# <a name="sqldriverconnect"></a>SQLDriverConnect
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 드라이버는 연결 문자열 키워드를 대체하거나 개선하는 연결 특성을 정의합니다. 몇 가지 연결 문자열 키워드에는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 드라이버가 지정한 기본값이 있습니다.  
  
 목록에서 사용할 수 있는 키워드는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 네이티브 클라이언트 ODBC 드라이버를 참조 [SQL Server Native Client를 사용 하 여 연결 문자열 키워드를 사용 하 여](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).  
  
 에 대 한 자세한 내용은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 연결 특성 및 드라이버의 기본 동작을 참조 하십시오. [SQLSetConnectAttr](sqlsetconnectattr.md).  
  
 유효한 연결 문자열 키워드에 대 한 내용은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 참조 [SQL Server Native Client를 사용 하 여 연결 문자열 키워드를 사용 하 여](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).  
  
 경우는 `SQLDriverConnect` *DriverCompletion* 매개 변수 값이 SQL_DRIVER_PROMPT, SQL_DRIVER_COMPLETE 또는 SQL_DRIVER_COMPLETE_REQUIRED 이면는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 드라이버에서 키워드 값을 검색 합니다 표시 되는 대화 상자입니다. 키워드 값이 연결 문자열에서 전달되었고 사용자가 대화 상자에서 키워드 값을 변경하지 않은 경우 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 드라이버는 연결 문자열의 값을 사용합니다. 키워드 값이 연결 문자열에서 설정되지 않았고 사용자가 대화 상자에서 키워드 값을 지정하지 않은 경우 드라이버는 기본값을 사용합니다.  
  
 `SQLDriverConnect` 유효한 지정 해야 합니다 *WindowHandle* 있으면 *DriverCompletion* 값 필요 (또는 필요할 수 있습니다) 드라이버의 연결 대화 상자를 표시 합니다. 잘못된 핸들을 지정하면 SQL_ERROR가 반환됩니다.  
  
 DRIVER 또는 DSN 키워드 중 하나를 지정합니다. 둘 모두 지정한 경우 ODBC 드라이버는 이 두 키워드 중 왼쪽의 키워드를 사용하고 다른 하나는 무시합니다. 드라이버가 지정 되거나 둘 중에서 가장 왼쪽을 하는 경우와 `SQLDriverConnect` *DriverCompletion* 매개 변수 값이 SQL_DRIVER_NOPROMPT 이면 SERVER 키워드 및 적절 한 값을 필요 합니다.  
  
 SQL_DRIVER_NOPROMPT를 지정하는 경우에는 사용자 인증 키워드를 값과 함께 제공해야 합니다. 드라이버는 문자열 "Trusted_Connection=yes" 또는 UID와 PWD 키워드가 제공되었는지 확인합니다.  
  
 경우는 *DriverCompletion* 매개 변수 값이 SQL_DRIVER_NOPROMPT 또는 SQL_DRIVER_COMPLETE_REQUIRED 언어나 데이터베이스 연결 문자열에서 오며 하거나 유효 하지 않은 `SQLDriverConnect` SQL_ERROR를 반환 합니다.  
  
 경우는 *DriverCompletion* 매개 변수 값이 SQL_DRIVER_NOPROMPT 또는 SQL_DRIVER_COMPLETE_REQUIRED 언어나 데이터베이스를 ODBC 데이터 원본 정의에서 오며 하거나 유효 하지 않은 `SQLDriverConnect` 기본값을 사용 하 여 언어 또는 데이터베이스에서 지정 된 사용자 ID 및 SQL_SUCCESS_WITH_INFO 반환 합니다.  
  
 경우는 *DriverCompletion* 매개 변수 값이 SQL_DRIVER_COMPLETE 또는 sql_driver_prompt이 고 언어나 데이터베이스 유효한 경우 `SQLDriverConnect` 대화 상자를 다시 표시 합니다.  
  
## <a name="sqldriverconnect-support-for-high-availability-disaster-recovery"></a>고가용성 재해 복구를 위한 SQLDriverConnect 지원  
 사용에 대 한 자세한 내용은 `SQLDriverConnect` 에 연결 하는 [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] 클러스터를 참조 하십시오 [SQL Server Native Client Support for High Availability, Disaster Recovery](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md)합니다.  
  
## <a name="sqldriverconnect-support-for-service-principal-names-spns"></a>SPN(서비스 사용자 이름)에 대한 SQLDriverConnect 지원  
 SQLDDriverConnect은 boxwhen 프롬프트 대화 상자를 사용할 수 있습니다. ODBC 로그인을 사용 합니다. 이를 통해 주 서버 및 해당 장애 조치(Failover) 파트너 모두에 대한 SPN이 입력되도록 할 수 있습니다.  
  
 SQLDriverConnect 새 연결 문자열 키워드를 수락할 `ServerSPN` 고 `FailoverPartnerSPN`, 새 연결 특성인 SQL_COPT_SS_SERVER_SPN과 SQL_COPT_SS_FAILOVER_PARTNER_SPN을 인식 합니다.  
  
 연결 특성 값이 두 번 이상 지정된 경우 프로그래밍 방식으로 설정된 값이 DSN의 값 및 연결 문자열의 값보다 우선 순위가 높고 DSN의 값이 연결 문자열의 값보다 우선 순위가 높습니다.  
  
 연결이 열릴 때 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client는 SQL_COPT_SS_MUTUALLY_AUTHENTICATED 및 SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD를 연결을 여는 데 사용하는 인증 방법으로 설정합니다.  
  
 Spn에 대 한 자세한 내용은 참조 하세요. [서비스 사용자 이름 &#40;Spn&#41; 클라이언트 연결의 &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md)합니다.  
  
## <a name="examples"></a>예  
 다음 호출에 필요한 데이터의 최소 크기를 보여 줍니다. `SQLDriverConnect`:  
  
```  
SQLDriverConnect(hdbc, hwnd,  
    (SQLTCHAR*) TEXT("DRIVER={SQL Server Native Client 10};"), SQL_NTS, szOutConn,  
    MAX_CONN_OUT, &cbOutConn, SQL_DRIVER_COMPLETE);  
```  
  
 다음 연결 문자열을 필요한 최소한의 데이터를 보여 줍니다. 때 합니다 *DriverCompletion* 매개 변수 값이 SQL_DRIVER_NOPROMPT:  
  
```  
"DSN=Human Resources;Trusted_Connection=yes"  
  
"FILEDSN=HR_FDSN;Trusted_Connection=yes"  
  
"DRIVER={SQL Server Native Client 10};SERVER=(local);Trusted_Connection=yes"  
```  
  
## <a name="see-also"></a>관련 항목  
 [SQLDriverConnect 함수](https://go.microsoft.com/fwlink/?LinkId=59340)   
 [ODBC API 구현 정보](odbc-api-implementation-details.md)   
 [SET ANSI_NULLS&#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql)   
 [SET ANSI_PADDING&#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql)   
 [SET ANSI_WARNINGS &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/set-ansi-warnings-transact-sql)  
  
  
