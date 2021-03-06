---
title: 함수 실행 비교 | Microsoft Docs
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- executing queries
ms.assetid: 130fc0fd-87dd-46b2-918f-de9dc572c769
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 46a1f3e53c4953f08400d5d5599bec348fb6b15c
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47749442"
---
# <a name="comparing-execution-functions"></a>함수 실행 비교
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

[!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] 는 함수를 실행하기 위한 몇 가지 옵션을 제공합니다.  

## <a name="sqlsrv-execution-functions"></a>SQLSRV 함수 실행  
SQLSRV 드라이버를 사용하는 경우 단일 쿼리를 실행하려면 [sqlsrv_query](../../connect/php/sqlsrv-query.md) 를 사용하고 각 실행에 대해 다른 매개 변수 값으로 준비된 문을 여러 번 실행하려면 [sqlsrv_prepare](../../connect/php/sqlsrv-prepare.md) 와 [sqlsrv_execute](../../connect/php/sqlsrv-execute.md) 를 사용합니다.  

## <a name="pdosqlsrv-execution-functions"></a>PDO_SQLSRV 함수 실행 
PDO_SQLSRV 드라이버를 사용하는 경우에 다음 중 하나를 사용하여 쿼리를 실행할 수 있습니다.  
  
-   [PDO::exec](../../connect/php/pdo-exec.md)  
  
-   [PDO::query](../../connect/php/pdo-query.md)  
  
-   [PDO::prepare](../../connect/php/pdo-prepare.md) 및 [PDOStatement::execute](../../connect/php/pdostatement-execute.md).  
  
## <a name="see-also"></a>참고 항목  
[SQLSRV 드라이버 API 참조](../../connect/php/sqlsrv-driver-api-reference.md)

[PDO_SQLSRV 드라이버 참조](../../connect/php/pdo-sqlsrv-driver-reference.md)

[SQL Server 용 PHP 용 Microsoft 드라이버에 대 한 가이드를 프로그래밍](../../connect/php/programming-guide-for-php-sql-driver.md)
  
