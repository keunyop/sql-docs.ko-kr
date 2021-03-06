---
title: 구독에 대한 만료 기간 설정 | Microsoft 문서
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication], expiration
- expiration [SQL Server replication]
- retention periods [SQL Server replication]
- deactivating subscriptions
ms.assetid: 542f0613-5817-42d0-b841-fb2c94010665
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: f7045454dfd2d05e37e18cdc57f53090cf8b9e76
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52778355"
---
# <a name="set-the-expiration-period-for-subscriptions"></a>구독에 대한 만료 기간 설정
  이 항목에서는 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] 또는 [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] 을 사용하여 [!INCLUDE[tsql](../../../includes/tsql-md.md)]에서 구독 만료 기간을 설정하는 방법에 대해 설명합니다. 구독 만료 기간은 구독이 만료되어 제거되기 전까지 유효한 기간을 나타냅니다. 자세한 내용은 [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md)을 참조하세요.  
  
 **항목 내용**  
  
-   **시작하기 전 주의 사항:**  
  
     [권장 사항](#Recommendations)  
  
-   **다음을 사용하여 구독에 대한 만료 기간을 설정하려면**  
  
     다른 도구는 [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> 시작하기 전에  
  
###  <a name="Recommendations"></a> 권장 사항  
  
-   구독 만료 기간을 *게시 보존 기간*이라고도 합니다. 병합 복제 메타데이터의 정리는 다음과 같이 이 설정의 영향을 받습니다.  
  
    -   보존 기간에 도달하기 전까지는 복제 작업을 통해 게시 및 구독 데이터베이스의 메타데이터를 정리할 수 없습니다. 보존 기간을 너무 길게 설정하면 복제 성능이 저하될 수 있으므로 주의해야 합니다. 보존 기간 내에 모든 구독자가 정기적으로 동기화될 가능성이 있으면 보존 기간을 낮은 값으로 설정하는 것이 좋습니다.  
  
         병합 게시의 보존 기간은 다양한 표준 시간대의 구독자를 수용하기 위해 24시간의 유예 기간을 갖습니다. 예를 들어 보존 기간을 하루로 설정한 경우 실제 보존 기간은 48시간이 됩니다.  
  
    -   구독이 만료되지 않도록 지정할 수 있지만 이 경우 메타데이터를 정리할 수 없으므로 이 값은 사용하지 않도록 합니다.  
  
##  <a name="SSMSProcedure"></a> SQL Server Management Studio 사용  
 **게시 속성 - \<Publication>** 대화 상자의 **일반** 페이지에서 구독의 만료 기간을 설정합니다. 이 대화 상자에 액세스하는 방법은 [View and Modify Publication Properties](view-and-modify-publication-properties.md)을 참조하세요.  
  
#### <a name="to-set-the-expiration-period-for-subscriptions"></a>구독에 대한 만료 기간을 설정하려면  
  
1.  **게시 속성 - \<게시>** 대화 상자의 **일반** 페이지에 있는 **구독 만료** 섹션에서 구독을 만료해야 할지 여부를 지정합니다.  
  
2.  구독이 만료되어야 하는 경우 만료 기간을 지정합니다.  
  
##  <a name="TsqlProcedure"></a> Transact-SQL 사용  
 복제 저장 프로시저를 사용하여 게시를 만들 때 이 값을 설정하거나 나중에 이 값을 수정할 수 있습니다.  
  
#### <a name="to-set-the-expiration-period-for-a-subscription-to-a-snapshot-or-transactional-publication"></a>스냅숏 또는 트랜잭션 게시에 대한 구독 만료 기간을 설정하려면  
  
1.  게시자에서 [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql)을 실행합니다. 이때 **@retention**에서 구독 만료 기간을 설정하는 방법에 대해 설명합니다. 기본 만료 기간은 336시간입니다. 자세한 내용은 [Create a Publication](create-a-publication.md)를 참조하세요.  
  
#### <a name="to-set-the-expiration-period-for-a-subscription-to-a-merge-publication"></a>병합 게시에 대한 구독 만료 기간을 설정하려면  
  
1.  게시자에서 [sp_addmergepublication](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql)을 실행합니다. 이때 **@retention**에서 구독 만료 기간을 설정하는 방법에 대해 설명합니다. **@retention_period_unit**에 다음과 같은 만료 기간 표현 단위 중 하나를 지정합니다.  
  
    -   **1** = 주  
  
    -   **2** = 개월  
  
    -   **3** = 년  
  
     기본 만료 기간은 14일입니다. 자세한 내용은 [Create a Publication](create-a-publication.md)를 참조하세요.  
  
#### <a name="to-change-the-expiration-period-for-a-subscription-to-a-snapshot-or-transactional-publication"></a>스냅숏 또는 트랜잭션 게시에 대한 구독 만료 기간을 변경하려면  
  
1.  게시자에서 [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql)을 실행합니다. 이때 **@property** 에 **@property** , **@value**에서 구독 만료 기간을 설정하는 방법에 대해 설명합니다.  
  
#### <a name="to-change-the-expiration-period-for-a-subscription-to-a-merge-publication"></a>병합 게시에 대한 구독의 만료 기간을 변경하려면  
  
1.  게시자에서 [sp_helpmergepublication](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql)을 실행하고 **@publication** 및 **@publisher**에서 구독 만료 기간을 설정하는 방법에 대해 설명합니다. 결과 집합의 **retention_period_unit** 값은 다음 중 하나일 수 있습니다.  
  
    -   **0** = 일  
  
    -   **1** = 주  
  
    -   **2** = 개월  
  
    -   **3** = 년  
  
2.  게시자에서 [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql)을 실행합니다. 이때 **@property** 에 **@property** 을 지정하고 **@value**에서 구독 만료 기간을 설정하는 방법에 대해 설명합니다.  
  
3.  (옵션) 게시자에서 [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql)을 실행합니다. 이때 **retention_period_unit** 에 **@property** 을 지정하고 **@value**에서 구독 만료 기간을 설정하는 방법에 대해 설명합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md)   
 [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md)  
  
  
