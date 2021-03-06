---
title: sp_dropmessage (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_dropmessage_TSQL
- sp_dropmessage
dev_langs:
- TSQL
helpviewer_keywords:
- sp_dropmessage
ms.assetid: 17287a15-cdde-43d1-bb18-9f920bc15db8
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: b36c576fb5bb3bb3cc168430902223802ca937a3
ms.sourcegitcommit: c44014af4d3f821e5d7923c69e8b9fb27aeb1afd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58535175"
---
# <a name="spdropmessage-transact-sql"></a>sp_dropmessage(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] 인스턴스에서 지정한 사용자 정의 오류 메시지를 삭제합니다. 사용 하 여 사용자 정의 메시지를 볼 수 있습니다 합니다 **sys.messages** 카탈로그 뷰에 있습니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_dropmessage [ @msgnum = ] message_number  
    [ , [ @lang = ] 'language' ]  
```  
  
## <a name="arguments"></a>인수  
`[ @msgnum = ] message_number` 삭제할 메시지 번호가입니다. *message_number* 메시지 번호가 50000 보다 커야 하는 사용자 정의 메시지 여야 합니다. *message_number* 됩니다 **int**, 기본값은 NULL입니다.  
  
`[ @lang = ] 'language'` 삭제할 메시지의 언어가입니다. 하는 경우 **모든** 지정 된 모든 언어 버전의 *message_number* 삭제 됩니다. *언어* 됩니다 **sysname**, 기본값은 NULL입니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 1(실패)  
  
## <a name="result-sets"></a>결과 집합  
 없음  
  
## <a name="permissions"></a>사용 권한  
 멤버 자격이 필요 합니다 **sysadmin** 하 고 **serveradmin** 고정 서버 역할입니다.  
  
## <a name="remarks"></a>Remarks  
 경우가 아니면 **모든** 에 대해 지정 된 *언어*모든 언어, 미국 메시지의 버전을 삭제 해야 미국의 영어 버전을 삭제할 수 있습니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-dropping-a-user-defined-message"></a>1. 사용자 정의 메시지 삭제  
 다음 예제에서는 수를 사용자 정의 메시지 삭제 `50001`에서 **sys.messages**합니다.  
  
```  
USE master;  
GO  
EXEC sp_dropmessage 50001;  
```  
  
### <a name="b-dropping-a-user-defined-message-that-includes-a-localized-version"></a>2. 다른 언어 버전을 포함하는 사용자 정의 메시지 삭제  
 다음 예에서는 메시지의 해당 언어 버전을 포함한 메시지 번호가 `60000`인 사용자 정의 메시지를 삭제합니다.  
  
```  
USE master;  
GO  
  
-- Create a user-defined message in U.S. English  
EXEC sp_addmessage   
    @msgnum = 60000,  
    @severity = 16,  
    @msgtext = N'The item named %s already exists in %s.',   
    @lang = 'us_english';  
  
-- Create a localized version of the same message.  
EXEC sp_addmessage   
    @msgnum = 60000,  
    @severity = 16,  
    @msgtext = N'L''élément nommé %1! existe déjà dans %2!',  
    @lang = 'French';  
GO  
  
-- This statement will fail as long as the localized version  
-- of the message exists.  
EXEC sp_dropmessage 60000;  
GO  
  
-- This statement will drop the message.  
EXEC sp_dropmessage  
    @msgnum = 60000,  
    @lang = 'all';  
GO  
```  
  
### <a name="c-dropping-a-localized-version-of-a-user-defined-message"></a>3. 사용자 정의 메시지의 다른 언어 버전 삭제  
 다음 예에서는 전체 메시지를 삭제하지 않고 메시지 번호가 `60000`인 사용자 정의 메시지의 다른 언어 버전을 삭제합니다.  
  
```  
USE master;  
GO  
  
-- Create a user-defined message in U.S. English  
EXEC sp_addmessage   
    @msgnum = 60000,  
    @severity = 16,  
    @msgtext = N'The item named %s already exists in %s.',   
    @lang = 'us_english';  
  
-- Create a localized version of the same message.  
EXEC sp_addmessage   
    @msgnum = 60000,  
    @severity = 16,  
    @msgtext = N'L''élément nommé %1! existe déjà dans %2!',  
    @lang = 'French';  
GO  
-- This statement will remove only the localized version of the   
-- message.  
EXEC sp_dropmessage  
    @msgnum = 60000,  
    @lang = 'French';  
GO  
```  
  
## <a name="see-also"></a>관련 항목  
 [RAISERROR&#40;Transact-SQL&#41;](../../t-sql/language-elements/raiserror-transact-sql.md)   
 [sp_addmessage &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addmessage-transact-sql.md)   
 [sp_altermessage &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-altermessage-transact-sql.md)   
 [FORMATMESSAGE &#40;Transact-SQL&#41;](../../t-sql/functions/formatmessage-transact-sql.md)   
 [sys.messages&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages.md)   
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
