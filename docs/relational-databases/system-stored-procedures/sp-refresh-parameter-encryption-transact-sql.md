---
title: sp_refresh_parameter_encryption (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 01/11/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: conceptual
f1_keywords:
- sp_refresh_parameter_encryption
- sp_refresh_parameter_encryption_TSQL
- sys.sp_refresh_parameter_encryption
- sys.sp_refresh_parameter_encryption_TSQL
helpviewer_keywords:
- sp_refresh_parameter_encryption
- Always Encrypted, sp_refresh_parameter_encryption
ms.assetid: 00b44baf-fcf0-4095-aabe-49fa87e77316
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: f483c6fe53ab980893ba8e1104b46e073336b027
ms.sourcegitcommit: c44014af4d3f821e5d7923c69e8b9fb27aeb1afd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58533985"
---
# <a name="sprefreshparameterencryption-transact-sql"></a>sp_refresh_parameter_encryption (Transact SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

매개 변수는 지정 된 비 스키마 바운드 저장된 프로시저, 사용자 정의 함수, 뷰, DML 트리거, 데이터베이스 수준 DDL 트리거 또는 서버 수준 DDL 트리거가 현재 데이터베이스에서 상시 암호화 메타 데이터를 업데이트합니다. 

 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
sys.sp_refresh_parameter_encryption [ @name = ] 'module_name' 
    [ , [ @namespace = ] '<class>' ]
[ ; ]

<class> ::=
{ DATABASE_DDL_TRIGGER | SERVER_DDL_TRIGGER }
```

## <a name="arguments"></a>인수

`[ @name = ] 'module_name'` 저장된 프로시저, 사용자 정의 함수, 뷰, DML 트리거, 데이터베이스 수준 DDL 트리거 또는 서버 수준 DDL 트리거 이름이입니다. *module_name* 는 CLR (공용 언어 런타임) 저장 프로시저 또는 CLR 함수 일 수 없습니다. *module_name* 스키마 바인딩할 수 없습니다. *module_name* 는 `nvarchar`, 기본값은 없습니다. *module_name* 다중 부분 식별자가 될 수 있지만 현재 데이터베이스의 개체만 참조할 수 있습니다.

`[ @namespace = ] ' < class > '` 지정된 된 모듈의 클래스가입니다. 때 *module_name* 이 DDL 트리거인 경우 `<class>` 필요 합니다. `<class>`가 `nvarchar(20)`인 경우 유효한 입력은 `DATABASE_DDL_TRIGGER` 고 `SERVER_DDL_TRIGGER`입니다.    

## <a name="return-code-values"></a>반환 코드 값  

0(성공) 또는 0이 아닌 수(실패)


## <a name="remarks"></a>Remarks

경우에 모듈의 매개 변수에 대 한 암호화 메타 데이터를 오래 커질 수 있습니다.   
* 암호화 속성 테이블에 있는 열의 모듈에 대 한 참조를 업데이트 되었습니다. 예를 들어, 삭제 된 열 및 동일한 이름 이지만 다른 암호화 유형을, 암호화 키 또는 암호화 알고리즘을 사용 하 여 새 열이 추가 되었습니다.  
* 모듈에는 오래 된 매개 변수 암호화 메타 데이터를 사용 하 여 다른 모듈 참조.  

테이블의 암호화 속성을 수정 하는 경우 `sp_refresh_parameter_encryption` 테이블을 직접 또는 간접적으로 참조 하는 모든 모듈에 대 한 실행 해야 합니다. 호출자에 게 진행 하기 전에 사용자가 첫 번째 새로 고침 내부 모듈 없이 순서에 관계 없이 해당 모듈에서이 저장된 프로시저를 호출할 수 있습니다.

`sp_refresh_parameter_encryption` 확장 속성, 어떠한 사용 권한도 영향을 주지 않습니다 또는 `SET` 개체와 연결 하는 옵션입니다. 

서버 수준 DDL 트리거를 새로 고치려면 아무 데이터베이스 컨텍스트에서 이 저장 프로시저를 실행하세요.

> [!NOTE]
>  실행할 때 개체와 연결 되어 있는 모든 서명이 삭제 됩니다 `sp_refresh_parameter_encryption`합니다.

## <a name="permissions"></a>사용 권한

필요 `ALTER` 모듈에 대 한 권한 및 `REFERENCES` 모든 CLR 사용자 정의 형식 및 개체에 의해 참조 되는 XML 스키마 컬렉션에 대 한 권한이 있습니다.   

데이터베이스 수준 DDL 트리거를 지정된 된 모듈을 사용 하는 경우 필요한 `ALTER ANY DATABASE DDL TRIGGER` 현재 데이터베이스의 권한입니다.    

서버 수준 DDL 트리거를 지정된 된 모듈을 사용 하는 경우 필요한 `CONTROL SERVER` 권한.

정의 된 모듈에 대 한 합니다 `EXECUTE AS` 절 `IMPERSONATE` 지정된 된 보안 주체에 권한이 필요 합니다. 일반적으로 개체를 새로 고치려면 변경 되지 않습니다 해당 `EXECUTE AS` 모듈을 사용 하 여 정의 된 경우가 아니면 주 `EXECUTE AS USER` 및 다른 사용자에 게 확인 수행 했던 것 보다 시 모듈이 만들어진 이제 보안 주체의 사용자 이름입니다.
 
## <a name="examples"></a>예

다음 예제에서는 테이블 및 테이블을 참조 하는 프로시저 상시 암호화를 구성 하 고 다음 테이블을 변경 하 고 실행을 보여 줍니다는 `sp_refresh_parameter_encryption` 프로시저입니다.  

먼저 초기 테이블 및 테이블을 참조 하는 저장된 프로시저를 만듭니다.
```sql
CREATE TABLE [Patients]([PatientID] [int] IDENTITY(1,1) NOT NULL,
    [SSN] [char](11), 
    [FirstName] [nvarchar](50) NULL,
    [LastName] [nvarchar](50) NOT NULL,
    [MiddleName] [nvarchar](50) NULL,
    [StreetAddress] [nvarchar](50) NOT NULL,
    [City] [nvarchar](50) NOT NULL,
    [ZipCode] [char](5) NOT NULL,
    [State] [char](2) NOT NULL,
    [BirthDate] [date] NOT NULL,
 CONSTRAINT [PK_Patients] PRIMARY KEY CLUSTERED 
(
    [PatientID] ASC
) WITH 
    (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, 
     IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, 
     ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY];
GO

CREATE PROCEDURE [find_patient] @SSN [char](11)
AS
BEGIN
    SELECT * FROM [Patients] WHERE SSN=@SSN
END;
GO
```

상시 암호화 키를 설정 합니다.
```sql
CREATE COLUMN MASTER KEY [CMK1]
WITH
(
       KEY_STORE_PROVIDER_NAME = N'MSSQL_CERTIFICATE_STORE',
    KEY_PATH = N'CurrentUser/my/A66BB0F6DD70BDFF02B62D0F87E340288E6F9305'
);
GO

CREATE COLUMN ENCRYPTION KEY [CEK1]
WITH VALUES
(
       COLUMN_MASTER_KEY = [CMK1],
    ALGORITHM = 'RSA_OAEP',
    ENCRYPTED_VALUE = 
       0x016E000001630075007200720065006E00740075007300650072002F006D0079002F006100360036006200620030006600360064006400370030006200640066006600300032006200360032006400300066003800370065003300340030003200380038006500360066003900330030003500CA0D0CEC74ECADD1804CF99137B4BD06BBAB15D7EA74E0C249A779C7768A5B659E0125D24FF827F5EA8CA517A8E197ECA1353BA814C2B0B2E6C8AB36E3AE6A1E972D69C3C573A963ADAB6686CF5D24F95FE43140C4F9AF48FBA7DF2D053F3B4A1F5693A1F905440F8015BDB43AF8A04BE4E045B89876A0097E5FBC4E6A3B9C3C0D278C540E46C53938B8C957B689C4DC095821C465C73117CBA95B758232F9E5B2FCC7950B8CA00AFE374DE42847E3FBC2FDD277035A2DEF529F4B735C20D980073B4965B4542A34723276A1646998FC6E1C40A3FDB6ABCA98EE2B447F114D2AC7FF8C7D51657550EC5C2BABFFE8429B851272086DCED94332CF18FA854C1D545A28B1EF4BE64F8E035175C1650F6FC5C4702ACF99850A4542B3747EAEC0CC726E091B36CE24392D801ECAA684DE344FECE05812D12CD72254A014D42D0EABDA41C89FC4F545E88B4B8781E5FAF40D7199D4842D2BFE904D209728ED4F527CBC169E2904F6E711FF81A8F4C25382A2E778DD2A58552ED031AFFDA9D9D891D98AD82155F93C58202FC24A77F415D4F8EF22419D62E188AC609330CCBD97CEE1AEF8A18B01958833604707FDF03B2B386487CC679D7E352D0B69F9FB002E51BCD814D077E82A09C14E9892C1F8E0C559CFD5FA841CEF647DAB03C8191DC46B772E94D579D8C80FE93C3827C9F0AE04D5325BC73111E07EEEDBE67F1E2A73580085
);
GO
```


마지막으로 실행 되 고 암호화 된 열을 사용 하 여 SSN 열을 바꿉니다는 `sp_refresh_parameter_encryption` Always Encrypted 구성 요소를 업데이트 하는 절차입니다.
```sql
ALTER TABLE [Patients] DROP COLUMN [SSN];
GO

ALTER TABLE [Patients] 
    ADD [SSN] [char](11) COLLATE Latin1_General_BIN2 
    ENCRYPTED WITH 
        (COLUMN_ENCRYPTION_KEY = [CEK1], 
        ENCRYPTION_TYPE = Deterministic, 
        ALGORITHM = 'AEAD_AES_256_CBC_HMAC_SHA_256') 
    NOT NULL;
GO

EXEC sp_refresh_parameter_encryption [find_patient];
GO
```

## <a name="see-also"></a>관련 항목 

[상시 암호화](../../relational-databases/security/encryption/always-encrypted-database-engine.md)   
[Always Encrypted 마법사](../../relational-databases/security/encryption/always-encrypted-wizard.md)   

