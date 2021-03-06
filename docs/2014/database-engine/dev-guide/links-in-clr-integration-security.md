---
title: CLR 통합 보안의 링크 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- table-access links [CLR integration]
- security [CLR integration]
- invocation links [CLR integration]
- gated links [CLR integration]
ms.assetid: 168efd01-d12e-4bdf-a1b3-0b5c76474eaf
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 32974fc138cb5bcd444af18d0854c7a07d8fdcad
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48067204"
---
# <a name="links-in-clr-integration-security"></a>CLR 통합 보안의 링크
  이 섹션에서는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 사용자 코드 조각이 [!INCLUDE[tsql](../../includes/tsql-md.md)] 또는 관리 언어 중 하나로 상호 호출하는 방법을 설명합니다. 개체 간의 이러한 관계를 링크라고 합니다.  
  
## <a name="invocation-links"></a>호출 링크  
 호출 링크는 개체를 호출하는 사용자(예: 저장 프로시저를 호출하는 [!INCLUDE[tsql](../../includes/tsql-md.md)] 일괄 처리)나 CLR(공용 언어 런타임) 저장 프로시저 또는 함수에서의 코드 호출에 해당합니다. 호출 링크를 사용할 경우 호출 수신자에게 `EXECUTE` 권한이 있는 있는지 확인합니다.  
  
## <a name="table-access-links"></a>테이블 액세스 링크  
 테이블 액세스 링크는 테이블, 뷰 또는 테이블 반환 함수의 값을 검색하거나 수정하는 것에 해당합니다. 테이블 액세스 링크는 SELECT, INSERT, UPDATE 및 DELETE 권한에 따라 액세스를 보다 세부적으로 제어한다는 점을 제외하고는 호출 링크와 유사합니다.  
  
## <a name="gated-links"></a>게이트 링크  
 게이트 링크는 권한이 설정된 후에는 실행하는 동안 전체 개체 관계에서 권한을 확인하지 않는다는 것을 의미합니다. 두 개체 간 게이트 링크가 있는 경우 (예를 들어 개체 **x** 및 개체 **y**), 개체에 대 한 권한을 **y** 개체에서액세스되는다른개체및**y** 개체의 생성 시간에만 검사할지 **x**합니다. 개체 생성 당시 **x**, `REFERENCE` 권한을 확인 **y** 소유자에 대 한 **x**합니다. 실행 시 (예를 들어 개체를 호출 하는 사람이 **x**), 검사 권한은 **y** 또는 정적으로 참조 하는 다른 개체입니다. 실행 시 적절 한 권한이 개체에 대해 검사 됩니다 **x** 자체입니다.  
  
 게이트 링크는 항상 두 개체 사이의 메타데이터 종속성과 함께 사용됩니다. 이 메타데이터 종속성은 다른 개체가 종속되어 있는 경우 개체를 삭제하지 못하게 하는 관계로, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 카탈로그에서 설정합니다.  
  
 여러 종속 개체에 권한을 부여하는 것이 적절하지 않거나 관리하기 어려울 경우에 게이트 링크를 사용할 수 있습니다. CLR 어셈블리로의 [!INCLUDE[tsql](../../includes/tsql-md.md)] 진입점을 정의하는 개체(예: CLR 프로시저, 트리거, 함수, 형식 및 집계)와 이 개체가 정의된 어셈블리 사이에 게이트 링크가 사용됩니다. 이러한 개체에 대한 게이트 보안은 CLR 어셈블리에 정의된 [!INCLUDE[tsql](../../includes/tsql-md.md)] 진입점을 호출하려면 호출자에게 해당 [!INCLUDE[tsql](../../includes/tsql-md.md)] 진입점에 대한 적절한 권한만 있으면 된다는 것을 의미합니다. 호출자에게 해당 어셈블리나 이 어셈블리가 정적으로 참조하는 다른 어셈블리에 대한 권한은 없어도 됩니다. 어셈블리에 대한 권한은 [!INCLUDE[tsql](../../includes/tsql-md.md)] 진입점을 만들 때 확인됩니다.  
  
## <a name="sql-server-authorization-based-security"></a>SQL Server 권한 부여 기반 보안  
 다음은 CLR 기반 데이터베이스 개체의 호출 및 이들 개체 상호 간의 호출에 대한 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 보안 검사의 기본 규칙입니다. 처음 세 규칙은 어떤 권한을 어떤 개체에 대해 확인하는지를 정의하고 네 번째 규칙은 권한 확인의 실행 컨텍스트를 정의합니다.  
  
1.  동일한 개체 내에서 호출하는 경우를 제외하고 모든 호출에는 `EXECUTE` 권한이 필요합니다. 동일한 어셈블리 내에서 호출하는 경우에는 권한 검사가 필요하지 않습니다. 권한 확인은 실행 시 수행됩니다.  
  
2.  게이트 링크를 사용하려면 호출하는 개체를 만들 때 호출 수신자에 대한 `REFERENCE` 권한이 필요합니다. 개체를 만들 때 호출하는 개체의 소유자에 대한 권한을 확인합니다.  
  
3.  테이블 액세스 링크를 사용하려면 액세스하는 테이블 또는 뷰에 대해 해당하는 `SELECT`, `INSERT`, `UPDATE` 또는 `DELETE` 권한이 있어야 합니다.  
  
4.  권한 확인은 현재 실행 컨텍스트에 대해 수행됩니다. 호출자와 다른 실행 컨텍스트에서 프로시저와 함수를 만들 수 있습니다. 어셈블리는 항상 해당 어셈블리에 대해 정의된 프로시저, 함수 또는 트리거의 실행 컨텍스트에서 만들어집니다.  
  
## <a name="see-also"></a>관련 항목  
 [CLR 통합 보안](../../relational-databases/clr-integration/security/clr-integration-security.md)  
  
  
