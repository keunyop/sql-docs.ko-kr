---
title: sys.dm_cryptographic_provider_algorithms (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dm_cryptographic_provider_algorithms_TSQL
- sys.dm_cryptographic_provider_algorithms
- sys.dm_cryptographic_provider_algorithms_TSQL
- dm_cryptographic_provider_algorithms
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_cryptographic_provider_algorithms dynamic management function
ms.assetid: 8bcccb37-5cfb-4e1e-a0bb-7ff4c279fe8e
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: cb48a9f0f7e30e6df4fa09485b9e0ea0c9fc8a56
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47699211"
---
# <a name="sysdmcryptographicprovideralgorithms-transact-sql"></a>sys.dm_cryptographic_provider_algorithms(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  EKM(확장 가능 키 관리) 공급자가 지원하는 알고리즘을 반환합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sys.dm_cryptographic_provider_algorithms ( provider_id )  
```  
  
## <a name="arguments"></a>인수  
 *provider_id*  
 EKM 공급자의 ID 번호이며 기본값은 없습니다.  
  
## <a name="tables-returned"></a>반환된 테이블  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|algorithm_id|**int**|알고리즘의 ID 번호입니다.|  
|algorithm_tag|**nvarchar(60)**|알고리즘의 ID 태그입니다.|  
|key_type|**nvarchar(128)**|키 입력을 표시합니다. ASYMMETRIC KEY 또는 SYMMETRIC KEY를 반환합니다.|  
|key_length|**int**|키 길이(비트)를 나타냅니다.|  
  
## <a name="permissions"></a>사용 권한  
 사용자는 공용 데이터베이스 역할의 멤버여야 합니다.  
  
## <a name="examples"></a>예  
 다음 예제에서는 ID 번호 `1234567`과 함께 공급자에 대한 공급자 옵션을 표시합니다.  
  
```  
SELECT * FROM sys.dm_cryptographic_provider_algorithms(1234567);  
GO  
```  
  
## <a name="see-also"></a>관련 항목  
 [확장 가능 키 관리 &#40;EKM&#41;](../../relational-databases/security/encryption/extensible-key-management-ekm.md)   
 [보안 관련 동적 관리 뷰 및 함수&#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/security-related-dynamic-management-views-and-functions-transact-sql.md)  
  
  
