---
title: '3단원: 병합 게시에 구독 동기화 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 49008384-2c55-4080-a890-9bceb40e4d6d
author: craigg-msft
ms.author: craigg
manager: craigg
ms.openlocfilehash: 847b833d793d3b572b44bcb77903c534300109b7
ms.sourcegitcommit: 7aa6beaaf64daf01b0e98e6c63cc22906a77ed04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54128473"
---
# <a name="lesson-3-synchronizing-the-subscription-to-the-merge-publication"></a>3단원: 병합 게시에 구독 동기화
  이 단원에서는 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]에서 병합 에이전트를 시작하여 구독을 초기화합니다. 또한 이 절차를 사용하여 게시자와 동기화합니다. 이 단원에서는 이전 단원을 완료 해야 [단원 2: 병합 게시에 대 한 구독 만들기](lesson-2-creating-a-subscription-to-the-merge-publication.md)합니다.  
  
### <a name="to-start-synchronization-and-initialize-the-subscription"></a>동기화를 시작하고 구독을 초기화하려면  
  
1.  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]에서 구독자에 연결하고 해당 서버 노드를 확장한 다음 **복제** 폴더를 확장합니다.  
  
2.  **로컬 구독** 폴더에서 **SalesOrdersReplica** 데이터베이스의 구독을 마우스 오른쪽 단추로 클릭한 다음 **동기화 상태 보기**를 클릭합니다.  
  
3.  **시작** 을 클릭하여 구독을 초기화합니다.  
  
## <a name="next-steps"></a>다음 단계  
 병합 에이전트를 실행하여 동기화를 시작하고 구독을 초기화했습니다. 또한 게시자나 구독자에 있는 **SalesOrderHeader** 나 **SalesOrderDetail** 테이블에서 데이터를 삽입, 업데이트 또는 삭제할 수 있고 네트워크가 연결되어 있을 때 이 절차를 반복하여 게시자와 구독자 사이의 데이터를 동기화한 다음 다른 서버에 있는 **SalesOrderHeader** 나 **SalesOrderDetail** 테이블을 쿼리하여 복제된 변경 내용을 볼 수 있습니다.  
  
 이로써 모바일 클라이언트와의 데이터 복제 자습서를 마쳤습니다. 트랜잭션 복제를 사용 하는 유사한 자습서를 참조 하세요. [자습서: 연결 된 서버 간에 데이터를 지속적으로 복제](tutorial-replicating-data-between-continuously-connected-servers.md)합니다.  
  
## <a name="see-also"></a>관련 항목  
 [스냅숏으로 구독 초기화](initialize-a-subscription-with-a-snapshot.md)   
 [데이터 동기화](synchronize-data.md)   
 [끌어오기 구독 동기화](synchronize-a-pull-subscription.md)  
  
  
