---
title: HASHBYTES(Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 07/29/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- HASHBYTES_TSQL
- HASHBYTES
dev_langs:
- TSQL
helpviewer_keywords:
- hash input
- HASHBYTES
ms.assetid: 0ea6a4d1-313e-4f70-b939-dd2cd570f6d6
author: MashaMSFT
ms.author: mathoma
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: ee8626047df76aaf9186295c092623a7cee6d263
ms.sourcegitcommit: 7c052fc969d0f2c99ad574f99076dc1200d118c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2019
ms.locfileid: "55570666"
---
# <a name="hashbytes-transact-sql"></a>HASHBYTES(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 해당 입력의 MD2, MD4, MD5, SHA, SHA1 또는 SHA2 해시를 반환합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
HASHBYTES ( '<algorithm>', { @input | 'input' } )  
  
<algorithm>::= MD2 | MD4 | MD5 | SHA | SHA1 | SHA2_256 | SHA2_512   
```  
  
## <a name="arguments"></a>인수  
 **'**\<algorithm>**'**  
 입력 해시에 사용할 해싱 알고리즘을 나타냅니다. 필수 인수이며 기본값은 없습니다. 작은따옴표가 필요합니다. [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)]부터 SHA2_256 및 SHA2_512 이외의 알고리즘은 사용되지 않습니다. 이전 알고리즘(권장하지 않음)은 계속 작동하지만 사용 중단 이벤트가 발생합니다.  
  
 **@input**  
 해시할 데이터를 포함하는 변수를 지정합니다. **@input**은 **varchar**, **nvarchar** 또는 **varbinary**입니다.  
  
 **'** *input* **'**  
 해시할 문자 또는 이진 문자열로 계산되는 식을 지정합니다.  
  
 출력은 MD2, MD4 및 MD5의 경우 128비트(16바이트), SHA 및 SHA1의 경우 160비트(20바이트), SHA2_256의 경우 256비트(32바이트), 그리고 SHA2_512의 경우 512비트(64바이트) 알고리즘 표준을 준수합니다.  
  
**적용 대상**: [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]부터 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]까지
  
 [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] 이하 버전에 허용되는 입력 값은 8000바이트로 제한됩니다.  
  
## <a name="return-value"></a>반환 값  
 **varbinary**(최대 8000바이트)  

## <a name="remarks"></a>Remarks  
해시 값을 계산하는 다른 방법으로 `CHECKSUM` 또는 `BINARY_CHECKSUM`을 사용하는 것이 좋습니다.

MD2, MD4, MD5, SHA 및 SHA1 알고리즘은 호환성 수준 130 이상에서 사용할 수 없습니다. 대신에 SHA2_256 또는 SHA2_512를 사용합니다.

## <a name="examples"></a>예  
### <a name="return-the-hash-of-a-variable"></a>변수의 해시 반환  
 다음 예에서는 변수 `@HashThis`에 저장된 **nvarchar** 데이터의 `SHA1` 해시를 반환합니다.  
  
```sql  
DECLARE @HashThis nvarchar(4000);  
SET @HashThis = CONVERT(nvarchar(4000),'dslfdkjLK85kldhnv$n000#knf');  
SELECT HASHBYTES('SHA1', @HashThis);  
```  
  
### <a name="return-the-hash-of-a-table-column"></a>테이블 열의 해시 반환  
 다음 예에서는 `c1` 테이블의 `Test1` 열에 있는 값의 SHA1 해시를 반환합니다.  
  
```sql  
CREATE TABLE dbo.Test1 (c1 nvarchar(50));  
INSERT dbo.Test1 VALUES ('This is a test.');  
INSERT dbo.Test1 VALUES ('This is test 2.');  
SELECT HASHBYTES('SHA1', c1) FROM dbo.Test1;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
-------------------------------------------  
0x0E7AAB0B4FF0FD2DFB4F0233E2EE7A26CD08F173  
0xF643A82F948DEFB922B12E50B950CEE130A934D6  
  
(2 row(s) affected)  
```  
  
## <a name="see-also"></a>참고 항목  
[암호화 알고리즘 선택](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md)  
[CHECKSUM_AGG&#40;Transact-SQL&#41;](../../t-sql/functions/checksum-agg-transact-sql.md)  
[CHECKSUM&#40;Transact-SQL&#41;](../../t-sql/functions/checksum-transact-sql.md)  
[BINARY_CHECKSUM&#40;Transact-SQL&#41;](../../t-sql/functions/binary-checksum-transact-sql.md)  
  
