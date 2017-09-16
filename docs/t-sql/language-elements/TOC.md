# [개요](language-elements-transact-sql.md)  
# [--(주석)](comment-transact-sql.md)  
# [슬래시 별표 주석](slash-star-comment-transact-sql.md)  
# [CREATE DIAGNOSTICS SESSION](create-diagnostics-session-transact-sql.md)  
# [NULL 및 UNKNOWN](null-and-unknown-transact-sql.md)  
# [USE](use-transact-sql.md)  
# [백슬래시](sql-server-utilities-statements-backslash.md)  
# [GO](sql-server-utilities-statements-go.md)  

# [흐름 제어](control-of-flow.md)  
## [BEGIN...END](begin-end-transact-sql.md)  
## [BREAK](break-transact-sql.md)  
## [CONTINUE](continue-transact-sql.md)  
## [ELSE(IF...ELSE)](else-if-else-transact-sql.md)  
## [END(BEGIN...END)](end-begin-end-transact-sql.md)  
## [GOTO](goto-transact-sql.md)  
## [IF...ELSE](if-else-transact-sql.md)  
## [RETURN](return-transact-sql.md)  
## [THROW](throw-transact-sql.md)  
## [TRY...CATCH](try-catch-transact-sql.md)  
## [WAITFOR](waitfor-transact-sql.md)  
## [WHILE](while-transact-sql.md)  

# [커서](cursors-transact-sql.md)  
## [CLOSE](close-transact-sql.md)  
## [DEALLOCATE](deallocate-transact-sql.md)  
## [DECLARE CURSOR](declare-cursor-transact-sql.md)  
## [FETCH](fetch-transact-sql.md)  
## [OPEN](open-transact-sql.md)  

# [식](expressions-transact-sql.md)  
## [CASE](case-transact-sql.md)  
## [COALESCE](coalesce-transact-sql.md)  
## [NULLIF](nullif-transact-sql.md)  

# [연산자](operators-transact-sql.md)  
## [단항 - 긍정](unary-operators-positive.md)  
## [단항 - 부정](unary-operators-negative.md)  
## [집합 - EXCEPT 및 INTERSECT](set-operators-except-and-intersect-transact-sql.md)  
## [집합 - UNION](set-operators-union-transact-sql.md)  
## [산술](arithmetic-operators-transact-sql.md)  
### [+(더하기)](add-transact-sql.md)  
### [+=(더하기 EQUALS)](add-equals-transact-sql.md)  
### [-(빼기)](subtract-transact-sql.md)  
### [-=(빼기 EQUALS)](subtract-equals-transact-sql.md)  
### [*(곱하기)](multiply-transact-sql.md)  
### [*=(곱하기 EQUALS)](multiply-equals-transact-sql.md)  
### [(나누기)](divide-transact-sql.md)  
### [/=(나누기 EQUALS)](divide-equals-transact-sql.md)  
### [나머지](modulo-transact-sql.md)  
### [나머지 EQUALS](modulo-equals-transact-sql.md)  
## [대입](assignment-operator-transact-sql.md)  
## [비트 단위](bitwise-operators-transact-sql.md)  
### [&(비트 단위 AND)](bitwise-and-transact-sql.md)  
### [&=(비트 단위 AND EQUALS)](bitwise-and-equals-transact-sql.md)  
### [|(비트 OR)](bitwise-or-transact-sql.md)  
### [|=(비트 단위 OR EQUALS)](bitwise-or-equals-transact-sql.md)  
### [^(배타적 비트 단위 OR)](bitwise-exclusive-or-transact-sql.md)  
### [^=(배타적 비트 단위 OR EQUALS)](bitwise-exclusive-or-equals-transact-sql.md)  
### [~(비트 단위 NOT)](bitwise-not-transact-sql.md)  
## [비교](comparison-operators-transact-sql.md)  
### [=(같음)](equals-transact-sql.md)  
### [>(보다 큼)](greater-than-transact-sql.md)  
### [<(보다 작음)](less-than-transact-sql.md)  
### [>=(크거나 같음)](greater-than-or-equal-to-transact-sql.md)  
### [<=(작거나 같음)](less-than-or-equal-to-transact-sql.md)  
### [<>(같지 않음)](not-equal-to-transact-sql-traditional.md)  
### [!<(보다 작지 않음)](not-less-than-transact-sql.md)  
### [!=(같지 않음)](not-equal-to-transact-sql-exclamation.md)  
### [!>(보다 크지 않음)](not-greater-than-transact-sql.md)  
## [복합](compound-operators-transact-sql.md)  
## [논리](logical-operators-transact-sql.md)  
### [ALL](all-transact-sql.md)  
### [AND](and-transact-sql.md)  
### [ANY](any-transact-sql.md)  
### [BETWEEN](between-transact-sql.md)  
### [EXISTS](exists-transact-sql.md)  
### [IN](in-transact-sql.md)  
### [LIKE](like-transact-sql.md)  
### [NOT](not-transact-sql.md)  
### [OR](or-transact-sql.md)  
### [SOME | ANY](some-any-transact-sql.md)  
## [범위 결정](scope-resolution-operator-transact-sql.md)  
## [문자열](string-operators-transact-sql.md)  
### [+(문자열 연결)](string-concatenation-transact-sql.md)  
### [+=(문자열 연결)](string-concatenation-equal-transact-sql.md)  
### [백분율 문자(와일드카드 - 일치하는 문자)](percent-character-wildcard-character-s-to-match-transact-sql.md)  
### [(와일드카드 - 일치하는 문자)](wildcard-character-s-to-match-transact-sql.md)  
### [(와일드카드 - 일치하지 않는 문자)](wildcard-character-s-not-to-match-transact-sql.md)  
### [_(와일드카드 - 문자 하나와 일치)](wildcard-match-one-character-transact-sql.md)  
## [연산자 우선 순위](operator-precedence-transact-sql.md)  

# [의](transactions-transact-sql.md)  
## [의](transactions-sql-data-warehouse.md)  
## [트랜잭션 격리 수준](transaction-isolation-levels.md)  
## [BEGIN DISTRIBUTED TRANSACTION](begin-distributed-transaction-transact-sql.md)  
## [BEGIN TRANSACTION](begin-transaction-transact-sql.md)  
## [COMMIT TRANSACTION](commit-transaction-transact-sql.md)  
## [COMMIT WORK](commit-work-transact-sql.md)  
## [ROLLBACK TRANSACTION](rollback-transaction-transact-sql.md)  
## [ROLLBACK WORK](rollback-work-transact-sql.md)  
## [SAVE TRANSACTION](save-transaction-transact-sql.md)  

# [변수](variables-transact-sql.md)  
## [SET @local_variable](set-local-variable-transact-sql.md)  
## [SELECT @local_variable](select-local-variable-transact-sql.md)  
## [DECLARE @local_variable](declare-local-variable-transact-sql.md)  
# [EXECUTE](execute-transact-sql.md)  
# [PRINT-Transact-SQL](print-transact-sql.md)  
# [RAISERROR](raiserror-transact-sql.md)  
# [CHECKPOINT](checkpoint-transact-sql.md)  
# [KILL](kill-transact-sql.md)  
# [KILL QUERY NOTIFICATION SUBSCRIPTION](kill-query-notification-subscription-transact-sql.md)  
# [KILL STATS JOB](kill-stats-job-transact-sql.md)  
# [RECONFIGURE](reconfigure-transact-sql.md)  
# [SHUTDOWN](shutdown-transact-sql.md)  
# [예약 키워드](reserved-keywords-transact-sql.md)  
# [구문 표기 규칙](transact-sql-syntax-conventions-transact-sql.md)  