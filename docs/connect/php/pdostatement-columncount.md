---
title: PDOStatement::columnCount | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d89a568-0c7c-40dd-9f54-db7313600df3
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: d8c9e73b5a1f29c7b16b7cb5e0371dfc451f7b0c
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="pdostatementcolumncount"></a>PDOStatement::columnCount
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

결과 집합에서 열 수를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
int PDOStatement::columnCount ();  
```  
  
## <a name="return-value"></a>반환 값  
결과 집합에서 열 수를 반환합니다. 결과 집합이 비어 있는 경우 0을 반환합니다.  
  
## <a name="remarks"></a>주의  
PDO 지원이 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]의 버전 2.0에 추가되었습니다.  
  
## <a name="example"></a>예제  
  
```  
<?php  
$database = "AdventureWorks";  
$server = "(local)";  
$conn = new PDO( "sqlsrv:server=$server ; Database = $database", "", "");  
  
$query = "select * from Person.ContactType";  
$stmt = $conn->prepare( $query );  
print $stmt->columnCount();   // 0  
  
echo "\n";  
$stmt->execute();  
print $stmt->columnCount();  
  
echo "\n";  
$stmt = $conn->query("select * from HumanResources.Department");  
print $stmt->columnCount();  
?>  
```  
  
## <a name="see-also"></a>참고 항목  
[PDOStatement 클래스](../../connect/php/pdostatement-class.md)  
[PDO](http://go.microsoft.com/fwlink/?LinkID=187441)  
  
