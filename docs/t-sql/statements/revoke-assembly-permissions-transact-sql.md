---
title: REVOKE Assembly Permissions(Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 07/26/2017
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- REVOKE statement, assemblies
- assemblies [CLR integration], permissions
ms.assetid: f88e9da1-2c0b-4bdd-9ec5-44467707cb46
author: VanMSFT
ms.author: vanto
manager: craigg
ms.openlocfilehash: f10a5ac6202e635d69756fa57430109c7459e353
ms.sourcegitcommit: c6e71ed14198da67afd7ba722823b1af9b4f4e6f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54326444"
---
# <a name="revoke-assembly-permissions-transact-sql"></a>REVOKE 어셈블리 권한(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  어셈블리에 대한 사용 권한을 취소합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
REVOKE [ GRANT OPTION FOR ] permission [ ,...n ]   
    ON ASSEMBLY :: assembly_name   
    { TO | FROM } database_principal [ ,...n ]  
    [ CASCADE ]  
    [ AS revoking_principal ]  
```  
  
## <a name="arguments"></a>인수  
 GRANT OPTION FOR  
 지정된 사용 권한을 부여 또는 거부할 수 있는 권한이 취소됨을 나타냅니다. 사용 권한 자체는 취소되지 않습니다.  
  
> [!IMPORTANT]  
>  보안 주체에 GRANT 옵션 없이 지정된 사용 권한이 있는 경우 사용 권한 자체가 취소됩니다.  
  
 *permission*  
 어셈블리에 대해 취소할 수 있는 사용 권한을 지정합니다. 아래와 같습니다.  
  
 ON ASSEMBLY **::**_assembly_name_  
 사용 권한을 취소할 어셈블리를 지정합니다. 범위 한정자 **::** 가 필요합니다.  
  
 *database_principal*  
 사용 권한을 취소할 보안 주체를 지정합니다. 다음 중 하나일 수 있습니다.  
  
-   데이터베이스 사용자  
  
-   데이터베이스 역할  
  
-   애플리케이션 역할  
  
-   Windows 로그인에 매핑된 데이터베이스 사용자  
  
-   Windows 그룹에 매핑된 데이터베이스 사용자  
  
-   인증서에 매핑된 데이터베이스 사용자  
  
-   비대칭 키에 매핑된 데이터베이스 사용자  
  
-   서버 보안 주체에 매핑되지 않은 데이터베이스 사용자  
  
 CASCADE  
 사용 권한이 취소된 보안 주체에게 사용 권한을 부여 받거나 거부당한 다른 보안 주체의 사용 권한도 취소됨을 나타냅니다.  
  
> [!CAUTION]  
>  WITH GRANT OPTION을 부여 받은 사용 권한이 연계되어 취소되면 해당 사용 권한의 GRANT 및 DENY가 모두 취소됩니다.  
  
 AS *revoking_principal*  
 이 쿼리를 실행하는 보안 주체가 사용 권한을 취소하는 권한을 부여할 수 있는 다른 보안 주체를 지정합니다. 다음 중 하나일 수 있습니다.  
  
-   데이터베이스 사용자  
  
-   데이터베이스 역할  
  
-   애플리케이션 역할  
  
-   Windows 로그인에 매핑된 데이터베이스 사용자  
  
-   Windows 그룹에 매핑된 데이터베이스 사용자  
  
-   인증서에 매핑된 데이터베이스 사용자  
  
-   비대칭 키에 매핑된 데이터베이스 사용자  
  
-   서버 보안 주체에 매핑되지 않은 데이터베이스 사용자  
  
## <a name="remarks"></a>Remarks  
 어셈블리는 사용 권한 계층에서 부모 데이터베이스에 포함된 데이터베이스 수준 보안 개체입니다. 아래에는 어셈블리에서 취소할 수 있는 가장 제한적인 특정 사용 권한이 의미상 이러한 사용 권한을 포함하는 보다 일반적인 사용 권한이 함께 나열되어 있습니다.  
  
|어셈블리 사용 권한|어셈블리 사용 권한에 포함된 사용 권한|데이터베이스 사용 권한에 포함된 사용 권한|  
|-------------------------|------------------------------------|------------------------------------|  
|CONTROL|CONTROL|CONTROL|  
|TAKE OWNERSHIP|CONTROL|CONTROL|  
|ALTER|CONTROL|ALTER ANY ASSEMBLY|  
|REFERENCES|CONTROL|REFERENCES|  
|VIEW DEFINITION|CONTROL|VIEW DEFINITION|  
  
## <a name="permissions"></a>Permissions  
 어셈블리에 대한 CONTROL 사용 권한이 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DENY&#40;Transact-SQL&#41;](../../t-sql/statements/deny-transact-sql.md)   
 [사용 권한&#40;데이터베이스 엔진&#41;](../../relational-databases/security/permissions-database-engine.md)   
 [보안 주체&#40;데이터베이스 엔진&#41;](../../relational-databases/security/authentication-access/principals-database-engine.md)   
 [CREATE ASSEMBLY&#40;Transact-SQL&#41;](../../t-sql/statements/create-assembly-transact-sql.md)   
 [CREATE CERTIFICATE&#40;Transact-SQL&#41;](../../t-sql/statements/create-certificate-transact-sql.md)   
 [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-asymmetric-key-transact-sql.md)   
 [CREATE APPLICATION ROLE &#40;Transact-SQL&#41;](../../t-sql/statements/create-application-role-transact-sql.md)   
 [암호화 계층](../../relational-databases/security/encryption/encryption-hierarchy.md)  
  
  
