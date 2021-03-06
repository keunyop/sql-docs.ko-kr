---
title: dbo.sysdownloadlist (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dbo.sysdownloadlist
- sysdownloadlist_TSQL
- dbo.sysdownloadlist_TSQL
- sysdownloadlist
dev_langs:
- TSQL
helpviewer_keywords:
- sysdownloadlist system table
ms.assetid: 71087a4c-e829-488e-aa7d-a9476e2b4779
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: d0568403cb7f5bdf48d9be33e1b40f0be3fc1c33
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47745094"
---
# <a name="dbosysdownloadlist-transact-sql"></a>dbo.sysdownloadlist(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  모든 대상 서버의 다운로드 명령 대기열을 포함합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**instance_id**|**int**|행의 자연 삽입 시퀀스를 제공하는 ID 열입니다.|  
|**source_server**|**sysname**|원본 서버의 이름입니다.|  
|**operation_code**|**tinyint**|작업의 운영 코드입니다.<br /><br /> **1** = INS (삽입)<br /><br /> **2** = UPD (업데이트)<br /><br /> **3** = DEL (삭제)<br /><br /> **4** = 시작<br /><br /> **5** = 중지|  
|**object_type**|**tinyint**|개체 유형 코드입니다.|  
|**object_id** <sup>1</sup>|**uniqueidentifier**|개체 ID입니다.|  
|**target_server**|**sysname**|대상 서버의 이름입니다.|  
|**error_message**|**nvarchar(1024)**|대상 서버가 특정 행을 처리하다가 오류가 발생한 경우에 표시되는 오류 메시지입니다.|  
|**date_posted**|**datetime**|대상 서버에 작업이 게시된 날짜 및 시간입니다.|  
|**date_downloaded**|**datetime**|마지막으로 작업을 다운로드한 날짜 및 시간입니다.|  
|**상태**|**tinyint**|작업의 상태입니다.<br /><br /> **0** = 아직 다운로드 되지 않음<br /><br /> **1** = 성공적으로 다운로드|  
|**deleted_object_name**|**sysname**|삭제된 개체의 이름입니다.|  
  
 <sup>1</sup> 는 **object_id** 열 값이 될 수 있습니다 **-1**, 경우 ALL 값에 해당 하는 합니다 **operation_code** 열이 삭제의 값입니다.  
  
  
