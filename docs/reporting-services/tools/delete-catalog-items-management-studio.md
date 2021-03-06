---
title: 카탈로그 항목 삭제(Management Studio) | Microsoft Docs
ms.date: 03/01/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.technology: tools
ms.topic: conceptual
f1_keywords:
- sql13.swb.reportserver.deleteitems.f1
ms.assetid: b0599e01-6dc3-4484-80d4-022a412e0ebd
author: markingmyname
ms.author: maghan
ms.openlocfilehash: fc1cdce9ed2e26874eaa19cff7ad9634880fd1db
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47792121"
---
# <a name="delete-catalog-items-management-studio"></a>카탈로그 항목 삭제(Management Studio)
  이 페이지를 사용하여 공유 일정 및 역할 정의를 삭제할 수 있습니다.  
  
 여러 보고서 및 구독에 사용되는 공유 일정을 삭제하면 보고서 서버는 공유 일정을 사용하던 각 보고서 및 구독에 대해 개별적인 일정을 만듭니다. 각 개별 일정에는 공유 일정에 지정되었던 날짜, 시간 및 되풀이 패턴이 포함됩니다. [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 는 개별 일정을 중앙에서 관리하지 않습니다. 공유 일정을 삭제하면 개별 항목에 대한 일정 정보를 관리해야 합니다. 공유 일정을 삭제하기 전에 [일정 속성(보고서 페이지)](../../reporting-services/tools/schedule-properties-reports-page.md) 을 사용하여 현재 공유 일정을 사용하고 있는 보고서를 확인합니다.  
  
 역할 정의의 경우 역할 할당에 현재 사용 중이 아닌 역할 정의만 삭제할 수 있습니다. 현재 사용 중인 역할을 삭제하려고 시도하면 보고서 서버는 해당 역할을 삭제하지 않고 이에 대한 오류 메시지가 표시됩니다. 이 페이지에 현재 사용 중이 아닌 하나의 역할 정의만 있는 경우 **확인**을 클릭하면 이 역할 정의가 삭제됩니다. 이 페이지에 여러 역할이 있는 경우 보관하거나 제거할 역할을 선택할 수 없습니다. **확인**을 클릭하면 사용되지 않는 모든 역할 정의가 삭제됩니다.  
  
 삭제 작업은 실행 취소할 수 없습니다. 삭제한 항목을 복구하려면 해당 항목을 다시 만들거나 보고서 서버 데이터베이스의 백업 복사본을 복원해야 합니다.  
  
## <a name="options"></a>Options  
 **이름**  
 삭제할 항목의 이름을 지정합니다.  
  
 **형식**  
 삭제할 항목의 유형을 표시합니다.  
  
 **소유자**  
 소유자의 이름을 표시합니다. 대부분의 경우 시스템입니다.  
  
 **상태**  
 삭제 작업의 진행률 정보를 표시합니다.  
  
 **오류**  
 항목을 삭제하는 동안 오류가 발생할 경우 오류 코드를 표시합니다.  
  
## <a name="see-also"></a>참고 항목  
 [항목 삭제&#40;Management Studio&#41;](../../reporting-services/tools/delete-an-item-management-studio.md)   
 [Management Studio의 보고서 서버 F1 도움말](../../reporting-services/tools/report-server-in-management-studio-f1-help.md)   
 [일정 만들기, 수정 및 삭제](../../reporting-services/subscriptions/create-modify-and-delete-schedules.md)  
  
  
