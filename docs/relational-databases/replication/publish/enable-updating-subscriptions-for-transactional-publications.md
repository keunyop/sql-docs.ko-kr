---
title: 트랜잭션 게시에 대해 업데이트할 수 있는 구독 설정 | Microsoft 문서
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- transactional replication, updatable subscriptions
- updatable subscriptions, enabling
- subscriptions [SQL Server replication], updatable
ms.assetid: 539d5bb0-b808-4d8c-baf4-cb6d32d2c595
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 9bb2b72da5f90cf2ff91c386e2a34fed1001de73
ms.sourcegitcommit: 7aa6beaaf64daf01b0e98e6c63cc22906a77ed04
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54130103"
---
# <a name="enable-updating-subscriptions-for-transactional-publications"></a>트랜잭션 게시에 대해 업데이트할 수 있는 구독 설정
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  이 항목에서는 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] 또는 [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] 을 사용하여 [!INCLUDE[tsql](../../../includes/tsql-md.md)]에서 트랜잭션 게시에 대해 구독 업데이트를 설정하는 방법에 대해 설명합니다.  
  
> **참고!** [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  

##  <a name="BeforeYouBegin"></a> 시작하기 전 주의 사항  
  
###  <a name="Security"></a> 보안  
 가능한 경우 런타임 시 사용자에게 보안 자격 증명을 입력하라는 메시지가 표시됩니다. 자격 증명을 스크립트 파일에 저장해야 하는 경우에는 파일에 무단으로 액세스하지 못하도록 보안을 설정해야 합니다.  
  
##  <a name="SSMSProcedure"></a> SQL Server Management Studio 사용  
 새 게시 마법사의 **게시 유형** 페이지에서 트랜잭션 게시에 대해 구독 업데이트를 설정합니다.  
  
 구독 업데이트를 사용하려면 새 구독 마법사에서도 옵션을 구성해야 합니다.  
  
#### <a name="to-enable-updating-subscriptions"></a>구독 업데이트를 설정하려면  
  
1.  새 게시 마법사의 **게시 유형** 페이지에서 **업데이트할 수 있는 구독이 있는 트랜잭션 게시**를 선택합니다.  
  
2.  **에이전트 보안** 페이지에서 스냅숏 에이전트, 로그 판독기 에이전트 및 큐 판독기 에이전트에 대한 보안 설정을 지정합니다. 큐 판독기 에이전트가 실행되는 계정에 필요한 사용 권한에 대한 자세한 내용은 [Replication Agent Security Model](../../../relational-databases/replication/security/replication-agent-security-model.md)을 참조하세요.  
  
    > **참고:** 즉시 업데이트 구독만 사용하는 경우에도 큐 판독기 에이전트가 구성됩니다.  
  
##  <a name="TsqlProcedure"></a> Transact-SQL 사용  
 복제 저장 프로시저를 사용하여 프로그래밍 방식으로 트랜잭션 게시를 만들 때 즉시 업데이트 구독 또는 지연 업데이트 구독을 설정할 수 있습니다.  
  
#### <a name="to-create-a-publication-that-supports-immediate-updating-subscriptions"></a>즉시 업데이트 구독을 지원하는 게시를 만들려면  
  
1.  필요한 경우 게시 데이터베이스에 대한 로그 판독기 에이전트 작업을 만듭니다.  
  
    -   게시 데이터베이스에 대한 로그 판독기 에이전트 작업이 이미 존재하면 2단계를 실행합니다.  
  
    -   게시된 데이터베이스에 대해 로그 판독기 에이전트 작업이 존재하는지 확실하지 않으면 게시 데이터베이스의 게시자에서 [sp_helplogreader_agent&#40;Transact-SQL&#41;](../../../relational-databases/system-stored-procedures/sp-helplogreader-agent-transact-sql.md)를 실행합니다. 결과 집합이 비어 있으면 로그 판독기 에이전트 작업을 만들어야 합니다.  
  
    -   게시자에서 [sp_addlogreader_agent&#40;Transact-SQL&#41;](../../../relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql.md)를 실행합니다. **@job_name** 및 **@password**에 에이전트가 실행되는 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 자격 증명을 지정합니다. 게시자에 연결할 때 에이전트가 SQL Server 인증을 사용하면 **@publisher_security_mode** 에 값 **@publisher_security_mode** 을 지정하고 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 및 **@publisher_login** @password **@publisher_password**에서 트랜잭션 게시에 대해 구독 업데이트를 설정하는 방법에 대해 설명합니다.  
  
2.  **@allow_sync_tran** 매개 변수에 **true** 값을 지정하여 [sp_addpublication&#40;Transact-SQL&#41;](../../../relational-databases/system-stored-procedures/sp-addpublication-transact-sql.md)을 실행합니다.  
  
3.  게시자에서 [sp_addpublication_snapshot&#40;Transact-SQL&#41;](../../../relational-databases/system-stored-procedures/sp-addpublication-snapshot-transact-sql.md)을 실행합니다. **@publication**에 2단계에서 사용된 게시 이름을, **@job_name** 및 **@password**에 스냅숏 에이전트를 실행하는 데 사용되는 Windows 자격 증명을 지정합니다. 게시자에 연결할 때 에이전트가 SQL Server 인증을 사용하면 **@publisher_security_mode** 에 값 **@publisher_security_mode** 을 지정하고 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 및 **@publisher_login** @password **@publisher_password**에서 트랜잭션 게시에 대해 구독 업데이트를 설정하는 방법에 대해 설명합니다. 이렇게 하면 게시에 대해 스냅숏 에이전트 작업이 만들어집니다.  
  
4.  아티클을 게시에 추가합니다. 자세한 내용은 [아티클을 정의](../../../relational-databases/replication/publish/define-an-article.md)을 참조하세요.  
  
5.  구독자에서 이 게시에 대한 업데이트 구독을 만듭니다.   
  
#### <a name="to-create-a-publication-that-supports-queued-updating-subscriptions"></a>지연 업데이트 구독을 지원하는 게시를 만들려면  
  
1.  필요한 경우 게시 데이터베이스에 대한 로그 판독기 에이전트 작업을 만듭니다.  
  
    -   게시 데이터베이스에 대한 로그 판독기 에이전트 작업이 이미 존재하면 2단계를 실행합니다.  
  
    -   게시된 데이터베이스에 대해 로그 판독기 에이전트 작업이 존재하는지 확실하지 않으면 게시 데이터베이스의 게시자에서 [sp_helplogreader_agent&#40;Transact-SQL&#41;](../../../relational-databases/system-stored-procedures/sp-helplogreader-agent-transact-sql.md)를 실행합니다. 결과 집합이 비어 있으면 로그 판독기 에이전트 작업을 만들어야 합니다.  
  
    -   게시자에서 [sp_addlogreader_agent&#40;Transact-SQL&#41;](../../../relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql.md)를 실행합니다. 이때 **@job_name** 및 **@password**의 Oracle 데이터베이스에서 구독을 만드는 방법에 대해 설명합니다. 게시자에 연결할 때 에이전트가 SQL Server 인증을 사용하면 **@publisher_security_mode** 에 값 **@publisher_security_mode** 을 지정하고 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 및 **@publisher_login** @password **@publisher_password**에서 트랜잭션 게시에 대해 구독 업데이트를 설정하는 방법에 대해 설명합니다.  
  
2.  필요한 경우 배포자에 대한 큐 판독기 에이전트 작업을 만듭니다.  
  
    -   배포 데이터베이스에 대한 큐 판독기 에이전트 작업이 이미 존재하면 3단계를 실행합니다.  
  
    -   배포 데이터베이스에 대해 큐 판독기 에이전트 작업이 존재하는지 확실하지 않으면 배포 데이터베이스의 배포자에서 [sp_helpqreader_agent&#40;Transact-SQL&#41;](../../../relational-databases/system-stored-procedures/sp-helpqreader-agent-transact-sql.md)를 실행합니다. 결과 집합이 비어 있으면 큐 판독기 에이전트 작업을 만들어야 합니다.  
  
    -   배포자에서 [sp_addqreader_agent&#40;Transact-SQL&#41;](../../../relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql.md)를 실행합니다. **@job_name** 및 **@password**에 에이전트가 실행되는 Windows 자격 증명을 지정합니다. 이러한 자격 증명은 큐 판독기 에이전트가 게시자 및 구독자에 연결할 때 사용됩니다. 자세한 내용은 [복제 에이전트 보안 모델](../../../relational-databases/replication/security/replication-agent-security-model.md)을 참조하세요.  
  
3.  **@allow_queued_tran** 매개 변수에 **true** 값, **@conflict_policy**에 **pub wins**, **sub reinit** 또는 **sub wins** 값을 지정하여 [sp_addpublication&#40;Transact-SQL&#41;](../../../relational-databases/system-stored-procedures/sp-addpublication-transact-sql.md)을 실행합니다.  
  
4.  게시자에서 [sp_addpublication_snapshot(Transact-SQL)](../../../relational-databases/system-stored-procedures/sp-addpublication-snapshot-transact-sql.md)을 실행합니다. **@publication**에 3단계에서 사용된 게시 이름을, **@snapshot_job_name** 및 **@password**에 스냅숏 에이전트를 실행하는 데 사용되는 Windows 자격 증명을 지정합니다. 게시자에 연결할 때 에이전트가 SQL Server 인증을 사용하면 **@publisher_security_mode** 에 값 **@publisher_security_mode** 을 지정하고 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 및 **@publisher_login** @password **@publisher_password**에서 트랜잭션 게시에 대해 구독 업데이트를 설정하는 방법에 대해 설명합니다. 이렇게 하면 게시에 대해 스냅숏 에이전트 작업이 만들어집니다.  
  
5.  아티클을 게시에 추가합니다. 자세한 내용은 [아티클을 정의](../../../relational-databases/replication/publish/define-an-article.md)을 참조하세요.  
  
6.  구독자에서 이 게시에 대한 업데이트 구독을 만듭니다.  
  
#### <a name="to-change-the-conflict-policy-for-a-publication-that-allows-queued-updating-subscriptions"></a>지연 업데이트 구독을 허용하는 게시에 대한 충돌 정책을 변경하려면  
  
1.  게시 데이터베이스의 게시자에서 [sp_changepublication&#40;Transact-SQL&#41;](../../../relational-databases/system-stored-procedures/sp-changepublication-transact-sql.md)을 실행합니다. **@property**에 **conflict_policy** 값을 지정하고 **@value**에 원하는 충돌 정책 모드(**pub wins**, **sub reinit** 또는 **sub wins**)를 지정합니다.  
  
###  <a name="TsqlExample"></a> 예(Transact-SQL)  
 이 예에서는 즉시 업데이트 끌어오기 구독과 지연 업데이트 끌어오기 구독을 모두 지원하는 게시를 만듭니다.  
  
 [!code-sql[HowTo#sp_createtranupdatingpub](../../../relational-databases/replication/codesnippet/tsql/enable-updating-subscrip_1.sql)]  
  
## <a name="see-also"></a>참고 항목  
 [지연 업데이트 충돌 해결 옵션 설정&#40;SQL Server Management Studio&#41;](../../../relational-databases/replication/publish/create-an-updatable-subscription-to-a-transactional-publication.md)   
 [트랜잭션 복제](../../../relational-databases/replication/transactional/transactional-replication.md)   
 [Updatable Subscriptions for Transactional Replication](../../../relational-databases/replication/transactional/updatable-subscriptions-for-transactional-replication.md)   
 [Create a Publication](../../../relational-databases/replication/publish/create-a-publication.md)   
 [Create an Updatable Subscription to a Transactional Publication](create-an-updatable-subscription-to-a-transactional-publication.md)   
 [Updatable Subscriptions for Transactional Replication](../../../relational-databases/replication/transactional/updatable-subscriptions-for-transactional-replication.md)   
 [스크립팅 변수와 함께 sqlcmd 사용](../../../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md)  
  
  
