---
title: SQL Server 오류 로그 보기(SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 09/29/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- viewing logs
- displaying logs
- errors [SQL Server], logs
- logs [SQL Server], SQL Server error logs
- logs [SQL Server], viewing
ms.assetid: 55f468ba-146c-4ab3-95cd-d35d051afd12
author: julieMSFT
ms.author: jrasnick
manager: craigg
ms.openlocfilehash: 71945328b2efeae919725ec687669104ce3d9951
ms.sourcegitcommit: 334cae1925fa5ac6c140e0b2c38c844c477e3ffb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/13/2018
ms.locfileid: "53376305"
---
# <a name="view-the-sql-server-error-log-sql-server-management-studio"></a>SQL Server 오류 로그 보기(SQL Server Management Studio)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 오류 로그에는 문제 해결에 사용할 수 있는 사용자 정의 이벤트와 특정 시스템 이벤트가 포함됩니다. 

## <a name="view-the-logs"></a>로그 보기

1. SQL Server Management Studio에서 **개체 탐색기**를 선택합니다. **개체 탐색기**를 열려면 F8을 선택합니다. 또는 상단 메뉴에서 **보기**를 선택하고 **개체 탐색기**를 선택합니다.
    
    ![Object_Explorer](../../relational-databases/performance/media/object-explorer.png) 

2. **개체 탐색기**에서 SQL Server의 인스턴스에 연결한 다음 해당 인스턴스를 확장합니다.
  
3. **관리** 섹션(볼 수 있는 권한이 있다고 가정)을 찾아 확장합니다.

4. **SQL Server 로그**를 마우스 오른쪽 단추로 클릭하고 **보기**를 선택하고 **SQL Server 로그 보기**를 선택합니다.

    ![View_SQLServer_Log_SSMS](../../relational-databases/performance/media/view-sqlserver-log-ssms.png) 
 
5. 확인할 로그 목록이 포함된 **로그 파일 뷰어**가 나타납니다(시간이 약간 걸릴 수 있음).
  
  ## <a name="see-also"></a>관련 항목:
  자세한 내용은 [MSSQLTips.com](https://www.mssqltips.com/)의 유용한 게시물인 [Identify location of the SQL Server Error Log file](https://www.mssqltips.com/sqlservertip/2506/identify-location-of-the-sql-server-error-log-file/)(SQL Server 오류 로그 파일의 위치 식별)을 참조하세요.

