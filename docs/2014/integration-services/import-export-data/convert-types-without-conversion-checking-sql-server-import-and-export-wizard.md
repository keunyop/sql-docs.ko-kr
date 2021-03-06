---
title: 변환 (SQL Server 가져오기 및 내보내기 마법사)를 확인 하지 않고 형식 변환 | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.nomappingfile.f1
ms.assetid: 87d9d3e5-477f-4117-a37f-bff53ea3e14d
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: ea8b678731a10b483c233cdb17b394a22f647060
ms.sourcegitcommit: 5a8678bf85f65be590676745a7fe4fcbcc47e83d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58374611"
---
# <a name="convert-types-without-conversion-checking-sql-server-import-and-export-wizard"></a>변환 검사를 수행하지 않고 형식 변환(SQL Server 가져오기 및 내보내기 마법사)
  마법사에서 **데이터 형식 변환 및 매핑 파일을 하나 이상 찾을 수 없는 경우** 변환 검사를 수행하지 않고 형식 변환 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 페이지를 사용하여 마법사에서 수행하는 매핑을 검토할 수 있습니다. 이 페이지에는 누락된 파일을 식별하는 데 도움이 되는 정보가 포함되어 있습니다.  
  
 이 마법사에 대 한 자세한 내용은 참조 하세요 [SQL Server 가져오기 및 내보내기 마법사](import-and-export-data-with-the-sql-server-import-and-export-wizard.md)합니다. 마법사 시작 옵션에 대 한 마법사를 성공적으로 실행 하는 데 필요한 권한에 대 한 자세한 내용은 참조 하세요 [SQL Server 가져오기 및 내보내기 마법사를 실행](start-the-sql-server-import-and-export-wizard.md)합니다.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 가져오기 및 내보내기 마법사는 원본에서 대상으로 데이터를 복사할 목적으로 사용됩니다. 이 마법사는 대상 데이터베이스 및 대상 테이블도 만들 수 있습니다. 그러나 여러 개의 데이터베이스 또는 테이블을 복사하거나 다른 종류의 데이터베이스 개체를 복사할 경우 대신 데이터베이스 복사 마법사를 사용해야 합니다. 자세한 내용은 [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md)을 참조하세요.  
  
  
