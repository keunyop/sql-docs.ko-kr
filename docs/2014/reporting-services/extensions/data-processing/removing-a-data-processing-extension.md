---
title: 데이터 처리 확장 프로그램 제거 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.topic: reference
helpviewer_keywords:
- deleting data processing extensions
- data processing extensions [Reporting Services], removing
- removing data processing extensions
ms.assetid: 1d89e32b-0631-44f6-8178-a57fb791d26d
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 5422f8cf4a462b6aeef7cd56bdccffdb13f930b5
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56022124"
---
# <a name="removing-a-data-processing-extension"></a>데이터 처리 확장 프로그램 제거
  데이터 처리 확장 프로그램을 제거하려면 구성 파일에서 데이터 처리 확장 프로그램에 대한 **Extension** 요소를 제거하면 됩니다. 보고서 서버 및 보고서 디자이너에 대한 항목을 만든 경우에는 RSReportServer.config 파일과 RSReportDesigner.config 파일 모두에서 **Extension** 요소를 제거합니다. 구성 정보를 제거한 후에는 구성 요소에서 데이터 처리 확장 프로그램을 사용할 수 없습니다.  
  
## <a name="see-also"></a>관련 항목  
 [Reporting Services 확장 프로그램](../reporting-services-extensions.md)   
 [데이터 처리 확장 프로그램 구현](implementing-a-data-processing-extension.md)   
 [Reporting Services 확장 라이브러리](../reporting-services-extension-library.md)  
  
  
