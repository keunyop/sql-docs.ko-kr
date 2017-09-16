---
title: "입력된 매개 변수가 있는 저장된 프로시저를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f491b70-7d1b-42bd-964f-9a8b86af5eaa
caps.latest.revision: 21
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 49f92bf52ddf9c06906f42b81945ec3d630c8be4
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="using-a-stored-procedure-with-input-parameters"></a>입력 매개 변수가 있는 저장 프로시저 사용
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  A [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 호출할 수 있는 저장된 프로시저는 하나를 포함 하는 하나 나 둘 매개 변수에서 데이터를 전달 하는 저장된 프로시저에 사용할 수 있는 매개 변수입니다. [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] 제공는 [SQLServerPreparedStatement](../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) 이러한 종류의 저장된 프로시저를 호출 하 고 반환 하는 데이터를 처리할 수 있는 클래스입니다.  
  
 JDBC 드라이버를 사용 하 여 매개 변수에서 사용 하 여 저장된 프로시저를 호출 하는 경우 사용 해야는 `call` 와 함께 SQL 이스케이프 시퀀스는 [prepareCall](../../connect/jdbc/reference/preparecall-method-sqlserverconnection.md) 의 메서드는 [SQLServerConnection](../../connect/jdbc/reference/sqlserverconnection-class.md) 클래스입니다. 에 대 한 구문에서 `call` 매개 변수가 있는 이스케이프 시퀀스는 다음과 같습니다.  
  
 `{call procedure-name[([parameter][,[parameter]]...)]}`  
  
> [!NOTE]  
>  SQL 이스케이프 시퀀스에 대 한 자세한 내용은 참조 [SQL 이스케이프 시퀀스를 사용 하 여](../../connect/jdbc/using-sql-escape-sequences.md)합니다.  
  
 생성할 때는 `call` 이스케이프 시퀀스를 사용 하 여 매개 변수를 지정 된? 입력 매개 변수를 지정합니다. 이 문자는 저장 프로시저로 전달될 매개 변수 값에 대한 자리 표시자로 사용됩니다. 매개 변수에 대해 값을 지정 하려면 SQLServerPreparedStatement 클래스의 setter 메서드 중 하나를 사용할 수 있습니다. 사용할 수 있는 setter 메서드는 입력 매개 변수의 데이터 형식에 따라 결정됩니다.  
  
 setter 메서드에 값을 전달할 때는 매개 변수에 사용할 실제 값은 물론 저장 프로시저에서 해당 매개 변수의 서수 위치도 지정해야 합니다. 예를 들어 저장 프로시저에 단일 입력 매개 변수가 들어 있는 경우 서수 값은 1이 됩니다. 또한 저장 프로시저에 입력 매개 변수가 두 개이면 첫 번째 서수 값은 1이고 두 번째 서수 값은 2가 됩니다.  
  
 IN 매개 변수를 포함 하는 저장된 프로시저를 호출 하는 방법의 예를 들어에 uspGetEmployeeManagers 저장 프로시저를 사용 하 여는 [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)] 예제 데이터베이스. 이 저장 프로시저는 정수인 EmployeeID라는 단일 입력 매개 변수를 허용하고 지정한 EmployeeID를 토대로 직원 및 해당 관리자의 재귀 목록을 반환합니다. 이 저장 프로시저를 호출하는 Java 코드는 다음과 같습니다.  
  
```  
public static void executeSprocInParams(Connection con) {  
   try {  
      PreparedStatement pstmt = con.prepareStatement("{call dbo.uspGetEmployeeManagers(?)}");  
      pstmt.setInt(1, 50);  
      ResultSet rs = pstmt.executeQuery();  
  
      while (rs.next()) {  
         System.out.println("EMPLOYEE:");  
         System.out.println(rs.getString("LastName") + ", " + rs.getString("FirstName"));  
         System.out.println("MANAGER:");  
         System.out.println(rs.getString("ManagerLastName") + ", " + rs.getString("ManagerFirstName"));  
         System.out.println();  
      }  
      rs.close();  
      pstmt.close();  
   }  
  
   catch (Exception e) {  
      e.printStackTrace();  
    }  
}  
```  
  
## <a name="see-also"></a>관련 항목:  
 [저장 프로시저가 있는 문 사용](../../connect/jdbc/using-statements-with-stored-procedures.md)  
  
  