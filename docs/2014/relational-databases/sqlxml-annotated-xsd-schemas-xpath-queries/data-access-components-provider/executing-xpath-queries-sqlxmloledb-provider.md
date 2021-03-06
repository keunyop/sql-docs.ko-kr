---
title: XPath 쿼리 실행 (SQLXMLOLEDB 공급자) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, executing XPath queries
- queries [SQLXML], SQLXMLOLEDB Provider
- Base Path property
- XPath queries [SQLXML], SQLXMLOLEDB Provider
- Mapping Schema property
ms.assetid: 19063222-dc9c-48ae-a55f-778103674a9e
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 742a7b42c4fe75699ff3bbdfd81068ace5163708
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52800155"
---
# <a name="executing-xpath-queries-sqlxmloledb-provider"></a>XPath 쿼리 실행(SQLXMLOLEDB 공급자)
  이 예에서는 다음 SQLXMLOLEDB 공급자별 속성을 사용하는 방법을 보여 줍니다.  
  
-   `ClientSideXML`  
  
-   `Base Path`  
  
-   `Mapping Schema`  
  
 이 예제 ADO 응용 프로그램에서는 XPath 쿼리(루트)를 XSD 매핑 스키마(MySchema.xml)에 대해 지정합니다. 스키마에는  **\<연락처 >** 사용 하 여 요소 **ContactID**를 **FirstName**, 및 **LastName** 특성입니다. 이 스키마에서는 기본 매핑이 수행됩니다. 즉, 요소 이름은 같은 이름의 테이블에 매핑되고 단순 유형의 특성은 같은 이름의 열에 매핑됩니다.  
  
```  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
   xmlns:sql='urn:schemas-microsoft-com:mapping-schema'>  
 <xsd:element name= 'root' sql:is-constant='1'>   
    <xsd:complexType>  
       <xsd:sequence>  
         <xsd:element ref = 'Contacts'/>  
       </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
  <xsd:element name='Contacts' sql:relation='Person.Contact'>   
     <xsd:complexType>  
          <xsd:attribute name='ContactID' type='xsd:integer' />  
          <xsd:attribute name='FirstName' type='xsd:string'/>   
          <xsd:attribute name='LastName' type='xsd:string' />   
     </xsd:complexType>  
   </xsd:element>  
</xsd:schema>  
```  
  
 매핑 스키마 속성 XPath 쿼리가 실행 되는 매핑 스키마를 제공 합니다. 매핑 스키마는 XSD 또는 XDR 스키마일 수 있습니다. Base Path 속성 매핑 스키마를 파일 경로 제공합니다.  
  
 ClientSideXML 속성을 true로 설정 됩니다. 따라서 XML 문서는 클라이언트에서 생성됩니다.  
  
 응용 프로그램에서 XPath 쿼리는 직접 지정됩니다. 따라서 XPath 언어 {ec2a4293-e898-11d2-b1b7-00c04f680c56}을 포함해야 합니다.  
  
> [!NOTE]  
>  코드에서 연결 문자열에 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 인스턴스의 이름을 지정해야 합니다. 또한 이 예에서는 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client(SQLNCLI11)를 데이터 공급자로 사용하도록 지정하고 있으며 이를 위해서는 추가 네트워크 클라이언트 소프트웨어가 설치되어 있어야 합니다. 자세한 내용은 [SQL Server Native Client에 대 한 시스템 요구 사항](../../native-client/system-requirements-for-sql-server-native-client.md)합니다.  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security= SSPI;"  
  
oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
  
oTestCommand.CommandText = "root"  
oTestStream.Open  
oTestCommand.Dialect = "{ec2a4293-e898-11d2-b1b7-00c04f680c56}"  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("Base Path").Value = "c:\Schemas\SQLXML4\XPathDirect\"  
oTestCommand.Properties("Mapping Schema").Value = "mySchema.xml"  
oTestCommand.Properties("Output Encoding") = "utf-8"  
oTestCommand.Execute , , adExecuteStream  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
  
