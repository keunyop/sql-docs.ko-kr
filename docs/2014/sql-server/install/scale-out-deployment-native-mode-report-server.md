---
title: 스케일 아웃 배포 (기본 모드 보고서 서버) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
f1_keywords:
- SQL12.rsconfigtool.scaleoutdeployment.F1
ms.assetid: 4df38294-6f9d-4b40-9f03-1f01c1f0700c
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: c091c115f9e03fbc0f1243e1c2fcf3a075f3586f
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48099943"
---
# <a name="scale-out-deployment-native-mode-report-server"></a>확장 배포(기본 모드 보고서 서버)
  사용 된 **스케일 아웃 배포** 페이지에서 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 스케일 아웃 배포에 대 한 초기화 상태를 보거나 보고서 서버 스케일 아웃 배포에 조인 하는 Configuration Manager입니다. *스케일 아웃 배포* 는 단일 보고서 서버 데이터베이스를 공유하는 두 개 이상의 보고서 서버 인스턴스를 말합니다.  
  
 [!INCLUDE[applies](../../includes/applies-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 기본 모드입니다.  
  
 *초기화된 보고서 서버* 는 보고서 서버 데이터베이스에 저장된 중요한 데이터를 암호화 및 해독할 수 있는 서버입니다(저장된 자격 증명 및 연결 문자열은 암호화되어 데이터베이스에 저장됨). 보고서 서버 작업을 위해서는 보고서 서버 초기화가 필요합니다.  
  
 *스케일 아웃 배포* 는 다음과 같은 시나리오에서 사용됩니다.  
  
-   서버 클러스터에 있는 여러 보고서 서버의 부하 분산을 위한 선행 조건. 여러 보고서 서버의 부하를 분산하려면 먼저 같은 보고서 서버 데이터베이스를 공유하도록 구성해야 합니다.  
  
-   한 서버는 대화형 보고서 처리에 사용하고 다른 서버는 예약된 보고서 처리에 사용하는 방식으로 보고서 서버 애플리케이션을 여러 컴퓨터에 분할하려는 경우. 이 시나리오에서 각 서버 인스턴스는 공유 보고서 서버 데이터베이스에 저장된 같은 보고서 서버 내용에 대해 각기 다른 유형의 요청을 처리합니다.  
  
 스케일 아웃 배포를 구성하려면 같은 보고서 서버 데이터베이스에 연결된 두 개 이상의 보고서 서버 인스턴스부터 시작합니다. 인스턴스를 모두 설치한 후 첫 번째 보고서 서버에 연결한 다음 확장 배포 페이지를 사용하여 각 추가 인스턴스를 조인합니다. 데이터베이스를 사용하도록 이미 초기화된 보고서 서버만 추가 노드를 초기화할 수 있습니다.  
  
 이 페이지를 열려면 시작 합니다 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 선택한 Configuration Manager **스케일 아웃 배포** 탐색 창에서. 자세한 내용은 [Reporting Services 구성 관리자&#40;기본 모드&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md)을 참조하세요.  
  
## <a name="options"></a>변수  
 **SQL Server 이름**  
 이름을 지정 합니다 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] 보고서 서버 데이터베이스를 호스팅하는 인스턴스.  
  
 **Database Name**  
 현재 보고서 서버 인스턴스에 연결된 데이터베이스 이름을 지정합니다.  
  
 **서버 모드**  
 서버 및 데이터베이스 모드를 표시합니다. 서버 모드는 기본 모드 또는 SharePoint 통합 모드입니다. 두 모드에서 모두 확장 배포가 지원됩니다.  
  
 **Server**  
 보고서 서버 이름을 표시합니다. 대부분의 경우 보고서 서버가 설치된 컴퓨터의 이름입니다.  
  
 **인스턴스**  
 보고서 서버 인스턴스 이름을 표시합니다. 보고서 서버 인스턴스는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스를 기반으로 합니다.  
  
 **상태**  
 보고서 서버를 초기화할 것인지 또는 스케일 아웃 배포 조인을 대기할 것인지 표시합니다.  
  
-   스케일 아웃 배포에 포함되지 않은 독립 실행형 보고서 서버인 경우 이 페이지에는 보고서 서버 인스턴스가 전용 보고서 서버 데이터베이스를 기준으로 초기화된다고 표시됩니다. 상태는 **조인됨**으로 설정됩니다.  
  
-   스케일 아웃 배포 조인을 대기하는 보고서 서버인 경우 이 페이지에서 서버, 인스턴스 및 상태 값이 비어 있습니다. 이미 다른 보고서 서버 인스턴스에서 사용하는 기존 보고서 서버 데이터베이스를 선택한 경우 보고서 서버는 스케일 아웃 배포 조인을 대기합니다. 이 페이지에는 이미 팜에 조인된 보고서 서버에 연결하도록 안내하는 메시지가 표시됩니다. 이 요청을 완료하려면 **연결**을 클릭하여 이미 보고서 서버 데이터베이스를 사용하도록 초기화된 보고서 서버를 선택하고 **확장 배포**를 클릭하여 **조인 대기**상태의 보고서 서버 인스턴스를 선택한 다음 **초기화**를 클릭합니다.  
  
-   보고서 서버가 현재 스케일 아웃 배포의 일부인 경우 이 페이지에서는 동일한 보고서 서버 데이터베이스를 공유하는 모든 보고서 서버 인스턴스의 초기화 상태를 표시합니다. 스케일 아웃 배포의 상태를 보는 작업은 연결된 서버와 관련이 없습니다. 상태 정보는 스케일 아웃 배포의 모든 노드에 대해 동일하게 보고됩니다.  
  
     이미 스케일 아웃 배포에 하위 보고서 서버인 경우 이 페이지를 사용하여 노드를 추가하거나 제거할 수 있습니다.  
  
 **초기화**  
 스케일 아웃 배포에 보고서 서버를 추가하려면 **초기화** 를 클릭합니다. 이 단계에서는 공유 보고서 서버 데이터베이스의 대칭 키를 사용하도록 보고서 서버를 구성합니다. **초기화** 를 사용하여 보고서 서버 인스턴스를 스케일 아웃 배포에 추가하거나 마이그레이션 또는 설치 문제를 해결할 수 있습니다.  
  
 보고서 서버 인스턴스는 공유 보고서 서버 데이터베이스 연결이 이미 구성된 경우에만 사용할 수 있습니다. 또한 보고서 서버 데이터베이스를 사용하도록 이미 초기화된 보고서 서버를 초기화해야 합니다.  
  
 **제거**  
 보고서 서버 데이터베이스에서 선택한 보고서 서버 인스턴스의 암호화 키를 제거하려면 **제거** 를 클릭합니다. 키를 제거하여 스케일 아웃 배포에서 보고서 서버를 제거하거나 마이그레이션 또는 설치 문제를 해결할 수 있습니다. 이 옵션을 사용하면 지정한 보고서 서버 인스턴스의 암호화 키만 제거됩니다. 보고서 서버의 암호화된 데이터는 영향을 받지 않습니다.  
  
 예방 조치로 대칭 키를 제거하기 전에 백업 복사본을 만들어야 합니다. 목록에 있는 마지막 보고서 서버의 암호화 키를 제거하면 해당 데이터베이스에 대한 이후의 모든 보고서 서버 초기화에 대해 새 요구 사항이 발생합니다. 즉, 보고서 서버를 초기화한 다음 대칭 키의 백업 복사본을 복원해야 합니다. 현재 보고서 서버 데이터베이스에 있는 암호화된 데이터에 액세스하려면 대칭 키를 복원해야 합니다.  
  
 암호화된 데이터가 더 이상 필요하지 않거나 키의 백업 복사본이 없는 경우 암호화된 데이터를 삭제해야 합니다. 자세한 내용은 [암호화 키 &#40;SSRS 기본 모드&#41;](../../../2014/sql-server/install/encryption-keys-ssrs-native-mode.md)합니다.  
  
## <a name="see-also"></a>관련 항목  
 [보고서 서버 초기화&#40;SSRS 구성 관리자&#41;](../../reporting-services/install-windows/ssrs-encryption-keys-initialize-a-report-server.md)   
 [암호화 키 구성 및 관리&#40;SSRS 구성 관리자&#41;](../../reporting-services/install-windows/ssrs-encryption-keys-manage-encryption-keys.md)   
 [기본 모드 보고서 서버 확장 배포 구성&#40;SSRS 구성 관리자&#41;](../../reporting-services/install-windows/configure-a-native-mode-report-server-scale-out-deployment.md)  
  
  
