---
title: 커서 유형 | Microsoft 문서
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC applications, cursors
- cursors [ODBC], types
- ODBC cursors, types
ms.assetid: 3a916cc7-f352-42cb-8b83-f78e06cef991
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 6d88b48c1fc4166b32821da9cdaaa5eb7f6c2e60
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48072293"
---
# <a name="cursor-types"></a>커서 유형
  ODBC Microsoft에서 지 원하는 네 가지 커서 유형을 정의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 하며 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 드라이버. 이 커서 결과 집합에 변경 내용을 검색 하는 기능에 따라 다양 하 고 리소스에서 예: 메모리 사용 공간 **tempdb**합니다. 커서는 이러한 행을 다시 인출할 때만 행 변경 내용을 검색할 수 있습니다. 데이터 원본은 현재 인출된 행의 변경 내용을 커서에 알릴 수 없습니다. 커서를 통해 변경되지 않은 내용에 대한 커서의 검색 기능은 트랜잭션 격리 수준에 의해서도 영향을 받습니다.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]지원하는 네 가지 ODBC 커서 유형은 다음과 같습니다.  
  
-   정방향 전용 커서는 스크롤을 지원하지 않으며 커서의 처음부터 끝까지 순차적인 행 인출만 지원합니다.  
  
-   정적 커서는 기본 제공 **tempdb** 는 커서가 열릴 때. 항상 커서가 열렸을 당시의 결과 집합을 표시합니다. 데이터 변경 내용은 반영되지 않습니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 정적 커서는 항상 읽기 전용입니다. 정적 서버 커서의 작업 테이블으로 빌드되므로 **tempdb**, 커서 결과 집합의 크기에서 허용 되는 최대 행 크기를 초과할 수 없습니다 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]합니다.  
  
-   키 집합 커서의 멤버 자격과 결과 집합의 행 순서는 커서가 열릴 때 고정됩니다. 키가 아닌 열의 변경 내용은 커서를 통해 볼 수 있습니다.  
  
-   동적 커서는 정적 커서의 반대 개념입니다. 동적 커서는 행의 모든 변경 내용을 결과 집합에 반영합니다. 따라서 인출할 때마다 결과 집합에서 행의 데이터 값, 순서 및 멤버 자격이 변경될 수 있습니다.  
  
## <a name="see-also"></a>관련 항목  
 [커서를 사용 하 여 &#40;ODBC&#41;](using-cursors-odbc.md)  
  
  
