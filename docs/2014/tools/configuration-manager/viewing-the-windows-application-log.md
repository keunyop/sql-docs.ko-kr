---
title: Windows 애플리케이션 로그 보기 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- application logs [SQL Server]
- Windows application logs [SQL Server]
- viewing Windows application logs
- errors [SQL Server], logs
- system logs [SQL Server]
- security logs [SQL Server]
- displaying Windows application logs
- logs [SQL Server], Windows application logs
ms.assetid: f9853b74-7db7-47cc-b957-e49ed5bc0a1a
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 654d4adbd2e4baa97b16e83261089d8d78289af6
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52779575"
---
# <a name="viewing-the-windows-application-log"></a>Windows 애플리케이션 로그 보기
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 가 Microsoft Windows 응용 프로그램 로그를 사용하도록 구성된 경우 각 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 세션은 이 로그에 새 이벤트를 씁니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 오류 로그와는 달리 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]인스턴스를 시작할 때마다 새 응용 프로그램 로그가 생성되지는 않습니다.  
  
 Windows 이벤트 뷰어 또는 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]의 로그 뷰어를 사용하여 Windows 애플리케이션 로그를 보고 관리하십시오.  
  
 이벤트 뷰어로 볼 수 있는 로그에는 세 가지가 있습니다.  
  
|Windows 로그 유형|Description|  
|----------------------|-----------------|  
|시스템 로그|Windows 운영 체제 구성 요소에서 로그한 이벤트를 기록합니다. 예를 들어 시작할 때 드라이버나 다른 시스템 구성 요소 로드를 실패했으면 시스템 로그에 기록됩니다.|  
|보안 로그|실패한 로그인 시도와 같은 보안 이벤트를 기록합니다. 이것은 보안 시스템의 변경 내용을 추적하고 일어날 수도 있는 보안 침해를 식별할 때 유용합니다. 예를 들어 시스템 로그온 시도는 사용자 관리자의 감사 설정에 따라 보안 로그에 기록됩니다.<br /><br /> 보안 로그를 보려면 **sysadmin** 고정 서버 역할의 멤버여야 합니다.|  
|애플리케이션 로그|애플리케이션에서 로그한 이벤트를 기록합니다. 예를 들어 데이터베이스 애플리케이션은 파일 오류를 애플리케이션 로그에 기록할 수 있습니다.|  
  
 이벤트 뷰어 사용, 애플리케이션 로그 관리 및 표시된 정보를 이해하는 방법은 Windows 설명서를 참조하십시오.  
  
 **Windows 응용 프로그램 로그를 보려면**  
  
 [Windows 응용 프로그램 로그 보기&#40;Windows&#41;](../../relational-databases/performance/view-the-windows-application-log-windows-10.md)  
  
  
