---
title: REVOKE (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/26/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- REVOKE_TSQL
- REVOKE
dev_langs:
- TSQL
helpviewer_keywords:
- schema-level securables [SQL Server]
- REVOKE statement, Transact-SQL syntax
- removing permissions
- server-level securables [SQL Server]
- deleting permissions
- revoking permissions [SQL Server]
- REVOKE statement
- denying permissions [SQL Server], removing
- database-level securables [SQL Server]
- granting permissions [SQL Server], removing
- permissions [SQL Server], revoking
- dropping permissions
ms.assetid: 9d31d3e7-0883-45cd-bf0e-f0361bbb0956
caps.latest.revision: 41
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: aa08be63c0d792ed1e0422860b55a0c8f2abdc8b
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="revoke-transact-sql"></a>REVOKE(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  이전에 부여하거나 거부한 사용 권한을 제거합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
-- Syntax for SQL Server and Azure SQL Database  
  
-- Simplified syntax for REVOKE  
REVOKE [ GRANT OPTION FOR ]  
      {   
        [ ALL [ PRIVILEGES ] ]  
        |  
                permission [ ( column [ ,...n ] ) ] [ ,...n ]  
      }  
      [ ON [ class :: ] securable ]   
      { TO | FROM } principal [ ,...n ]   
      [ CASCADE] [ AS principal ]  
```  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
REVOKE   
    <permission> [ ,...n ]  
    [ ON [ <class_type> :: ] securable ]   
    [ FROM | TO ] principal [ ,...n ]  
    [ CASCADE ]  
[;]  
  
<permission> ::=  
{ see the tables below }  
  
<class_type> ::=  
{  
      LOGIN  
    | DATABASE  
    | OBJECT  
    | ROLE  
    | SCHEMA  
    | USER  
}  
```  
  
## <a name="arguments"></a>인수  
 GRANT OPTION FOR  
 지정된 사용 권한을 부여할 수 있는 권한이 취소됨을 나타냅니다. CASCADE 인수를 사용할 경우 이 인수가 필요합니다.  
  
> [!IMPORTANT]  
>  보안 주체에 GRANT 옵션 없이 지정된 사용 권한이 있는 경우 사용 권한 자체가 취소됩니다.  
  
 ALL  
**적용 대상**: [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] 통해[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]
  
 이 옵션은 모든 가능한 사용 권한을 취소하지 않습니다. ALL을 취소하는 것은 다음 사용 권한을 취소하는 것과 같습니다.  
  
-   보안 개체가 데이터베이스인 경우 ALL은 BACKUP DATABASE, BACKUP LOG, CREATE DATABASE, CREATE DEFAULT, CREATE FUNCTION, CREATE PROCEDURE, CREATE RULE, CREATE TABLE 및 CREATE VIEW를 의미합니다.  
  
-   보안 개체가 스칼라 함수인 경우 ALL은 EXECUTE 및 REFERENCES를 의미합니다.  
  
-   보안 개체가 테이블 반환 함수인 경우 ALL은 DELETE, INSERT, REFERENCES, SELECT 및 UPDATE를 의미합니다.  
  
-   보안 개체가 저장 프로시저인 경우 ALL은 EXECUTE를 의미합니다.  
  
-   보안 개체가 테이블인 경우 ALL은 DELETE, INSERT, REFERENCES, SELECT 및 UPDATE를 의미합니다.  
  
-   보안 개체가 뷰인 경우 ALL은 DELETE, INSERT, REFERENCES, SELECT 및 UPDATE를 의미합니다.  
  
> [!NOTE]  
>  REVOKE ALL 구문은 더 이상 사용되지 않습니다. 대신 [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] Revoke 관련 권한을 사용하세요.  
  
 PRIVILEGES  
 ISO 호환성을 위해 포함됩니다. ALL의 동작을 변경하지 않습니다.  
  
 *사용 권한*  
 사용 권한의 이름입니다. 보안 개체에 사용 권한의 올바른 매핑에 대해서에 나열 된 항목에 설명 되어 [보안 개체별 구문](#securable) 이 항목의 뒷부분에 나오는 합니다.  
  
 *열*  
 사용 권한을 취소할 테이블의 열 이름을 지정합니다. 괄호가 필요합니다.  
  
 *클래스*  
 사용 권한을 취소할 보안 개체의 클래스를 지정합니다. 범위 한정자 **::** 가 필요 합니다.  
  
 *보안 개체*  
 사용 권한을 취소할 보안 개체를 지정합니다.  
  
 | *주*  
 보안 주체의 이름입니다. 보안 개체에 대한 사용 권한을 취소할 대상 보안 주체는 보안 개체에 따라 다릅니다. 유효한 조합에 대 한 자세한 내용은에 나열 된 항목을 참조 하십시오. [보안 개체별 구문](#securable) 이 항목의 뒷부분에 나오는 합니다.  
  
 CASCADE  
 특정 보안 주체가 부여한 사용 권한을 취소하면 동일한 보안 주체가 부여한 다른 보안 주체의 사용 권한도 취소됨을 나타냅니다. CASCADE 인수를 사용할 경우에는 GRANT OPTION FOR 인수도 포함해야 합니다.  
  
> [!CAUTION]  
>  WITH GRANT OPTION을 부여 받은 사용 권한이 연계되어 취소되면 해당 사용 권한의 GRANT 및 DENY가 모두 취소됩니다.  
  
 AS *주*  
 본인이 아닌 다른 사용자에 의해 부여 된 사용 권한을 취소할 수 있는지 나타내려면 AS 주 절을 사용 합니다. 예를 들어 사용자 Mary가 principal_id 12 및 Raul 사용자가 주 15 한다고 가정해 보겠습니다. Mary 및 Raul 모두 동일한 권한에 서 라는 사용자 권한을 부여 합니다. Sys.database_permissions 테이블 사용 권한을 두 번 표시 됩니다 하지만 각각 아무런 다른 grantor_prinicpal_id 값입니다. Mary 사용 하 여 권한을 해지할 수는 `AS RAUL` 절을 사용 권한의 Raul의 권한 부여를 제거 합니다.
 
이 문 에서처럼 사용 하는 다른 사용자를 가장 하는 기능을 의미 하지 않습니다.  
  
## <a name="remarks"></a>주의  
 REVOKE 문의 전체 구문은 복잡합니다. 위의 구문 다이어그램은 구조를 강조하기 위해 단순하게 표현되었습니다. 특정 보안 개체에 대 한 사용 권한을 취소 하는 전체 구문은에 나열 된 항목에서 설명 [보안 개체별 구문](#securable) 이 항목의 뒷부분에 나오는 합니다.  
  
 REVOKE 문을 사용하여 부여된 사용 권한을 제거할 수 있으며 DENY 문을 사용하여 보안 주체가 GRANT를 통해 특정 사용 권한을 얻지 못하도록 막을 수 있습니다.  
  
 사용 권한을 부여하면 지정된 보안 개체에 대한 이 사용 권한의 DENY 또는 REVOKE가 제거됩니다. 보안 개체가 포함된 상위 범위에서 동일한 사용 권한이 거부되면 DENY가 우선 적용됩니다. 그러나 상위 범위에서 부여된 사용 권한을 취소하는 것은 우선 적용되지 않습니다.  
  
> [!CAUTION]  
>  테이블 수준의 DENY는 열 수준의 GRANT보다 우선하지 않습니다. 사용 권한 계층에서의 이러한 불일치는 이전 버전과의 호환성을 위해 유지되었습니다. 후속 릴리스에서 제거될 예정입니다.  
  
 sp_helprotect 시스템 저장 프로시저는 데이터베이스 수준 보안 개체에 대한 사용 권한을 보고합니다.  
  
 GRANT OPTION을 지정하여 사용 권한이 부여된 보안 주체의 사용 권한을 취소할 경우 CASCADE를 지정하지 않으면 REVOKE 문이 실패합니다.  
  
## <a name="permissions"></a>Permissions  
 보안 개체에 대한 CONTROL 권한이 있는 보안 주체는 해당 보안 개체에 대한 사용 권한을 취소할 수 있습니다. 개체 소유자는 소유하고 있는 개체에 대한 사용 권한을 취소할 수 있습니다.  
  
 sysadmin 고정 서버 역할의 멤버와 같이 CONTROL SERVER 권한이 부여된 사용자는 서버의 모든 보안 개체에 대한 사용 권한을 취소할 수 있습니다. db_owner 고정 데이터베이스 역할의 멤버와 같이 데이터베이스에 대한 CONTROL 권한이 부여된 사용자는 데이터베이스의 모든 보안 개체에 대한 사용 권한을 취소할 수 있습니다. 스키마에 대한 CONTROL 권한이 부여된 사용자는 스키마 내의 모든 개체에 대한 사용 권한을 취소할 수 있습니다.  
  
##  <a name="securable"></a>보안 개체별 구문  
 다음 표에는 보안 개체와 보안 개체별 구문을 설명하는 항목 목록이 정리되어 있습니다.  
  
|보안 개체|항목|  
|---------------|-----------|  
|응용 프로그램 역할|[REVOKE 데이터베이스 보안 주체 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-database-principal-permissions-transact-sql.md)|  
|어셈블리|[REVOKE 어셈블리 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-assembly-permissions-transact-sql.md)|  
|비대칭 키|[REVOKE 비대칭 키 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-asymmetric-key-permissions-transact-sql.md)|  
|가용성 그룹|[REVOKE 가용성 그룹 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-availability-group-permissions-transact-sql.md)|  
|인증서|[REVOKE 인증서 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-certificate-permissions-transact-sql.md)|  
|계약|[REVOKE Service Broker 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-service-broker-permissions-transact-sql.md)|  
|데이터베이스|[REVOKE 데이터베이스 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-database-permissions-transact-sql.md)|  
|끝점|[REVOKE 끝점 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-endpoint-permissions-transact-sql.md)|  
|데이터베이스 범위 자격 증명|[REVOKE 데이터베이스 범위 자격 증명 (Transact SQL)](../../t-sql/statements/revoke-database-scoped-credential-transact-sql.md)|  
|전체 텍스트 카탈로그|[REVOKE 전체 텍스트 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-full-text-permissions-transact-sql.md)|  
|전체 텍스트 중지 목록|[REVOKE 전체 텍스트 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-full-text-permissions-transact-sql.md)|  
|함수|[REVOKE 개체 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-object-permissions-transact-sql.md)|  
|로그인|[REVOKE 서버 보안 주체 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-server-principal-permissions-transact-sql.md)|  
|메시지 유형|[REVOKE Service Broker 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-service-broker-permissions-transact-sql.md)|  
|개체|[REVOKE 개체 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-object-permissions-transact-sql.md)|  
|큐|[REVOKE 개체 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-object-permissions-transact-sql.md)|  
|원격 서비스 바인딩|[REVOKE Service Broker 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-service-broker-permissions-transact-sql.md)|  
|역할|[REVOKE 데이터베이스 보안 주체 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-database-principal-permissions-transact-sql.md)|  
|경로|[REVOKE Service Broker 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-service-broker-permissions-transact-sql.md)|  
|스키마|[REVOKE 스키마 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-schema-permissions-transact-sql.md)|  
|검색 속성 목록|[검색 속성 목록 사용 권한 &#40; 해지 Transact SQL &#41;](../../t-sql/statements/revoke-search-property-list-permissions-transact-sql.md)|  
|Server|[REVOKE 서버 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-server-permissions-transact-sql.md)|  
|서비스|[REVOKE Service Broker 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-service-broker-permissions-transact-sql.md)|  
|저장 프로시저|[REVOKE 개체 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-object-permissions-transact-sql.md)|  
|대칭 키|[REVOKE 대칭 키 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-symmetric-key-permissions-transact-sql.md)|  
|동의어|[REVOKE 개체 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-object-permissions-transact-sql.md)|  
|시스템 개체|[REVOKE 시스템 개체 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-system-object-permissions-transact-sql.md)|  
|테이블|[REVOKE 개체 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-object-permissions-transact-sql.md)|  
|형식|[REVOKE 유형 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-type-permissions-transact-sql.md)|  
|사용자|[REVOKE 데이터베이스 보안 주체 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-database-principal-permissions-transact-sql.md)|  
|보기|[REVOKE 개체 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-object-permissions-transact-sql.md)|  
|XML 스키마 컬렉션|[REVOKE XML 스키마 컬렉션 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-xml-schema-collection-permissions-transact-sql.md)|  
  
## <a name="see-also"></a>관련 항목:  
 [사용 권한 계층&#40;데이터베이스 엔진&#41;](../../relational-databases/security/permissions-hierarchy-database-engine.md)   
 [DENY&#40;Transact-SQL&#41;](../../t-sql/statements/deny-transact-sql.md)   
 [GRANT&#40;Transact-SQL&#41;](../../t-sql/statements/grant-transact-sql.md)   
 [sp_addlogin&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addlogin-transact-sql.md)   
 [sp_adduser&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-adduser-transact-sql.md)   
 [sp_changedbowner &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-changedbowner-transact-sql.md)   
 [sp_dropuser&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dropuser-transact-sql.md)   
 [sp_helprotect&#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-helprotect-transact-sql.md)   
 [sp_helpuser &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-helpuser-transact-sql.md)  
  
  
