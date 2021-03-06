---
title: 데이터 원본 (ODBC)를 삭제 합니다. | Microsoft 문서
ms.custom: ''
ms.date: 08/01/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [ODBC]
ms.assetid: 910e3e16-7b91-49d8-80bb-b4243926afaa
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 087e2194fb5d0963e8fd9cb4aef0d0193359de04
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47818662"
---
# <a name="configuring-the-sql-server-odbc-driver---delete-a-data-source"></a>SQL Server ODBC 드라이버 구성 - 데이터 원본 삭제
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] 이상 버전에서 ODBC 응용 프로그램을 사용하려면 이전 버전의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 카탈로그 저장 프로시저의 버전을 업그레이드하는 방법과 데이터 원본을 추가, 삭제 및 테스트하는 방법을 알아 두어야 합니다.  
  
  ODBC 관리자를 프로그래밍 방식으로 사용 하 여 데이터 원본을 삭제할 수 있습니다 (사용 하 여 [SQLConfigDataSource](../../relational-databases/native-client-odbc-api/sqlconfigdatasource.md)), 또는 (경우 파일 데이터 원본 이름) 파일을 삭제 하 여 합니다.  
  
### <a name="to-delete-a-data-source-by-using-odbc-administrator"></a>ODBC 관리자를 사용하여 데이터 원본을 삭제하려면  
  
1.  **Control Panel**오픈 **관리 도구**, 다음 중 하나를 두 번 클릭 하 고 **ODBC 데이터 원본 (64 비트)** 또는 **ODBC데이터원본(32비트)**. 또는 명령 프롬프트에서 odbcad32.exe를 실행할 수도 있습니다.  
  
2.  클릭 합니다 **사용자 DSN**를 **시스템 DSN**, 또는 **파일 DSN** 탭 합니다.  
  
3.  삭제할 데이터 원본을 선택 합니다.  
  
4.  클릭 **제거**를 선택한 다음 삭제를 확인 합니다.  
  
## <a name="example"></a>예제  
 데이터 소스를 프로그래밍 방식으로 삭제 하려면 호출 [SQLConfigDataSource](../../relational-databases/native-client-odbc-api/sqlconfigdatasource.md) 하려면 ODBC_REMOVE_DSN 또는 ODBC_REMOVE_SYS_DSN을 두 번째 매개 변수로 사용 합니다.  
  
 다음 예에서는 데이터 원본을 프로그래밍 방식으로 삭제하는 방법을 보여 줍니다.  
  
```  
// remove_odbc_data_source.cpp  
// compile with: ODBCCP32.lib user32.lib  
#include <iostream>  
#include \<windows.h>  
#include \<odbcinst.h>  
  
int main() {   
   LPCSTR provider = "SQL Server";   // Windows SQL Server Driver  
   LPCSTR provider = "SQL Server";   // Windows SQL Server driver  
   LPCSTR provider2 = "SQL Server Native Client 11.0";   // SQL Server 2012 Native Client driver  
   LPCSTR dsnname = "DSN=data2";  
   BOOL retval = SQLConfigDataSource(NULL, ODBC_REMOVE_DSN, provider, dsnname);  
   std::cout << retval;   // 1 if successful  
}  
```  
  
## <a name="see-also"></a>관련 항목  
 [데이터 원본 추가 &#40;ODBC&#41;](../../relational-databases/native-client-odbc-how-to/configuring-the-sql-server-odbc-driver-add-a-data-source.md)  
  
  
