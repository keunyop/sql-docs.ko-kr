---
title: EXECUTE AS (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 08/10/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- EXECUTE AS
- EXECUTE_AS_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- REVERT statement
- WITH NO REVERT clause
- sessions [SQL Server], execution context
- EXECUTE AS
- execution context [SQL Server]
- switching execution context
ms.assetid: 613b8271-7f7d-4378-b7a2-5a7698551dbd
caps.latest.revision: 39
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: e389fdc50da662deeab7eba030a367e5fc7e97cb
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="execute-as-transact-sql"></a>EXECUTE AS(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  세션의 실행 컨텍스트를 설정합니다.  
  
 기본적으로 세션은 사용자가 로그인할 때 시작되고 로그오프할 때 종료됩니다. 세션 동안 이루어진 모든 작업에 대해 해당 사용자의 권한을 확인합니다. 경우는 **EXECUTE AS** 명령문을 실행, 지정된 된 로그인 또는 사용자 이름에는 세션의 실행 컨텍스트가 전환 됩니다. 컨텍스트가 전환 된 후의 권한을 확인 호출 하는 사용자 대신 해당 계정에 대 한 로그인 및 사용자 보안 토큰의 **EXECUTE AS** 문. 기본적으로 사용자 또는 로그인 계정은 세션 또는 모듈이 실행되는 동안이나 컨텍스트 전환이 명시적으로 되돌려질 때까지 가장됩니다.  
  

  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
{ EXEC | EXECUTE } AS <context_specification>  
[;]  
  
<context_specification>::=  
{ LOGIN | USER } = 'name'  
    [ WITH { NO REVERT | COOKIE INTO @varbinary_variable } ]   
| CALLER  
```  
  
## <a name="arguments"></a>인수  
 Login  
 **적용 대상**: [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] 부터 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]까지  
  
 가장할 실행 컨텍스트를 로그인으로 지정합니다. 가장의 범위는 서버 수준입니다.  
  
> [!NOTE]  
>  이 옵션은 포함 된 데이터베이스에서 또는 SQL 데이터베이스에서 사용할 수 없습니다.  
  
 User  
 가장할 컨텍스트를 현재 데이터베이스의 사용자로 지정합니다. 가장의 범위는 현재 데이터베이스로 제한됩니다. 데이터베이스 사용자로 컨텍스트 전환 시 해당 사용자의 서버 수준 사용 권한은 상속되지 않습니다.  
  
> [!IMPORTANT]  
>  데이터베이스 사용자로의 컨텍스트 전환이 활성화되어 있는 동안 해당 데이터베이스 외부의 리소스에 액세스하려고 하면 문이 실패합니다. 여기에 사용 하 여 *데이터베이스* 문, 분산된 쿼리 및 3-또는 4 부분으로 구성 식별자를 사용 하는 다른 데이터베이스를 참조 하는 쿼리 합니다.  
  
 **'** *이름* **'**  
 유효한 사용자 또는 로그인 이름입니다. *이름* 의 구성원 이어야 합니다는 **sysadmin** 고정 서버 역할 또는에서 보안 주체로 존재 [sys.database_principals](../../relational-databases/system-catalog-views/sys-database-principals-transact-sql.md) 또는 [sys.server_principals](../../relational-databases/system-catalog-views/sys-server-principals-transact-sql.md), 각각.  
  
 *이름* 지역 변수로 지정할 수 있습니다.  
  
 *이름* 는 단일 계정 이어야 하며 그룹, 역할, 인증서, 키 또는 NT AUTHORITY\LocalService, NT AUTHORITY\NetworkService 또는 NT AUTHORITY\LocalSystem 같은 기본 제공 계정이 될 수 없습니다.  
  
 자세한 내용은 참조 [사용자 또는 로그인 이름 지정](#_user) 이 항목의 뒷부분에 나오는 합니다.  
  
 NO REVERT  
 컨텍스트 전환을 이전 컨텍스트로 되돌릴 수 없도록 지정합니다. **NO REVERT** 옵션은 임시 수준 에서만 사용할 수 있습니다.  
  
 이전 컨텍스트로 되돌리기 하는 방법에 대 한 자세한 내용은 참조 [REVERT &#40; Transact SQL &#41; ](../../t-sql/statements/revert-transact-sql.md).  
  
 쿠키에  **@**  *varbinary_variable*  
 호출 REVERT WITH COOKIE 문에 올바른 있으면 실행 컨텍스트를 이전 컨텍스트로 되돌릴만 수 있도록 지정  **@**  *varbinary_variable* 값입니다. [!INCLUDE[ssDE](../../includes/ssde-md.md)] 쿠키를 전달  **@**  *varbinary_variable*합니다. **쿠키에** 옵션은 임시 수준 에서만 사용할 수 있습니다.  
  
 **@***varbinary_variable* 은 **varbinary (8000)**합니다.  
  
> [!NOTE]  
>  쿠키 **출력** 에 대 한 매개 변수는 현재으로 문서화 **varbinary (8000)** 정확한 최대 길이인 합니다. 그러나 현재 구현은 **varbinary(100)**입니다. 응용 프로그램을 예약 해야 **varbinary (8000)** 쿠키 반환 크기가 늘어날 이후 릴리스에서 경우 제대로 작동 하도록 응용 프로그램이 계속 되도록 합니다.  
  
 CALLER  
 모듈 내에서 사용된 경우 모듈 내의 문이 모듈 호출자의 컨텍스트에서 실행되도록 지정합니다.  
  
 모듈 외부에서 사용된 경우에는 문이 아무런 동작도 수행하지 않습니다.  
  
## <a name="remarks"></a>주의  
 실행 컨텍스트의 변경은 다음 조건 중 하나가 발생할 때까지 유효합니다.  
  
-   다른 EXECUTE AS 문이 실행됩니다.  
  
-   REVERT 문이 실행됩니다.  
  
-   세션이 삭제됩니다.  
  
-   명령이 실행된 저장 프로시저 또는 트리거가 종료됩니다.  
  
여러 보안 주체에서 EXECUTE AS 문을 여러 번 호출하여 실행 컨텍스트 스택을 만들 수 있습니다. 호출 시 REVERT 문은 컨텍스트를 컨텍스트 스택의 다음 수준에 있는 로그인 또는 사용자로 전환합니다. 이 동작의 데모를 보려면 참조 [예 A](#_exampleA)합니다.  
  
##  <a name="_user"></a>사용자 또는 로그인 이름 지정  
 EXECUTE AS에 지정 된 사용자 또는 로그인 이름은 \<context_specification >의 보안 주체로 존재 해야 **sys.database_principals** 또는 **sys.server_principals**각각 또는 EXECUTE AS 문이 실패합니다. 또한 보안 주체에 IMPERSONATE 권한을 부여해야 합니다. 호출자가 데이터베이스 소유자 또는의 멤버인 하지 않는 한는 **sysadmin** 고정 서버 역할, 보안 주체가 있어야도 사용자가 액세스 하는 경우 데이터베이스 또는 인스턴스의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 는 Windows를 통해 그룹 구성원 자격. 예를 들어 다음과 같은 조건을 가정해 보세요. 
  
-   **CompanyDomain\SQLUsers** 그룹에 대 한 액세스는 **Sales** 데이터베이스입니다.  
  
-   **CompanyDomain\SqlUser1** 의 멤버인 **SQLUsers** 에 암시적 권한이 따라서 및는 **Sales** 데이터베이스.  
  
 하지만 **CompanyDomain\SqlUser1** 멤버 자격을 통해 데이터베이스에 액세스할 수는 **SQLUsers** 그룹 문을 `EXECUTE AS USER = 'CompanyDomain\SqlUser1'` 하기 때문에 실패 `CompanyDomain\SqlUser1` 에서 보안 주체로 존재 하지 않습니다 데이터베이스입니다.  
  
사용자가 분리 하는 경우 (연결 된 로그인 더 이상 존재), 사용자를 만들지 않고 **WITHOUT LOGIN**, **EXECUTE AS** 사용자에 대 한 실패 합니다.  
  
## <a name="best-practice"></a>최선의 구현 방법  
 세션에서 작업을 수행하는 데 필요한 최소 권한을 가진 로그인 또는 사용자를 지정합니다. 예를 들어 데이터베이스 수준 사용 권한만 필요한 경우에는 서버 수준 사용 권한을 가진 로그인 이름을 지정하지 않도록 합니다. 또한 데이터베이스 소유자 계정과 관련된 사용 권한이 필요하지 않으면 이 계정을 지정하지 않도록 합니다.  
  
> [!CAUTION]  
>  [!INCLUDE[ssDE](../../includes/ssde-md.md)]가 이름을 확인할 수 있는 한 EXECUTE AS 문은 성공할 수 있습니다. 도메인 사용자가 있는 경우 Windows 사용자에게 [!INCLUDE[ssDE](../../includes/ssde-md.md)]에 대한 액세스 권한이 없어도 Windows는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 사용자를 확인할 수 있습니다. 가장된 로그인은 공용 또는 게스트 사용 권한만 부여하더라도 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에 대한 액세스 권한이 없는 로그인이 로그인된 것으로 나타날 수 있습니다.  
  
## <a name="using-with-no-revert"></a>WITH NO REVERT 사용  
 EXECUTE AS 문에 선택적 WITH NO REVERT 절이 포함되어 있으면 REVERT를 사용하거나 다른 EXECUTE AS 문을 실행하여 세션의 실행 컨텍스트를 다시 설정할 수 없습니다. 해당 문으로 설정한 컨텍스트는 세션이 삭제될 때까지 유효합니다.  
  
 때 WITH NO REVERT COOKIE = @*varbinary_variabl*절을 지정 된 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] @ 쿠키 값을 전달*varbinary_variabl*e입니다. 설정한 실행 컨텍스트는 문 수 경우에 되돌릴를 이전 컨텍스트로 호출 REVERT WITH COOKIE = @*varbinary_variable* 같은 문을 포함  *@varbinary_variable*  값입니다.  
  
 이 옵션은 연결 풀링을 사용하는 환경에서 유용합니다. 연결 풀링은 응용 프로그램 서버의 응용 프로그램이 다시 사용할 수 있도록 데이터베이스 연결 그룹을 유지 관리하는 것입니다. 에 전달 된 값  *@varbinary_variable*  EXECUTE AS 호출자 에게만 알려지므로 호출자 문의 호출자에 게 보장할 수 있는 다른 사용자가 자신이 설정한 실행 컨텍스트를 변경할 수 없습니다.  
  
## <a name="determining-the-original-login"></a>원래 로그인 결정  
 사용 하 여 [ORIGINAL_LOGIN](../../t-sql/functions/original-login-transact-sql.md) 의 인스턴스에 연결 하는 로그인의 이름을 반환 하는 함수 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]합니다. 이 함수를 사용하여 명시적 또는 암시적 컨텍스트 전환이 많이 있는 세션의 원래 로그인 ID를 반환할 수 있습니다.  
  
## <a name="permissions"></a>Permissions  
 지정 하려면 **EXECUTE AS** 호출자에 게는 로그인 있어야 **IMPERSONATE** 지정된 된 로그인에 대 한 권한 이름을 지정 하 고 거부 되지 않아야는 **IMPERSONATE ANY LOGIN** 사용 권한 . 지정 하려면 **EXECUTE AS** 호출자에 게 데이터베이스 사용자에 있어야 **IMPERSONATE** 지정된 된 사용자 이름에 대 한 권한이 있습니다. 때 **EXECUTE AS CALLER** 지정 된 **IMPERSONATE** 권한이 필요 하지 않습니다.  
  
## <a name="examples"></a>예  
  
###  <a name="_exampleA"></a> 1. EXECUTE AS 및 REVERT를 사용하여 컨텍스트 전환  
 다음 예에서는 여러 보안 주체를 사용하여 컨텍스트 실행 스택을 만듭니다. 그런 다음 `REVERT` 문을 사용하여 실행 컨텍스트를 이전 호출자로 다시 설정합니다. `REVERT` 문은 실행 컨텍스트가 원래 호출자로 설정될 때까지 스택 위로 이동하면서 여러 번 실행됩니다.  
  
```  
USE AdventureWorks2012;  
GO  
--Create two temporary principals  
CREATE LOGIN login1 WITH PASSWORD = 'J345#$)thb';  
CREATE LOGIN login2 WITH PASSWORD = 'Uor80$23b';  
GO  
CREATE USER user1 FOR LOGIN login1;  
CREATE USER user2 FOR LOGIN login2;  
GO  
--Give IMPERSONATE permissions on user2 to user1  
--so that user1 can successfully set the execution context to user2.  
GRANT IMPERSONATE ON USER:: user2 TO user1;  
GO  
--Display current execution context.  
SELECT SUSER_NAME(), USER_NAME();  
-- Set the execution context to login1.   
EXECUTE AS LOGIN = 'login1';  
--Verify the execution context is now login1.  
SELECT SUSER_NAME(), USER_NAME();  
--Login1 sets the execution context to login2.  
EXECUTE AS USER = 'user2';  
--Display current execution context.  
SELECT SUSER_NAME(), USER_NAME();  
-- The execution context stack now has three principals: the originating caller, login1 and login2.  
--The following REVERT statements will reset the execution context to the previous context.  
REVERT;  
--Display current execution context.  
SELECT SUSER_NAME(), USER_NAME();  
REVERT;  
--Display current execution context.  
SELECT SUSER_NAME(), USER_NAME();  
  
--Remove temporary principals.  
DROP LOGIN login1;  
DROP LOGIN login2;  
DROP USER user1;  
DROP USER user2;  
GO  
```  
  
### <a name="b-using-the-with-cookie-clause"></a>2. WITH COOKIE 절 사용  
 다음 예제에서는 지정된 된 사용자에 세션의 실행 컨텍스트를 설정 하 고 지정 WITH NO REVERT COOKIE = @*varbinary_variabl*절. 컨텍스트를 호출자로 되돌리려면 `REVERT` 문에 `@cookie` 문의 `EXECUTE AS` 변수로 전달되는 값을 지정해야 합니다. 이 예를 실행하려면 예 1에서 생성된 `login1` 로그인 및 `user1` 사용자가 있어야 합니다.  
  
```  
DECLARE @cookie varbinary(8000);  
EXECUTE AS USER = 'user1' WITH COOKIE INTO @cookie;  
-- Store the cookie in a safe location in your application.  
-- Verify the context switch.  
SELECT SUSER_NAME(), USER_NAME();  
--Display the cookie value.  
SELECT @cookie;  
GO  
-- Use the cookie in the REVERT statement.  
DECLARE @cookie varbinary(8000);  
-- Set the cookie value to the one from the SELECT @cookie statement.  
SET @cookie = <value from the SELECT @cookie statement>;  
REVERT WITH COOKIE = @cookie;  
-- Verify the context switch reverted.  
SELECT SUSER_NAME(), USER_NAME();  
GO  
```  
  
## <a name="see-also"></a>관련 항목:  
 [되돌리기 &#40; Transact SQL &#41;](../../t-sql/statements/revert-transact-sql.md)   
 [EXECUTE AS 절 &#40; Transact SQL &#41;](../../t-sql/statements/execute-as-clause-transact-sql.md)  
  
  

