---
title: sp_addmessage (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/16/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_addmessage
- sp_addmessage_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_addmessage
ms.assetid: 54746d30-f944-40e5-a707-f2d9be0fb9eb
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 63d206e6b6f32aeb12e2e04b9edc2ef1d84599b2
ms.sourcegitcommit: 2db83830514d23691b914466a314dfeb49094b3c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58494235"
---
# <a name="spaddmessage-transact-sql"></a>sp_addmessage(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  새 사용자 정의 오류 메시지를 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] 인스턴스에 저장합니다. 사용 하 여 저장 된 메시지 **sp_addmessage** 사용 하 여 볼 수 있습니다 합니다 **sys.messages** 카탈로그 뷰.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_addmessage [ @msgnum= ] msg_id , [ @severity= ] severity , [ @msgtext= ] 'msg'   
     [ , [ @lang= ] 'language' ]   
     [ , [ @with_log= ] { 'TRUE' | 'FALSE' } ]   
     [ , [ @replace= ] 'replace' ]   
```  
  
## <a name="arguments"></a>인수  
`[ \@msgnum = ] msg_id` 메시지의 ID입니다. *msg_id* 됩니다 **int** 이며 기본값은 NULL입니다. *msg_id* 사용자 정의 오류 메시지에는 50,001과 2,147,483,647 사이의 정수로 지정할 수 있습니다. 조합 *msg_id* 하 고 *언어* 고유 해야 합니다. 지정 된 언어 ID가 이미 있으면 오류가 반환 됩니다.  
  
`[ \@severity = ]severity` 오류의 심각도 수준이입니다. *심각도* 됩니다 **smallint** 이며 기본값은 NULL입니다. 유효한 수준은 0에서 25까지입니다. 심각도에 대한 자세한 내용은 [데이터베이스 엔진 오류 심각도](../../relational-databases/errors-events/database-engine-error-severities.md)를 참조하세요.  
  
`[ \@msgtext = ] 'msg'` 오류 메시지의 텍스트가입니다. *msg* 됩니다 **nvarchar(255)** 이며 기본값은 NULL입니다.  
  
`[ \@lang = ] 'language'` 이 메시지의 언어가입니다. *언어* 됩니다 **sysname** 이며 기본값은 NULL입니다. 동일한 서버에서 여러 언어를 설치할 수 있으므로 *언어* 각 메시지가 작성 되는 언어를 지정 합니다. 때 *언어* 는 생략 하면 언어는 기본 언어는 세션에 대 한 합니다.  
  
`[ \@with_log = ] { 'TRUE' | 'FALSE' }` 발생 하는 경우 Windows 응용 프로그램 로그에 쓸 메시지 인지 됩니다. **\@with_log** 됩니다 **varchar(5)** 이며 기본값은 FALSE입니다. TRUE인 경우 오류가 항상 Windows 응용 프로그램 로그에 기록됩니다. FALSE인 경우 오류가 항상 Windows 응용 프로그램 로그에 기록되지는 않으며 오류가 어떻게 발생했는지에 따라 달라집니다. 멤버를 **sysadmin** 서버 역할이이 옵션을 사용할 수 있습니다.  
  
> [!NOTE]  
>  Windows 응용 프로그램 로그에 메시지가 기록된 경우에는 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 오류 로그 파일에도 기록됩니다.  
  
`[ \@replace = ] 'replace'` 문자열로 지정 된 경우 *대체*, 기존의 오류 메시지는 새 메시지 텍스트와 심각도 수준으로 덮어씁니다. *바꿉니다* 됩니다 **varchar(7)** 이며 기본값은 NULL입니다. 하는 경우이 옵션을 지정 해야 *msg_id* 이미 있습니다. 영어(미국)로 작성된 모든 메시지는 다른 모든 언어의 영어 메시지 심각도 바뀝니다 *msg_id*합니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 1(실패)  
  
## <a name="result-sets"></a>결과 집합  
 없음  
  
## <a name="remarks"></a>Remarks  
 영어 버전이 아닌 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]의 경우 경우 영어(미국) 버전의 메시지가 이미 존재하고 있어야 다른 언어를 사용하여 메시지를 추가할 수 있습니다. 두 버전의 메시지에 대한 심각도는 일치해야 합니다.  
  
 매개 변수를 포함한 메시지를 지역화하는 경우에는 원래 메시지의 매개 변수와 일치하는 매개 변수 번호를 사용하십시오. 각 매개 변수 번호 뒤에는 느낌표(!)를 삽입하십시오.  
  
|원래 메시지|지역화된 메시지|  
|----------------------|-----------------------|  
|' 원래 메시지 param 1: %s<br /><br /> 매개 변수 2: %d '|' 지역화 된 메시지 param 1: %1!를<br /><br /> 매개 변수 2: %2. '|  
  
 언어 구문이 다르므로 지역화된 메시지의 매개 변수 번호 순서가 원래 메시지의 경우와 다를 수 있습니다.  
  
## <a name="permissions"></a>사용 권한  
멤버 자격이 필요 합니다 **sysadmin** 하거나 **serveradmin** 고정 서버 역할입니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-defining-a-custom-message"></a>1. 사용자 지정 메시지 정의  
 다음 예제에서는 사용자 지정 메시지를 추가 **sys.messages**합니다.  
  
```  
USE master;  
GO  
EXEC sp_addmessage 50001, 16,   
   N'Percentage expects a value between 20 and 100.   
   Please reexecute with a more appropriate value.';  
GO  
```  
  
### <a name="b-adding-a-message-in-two-languages"></a>2. 두 언어로 작성된 메시지 추가  
 다음 예에서는 영어(미국)로 된 메시지를 먼저 추가한 다음 동일한 메시지를 프랑스어로 추가합니다`.`  
  
```  
USE master;  
GO  
EXEC sp_addmessage @msgnum = 60000, @severity = 16,   
   @msgtext = N'The item named %s already exists in %s.',   
   @lang = 'us_english';  
  
EXEC sp_addmessage @msgnum = 60000, @severity = 16,   
   @msgtext = N'L''élément nommé %1! existe déjà dans %2!',   
   @lang = 'French';  
GO  
```  
  
### <a name="c-changing-the-order-of-parameters"></a>3. 매개 변수 순서 변경  
 다음 예에서는 영어(미국)로 된 메시지를 먼저 추가한 다음 매개 변수 순서를 변경하여 해당 지역 언어로 된 메시지를 추가합니다.  
  
```  
USE master;  
GO  
  
EXEC sp_addmessage   
    @msgnum = 60000,   
    @severity = 16,  
    @msgtext =   
        N'This is a test message with one numeric  
        parameter (%d), one string parameter (%s),   
        and another string parameter (%s).',  
    @lang = 'us_english';  
  
EXEC sp_addmessage   
    @msgnum = 60000,   
    @severity = 16,  
    @msgtext =   
        -- In the localized version of the message,  
        -- the parameter order has changed. The   
        -- string parameters are first and second  
        -- place in the message, and the numeric   
        -- parameter is third place.  
        N'Dies ist eine Testmeldung mit einem   
        Zeichenfolgenparameter (%3!),  
        einem weiteren Zeichenfolgenparameter (%2!),   
        und einem numerischen Parameter (%1!).',  
    @lang = 'German';  
GO    
  
-- Changing the session language to use the U.S. English  
-- version of the error message.  
SET LANGUAGE us_english;  
GO  
  
RAISERROR(60000,1,1,15,'param1','param2') -- error, severity, state,  
GO                                       -- parameters.  
  
-- Changing the session language to use the German  
-- version of the error message.  
SET LANGUAGE German;  
GO  
  
RAISERROR(60000,1,1,15,'param1','param2'); -- error, severity, state,   
GO                                       -- parameters.  
```  
  
## <a name="see-also"></a>관련 항목  
 [RAISERROR&#40;Transact-SQL&#41;](../../t-sql/language-elements/raiserror-transact-sql.md)   
 [sp_altermessage &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-altermessage-transact-sql.md)   
 [sp_dropmessage &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dropmessage-transact-sql.md)   
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
