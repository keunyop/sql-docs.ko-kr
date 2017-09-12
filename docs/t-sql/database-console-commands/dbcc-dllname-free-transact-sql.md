---
title: DBCC dllname (FREE) (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/16/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- dbcc_dllname_(FREE)_TSQL
- dllname
- dbcc dllname (FREE)
- FREE
- dbcc_dllname(FREE)_TSQL
- FREE_TSQL
- dllname_TSQL
- dbcc dllname(FREE)
dev_langs:
- TSQL
helpviewer_keywords:
- DLL unloading [SQL Server]
- DBCC dllname (FREE)
- freeing DLLs
- unloading DLLs
ms.assetid: 1eb71c17-fe15-430b-8916-e4e312dcf9c0
caps.latest.revision: 27
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: e6d70bdab3515c883ea6f541ece6857f8ecda914
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="dbcc-dllname-free-transact-sql"></a>DBCC dllname(FREE)(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]지정 된 확장된 저장된 프로시저 DLL 메모리에서 언로드합니다.
  
![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>구문  
```sql
DBCC <dllname> ( FREE ) [ WITH NO_INFOMSGS ]  
```  
  
## <a name="arguments"></a>인수  
 \<*dllname*>  
 메모리에서 해제할 DLL의 이름입니다.  
  
 WITH NO_INFOMSGS  
 모든 정보 메시지를 표시하지 않습니다.  
  
## <a name="remarks"></a>주의
확장 저장 프로시저를 실행하면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스가 로드한 DLL은 서버가 종료될 때까지 그대로 유지됩니다. 이 문은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]를 종료하지 않아도 메모리에서 DLL을 언로드할 수 있도록 허용합니다. 현재 로드 한 DLL 파일을 표시 하려면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], 실행 **sp_helpextendedproc**
  
## <a name="result-sets"></a>결과 집합  
유효한 DLL을 지정 하면 DBCC *dllname* (FREE) 반환 합니다.
  
```sql
DBCC execution completed. If DBCC printed error messages, contact your system administrator.  
```  
  
## <a name="permissions"></a>Permissions  
**sysadmin** 고정 서버 역할의 멤버 또는 **db_owner** 고정 데이터베이스 역할의 멤버여야 합니다.
  
## <a name="examples"></a>예  
다음 예에서는 가정 `xp_sample` xp_sample.dll로 구현 하 고 실행 합니다. DBCC \< *dllname*>과 연결 된 xp_sample.dll 파일 (FREE) 언로드는 `xp_sample` 확장 프로시저입니다.
  
```sql  
DBCC xp_sample (FREE);  
```  
  
## <a name="see-also"></a>관련 항목:  
[DBCC&#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-transact-sql.md)  
[확장 저장 프로시저의 실행 특징](../../relational-databases/extended-stored-procedures-programming/execution-characteristics-of-extended-stored-procedures.md)  
[sp_addextendedproc &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql.md)  
[sp_dropextendedproc &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql.md)  
[sp_helpextendedproc &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-helpextendedproc-transact-sql.md)  
[저장 프로시저 DLL 언로드 확장](../../relational-databases/extended-stored-procedures-programming/unloading-an-extended-stored-procedure-dll.md)
  
  
