---
title: ICommand (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ICommand [SQL Server Native Client]
ms.assetid: 5e24b3a0-0658-44fc-b653-f4c52f9eb328
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d4e583b08cf0ba55268c4acb9e19722d3a693d50
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48187783"
---
# <a name="icommand-ole-db"></a>ICommand(OLE DB)
  이 항목에서는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client의 고유한 OLE DB 동작을 설명합니다.  
  
## <a name="icommandexecute"></a>ICommand::Execute  
 열 크기보다 큰 데이터를 삽입하면 일반적으로 오류가 발생합니다. 그러나 경우에 따라서는 S_OK가 반환되는 상황에서 *dwStatus* 가 DBSTATUS_S_TRUNCATED로 설정될 수도 있습니다. 이 문제는 대개 매개 변수를 사용하여 데이터를 삽입할 때 열이 너무 작아 데이터를 저장할 수 없고 `ICommandWithParameters::SetParameterInfo`가 호출되지 않은 경우에 발생합니다.  
  
## <a name="see-also"></a>관련 항목  
 [인터페이스 &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
