---
title: 사용자 지정 개체 빌드, 배포 및 디버깅 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom objects [Integration Services]
ms.assetid: b03685bc-5398-4c3f-901a-1219c1098fbe
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: 131f86336c2eecb4995304fc87e15a7b910833ab
ms.sourcegitcommit: 5a8678bf85f65be590676745a7fe4fcbcc47e83d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58382391"
---
# <a name="building-deploying-and-debugging-custom-objects"></a>사용자 지정 개체 빌드, 배포 및 디버깅
  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]의 사용자 지정 개체에 대한 코드를 작성한 후에는 어셈블리를 빌드하여 배포하고 패키지에서 사용할 수 있도록 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 디자이너에 통합한 다음 테스트 및 디버깅을 수행해야 합니다.  
  
##  <a name="top"></a> Integration Services의 사용자 지정 개체 빌드, 배포 및 디버깅 단계  
 개체의 사용자 지정 기능을 작성한 후에는 이를 테스트하고 사용자가 사용할 수 있도록 해야 합니다. 이 단계는 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]용으로 만들 수 있는 모든 유형의 사용자 지정 개체에서 매우 비슷합니다.  
  
 사용자 지정 개체를 빌드, 배포 및 디버깅할 때 따라야 하는 단계는 다음과 같습니다.  
  
1.  생성할 어셈블리를 강력한 이름으로 [서명](#signing)합니다.  
  
2.  어셈블리를 [빌드](#building)합니다.  
  
3.  어셈블리를 적절한 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 폴더로 이동하거나 복사하여 [배포](#deploying)합니다.  
  
4.  GAC(전역 어셈블리 캐시)에 어셈블리를 [설치](#installing)합니다.  
  
     이 개체는 도구 상자에 자동으로 추가됩니다.  
  
5.  필요한 경우 [배포 문제를 해결](#troubleshooting)합니다.  
  
6.  코드를 [테스트](#testing)하고 디버그합니다.  
  
##  <a name="signing"></a> 어셈블리 서명  
 공유하려는 어셈블리는 전역 어셈블리 캐시에 설치해야 합니다. 전역 어셈블리 캐시에 추가된 어셈블리는 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]와 같은 응용 프로그램에서 사용할 수 있습니다. 전역 어셈블리 캐시에 어셈블리를 추가하려면 어셈블리를 강력한 이름으로 서명하여 해당 어셈블리가 전역적으로 고유함을 보장해야 합니다. 강력한 이름의 어셈블리에는 어셈블리의 이름, culture, 공개 키 및 버전 번호를 포함하는 정규화된 이름이 있습니다. 런타임에서는 이 정보를 사용하여 어셈블리를 찾고 같은 이름의 다른 어셈블리와 구별합니다.  
  
 강력한 이름으로 어셈블리를 서명하려면 먼저 공개/개인 키 쌍이 있어야 하며 이 키 쌍이 없으면 만들어야 합니다. 이 암호화 키 쌍은 빌드할 때 강력한 이름의 어셈블리를 만드는 데 사용합니다.  
  
 강력한 이름과 어셈블리를 서명할 때 따라야 하는 단계에 대한 자세한 내용은 [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK 설명서의 다음 항목을 참조하십시오.  
  
-   강력한 이름의 어셈블리  
  
-   공개/개인 키 쌍 만들기  
  
-   방법: 강력한 이름으로 어셈블리 서명  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]에서는 빌드할 때 어셈블리를 강력한 이름으로 서명하기가 쉽습니다. **프로젝트 속성** 대화 상자에서 **서명** 탭을 선택하고, **어셈블리 서명** 옵션을 선택한 다음, 키 파일(.snk)의 경로를 제공합니다.  
  
##  <a name="building"></a> 어셈블리 빌드  
 프로젝트를 서명한 후에는 [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]의 **빌드** 메뉴에서 사용할 수 있는 명령을 사용하여 프로젝트 또는 솔루션을 빌드하거나 다시 빌드해야 합니다. 솔루션에 사용자 지정 사용자 인터페이스를 위한 별도의 프로젝트가 포함된 경우 이 프로젝트도 강력한 이름으로 서명해야 하며 이 프로젝트를 솔루션과 동시에 빌드할 수 있습니다.  
  
 어셈블리를 배포하고 글로벌 어셈블리 캐시에 설치하는 다음 두 단계를 수행하는 데 가장 편리한 방법은 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]에서 이러한 단계를 빌드 후 이벤트로 스크립팅하는 것입니다. 빌드 이벤트는 [프로젝트 속성]의 **컴파일** 페이지([!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] 프로젝트의 경우) 또는 **빌드 이벤트** 페이지(C# 프로젝트의 경우)에서 사용할 수 있습니다. **gacutil.exe**와 같은 명령 프롬프트 유틸리티에는 전체 경로가 필요합니다. 공백이 포함된 경로와 공백이 포함된 경로로 확장되는 $(TargetPath) 등의 매크로는 모두 따옴표로 묶어야 합니다.  
  
 다음은 사용자 지정 로그 공급자에 대한 빌드 후 이벤트 명령줄의 예입니다.  
  
```  
"C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0A\bin\NETFX 4.0 Tools\gacutil.exe" -u $(TargetName)  
"C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0A\bin\NETFX 4.0 Tools\gacutil.exe" -i $(TargetFileName)  
copy $(TargetFileName) "C:\Program Files\Microsoft SQL Server\120\DTS\LogProviders "  
```  
  
##  <a name="deploying"></a> 어셈블리 배포  
 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 디자이너는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]가 설치될 때 만들어진 일련의 폴더에 있는 파일을 열거하여 패키지에서 사용할 수 있는 사용자 지정 개체를 찾습니다. 경우 기본값 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 설치 설정을 사용한 경우 이러한 폴더 집합 아래에 있는 **C:\Program Files\Microsoft SQL Server\120\DTS**합니다. 그러나 사용자 지정 개체에 대 한 설치 프로그램을 만드는 경우의 값을 확인 해야 합니다 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\120\SSIS\Setup\DtsPath** 레지스트리 키의 위치를 확인 하려면 폴더입니다.  
  
 다음과 같은 두 가지 방법으로 폴더에 어셈블리를 추가할 수 있습니다.  
  
-   빌드 후 컴파일된 어셈블리를 적절한 폴더로 이동하거나 복사합니다. 편의상 빌드 후 이벤트에 복사 명령을 포함할 수 있습니다.  
  
-   어셈블리를 적절한 폴더에 직접 빌드합니다.  
  
 아래에 있는 다음 배포 폴더 **C:\Program Files\Microsoft SQL Server\120\DTS** 다양 한 유형의 사용자 지정 개체에 사용 됩니다.  
  
|사용자 지정 개체|배포 폴더|  
|-------------------|-----------------------|  
|태스크|태스크|  
|ODBC 대상 편집기|Connections|  
|로그 공급자|LogProviders|  
|데이터 흐름 구성 요소|PipelineComponents|  
  
> [!NOTE]  
>  이러한 폴더에 복사된 어셈블리는 사용 가능한 태스크, 연결 관리자 등의 열거형을 지원합니다. 따라서 사용자 지정 개체의 사용자 지정 사용자 인터페이스만 포함된 어셈블리는 이러한 폴더에 배포하지 않아도 됩니다.  
  
##  <a name="installing"></a> 전역 어셈블리 캐시에 어셈블리 설치  
 GAC(전역 어셈블리 캐시)에 태스크 어셈블리를 설치하려면 **gacutil.exe** 명령줄 도구를 사용하거나 어셈블리를 `%system%\assembly` 디렉터리에 끌어 놓습니다. 편의상 **gacutil.exe**에 대한 호출을 빌드 후 이벤트에 포함할 수도 있습니다.  
  
 다음 명령은 **gacutil.exe**를 사용하여 *MyTask.dll*이라는 구성 요소를 GAC에 설치합니다.  
  
 `gacutil /iF MyTask.dll`  
  
 새 버전의 사용자 지정 개체를 설치한 후에는 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 디자이너를 닫았다가 다시 열어야 합니다. 전역 어셈블리 캐시에 이전 버전의 사용자 지정 개체를 설치한 경우 새 버전을 설치하려면 먼저 이전 버전을 제거해야 합니다. 어셈블리를 제거하려면 **gacutil.exe**를 실행하고 `/u` 옵션을 사용하여 어셈블리 이름을 지정합니다.  
  
 전역 어셈블리 캐시에 대한 자세한 내용은 "[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 도구"의 "전역 어셈블리 캐시 도구(Gactutil.exe)"를 참조하십시오.  
  
##  <a name="troubleshooting"></a> 배포 문제 해결  
 사용자 지정 개체가 **도구 상자** 또는 사용 가능한 개체 목록에 표시되지만 패키지에 추가할 수 없는 경우 다음을 시도해 보세요.  
  
1.  전역 어셈블리 캐시에 여러 버전의 구성 요소가 있는지 확인합니다. 전역 어셈블리 캐시에 여러 버전의 구성 요소가 있는 경우 디자이너에서 구성 요소를 로드하지 못할 수 있습니다. 전역 어셈블리 캐시에서 어셈블리의 모든 인스턴스를 삭제하고 어셈블리를 다시 추가합니다.  
  
2.  배포 폴더에 어셈블리의 단일 인스턴스만 있는지 확인합니다.  
  
3.  도구 상자를 새로 고칩니다.  
  
4.  [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]를 **devenv.exe**에 연결하고 초기화 코드를 단계별로 실행하도록 중단점을 설정하여 예외가 발생하지 않도록 합니다.  
  
##  <a name="testing"></a> 코드 테스트 및 디버깅  
 사용자 지정 개체의 런타임 메서드를 가장 간단하게 디버그하려면 사용자 지정 개체를 빌드하고 해당 구성 요소를 사용하는 패키지를 실행한 후에 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]에서 **dtexec.exe**를 시작합니다.  
  
 와 같은 구성 요소의 디자인 타임 메서드를 디버그 하려는 경우는 `Validate` 메서드를 두 번째 인스턴스의 구성 요소를 사용 하는 패키지를 열고 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]에 연결 하 고 해당 **devenv.exe** 프로세스입니다.  
  
 또한 패키지가 열려 있고 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 디자이너에서 실행 중일 때 구성 요소의 런타임 메서드를 디버그하려면 **DtsDebugHost.exe** 프로세스에도 연결할 수 있도록 패키지 실행을 강제로 일시 중지해야 합니다.  
  
#### <a name="to-debug-an-objects-run-time-methods-by-attaching-to-dtexecexe"></a>dtexec.exe에 연결하여 개체의 런타임 메서드를 디버깅하려면  
  
1.  이 항목에 설명된 대로 디버그 구성 요소에서 프로젝트를 서명 및 빌드하고 배포한 다음 전역 어셈블리 캐시에 설치합니다.  
  
2.  에 **디버그** 탭 **프로젝트 속성**를 선택 **시작 외부 프로그램** 으로 **시작 작업**를 찾아서  **dtexec.exe**, 기본적으로 C:\Program Files\Microsoft SQL Server\120\DTS\Binn에 설치 되는 합니다.  
  
3.  **명령줄 옵션** 입력란의 **시작 옵션** 아래에서 구성 요소를 사용하는 패키지를 실행하는 데 필요한 명령줄 인수를 입력합니다. 명령줄 인수는 /F[ILE] 스위치와 그 다음에 나오는 .dtsx 파일의 경로 및 파일 이름으로 구성되는 경우가 많습니다. 자세한 내용은 [dtexec Utility](../packages/dtexec-utility.md)를 참조하세요.  
  
4.  원본 코드에서 구성 요소의 런타임 메서드 중 적절한 위치에 중단점을 설정합니다.  
  
5.  프로젝트를 실행합니다.  
  
#### <a name="to-debug-a-custom-objects-design-time-methods-by-attaching-to-sql-server-data-tools"></a>SQL Server Data Tools에 연결하여 사용자 지정 개체의 디자인 타임 메서드를 디버깅하려면  
  
1.  이 항목에 설명된 대로 디버그 구성 요소에서 프로젝트를 서명 및 빌드하고 배포한 다음 전역 어셈블리 캐시에 설치합니다.  
  
2.  원본 코드에서 사용자 지정 개체의 디자인 타임 메서드 중 적절한 위치에 중단점을 설정합니다.  
  
3.  [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]의 두 번째 인스턴스를 열고 해당 사용자 지정 개체를 사용하는 패키지가 포함된 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 프로젝트를 로드합니다.  
  
4.  [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]의 첫 번째 인스턴스에서 **디버그** 메뉴의 **프로세스에 연결**을 선택하여 패키지가 로드되는 **devenv.exe**의 두 번째 인스턴스에 연결합니다.  
  
5.  [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]의 두 번째 인스턴스에서 패키지를 실행합니다.  
  
#### <a name="to-debug-a-custom-objects-run-time-methods-by-attaching-to-sql-server-data-tools"></a>SQL Server Data Tools에 연결하여 사용자 지정 개체의 런타임 메서드를 디버깅하려면  
  
1.  이전 절차에 나열된 단계를 완료한 후 **DtsDebugHost.exe**에 연결할 수 있도록 패키지 실행을 강제로 일시 중지합니다. 패키지는 `OnPreExecute` 이벤트에 중단점을 추가하거나, 프로젝트에 스크립트 태스크를 추가하고 모달 메시지 상자를 표시하는 스크립트를 입력하여 강제로 일시 중지할 수 있습니다.  
  
2.  패키지를 실행합니다. 일시 중지가 발생하면 코드 프로젝트가 열려 있는 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 인스턴스로 전환하고 **디버그** 메뉴에서 **프로세스에 연결**을 선택합니다. **형식** 열에 **x86** 전용으로 나열된 인스턴스가 아니라 **Managed, x86**으로 나열된 **DtsDebugHost.exe** 인스턴스에 연결해야 합니다.  
  
3.  일시 중지된 패키지로 돌아가서 중단점을 지나 계속하거나 **확인**을 클릭하여 스크립트 태스크에서 발생한 메시지 상자를 닫고 패키지 실행 및 디버깅을 계속합니다.  
  
![Integration Services 아이콘 (작은)](../media/dts-16.gif "Integration Services 아이콘 (작은)")**Integration Services를 사용 하 여 날짜를 알림 설정**<br /> Microsoft의 최신 다운로드, 문서, 예제 및 비디오와 커뮤니티에서 선택된 솔루션을 보려면 MSDN의 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 페이지를 방문하세요.<br /><br /> [MSDN의 Integration Services 페이지 방문](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> 이러한 업데이트에 대한 자동 알림을 받으려면 해당 페이지에서 제공하는 RSS 피드를 구독하세요.  
  
## <a name="see-also"></a>관련 항목  
 [Integration Services 사용자 지정 개체 개발](developing-custom-objects-for-integration-services.md)   
 [사용자 지정 개체 지속](persisting-custom-objects.md)   
 [패키지 배포 문제 해결 도구](../troubleshooting/troubleshooting-tools-for-package-development.md)  
  
  
