---
title: "(Transact SQL) 수신 | Microsoft Docs"
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
- RECEIVE_TSQL
- RECEIVE
dev_langs:
- TSQL
helpviewer_keywords:
- queues [Service Broker], message retrieval
- messages [Service Broker], retrieving
- RECEIVE statement
- receiving messages
- retrieving messages
ms.assetid: 878c6c14-37ab-4b87-9854-7f8f42bac7dd
caps.latest.revision: 50
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 4cf66234550d32eafae1029d80c0330499d75553
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="receive-transact-sql"></a>RECEIVE(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  큐에서 하나 이상의 메시지를 검색합니다. 큐의 보존 기간 설정에 따라 큐에서 메시지를 제거하거나 큐에 있는 메시지의 상태를 업데이트합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
[ WAITFOR ( ]  
    RECEIVE [ TOP ( n ) ]   
        <column_specifier> [ ,...n ]  
        FROM <queue>  
        [ INTO table_variable ]  
        [ WHERE {  conversation_handle = conversation_handle  
                 | conversation_group_id = conversation_group_id } ]  
[ ) ] [ , TIMEOUT timeout ]  
[ ; ]  
  
<column_specifier> ::=  
{    *   
  |  { column_name | [ ] expression } [ [ AS ] column_alias ]  
  |  column_alias = expression   
}     [ ,...n ]   
  
<queue> ::=  
{  
    [ database_name . [ schema_name ] . | schema_name . ]  
        queue_name  
}  
  
```  
  
## <a name="arguments"></a>인수  
 WAITFOR  
 현재 메시지가 없으면 메시지가 큐에 도착할 때까지 RECEIVE 문이 대기하도록 지정합니다.  
  
 TOP (  *n*  )  
 반환할 메시지의 최대 개수를 지정합니다. 이 절을 지정하지 않으면 문 조건을 만족하는 모든 메시지가 반환됩니다.  
  
 \*  
 결과 집합이 큐에 있는 모든 열을 포함하도록 지정합니다.  
  
 *column_name*  
 결과 집합에 포함할 열의 이름입니다.  
  
 *expression*  
 열 이름, 상수, 함수이거나 열 이름, 상수, 연산자로 연결된 함수의 모든 조합입니다.  
  
 *column_alias를 사용할*  
 결과 집합에서 열 이름을 대신하는 또 다른 이름입니다.  
  
 FROM  
 메시지를 가져올 큐를 지정합니다.  
  
 *database_name*  
 메시지를 받을 큐가 포함된 데이터베이스의 이름입니다. No *데이터베이스 이름* 제공 되는 현재 데이터베이스에 대 한 기본값입니다.  
  
 *schema_name*  
 메시지를 받을 큐를 소유하는 스키마의 이름입니다. No *스키마 이름* 제공 되는 현재 사용자의 기본 스키마는 기본값입니다.  
  
 *queue_name*  
 메시지를 받을 큐의 이름입니다.  
  
 에 *table_variable*  
 RECEIVE가 메시지를 넣을 테이블 변수를 지정합니다. 테이블 변수의 열 개수는 메시지의 열 개수와 동일해야 합니다. 테이블 변수에 있는 각 열의 데이터 형식은 메시지에 있는 해당 열의 데이터 형식으로 암시적으로 변환할 수 있어야 합니다. INTO를 지정하지 않으면 메시지가 결과 집합으로 반환됩니다.  
  
 WHERE  
 받은 메시지에 대한 대화 또는 대화 그룹을 지정합니다. 생략하면 사용 가능한 다음 대화 그룹에서 메시지를 반환합니다.  
  
 conversation_handle = *conversation_handle*  
 받은 메시지에 대한 대화를 지정합니다. *대화 핸들* 반드시 제공 수는 **uniqueidentifer**, 또는로 변환할 수 있는 형식 **uniqueidentifier**합니다.  
  
 conversation_group_id = *conversation_group_id*  
 받은 메시지에 대한 대화 그룹을 지정합니다. *은 대화 그룹 ID* 제공 해야 합니다 수는 **uniqueidentifier**, 또는를 변환할 수 있는 형식 **uniqueidentifier**합니다.  
  
 제한 시간 *제한 시간*  
 문이 메시지를 대기하는 시간(밀리초)을 지정합니다. 이 절은 WAITFOR 절에서만 사용할 수 있습니다. 이 절을 지정 하지 않거나 제한 시간이-경우**1**, 대기 시간 제한 됩니다. 제한 시간이 만료되면 RECEIVE가 빈 결과 집합을 반환합니다.  
  
## <a name="remarks"></a>주의  
  
> [!IMPORTANT]  
>  일괄 처리 또는 저장 프로시저에서 RECEIVE 문이 첫 번째 문이 아닌 경우 이전 문은 세미콜론(;)으로 끝나야 합니다.  
  
 RECEIVE 문은 큐에서 메시지를 읽고 결과 집합을 반환합니다. 결과 집합은 없거나 1개 이상의 행으로 구성되며 각 행에는 메시지 하나가 들어 있습니다. INTO 절을 사용 하지 않는 경우 및 *column_specifier* 값을 할당 하지 않습니다 문이 지역 변수에 결과 호출 프로그램으로 집합을 반환 합니다.  
  
 RECEIVE 문에서 반환하는 메시지는 다양한 유형일 수 있습니다. 응용 프로그램이 사용할 수는 **message_type_name** 연관된 된 메시지 유형을 처리 하는 코드에 각 메시지를 라우팅하는 열입니다. 메시지 유형에는 다음과 같은 두 가지가 있습니다.  
  
-   CREATE MESSAGE TYPE 문을 사용하여 만든 응용 프로그램 정의 메시지 유형. 대화에 사용할 수 있는 응용 프로그램 정의 메시지 유형 집합은 대화에 지정된 [!INCLUDE[ssSB](../../includes/sssb-md.md)] 계약을 사용하여 정의됩니다.  
  
-   상태 또는 오류 정보를 반환하는 [!INCLUDE[ssSB](../../includes/sssb-md.md)] 시스템 메시지.  
  
 큐에서 메시지 보존 기간을 지정하지 않으면 RECEIVE 문은 받은 메시지를 큐에서 제거합니다. 큐의 RETENTION 설정이 ON 이면 RECEIVE 문이 업데이트 경우는 **상태** 열을 **0** 큐에 메시지를 유지 합니다. RECEIVE 문을 포함하는 트랜잭션이 롤백되면 트랜잭션 내에 있는 큐의 모든 변경 내용도 롤백되어 메시지를 큐로 반환합니다.  
  
 RECEIVE 문에 의해 반환된 모든 메시지는 동일한 대화 그룹에 속합니다. RECEIVE 문은 문을 포함하는 트랜잭션이 완료될 때까지 반환된 메시지에 대한 대화 그룹을 잠급니다. RECEIVE 문은 메시지를 반환 합니다.는 **상태** 의 **1입니다.** RECEIVE 문에 의해 반환된 결과 집합은 다음과 같이 암시적으로 정렬됩니다.  
  
-   여러 대화의 메시지가 WHERE 절 조건을 충족하는 경우 RECEIVE 문은 한 대화의 모든 메시지를 반환한 후 다른 대화의 메시지를 반환합니다. 대화는 우선 순위의 내림차순으로 처리됩니다.  
  
-   메시지를 오름차순으로 정렬 RECEIVE 문은 특정된 대화에 대 한 반환 **message_sequence_number** 순서입니다.  
  
 RECEIVE 문의 WHERE 절 중 하나를 사용 하는 검색 조건만 포함할 수 있습니다 **conversation_handle** 또는 **conversation_group_id**합니다. 검색 조건에는 큐에 있는 하나 이상의 다른 열이 포함되지 않습니다. **conversation_handle** 또는 **conversation_group_id** 식일 수 없습니다. 반환되는 메시지 집합은 WHERE 절에 지정된 조건에 따라 달라집니다.  
  
-   경우 **conversation_handle** 지정, 수신 큐에서 사용할 수 있는 지정된 된 대화의 모든 메시지를 반환 합니다.  
  
-   경우 **conversation_group_id** 지정 하면 수신 큐가 지정된 된 대화 그룹의 멤버인 모든 대화에서에 사용할 수 있는 모든 메시지를 반환 합니다.  
  
-   WHERE 절이 없으면 RECEIVE가 다음과 같은 대화 그룹을 선택합니다.  
  
    -   큐에 하나 이상의 메시지가 있는 대화 그룹  
  
    -   다른 RECEIVE 문으로 잠기지 않은 대화 그룹  
  
    -   이러한 조건을 충족하는 모든 대화 그룹 중 우선 순위가 가장 높은 대화 그룹  
  
     그런 다음 RECEIVE는 선택한 대화 그룹에 속한 대화의 큐에서 사용 가능한 모든 메시지를 반환합니다.  
  
 WHERE 절에 지정된 대화 핸들 또는 대화 그룹 식별자가 없거나 지정된 큐에 연결되어 있지 않으면 RECEIVE 문은 오류를 반환합니다.  
  
 RECEIVE 문에 지정된 큐의 상태가 OFF로 설정되어 있으면 문은 [!INCLUDE[tsql](../../includes/tsql-md.md)] 오류로 실패합니다.  
  
 WAITFOR 절을 지정하면 문은 지정된 제한 시간 동안 대기하거나 결과 집합을 사용할 수 있을 때까지 대기합니다. 문이 대기하는 동안 큐가 삭제되거나 큐의 상태가 OFF로 설정되면 문은 즉시 오류를 반환합니다. RECEIVE 문에서 대화 그룹 또는 대화 핸들을 지정하고 해당 대화에 대한 서비스가 삭제되거나 또 다른 큐로 옮겨지면 RECEIVE 문은 [!INCLUDE[tsql](../../includes/tsql-md.md)] 오류를 보고합니다.  
  
 RECEIVE는 사용자 정의 함수에 유효하지 않습니다.  
  
 RECEIVE 문에는 우선 순위 기아 상태 방지(starvation prevention) 기능이 없습니다. 단일 RECEIVE 문이 대화 그룹을 잠그고 우선 순위가 낮은 대화에서 많은 메시지를 검색한 경우에는 해당 그룹의 우선 순위가 높은 대화의 메시지를 받을 수 없습니다. 이를 방지하려면 우선 순위가 낮은 대화의 메시지를 검색할 때 TOP 절을 사용하여 각 RECEIVE 문에서 검색하는 메시지 수를 제한하십시오.  
  
## <a name="queue-columns"></a>큐 열  
 다음 표에서는 큐의 열을 나열합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**상태**|**tinyint**|메시지의 상태입니다. RECEIVE 명령에서 반환 된 메시지에 대 한 상태는 항상 **0**합니다. 큐의 메시지는 다음 값 중 하나를 포함할 수 있습니다.<br /><br /> **0**= 준비**1**= 받은 메시지**2**= 아직 완료**3**= 보낸 메시지 보유|  
|**우선 순위**|**tinyint**|메시지에 적용된 대화의 우선 순위 수준입니다.|  
|**queuing_order**|**bigint**|큐 내의 메시지 정렬 번호입니다.|  
|**conversation_group_id**|**uniqueidentifier**|이 메시지가 속하는 대화 그룹의 식별자입니다.|  
|**conversation_handle**|**uniqueidentifier**|이 메시지가 속하는 대화의 핸들입니다.|  
|**message_sequence_number**|**bigint**|대화 내의 메시지 시퀀스 번호입니다.|  
|**service_name**|**nvarchar(512)**|대화와 연관된 서비스의 이름입니다.|  
|**service_id**|**int**|대화와 연관된 서비스의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 개체 식별자입니다.|  
|**service_contract_name**|**nvarchar(256)**|대화에서 준수하는 계약의 이름입니다.|  
|**service_contract_id**|**int**|대화에서 준수하는 계약의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 개체 식별자입니다.|  
|**message_type_name**|**nvarchar(256)**|메시지 형식을 설명하는 메시지 유형의 이름입니다. 메시지는 응용 프로그램 메시지 유형이거나 Broker 시스템 메시지일 수 있습니다.|  
|**message_type_id**|**int**|메시지를 설명하는 메시지 유형의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 개체 식별자입니다.|  
|**유효성 검사**|**nchar(2)**|메시지에 사용된 유효성 검사입니다.<br /><br /> **E**= 비어 있음**N**= None**X**= XML|  
|**message_body**|**varbinary (max)**|메시지 내용입니다.|  
  
## <a name="permissions"></a>Permissions  
 메시지를 받으려면 현재 사용자는 큐에서 RECEIVE 권한이 있어야 합니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-receiving-all-columns-for-all-messages-in-a-conversation-group"></a>1. 대화 그룹의 모든 메시지에 대한 모든 열 받기  
 다음 예에서는 `ExpenseQueue` 큐에서 사용 가능한 다음 대화 그룹에 대한 모든 수신 가능한 메시지를 받습니다. 문은 결과 집합으로 메시지를 반환합니다.  
  
```  
RECEIVE * FROM ExpenseQueue ;  
```  
  
### <a name="b-receiving-specified-columns-for-all-messages-in-a-conversation-group"></a>2. 대화 그룹의 모든 메시지에 대해 지정된 열 받기  
 다음 예에서는 `ExpenseQueue` 큐에서 사용 가능한 다음 대화 그룹에 대한 모든 수신 가능한 메시지를 받습니다. 문은 `conversation_handle`, `message_type_name` 및 `message_body` 열을 포함하는 결과 집합으로 메시지를 반환합니다.  
  
```  
RECEIVE conversation_handle, message_type_name, message_body  
FROM ExpenseQueue ;  
```  
  
### <a name="c-receiving-the-first-available-message-in-the-queue"></a>3. 큐에서 수신 가능한 첫 번째 메시지 받기  
 다음 예에서는 `ExpenseQueue` 큐에서 수신 가능한 첫 번째 메시지를 결과 집합으로 받습니다.  
  
```  
RECEIVE TOP (1) * FROM ExpenseQueue ;  
```  
  
### <a name="d-receiving-all-messages-for-a-specified-conversation"></a>4. 지정된 대화에 대한 모든 메시지 받기  
 다음 예에서는 `ExpenseQueue` 큐에서 지정된 대화에 대해 수신 가능한 모든 메시지를 결과 집합으로 받습니다.  
  
```  
DECLARE @conversation_handle UNIQUEIDENTIFIER ;  
  
SET @conversation_handle = <retrieve conversation from database> ;  
  
RECEIVE *  
FROM ExpenseQueue  
WHERE conversation_handle = @conversation_handle ;  
```  
  
### <a name="e-receiving-messages-for-a-specified-conversation-group"></a>5. 지정된 대화 그룹에 대한 메시지 받기  
 다음 예에서는 `ExpenseQueue` 큐에서 지정된 대화 그룹에 대해 수신 가능한 모든 메시지를 결과 집합으로 받습니다.  
  
```  
DECLARE @conversation_group_id UNIQUEIDENTIFIER ;  
  
SET @conversation_group_id =   
    <retrieve conversation group ID from database> ;  
  
RECEIVE *  
FROM ExpenseQueue  
WHERE conversation_group_id = @conversation_group_id ;  
```  
  
### <a name="f-receiving-into-a-table-variable"></a>6. 테이블 변수로 받기  
 다음 예에서는 `ExpenseQueue` 큐에서 지정된 대화 그룹에 대해 수신 가능한 모든 메시지를 테이블 변수로 받습니다.  
  
```  
DECLARE @conversation_group_id UNIQUEIDENTIFIER ;  
  
DECLARE @procTable TABLE(  
     service_instance_id UNIQUEIDENTIFIER,  
     handle UNIQUEIDENTIFIER,  
     message_sequence_number BIGINT,  
     service_name NVARCHAR(512),  
     service_contract_name NVARCHAR(256),  
     message_type_name NVARCHAR(256),  
     validation NCHAR,  
     message_body VARBINARY(MAX)) ;  
  
SET @conversation_group_id = <retrieve conversation group ID from database> ;  
  
RECEIVE TOP (1)  
    conversation_group_id,  
    conversation_handle,  
    message_sequence_number,  
    service_name,  
    service_contract_name,  
    message_type_name,  
    validation,  
    message_body  
FROM ExpenseQueue  
INTO @procTable  
WHERE conversation_group_id = @conversation_group_id ;  
```  
  
### <a name="g-receiving-messages-and-waiting-indefinitely"></a>7. 메시지 받기 및 무기한 대기  
 다음 예에서는 `ExpenseQueue` 큐에서 사용 가능한 다음 대화 그룹에 대한 모든 수신 가능한 메시지를 받습니다. 문은 적어도 하나 이상의 메시지를 사용할 수 있을 때까지 대기한 다음 모든 메시지 열을 포함하는 결과 집합을 반환합니다.  
  
```  
WAITFOR (  
    RECEIVE *  
    FROM ExpenseQueue) ;  
```  
  
### <a name="h-receiving-messages-and-waiting-for-a-specified-interval"></a>8. 메시지 받기 및 지정된 기간 동안 대기  
 다음 예에서는 `ExpenseQueue` 큐에서 사용 가능한 다음 대화 그룹에 대한 모든 수신 가능한 메시지를 받습니다. 문은 어떤 경우가 먼저 발생하는지에 관계없이 60초 동안 대기하거나 적어도 하나 이상의 메시지를 사용할 수 있을 때까지 대기합니다. 적어도 하나 이상의 메시지를 사용할 수 있으면 문은 모든 메시지 열을 포함하는 결과 집합을 반환합니다. 그렇지 않으면 빈 결과 집합을 반환합니다.  
  
```  
WAITFOR (  
    RECEIVE *  
    FROM ExpenseQueue ),  
TIMEOUT 60000 ;  
```  
  
### <a name="i-receiving-messages-modifying-the-type-of-a-column"></a>9. 메시지 받기, 열의 유형 수정  
 다음 예에서는 `ExpenseQueue` 큐에서 사용 가능한 다음 대화 그룹에 대한 모든 수신 가능한 메시지를 받습니다. 메시지 유형이 메시지에 XML 문서가 포함되어 있음을 나타내면 문은 메시지 본문을 XML로 변환합니다.  
  
```  
WAITFOR (  
    RECEIVE message_type_name,  
        CASE  
            WHEN validation = 'X' THEN CAST(message_body as XML)  
            ELSE NULL  
         END AS message_body   
         FROM ExpenseQueue ),  
TIMEOUT 60000 ;  
```  
  
### <a name="j-receiving-a-message-extracting-data-from-the-message-body-retrieving-conversation-state"></a>10. 메시지 받기, 메시지 본문에서 데이터 추출, 대화 상태 검색  
 다음 예에서는 `ExpenseQueue` 큐에서 사용 가능한 다음 대화 그룹에 대해 수신 가능한 다음 메시지를 받습니다. 메시지가 `//Adventure-Works.com/Expenses/SubmitExpense` 유형이면 문은 메시지 본문에서 직원 ID와 항목 목록을 추출합니다. 또한 문은 `ConversationState` 테이블에서 대화의 상태를 검색합니다.  
  
```  
WAITFOR(  
    RECEIVE   
    TOP(1)  
      message_type_name,  
      COALESCE(  
           (SELECT TOP(1) ConversationState  
            FROM CurrentConversations AS cc  
            WHERE cc.ConversationHandle = conversation_handle),  
           'NEW')  
      AS ConversationState,  
      COALESCE(  
          (SELECT TOP(1) ErrorCount  
           FROM CurrentConversations AS cc  
           WHERE cc.ConversationHandle = conversation_handle),   
           0)  
      AS ConversationErrors,  
      CASE WHEN message_type_name = N'//Adventure-Works.com/Expenses/SubmitExpense'  
          THEN CAST(message_body AS XML).value(  
                'declare namespace rpt = "http://Adventure-Works.com/schemas/expenseReport"  
                   (/rpt:ExpenseReport/rpt:EmployeeID)[1]', 'nvarchar(20)')  
         ELSE NULL  
      END AS EmployeeID,  
      CASE WHEN message_type_name = N'//Adventure-Works.com/Expenses/SubmitExpense'  
          THEN CAST(message_body AS XML).query(  
                'declare namespace rpt = "http://Adventure-Works.com/schemas/expenseReport"   
                     /rpt:ExpenseReport/rpt:ItemDetail')  
          ELSE NULL  
      END AS ItemList  
    FROM ExpenseQueue   
), TIMEOUT 60000 ;  
```  
  
## <a name="see-also"></a>관련 항목:  
 [BEGIN DIALOG conversation&#40; Transact SQL &#41;](../../t-sql/statements/begin-dialog-conversation-transact-sql.md)   
 [BEGIN CONVERSATION TIMER &#40; Transact SQL &#41;](../../t-sql/statements/begin-conversation-timer-transact-sql.md)   
 [END CONVERSATION &#40; Transact SQL &#41;](../../t-sql/statements/end-conversation-transact-sql.md)   
 [계약 &#40; 만들기 Transact SQL &#41;](../../t-sql/statements/create-contract-transact-sql.md)   
 [메시지 유형 &#40; 만들기 Transact SQL &#41;](../../t-sql/statements/create-message-type-transact-sql.md)   
 [Send&#40; Transact SQL &#41;](../../t-sql/statements/send-transact-sql.md)   
 [CREATE QUEUE&#40;Transact-SQL&#41;](../../t-sql/statements/create-queue-transact-sql.md)   
 [ALTER queue&#40; Transact SQL &#41;](../../t-sql/statements/alter-queue-transact-sql.md)   
 [DROP queue&#40; Transact SQL &#41;](../../t-sql/statements/drop-queue-transact-sql.md)  
  
  
