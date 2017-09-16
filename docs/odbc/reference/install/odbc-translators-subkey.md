---
title: "ODBC 변환기가 하위 키 | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- translator subkey [ODBC]
- subkeys [ODBC], translator subkey
- registry entries for components [ODBC], translator subkey
ms.assetid: 6b170f1f-e263-4aac-9d49-8d0ca0470ca2
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: dfc34daa6236fa7187c27a204ee16cc47a0de7b0
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="odbc-translators-subkey"></a>ODBC 변환기가 하위 키
설치 된 변환기가 ODBC 변환기 하위 키 아래 값을 나열합니다. 이러한 값의 서식은 다음 표에 표시 됩니다.  
  
|이름|데이터 형식|data|  
|----------|---------------|----------|  
|*변환기 desc*|REG_SZ|**설치**|  
  
 *변환기 desc* 변환기 개발자 이름이 정의 됩니다.  
  
 예를 들어 사용자가 설치는 Microsoft® 코드 페이지 변환기 및 사용자 지정 ASCII EBCDIC 변환기를 가정 합니다. ODBC 변환기 하위 키 아래에 값은 다음과 같을 수 있습니다.  
  
```  
MS Code Page Translator: REG_SZ : Installed  
ASCII to EBCDIC: REG_SZ : Installed.  
```