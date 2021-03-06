---
title: srv_message_handler(확장 저장 프로시저 API) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_message_handler
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_message_handler
ms.assetid: 41bcd057-436f-4fa8-8293-fc8057a30877
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: f597aa6c9ba9759b606501b0bd72a2166b1805e5
ms.sourcegitcommit: 334cae1925fa5ac6c140e0b2c38c844c477e3ffb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/13/2018
ms.locfileid: "53367085"
---
# <a name="srvmessagehandler-extended-stored-procedure-api"></a>srv_message_handler(확장 저장 프로시저 API)
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] 대신 CLR 통합을 사용하세요.  
  
 설치된 확장 저장 프로시저 API 메시지 처리기를 호출합니다. 일반적으로 이 함수는 확장 저장 프로시저에서 [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]를 호출하여 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 오류 로그 파일이나 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 애플리케이션 로그에 확장 저장 프로시저에 정의된 오류를 기록하는 데 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
int srv_message_handler (  
SRV_PROC *  
srvproc  
,  
int  
errornum  
,  
BYTE   
severity  
,  
BYTE  
state  
,  
int  
oserrnum  
,  
char *  
errtext  
,  
int  
errtextlen  
,  
char *  
oserrtext  
,  
int  
oserrtextlen  
);  
  
```  
  
## <a name="arguments"></a>인수  
 *srvproc*  
 특정 클라이언트 연결에 대한 핸들인 SRV_PROC 구조에 대한 포인터입니다. *srvproc* 매개 변수에는 애플리케이션과 클라이언트 간 통신 및 데이터를 관리하는 데 사용되는 정보가 들어 있습니다.  
  
 *errornum*  
 확장 저장 프로시저에 정의된 오류 번호입니다. 이 숫자는 50,001과 2,147,483,647 사이여야 합니다.  
  
 *severity*  
 오류의 표준 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 심각도 값입니다. 이 숫자는 0과 24 사이여야 합니다.  
  
 *state*  
 오류의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 상태 값입니다.  
  
 *oserrnum*  
 운영 체제 오류 번호입니다. 이 인수는 무시 됩니다.  
  
 *errtext*  
 확장 저장 프로시저 오류 *errornum*에 대한 설명입니다.  
  
 *errtextlen*  
 확장 저장 프로시저 오류 문자열 *errtext*의 길이입니다.  
  
 *oserrtext*  
 운영 체제 오류 *oserrnum*에 대한 설명입니다. 이 인수는 무시 됩니다.  
  
 *oserrtextlen*  
 운영 체제 오류 문자열 *oserrtext*의 길이입니다.  
  
## <a name="returns"></a>반환 값  
 SUCCEED 또는 FAIL  
  
## <a name="remarks"></a>Remarks  
 **srv_message_handler** 함수를 사용하면 확장 저장 프로시저가 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]의 중앙 집중식 오류 로깅 및 보고 기능과 통합될 수 있습니다. 확장 저장 프로시저의 이벤트에 대해 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 경고를 설정할 수 있으며, SQL Server 에이전트가 이러한 경고 조건을 모니터링합니다.  
  
 오류 메시지가 더 길면 412바이트로 잘립니다.  
  
> [!IMPORTANT]  
>  확장 저장 프로시저의 원본 코드를 철저히 검토하고 프로덕션 서버에 DLL을 설치하기 전에 컴파일한 DLL을 테스트해야 합니다. 보안 검토 및 테스트에 대한 자세한 내용은 [Microsoft 웹 사이트](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/)를 참조하십시오.  
  
  
