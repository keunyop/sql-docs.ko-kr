---
title: 쿼리 결과 요약(Visual Database Tools) | Microsoft 문서
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- queries [SQL Server], results
- aggregate queries [SQL Server]
ms.assetid: c9e15350-ed57-4d95-814d-815fbebfd86b
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 9236c31b8ae7cb248b0ce78f87d486039b3d704b
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47759631"
---
# <a name="summarize-query-results-visual-database-tools"></a>쿼리 결과 요약(Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
집계 쿼리를 만들 때 특정 논리 원칙이 적용됩니다. 예를 들어, 요약 쿼리에서는 개별 행의 내용을 표시할 수 없습니다. 쿼리 및 뷰 디자이너를 사용하면 [다이어그램 창](../../ssms/visual-db-tools/diagram-pane-visual-database-tools.md) 및 [조건 창](../../ssms/visual-db-tools/criteria-pane-visual-database-tools.md) 의 동작에 따라 이러한 원칙을 준수할 수 있습니다.  
  
집계 쿼리의 원칙과 쿼리 및 뷰 디자이너의 동작을 이해하면 논리적으로 올바른 집계 쿼리를 만들 수 있습니다. 가장 우선하는 원칙은 집계 쿼리를 사용하면 요약 정보만 만들어진다는 것입니다. 따라서 나머지 대부분의 원칙은 집계 쿼리 내의 개별 데이터 열을 참조할 수 있는 방법에 대해 설명합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
[집계 쿼리에서 열 작업&#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/work-with-columns-in-aggregate-queries-visual-database-tools.md)  
GROUP BY, WHERE 및 HAVING 절을 사용하여 열을 그룹화하고 요약하는 데 관련된 기본적인 개념을 설명합니다.  
  
[테이블의 행 계산&#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/count-rows-in-a-table-visual-database-tools.md)  
테이블의 행 수 또는 테이블에서 조건 집합을 충족하는 행 수를 계산하는 방법에 대해 설명합니다.  
  
[테이블에 있는 모든 행의 값 요약 또는 집계&#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md)  
그룹화된 행 집합이 아닌 모든 행을 요약하는 방법에 대해 설명합니다.  
  
[사용자 지정 식을 사용하여 값 요약 또는 집계&#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-or-aggregate-values-using-custom-expressions-visual-database-tools.md)  
미리 정의된 절을 사용하는 대신 요약 또는 집계 식을 사용하는 방법에 대해 설명합니다.  
  
## <a name="related-sections"></a>관련 섹션  
[쿼리 및 뷰 디자인 방법 도움말 항목&#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/design-queries-and-views-how-to-topics-visual-database-tools.md)  
쿼리 및 뷰 디자이너를 사용하는 방법과 관련된 항목에 대한 링크를 제공합니다.  
  
