---
title: sys.fn_cdc_decrement_lsn (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- fn_cdc_decrement_lsn
- sys.fn_cdc_decrement_lsn_TSQL
- sys.fn_cdc_decrement_lsn
- fn_cdc_decrement_lsn_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- fn_cdc_decrement_lsn
- sys.fn_cdc_decrement_lsn
ms.assetid: 83c182ad-4713-439b-8769-9b7408aec8b4
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 2bfbe04376b71401694eb8bea025b8418cfea643
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47636541"
---
# <a name="sysfncdcdecrementlsn-transact-sql"></a>sys.fn_cdc_decrement_lsn(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  지정된 LSN를 기준으로 시퀀스의 이전 LSN(로그 시퀀스 번호)을 반환합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sys.fn_cdc_decrement_lsn ( lsn_value )  
```  
  
## <a name="arguments"></a>인수  
 *lsn_value*  
 LSN 값 *lsn_value* 됩니다 **binary(10)로 표현**합니다.  
  
## <a name="return-type"></a>반환 형식  
 **binary(10)**  
  
## <a name="remarks"></a>Remarks  
 이 함수에 의해 반환된 LSN은 지정된 값보다 항상 작으며 두 값 사이에는 LSN 값이 존재할 수 없습니다.  
  
## <a name="permissions"></a>사용 권한  
 멤버 자격이 필요 합니다 **공용** 데이터베이스 역할.  
  
## <a name="examples"></a>예  
 다음 예에서는 `sys.fn_cdc_decrement_lsn`을 사용하여 최대 LSN 값보다 작은 LSN 값을 갖는 변경 데이터 행을 반환하는 쿼리에서 LSN 상한을 설정합니다.  
  
```  
Use AdventureWorks2012;  
GO  
DECLARE @from_lsn binary(10), @to_lsn binary(10);  
SET @from_lsn = sys.fn_cdc_get_min_lsn('HumanResources_Employee');  
SET @to_lsn = sys.fn_cdc_decrement_lsn(sys.fn_cdc_get_max_lsn());  
SELECT * FROM cdc.fn_cdc_get_all_changes_HumanResources_Employee( @from_lsn, @to_lsn, 'all');   
GO  
```  
  
## <a name="see-also"></a>관련 항목  
 [sys.fn_cdc_increment_lsn &#40;TRANSACT-SQL&#41;](../../relational-databases/system-functions/sys-fn-cdc-increment-lsn-transact-sql.md)   
 [sys.fn_cdc_get_min_lsn &#40;TRANSACT-SQL&#41;](../../relational-databases/system-functions/sys-fn-cdc-get-min-lsn-transact-sql.md)   
 [sys.fn_cdc_get_max_lsn &#40;TRANSACT-SQL&#41;](../../relational-databases/system-functions/sys-fn-cdc-get-max-lsn-transact-sql.md)   
 [트랜잭션 로그&#40;SQL Server&#41;](../../relational-databases/logs/the-transaction-log-sql-server.md)   
 [변경 데이터 캡처 정보&#40;SQL Server&#41;](../../relational-databases/track-changes/about-change-data-capture-sql-server.md)  
  
  
