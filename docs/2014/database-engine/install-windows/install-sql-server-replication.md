---
title: SQL Server 복제 설치 | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- components [SQL Server replication]
- command line installations [SQL Server replication]
- installing replication
- replication [SQL Server], installing
- command prompt [SQL Server replication]
ms.assetid: c50ad078-060b-4a8d-ad45-9e31a8d85729
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 3fd70d208960af1f121795bfdf8a657ceaf59f21
ms.sourcegitcommit: 87f29b23d5ab174248dab5d558830eeca2a6a0a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51018228"
---
# <a name="install-sql-server-replication"></a>SQL Server 복제 설치
  복제 구성 요소는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 설치 마법사 또는 명령 프롬프트를 사용하여 설치할 수 있습니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]인스턴스를 설치할 때나 기존 인스턴스를 수정할 때 복제를 설치할 수 있습니다.  
  
 복제 구성 요소를 설치한 후에는 복제를 사용하기 전에 먼저 서버를 구성해야 합니다. 자세한 내용은 [온라인 설명서의](../../relational-databases/replication/configure-distribution.md) 배포 구성 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 을 참조하세요.  
  
> [!IMPORTANT]  
>  기존 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]인스턴스를 수정할 때 복제 구성 요소를 설치하는 경우 설치가 완료된 다음 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트를 중지하고 다시 시작해야 합니다. 이 동작을 수행하면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트가 복제 에이전트 하위 시스템을 인식하며 작업 단계에서 복제 에이전트를 호출할 수 있습니다.  
  
## <a name="installing-replication-by-using-setup"></a>설치 프로그램을 사용하여 복제 설치  
 **다음의 새 인스턴스를 설치할 때 복제를 설치하려면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**  
  
-   RMO(복제 관리 개체)를 비롯한 복제 구성 요소를 설치하려면 설치 마법사의 **기능 선택** 페이지에서 **SQL Server 복제** 를 선택합니다.  
  
## <a name="installing-replication-from-the-command-prompt"></a>명령 프롬프트에서 복제 설치  
 **다음의 새 인스턴스를 설치할 때 복제를 설치하려면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**  
  
-   참조 [명령 프롬프트에서 SQL Server 2014 설치](install-sql-server-from-the-command-prompt.md)합니다.  
  
## <a name="see-also"></a>관련 항목  
 [SQL Server 2014 설치](install-sql-server.md)   
 [명령 프롬프트에서 SQL Server 2014 설치](install-sql-server-from-the-command-prompt.md)   
 [SQL Server 2014 버전에서 지원하는 기능](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
  
