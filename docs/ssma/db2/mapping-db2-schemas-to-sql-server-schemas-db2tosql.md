---
title: DB2 스키마를 SQL Server 스키마 (DB2ToSQL)에 매핑 | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 05ff7bd4-e60b-4f48-a893-bc2346aa9a8a
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: e9ccc7648be4915a68b798f314689d961113639a
ms.sourcegitcommit: 1ab115a906117966c07d89cc2becb1bf690e8c78
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2018
ms.locfileid: "52409513"
---
# <a name="mapping-db2-schemas-to-sql-server-schemas-db2tosql"></a>DB2 스키마를 SQL Server 스키마 (DB2ToSQL)에 매핑
DB2의 경우 각 데이터베이스에는 하나 이상의 스키마입니다. SSMA 기본적으로 DB2 스키마의 모든 개체를 마이그레이션하는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 스키마에 대 한 명명 된 데이터베이스입니다. DB2 스키마 간의 매핑을 사용자 지정할 수는 있지만 및 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스입니다.  
  
## <a name="db2-and-sql-server-schemas"></a>DB2 및 SQL Server 스키마  
DB2 데이터베이스 스키마를 포함합니다. 인스턴스의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 여러 데이터베이스에는 각각 여러 스키마를 가질 수를 포함 합니다.  
  
DB2 개념 스키마에 매핑되는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 개념이 데이터베이스 및 해당 스키마 중 하나입니다. 예를 들어 DB2 라는 스키마가 있을 **HR**합니다. 인스턴스의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 라는 데이터베이스가 있을 **HR**, 되며 해당 데이터베이스 내의 스키마입니다. 하나의 스키마를 **dbo** (또는 데이터베이스 소유자) 스키마. 기본적으로 DB2 스키마 **HR** 매핑될 합니다 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스 및 스키마 **HR.dbo**합니다. SSMA 참조는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 스키마로 데이터베이스 및 스키마의 조합입니다.  
  
DB2 간의 매핑을 수정할 수 있습니다 및 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 스키마입니다.  
  
## <a name="modifying-the-target-database-and-schema"></a>대상 데이터베이스 및 스키마를 수정합니다.  
SSMA에 매핑할 수 있습니다 DB2 스키마를 사용 가능한 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 스키마입니다.  
  
**데이터베이스 및 스키마를 수정 하려면**  
  
1.  DB2 메타 데이터 탐색기에서 선택 **스키마**합니다.  
  
    **스키마 매핑** 탭 역시 사용할 수 있는 개별 데이터베이스를 선택 합니다 **스키마** 폴더 또는 개별 스키마입니다. 목록에는 **스키마 매핑** 탭은 선택한 개체에 대 한 사용자 지정 합니다.  
  
2.  오른쪽 창에서을 클릭 합니다 **스키마 매핑** 탭 합니다.  
  
    대상 값이 오는 모든 DB2 스키마의 목록이 표시 됩니다. 이 대상 표기법을 두 부분으로에서 표시 됩니다 (*database.schema*)에서 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 프로그램 개체 및 데이터를 마이그레이션할 수 있습니다.  
  
3.  변경 하 고 클릭 하려는 매핑을 포함 하는 행 선택 **수정**합니다.  
  
    에 **대상 스키마 선택** 대화 상자에서 사용할 수 있는 대상 데이터베이스 및 스키마 또는 데이터베이스와 스키마 2 부 표기법 (database.schema) 텍스트 상자에 이름과 클릭 형식에 대 한 찾아보기 있습니다 **확인**.  
  
4.  대상에 변경 된 **스키마 매핑** 탭 합니다.  
  
**매핑 모드**  
  
-   SQL Server에 매핑  
  
원본 데이터베이스는 대상 데이터베이스에 매핑할 수 있습니다. 기본적으로 원본 데이터베이스 매핑된 대상 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 있는 연결한 SSMA를 사용 하 여 데이터베이스입니다. 매핑되는 대상 데이터베이스에 존재 하지 않는 경우 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], 다음 메시지와 함께 나타납니다 **"데이터베이스 및/또는 스키마를 대상에 존재 하지 않는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 메타 데이터입니다. 동기화 하는 동안 만들어집니다. 수행할 계속 하 시겠습니까 "?** 예를 클릭 합니다. 마찬가지로 존재 하지 않는 대상 스키마에 스키마를 매핑할 수 있습니다 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 동기화 하는 동안 만들어질 수 있는 데이터베이스입니다.  
  
## <a name="reverting-to-the-default-database-and-schema"></a>기본 데이터베이스 및 스키마를 되돌리기  
DB2 스키마를 간의 매핑을 사용자 지정 하면 및 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 스키마 매핑을 다시 기본 값으로 되돌릴 수 있습니다.  
  
**기본 데이터베이스 및 스키마를 되돌리려면**  
  
1.  스키마 매핑 탭에서 모든 행을 선택 하 고 클릭 **기본값으로** 기본 데이터베이스 및 스키마를 되돌리려면 합니다.  
  
## <a name="next-steps"></a>다음 단계  
DB2 개체를 변환 하는 분석 하려는 경우 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 개체를 할 수 있습니다 [데이터 마이그레이션 보고서 (SSMA 공통)](https://msdn.microsoft.com/bbfb9d88-5a98-4980-8d19-c5d78bd0d241)합니다.  
  
## <a name="see-also"></a>관련 항목  
[SQL Server에 연결 &#40;DB2eToSQL&#41;](../../ssma/db2/connecting-to-sql-server-db2etosql.md)  
[SQL Server로 데이터베이스 마이그레이션 DB2 &#40;DB2ToSQL&#41;](../../ssma/db2/migrating-db2-databases-to-sql-server-db2tosql.md)  
  
