---
title: SQLAllocEnv 매핑 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLAllocEnv function [ODBC], mapping
- mapping deprecated functions [ODBC], SQLAllocEnv
ms.assetid: 4bb51845-ee91-4b97-9dd4-2fab977f2aec
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 39736d4d007814e29bc8c8293fa7e1020539b940
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47692742"
---
# <a name="sqlallocenv-mapping"></a>SQLAllocEnv 매핑
응용 프로그램을 호출할 때 **SQLAllocEnv** 는 ODBC 3 *.x* 드라이버, 호출 **SQLAllocEnv**(*phenv*) 매핑되**SQLAllocHandle** 다음과 같습니다.  
  
1.  드라이버 관리자는 환경 핸들을 할당 하 고 응용 프로그램에 반환 합니다. 드라이버 관리자 호출 **SQLSetEnvAttr** SQL_OV_ODBC2를 SQL_ATTR_ODBC_VERSION 환경 특성을 설정 합니다.  
  
2.  드라이버 관리자를 호출 하는 드라이버에 대 한 첫 번째 연결을 설정 하는 응용 프로그램을 경우  
  
    ```  
    SQLAllocHandle(SQL_HANDLE_ENV, SQL_NULL_HANDLE, OutputHandlePtr)  
    ```  
  
     사용 하 여에서 *OutputHandlePtr* 로 설정 *phenv*합니다.
