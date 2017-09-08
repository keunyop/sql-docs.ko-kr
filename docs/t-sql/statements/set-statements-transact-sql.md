---
title: "SET 문 (Transact SQL) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SET
- SET_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- ISO SET statements
- queries [SQL Server], executing
- dates [SQL Server], SET statements
- time [SQL Server], SET statements
- SET statement, about SET statement
- SET statement
- statistical information [SQL Server], SET statements
- locking [SQL Server], SET statements
ms.assetid: f7e107f8-0fcf-408b-b30f-da2323eeb714
caps.latest.revision: 38
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: f0426730b33f0b70fda11a8cb07242a365d10fae
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="set-statements-transact-sql"></a>SET 문(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[tsql](../../includes/tsql-md.md)] 프로그래밍 언어는 특정 정보를 처리하는 현재 세션을 변경할 수 있는 몇 가지 SET 문을 제공합니다. SET 문은 다음 표에 표시된 범주별로 그룹화됩니다.  
  
 SET 문 사용 하 여 지역 변수를 설정 하는 방법에 대 한 정보를 참조 하십시오. [설정 @local_variable &#40; Transact SQL &#41; ](../../t-sql/language-elements/set-local-variable-transact-sql.md).  
  
|범주|문|  
|--------------|----------------|  
|날짜 및 시간 문|[SET DATEFIRST](../../t-sql/statements/set-datefirst-transact-sql.md)<br /><br /> [SET DATEFORMAT](../../t-sql/statements/set-dateformat-transact-sql.md)|  
|잠금 문|[SET DEADLOCK_PRIORITY](../../t-sql/statements/set-deadlock-priority-transact-sql.md)<br /><br /> [SET LOCK_TIMEOUT](../../t-sql/statements/set-lock-timeout-transact-sql.md)|  
|기타 문|[SET CONCAT_NULL_YIELDS_NULL](../../t-sql/statements/set-concat-null-yields-null-transact-sql.md)<br /><br /> [SET CURSOR_CLOSE_ON_COMMIT 옵션](../../t-sql/statements/set-cursor-close-on-commit-transact-sql.md)<br /><br /> [SET FIPS_FLAGGER](../../t-sql/statements/set-fips-flagger-transact-sql.md)<br /><br /> [SET IDENTITY_INSERT](../../t-sql/statements/set-identity-insert-transact-sql.md)<br /><br /> [언어 설정](../../t-sql/statements/set-language-transact-sql.md)<br /><br /> [집합 오프셋](../../t-sql/statements/set-offsets-transact-sql.md)<br /><br /> [SET QUOTED_IDENTIFIER](../../t-sql/statements/set-quoted-identifier-transact-sql.md)|  
|쿼리 실행 문|[SET ARITHABORT](../../t-sql/statements/set-arithabort-transact-sql.md)<br /><br /> [SET ARITHIGNORE 옵션](../../t-sql/statements/set-arithignore-transact-sql.md)<br /><br /> [SET FMTONLY](../../t-sql/statements/set-fmtonly-transact-sql.md)<br /><br /> 참고:[!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]<br /><br /> [SET NOCOUNT](../../t-sql/statements/set-nocount-transact-sql.md)<br /><br /> [SET NOEXEC](../../t-sql/statements/set-noexec-transact-sql.md)<br /><br /> [SET NUMERIC_ROUNDABORT](../../t-sql/statements/set-numeric-roundabort-transact-sql.md)<br /><br /> [SET PARSEONLY](../../t-sql/statements/set-parseonly-transact-sql.md)<br /><br /> [SET QUERY_GOVERNOR_COST_LIMIT](../../t-sql/statements/set-query-governor-cost-limit-transact-sql.md)<br /><br /> [SET ROWCOUNT](../../t-sql/statements/set-rowcount-transact-sql.md)<br /><br /> [SET TEXTSIZE](../../t-sql/statements/set-textsize-transact-sql.md)|  
|ISO 설정 문|[SET ANSI_DEFAULTS](../../t-sql/statements/set-ansi-defaults-transact-sql.md)<br /><br /> [SET ANSI_NULL_DFLT_OFF](../../t-sql/statements/set-ansi-null-dflt-off-transact-sql.md)<br /><br /> [SET ANSI_NULL_DFLT_ON](../../t-sql/statements/set-ansi-null-dflt-on-transact-sql.md)<br /><br /> [SET ANSI_NULLS](../../t-sql/statements/set-ansi-nulls-transact-sql.md)<br /><br /> [SET ANSI_PADDING](../../t-sql/statements/set-ansi-padding-transact-sql.md)<br /><br /> [SET ANSI_WARNINGS](../../t-sql/statements/set-ansi-warnings-transact-sql.md)|  
|통계 문|[SET FORCEPLAN](../../t-sql/statements/set-forceplan-transact-sql.md)<br /><br /> [SET SHOWPLAN_ALL](../../t-sql/statements/set-showplan-all-transact-sql.md)<br /><br /> [SET SHOWPLAN_TEXT 옵션](../../t-sql/statements/set-showplan-text-transact-sql.md)<br /><br /> [SET SHOWPLAN_XML](../../t-sql/statements/set-showplan-xml-transact-sql.md)<br /><br /> [SET STATISTICS IO](../../t-sql/statements/set-statistics-io-transact-sql.md)<br /><br /> [SET STATISTICS XML](../../t-sql/statements/set-statistics-xml-transact-sql.md)<br /><br /> [SET STATISTICS PROFILE](../../t-sql/statements/set-statistics-profile-transact-sql.md)<br /><br /> [SET STATISTICS TIME](../../t-sql/statements/set-statistics-time-transact-sql.md)|  
|트랜잭션 문|[SET IMPLICIT_TRANSACTIONS](../../t-sql/statements/set-implicit-transactions-transact-sql.md)<br /><br /> [SET REMOTE_PROC_TRANSACTIONS](../../t-sql/statements/set-remote-proc-transactions-transact-sql.md)<br /><br /> [SET TRANSACTION ISOLATION LEVEL](../../t-sql/statements/set-transaction-isolation-level-transact-sql.md)<br /><br /> [SET XACT_ABORT](../../t-sql/statements/set-xact-abort-transact-sql.md)|  
  
## <a name="considerations-when-you-use-the-set-statements"></a>SET 문 사용 시 고려 사항  
  
-   SET FIPS_FLAGGER, SET OFFSETS, SET PARSEONLY 및 SET QUOTED_IDENTIFIER를 제외한 모든 SET 문은 실행 시간 또는 런타임에 구현됩니다. 이러한 문은 구문 분석 시 구현됩니다.  
  
-   저장 프로시저에 또는 트리거에서 SET 문을 실행하면 저장 프로시저 또는 트리거에서 컨트롤이 반환된 후 SET 옵션 값이 복원됩니다. 또한 SET 문을 사용 하 여 실행 되는 동적 SQL 문자열에 지정 된 경우 **sp_executesql** 또는 동적 SQL 문자열에 지정 된 일괄 처리에서 컨트롤이 반환 된 후 실행, SET 옵션의 값이 복원 됩니다.  
  
-   저장 프로시저는 SET ANSI_NULLS와 SET QUOTED_IDENTIFIER를 제외한 실행 시간에 지정된 SET 설정으로 실행됩니다. SET ANSI_NULLS나 SET QUOTED_IDENTIFIER를 지정하는 저장 프로시저는 저장 프로시저를 만든 시간에 지정된 설정을 사용합니다. SET 설정을 저장 프로시저 내에서 사용하면 모두 무시됩니다.  
  
-   **사용자 옵션** 설정인 **sp_configure** 서버 차원의 설정은 수 있으며 여러 데이터베이스에 걸쳐 작동 합니다. 또한 이 설정은 로그인 시간에 발생할 경우를 제외하고 명시적 SET 문과 같이 작동합니다.  
  
-   ALTER DATABASE를 사용하여 지정한 데이터베이스 설정은 데이터베이스 수준에서만 유효하며 명시적으로 설정된 경우에만 적용됩니다. 데이터베이스 설정을 사용 하 여 설정 인스턴스 옵션 설정 보다 우선 **sp_configure**합니다.  
  
-   SET 문 중 하나라도 ON이나 OFF로 설정하면 여러 SET 옵션을 ON 또는 OFF로 설정할 수 있습니다.  
  
    > [!NOTE]  
    >  통계 관련 SET 옵션에는 적용되지 않습니다.  
  
     예를 들어 `SET QUOTED_IDENTIFIER, ANSI_NULLS ON` 은 QUOTED_IDENTIFIER 및 ANSI_NULLS를 ON으로 설정 합니다.  
  
-   SET 문 설정은 ALTER DATABASE를 사용하여 설정한 해당 데이터베이스 옵션 설정보다 우선 적용됩니다. 예를 들어 SET ANSI_NULLS 문에서 지정한 값은 ANSI_NULL에 대한 데이터베이스 설정보다 우선 적용됩니다. 또한, 일부 연결 설정은 자동으로 설정 됩니다에 사용자가 이전에 사용한 값을 기반으로 데이터베이스를 연결할 때는 **sp_configure 사용자 옵션** 설정 또는 모든 ODBC에 적용 되는 값 및 OLE/DB 연결 합니다.  
  
-   ALTER, CREATE 및 DROP DATABASE 문은 SET LOCK_TIMEOUT 설정을 인식하지 못합니다.  
  
-   전역 또는 바로 가기 SET 문(예: SET ANSI_DEFAULTS)은 여러 개의 설정을 설정해 바로 가기 SET 문이 이 문에 의해 영향을 받은 모든 옵션에 대해 이전 설정을 되돌리도록 합니다. 바로 가기 SET 문이 실행된 후 바로 가기 SET 문에 의해 영향을 받은 개별 SET 옵션을 명시적으로 설정하면 이 SET 문은 해당 바로 가기 설정보다 우선 적용됩니다.  
  
-   일괄 처리를 사용하면 USE 문을 사용해 만든 일괄 처리에 의해 데이터베이스 컨텍스트가 결정됩니다. 임의 쿼리 및 저장 프로시저 외부에서 실행되고 일괄 처리되는 다른 모든 문은 USE 문을 사용해 만든 연결 및 데이터베이스 옵션 설정을 따릅니다.  
  
-   MARS(Multiple Active Result Set) 요청은 최신 세션 SET 옵션 설정이 포함된 전역 상태를 공유합니다. 각 요청을 실행하면 SET 옵션을 수정할 수 있습니다. 변경 내용은 이 옵션이 설정된 요청 컨텍스트에만 적용되며 다른 동시 MARS 요청에는 영향을 주지 않습니다. 그러나 요청 실행을 완료한 후 새 SET 옵션이 전역 세션 상태로 복사됩니다. 이 변경 작업 후 같은 세션에서 실행되는 새 요청은 이러한 새 SET 옵션 설정을 사용합니다.  
  
-   일괄 처리 또는 다른 저장 프로시저의 저장 프로시저를 실행하면 저장 프로시저가 포함된 데이터베이스에 현재 설정된 옵션 값에 따라 실행됩니다. 예를 들어, 저장 프로시저 **db1.dbo.sp1** 저장된 프로시저를 호출 **db2.dbo.sp2**, 저장 프로시저 **sp1** 현재 호환성 수준에서 실행 된 데이터베이스의 설정 **db1**, 저장 프로시저 및 **sp2** 데이터베이스의 현재 호환성 수준 설정에서 실행 된 **db2**합니다.  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] 문이 여러 데이터베이스에 있는 개체를 참조할 경우 현재 데이터베이스 컨텍스트 및 현재 연결 컨텍스트가 이 문에 적용됩니다. 이러한 경우 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문이 일괄 처리에 있을 경우 현재 연결 컨텍스트는 USE 문으로 정의된 데이터베이스입니다. [!INCLUDE[tsql](../../includes/tsql-md.md)] 문이 저장 프로시저에 있을 경우 연결 컨텍스트는 이 저장 프로시저가 포함된 데이터베이스입니다.  
  
-   계산 열이나 인덱싱된 뷰에서 인덱스를 만들고 조작할 때는 ARITHABORT, CONCAT_NULL_YIELDS_NULL, QUOTED_IDENTIFIER, ANSI_NULLS, ANSI_PADDING 및 ANSI_WARNINGS SET 옵션을 ON으로 설정해야 합니다. NUMERIC_ROUNDABORT 옵션은 OFF로 설정해야 합니다.  
  
     이 옵션 중 하나라도 필요한 값으로 설정하지 않으면 인덱싱된 뷰나 계산 열에 인덱스가 있는 테이블에서의 INSERT, UPDATE, DELETE, DBCC CHECKDB 및 DBCC CHECKTABLE 동작이 실패합니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]는 잘못 설정된 모든 옵션을 나열하는 오류 메시지를 표시합니다. 또한 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서는 옵션이 잘못 설정된 테이블이나 인덱싱된 뷰에 대해 계산 열이나 뷰에 이러한 인덱스가 존재하지 않는 것처럼 SELECT 문을 처리합니다.  
  
  