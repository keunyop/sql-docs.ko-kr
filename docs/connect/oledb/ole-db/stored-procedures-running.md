---
title: 저장된 프로시저 (OLE DB) 실행 | Microsoft Docs
description: 저장 프로시저 실행(OLE DB)
ms.custom: ''
ms.date: 06/12/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- stored procedures [OLE DB], executing
- OLE DB, stored procedures
- OLE DB Driver for SQL Server, stored procedures
author: pmasl
ms.author: pelopes
manager: craigg
ms.openlocfilehash: a016e7c0d6ffb59b01ab679bbe21029558f7966b
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47830791"
---
# <a name="stored-procedures---running"></a>저장 프로시저 - 실행
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  문을 실행할 때 클라이언트 응용 프로그램에서 직접 문을 실행하거나 준비하는 대신 데이터 원본의 저장 프로시저를 호출하면 다음과 같은 장점이 있습니다.  
  
-   성능 향상  
  
-   네트워크 오버헤드 감소  
  
-   일관성 향상  
  
-   정확성 향상  
  
-   기능 추가  
  
 OLE DB Driver for SQL Server를 지 원하는 세 가지 메커니즘을 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 반환 데이터를 사용 하 여 저장된 프로시저:  
  
-   프로시저의 모든 SELECT 문은 결과 집합을 생성합니다.  
  
-   프로시저는 출력 매개 변수를 통해 데이터를 반환할 수 있습니다.  
  
-   프로시저에는 정수 반환 코드가 있을 수 있습니다.  
  
 응용 프로그램은 저장 프로시저의 이러한 모든 출력을 처리할 수 있어야 합니다.  
  
 OLE DB 공급자는 결과를 처리하는 동안 각각 다른 시기에 출력 매개 변수와 반환 값을 반환합니다. SQL Server용 OLE DB 드라이버의 경우 저장 프로시저에서 반환되는 결과 집합을 소비자가 검색 또는 취소하기 전에는 출력 매개 변수와 반환 코드를 제공하지 않습니다. 반환 코드와 출력 매개 변수는 서버에서 보내는 마지막 TDS 패킷에서 반환됩니다.  
  
 공급자는 출력 매개 변수와 반환 값을 반환할 때 DBPROP_OUTPUTPARAMETERAVAILABILITY 속성을 사용하여 보고합니다. 이 속성은 DBPROPSET_DATASOURCEINFO 속성 집합에 들어 있습니다.  
  
 SQL Server용 OLE DB 드라이버는 DBPROP_OUTPUTPARAMETERAVAILABILITY 속성을 DBPROPVAL_OA_ATROWRELEASE로 설정하여 결과 집합이 처리 또는 해제되기 전에는 반환 코드와 출력 매개 변수가 반환되지 않도록 지정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [저장 프로시저](../../oledb/ole-db/stored-procedures.md)  
  
  
