---
title: setURL 메서드(SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDataSource.setURL
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: bea70100-ac98-4625-8748-ef7cc0b111ea
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 29e1b67caaf566f04cf01c7c93a5e8d2445c31ef
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47633951"
---
# <a name="seturl-method-sqlserverdatasource"></a>setURL 메서드(SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  데이터 원본에 연결하는 데 사용되는 URL을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public void setURL(java.lang.String url)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *url*  
  
 URL을 포함하는 **문자열**입니다.  
  
## <a name="remarks"></a>Remarks  
 보안을 강화하려면 setURL 메서드에 제공되는 URL에 암호를 포함하지 말아야 합니다. 이는 타사 Java 응용 프로그램 서버가 URL 속성에 설정된 값을 데이터 원본 구성 사용자 인터페이스에 표시하는 경우가 매우 많기 때문입니다. 대신 [setPassword](../../../connect/jdbc/reference/setpassword-method-sqlserverdatasource.md) 메서드를 사용하여 암호 값을 설정하십시오. 데이터 원본에 설정된 암호는 Java 응용 프로그램 서버가 구성 사용자 인터페이스에 표시하지 않습니다.  
  
> [!NOTE]  
>  [getURL](../../../connect/jdbc/reference/geturl-method-sqlserverdatasource.md) 메서드를 호출하기 전에 setURL 메서드를 호출하지 않은 경우 getURL은 기본값인 “jdbc:sqlserver://”를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerDataSource 멤버](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 클래스](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
