---
title: MSSQLSERVER_21889 | Microsoft 문서
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 21889 (Database Engine error)
ms.assetid: ae199540-7986-4cc2-b782-cd22793236d3
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 635205cbc92121034cd8c949382c4910c794b55e
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47835351"
---
# <a name="mssqlserver21889"></a>MSSQLSERVER_21889
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>세부 정보  
  
|||  
|-|-|  
|제품 이름|SQL Server|  
|이벤트 ID|21889|  
|이벤트 원본|MSSQLSERVER|  
|구성 요소|SQLEngine|  
|심볼 이름|SQLErrorNum21889|  
|메시지 텍스트|SQL Server 인스턴스 ‘%s’이(가) 복제 게시자가 아닙니다. 인스턴스에서 게시 데이터베이스 ‘%s’을(를) 호스트하도록 설정하려면 배포자가 ‘%s’인 SQL Server 인스턴스 ‘%s’에서 **sp_adddistributor**를 실행하세요. 이때 원래 게시자에 사용된 것과 동일한 로그인 및 암호를 지정해야 합니다.|  
  
## <a name="explanation"></a>설명  
게시자 데이터베이스를 호스트하려면 SQL Server 인스턴스가 복제 게시자여야 합니다. **sp_validate_redirected_publisher**는 원격 서버에서 **sp_helpdistributor**를 호출하여 서버가 복제 게시자인지 여부를 확인합니다. 이 오류는 SQL Server의 대상 인스턴스가 복제 게시자가 아님을 나타냅니다.  
  
## <a name="user-action"></a>사용자 동작  
게시자 데이터베이스를 호스트하는 SQL Server 인스턴스에서 **sp_adddistributor**를 실행합니다. **sp_adddistributor**를 실행할 때 올바른 배포자를 지정합니다. *@password* 매개 변수에 대해 **sp_adddistributor**가 배포자에서 처음 실행될 때 사용된 것과 동일한 값을 사용합니다.  
  
