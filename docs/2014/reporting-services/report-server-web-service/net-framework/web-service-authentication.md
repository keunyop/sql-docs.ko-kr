---
title: 웹 서비스 인증 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], authentication
- XML Web service [Reporting Services], authentication
- Report Server Web service, authentication
ms.assetid: 852b4947-a090-4e54-8555-5a503945ceab
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: a670fe4019d1bc8eebfeb385a63b0c0e58ae61d5
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56031448"
---
# <a name="web-service-authentication"></a>웹 서비스 인증
  Windows 인증 또는 기본 인증을 사용하여 보고서 서버 웹 서비스에 대한 호출을 인증할 수 있습니다. 보고서 서버에 SOAP 요청을 하는 클라이언트는 지원되는 인증 프로토콜 중 하나의 클라이언트 부분을 구현해야 합니다. [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]를 사용하는 경우 관리 코드 HTTP 클래스를 사용하여 인증을 구현할 수 있습니다. 이러한 API를 사용하면 SOAP 요청과 함께 인증 정보를 쉽게 보낼 수 있습니다.  
  
 보고서 서버 웹 서비스에 호출하기 전에 적절한 자격 증명이 없는 경우 호출이 실패합니다. 런타임에 해당 메서드를 호출하기 전에 웹 서비스를 나타내는 클라이언트 쪽 개체의 **Credentials** 속성을 설정하여 웹 서비스에 자격 증명을 전달할 수 있습니다.  
  
 다음 섹션에는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]를 사용하여 자격 증명을 보내는 예제 코드가 포함되어 있습니다.  
  
## <a name="windows-authentication"></a>Windows 인증  
 다음 코드는 Windows 자격 증명을 웹 서비스에 전달합니다.  
  
```vb  
Dim rs As New ReportingService()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
```  
  
```csharp  
ReportingService rs = new ReportingService();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
```  
  
## <a name="basic-authentication"></a>기본 인증  
 다음 코드는 기본 자격 증명을 웹 서비스에 전달합니다.  
  
```vb  
Dim rs As New ReportingService()  
rs.Credentials = New System.Net.NetworkCredential("username", "password", "domain")  
```  
  
```csharp  
ReportingService service = new ReportingService();  
service.Credentials = new System.Net.NetworkCredential("username", "password", "domain");  
```  
  
 보고서 서버 웹 서비스의 메서드를 호출하기 전에 먼저 자격 증명을 설정해야 합니다. 자격 증명을 설정하지 않을 경우 오류 코드(HTTP 401 오류: 액세스가 거부되었습니다.)가 나타납니다. 서비스를 사용하기 전에 인증해야 하지만, 자격 증명을 설정한 후에는 동일한 서비스 변수(*rs* 등)를 계속 사용한다면 다시 설정할 필요가 없습니다.  
  
## <a name="custom-authentication"></a>사용자 지정 인증  
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]에는 개발자가 보안 확장 프로그램이라고 하는 사용자 지정 인증 확장 프로그램을 디자인하고 개발할 수 있도록 프로그래밍 API가 포함되어 있습니다. 자세한 내용은 [Implementing a Security Extension](../../extensions/security-extension/implementing-a-security-extension.md)을 참조하세요.  
  
## <a name="see-also"></a>관련 항목  
 [웹 서비스와 .NET Framework를 사용하여 응용 프로그램 빌드](building-applications-using-the-web-service-and-the-net-framework.md)   
 [보고서 서버 웹 서비스](../report-server-web-service.md)  
  
  
