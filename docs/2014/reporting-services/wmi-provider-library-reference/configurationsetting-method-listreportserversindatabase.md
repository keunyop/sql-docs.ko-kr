---
title: ListReportServersInDatabase 메서드(WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
api_name:
- ListReportServersInDatabase (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ListReportServersInDatabase method
ms.assetid: a4bf5968-c46f-484f-a510-65e2dde65a0d
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 57b93a04e4003d56e7e6a1aef4b264240f2b7f46
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56022184"
---
# <a name="listreportserversindatabase-method-wmi-msreportserverconfigurationsetting"></a>ListReportServersInDatabase 메서드(WMI MSReportServer_ConfigurationSetting)
  보고서 서버에 보안 정보에 대한 액세스 권한이 있는지 여부에 관계없이 보고서 서버 데이터베이스에 있는 보고서 서버 설치 목록을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Public Sub ListReportServersInDatabase(ByRef MachineNames() As String, _  
    ByRef InstanceNames() As String, ByRef InstallationIDs() As String, _  
    ByRef IsInitialized() As Boolean, ByRef Length As Int32, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void ListReportServersInDatabase (out string[] MachineNames,   
    out string[] InstanceNames, out string[] InstallationIDs,   
    out Boolean[] IsInitialized,out Int32 Length, out Int32 HRESULT,    
    out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a>매개 변수  
 *MachineNames[]*  
 [out] 데이터베이스에서 설치된 보고서 서버의 컴퓨터 이름이 들어 있는 배열입니다.  
  
 *InstanceNames[]*  
 [out] 데이터베이스에서 설치된 각 보고서 서버의 인스턴스 이름이 들어 있는 배열입니다.  
  
 *InstallationIDs[]*  
 [out] 데이터베이스에서 설치된 각 보고서 서버의 설치 ID가 들어 있는 배열입니다.  
  
 *IsInitialized[]*  
 [out] 데이터베이스에서 설치된 각 보고서 서버의 초기화 상태가 들어 있는 배열입니다.  
  
 *길이*  
 [out] 메서드에서 반환된 배열의 길이입니다. 반환된 모든 배열의 길이는 같습니다.  
  
 *HRESULT*  
 [out] 호출의 성공 여부를 나타내는 값입니다.  
  
 *ExtendedErrors[]*  
 [out] 호출에서 반환되는 추가 오류가 들어 있는 문자열 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드 호출의 성공 또는 실패를 나타내는 *HRESULT* 를 반환합니다. 0 값은 메서드 호출이 성공했음을 나타냅니다. 0 이외의 값은 오류가 발생했음을 나타냅니다.  
  
## <a name="remarks"></a>Remarks  
 ListReportServersInDatabase는 보고서 서버에 보안 정보에 대한 액세스 권한이 있는지 여부에 관계없이 보고서 서버 데이터베이스에 있는 보고서 서버 설치 목록을 나열하고 각 설치 정보가 들어 있는 일치하는 배열 집합을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **네임스페이스:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## <a name="see-also"></a>관련 항목  
 [MSReportServer_ConfigurationSetting 멤버](msreportserver-configurationsetting-members.md)  
  
  
