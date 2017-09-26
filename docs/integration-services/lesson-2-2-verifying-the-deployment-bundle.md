---
title: "2 단계: 배포 번들 확인 | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- SQL Server 2016
ms.assetid: 6c13f5c9-c75e-4e52-94dc-2d2db2c578fe
caps.latest.revision: 18
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 20d8b11e28f7e26e5b61662d8340ab6dbfcc0b95
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="lesson-2-2---verifying-the-deployment-bundle"></a>단원 2-2-배포 번들 확인
1단원에서는 Deployment Tutorial 프로젝트를 만들고 패키지와 보조 파일을 프로젝트에 추가했습니다. 이전 태스크에서는 프로젝트를 위한 배포 유틸리티를 작성했습니다.  
  
이 태스크에서는 배포 번들의 내용을 확인합니다. 배포 번들은 대상 컴퓨터에 복사하고 패키지를 설치하는 데 사용하는 폴더입니다. 배포 유틸리티의 위치로 기본값인 bin\Deployment를 사용한 경우 배포 번들은 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] 프로젝트의 Deployment Tutorial 폴더에 있는 Bin\Deployment 폴더입니다.  
  
### <a name="to-verify-the-content-of-deployment-bundle"></a>배포 번들의 내용을 확인하려면  
  
1.  컴퓨터에서 bin\Deployment 폴더를 찾습니다.  
  
2.  다음 파일이 있는지 확인합니다.  
  
    -   DataTransfer.dtsx  
  
    -   datatransferconfig.dtsconfig  
  
    -   Deployment Tutorial.SSISDeploymentManifest  
  
    -   LoadXMLData.dtsx  
  
    -   loadxmldataconfig.dtsconfig  
  
    -   NewCustomers.txt  
  
    -   orders.xml  
  
    -   orders.xsd  
  
    -   Readme.txt  
  
3.  Deployment Tutorial.SSISDeploymentManifest를 마우스 오른쪽 단추로 클릭하고 **연결 프로그램**을 가리킨 다음 **Internet Explorer**를 클릭합니다. 또한 메모장과 같은 텍스트 편집기에서 파일을 열 수도 있습니다. 파일의 XML 코드는 다음과 같아야 합니다.  
  
    `<?xml version="1.0"?><DTSDeploymentManifest GeneratedBy="Domain\UserName" GeneratedFromProjectName="Deployment Tutorial" GeneratedDate="2006-02-24T13:29:02.6537669-08:00" AllowConfigurationChanges="true"><Package>DataTransfer.dtsx</Package><Package>LoadXMLData.dtsx</Package><ConfigurationFile>datatransferconfig.dtsconfig</ConfigurationFile><ConfigurationFile>loadxmldataconfig.dtsconfig</ConfigurationFile><MiscellaneousFile>Readme.txt</MiscellaneousFile><MiscellaneousFile>orders.xml</MiscellaneousFile><MiscellaneousFile>NewCustomers.txt</MiscellaneousFile><MiscellaneousFile>orders.xsd</MiscellaneousFile></DTSDeploymentManifest>`  
  
4.  **AllowConfigurationChanges** 특성 값이 **true** 인지 확인하고 두 패키지 각각에 대한 **Package** 요소, 패키지가 아닌 4개의 파일 각각에 대한 **MiscellaneousFile** 요소, 두 XML 구성 파일 각각에 대한 **ConfigurationFile** 요소가 XML에 포함되어 있는지 확인합니다.  
  
5.  Internet Explorer 또는 텍스트 편집기를 종료합니다.  
  
## <a name="next-lesson"></a>다음 단원  
[3단원: SSIS 패키지 설치](../integration-services/lesson-3-install-ssis-packages.md)  
  
  
  
