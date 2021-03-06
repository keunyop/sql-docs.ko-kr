---
title: SQLServerException 생성자 (java.lang.Object, java.lang.String, java.lang.String, int, boolean) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: ''
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 5b8c39021b8afac5631e44cddd8874cbf22975a3
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47670031"
---
# <a name="sqlserverexception-constructor-javalangobject-javalangstring-javalangstring-int-boolean"></a>SQLServerException 생성자 (java.lang.Object, java.lang.String, java.lang.String, int, boolean)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  새 인스턴스를 초기화 합니다 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md) 주어 지 면 클래스는 **개체**, **문자열** 개체를 **문자열** 개체는 **int**, 및 **부울**합니다.

## <a name="syntax"></a>구문  
  
```  

public SQLServerException(java.lang.Object obj,
            java.lang.String errText,
            java.lang.String errState,
            int errNum,
            boolean bStack)

            
```  
  
#### <a name="parameters"></a>매개 변수  
 *obj*  
  
 예외를 생성 하는 IO 버퍼입니다.

 *errText*  
  
 오류 텍스트를 포함 하는 문자열입니다.
  
 *sqlState*  
  
 SQL 상태를 포함 하는 열거형 개체입니다.
 
 *오류 번호*  
  
 예외에 대 한 오류 코드가 포함 된 int입니다.
 
 *bStack*  
  
 스택 추적을 생성 해야 하는 경우를 나타내는 부울입니다.
  
## <a name="see-also"></a>참고 항목  
 [SQLServerException 생성자](../../../connect/jdbc/reference/sqlserverexception-constructors.md)   
 [SQLServerException 멤버](../../../connect/jdbc/reference/sqlserverexception-members.md)   
 [SQLServerException 클래스](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
  
