---
title: SetStartMode 메서드 (SqlService 클래스) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStartMode Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStartMode method
ms.assetid: f6f198b4-f9a4-468c-8977-76462ef06e61
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 0b3689c843fbbe7ad845a45aca6bb962f8f0c75e
ms.sourcegitcommit: 334cae1925fa5ac6c140e0b2c38c844c477e3ffb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/13/2018
ms.locfileid: "53371675"
---
# <a name="setstartmode-method-sqlservice-class"></a>SetStartMode 메서드(SqlService 클래스)
  서비스 인스턴스의 시작 모드를 수정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object  
.SetStartMode(  
StartMode  
)  
  
```  
  
## <a name="parts"></a>부분  
 *object*  
 서비스를 나타내는 [SqlService 클래스](sqlservice-class.md) 개체입니다.  
  
#### <a name="parameters"></a>매개 변수  
 *StartMode*  
 서비스 인스턴스의 시작 모드를 지정하는 `uint32` 값입니다.  
  
 유효한 값은 다음과 같습니다.  
  
 값 = 0. 부팅 - 운영 체제 로더에 의해 디바이스 드라이버가 시작됩니다. 이 값은 드라이버 서비스에 대해서만 유효합니다.  
  
 값 = 1입니다. 시스템 - `IoInitSystem` 메서드에 의해 장치 드라이버가 시작됩니다. 이 값은 드라이버 서비스에 대해서만 유효합니다.  
  
 값 = 2입니다. 자동 - 시스템 시작 중 서비스 제어 관리자에 의해 자동으로 서비스가 시작됩니다.  
  
 값 = 3입니다. 수동 - 프로세스에서 `StartService` 메서드를 호출할 때 컴퓨터 관리자에 의해 서비스가 시작됩니다.  
  
 값 = 4입니다. 사용 안 함 - 서비스를 더 이상 시작할 수 없습니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 `uint32` 값으로, 0은 서비스가 수정되었음을 나타내고 1은 요청이 지원되지 않음을 나타내며 다른 모든 숫자는 오류를 나타냅니다.  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>관련 항목  
 [서비스 시작 및 중지](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
