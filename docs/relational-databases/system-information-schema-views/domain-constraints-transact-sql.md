---
title: DOMAIN_CONSTRAINTS (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- DOMAIN_CONSTRAINTS
- DOMAIN_CONSTRAINTS_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- INFORMATION_SCHEMA.DOMAIN_CONSTRAINTS view
- DOMAIN_CONSTRAINTS view
ms.assetid: 436c4480-f1e3-403f-b2bd-de04539afe3c
author: CarlRabeler
ms.author: carlrab
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 7b8935bc203c616f88a7e5929bd19e10a41592d3
ms.sourcegitcommit: 37310da0565c2792aae43b3855bd3948fd13e044
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/18/2018
ms.locfileid: "53591037"
---
# <a name="domainconstraints-transact-sql"></a>DOMAIN_CONSTRAINTS(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  현재 사용자가 액세스할 수 있고 바인딩되어 있는 규칙이 있는 현재 데이터베이스의 각 별칭 데이터 형식당 한 개의 행을 반환합니다.  
  
 이러한 뷰에서 정보를 검색할의 정규화 된 이름을 지정 **INFORMATION_SCHEMA.** _view_name_합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**CONSTRAINT_CATALOG**|**nvarchar(** 128 **)**|규칙이 존재하는 데이터베이스입니다.|  
|**CONSTRAINT_SCHEMA**|**nvarchar(** 128 **)**|제약 조건이 포함된 스키마의 이름입니다.<br /><br /> <strong>\*\* 중요 \* \*</strong>  개체의 스키마를 확인 하려면 INFORMATION_SCHEMA 뷰를 사용 하지 마십시오. 개체의 스키마를 확인하는 신뢰할 수 있는 유일한 방법은 sys.objects 카탈로그 뷰를 쿼리하는 것입니다.|  
|**제약 조건 이름**|**sysname**|규칙 이름입니다.|  
|**DOMAIN_CATALOG**|**nvarchar(** 128 **)**|별칭 데이터 형식이 존재하는 데이터베이스입니다.|  
|**DOMAIN_SCHEMA**|**nvarchar(** 128 **)**|별칭 데이터 형식이 포함된 스키마의 이름입니다.<br /><br /> <strong>\*\* 중요 \* \*</strong>  데이터 형식의 스키마를 확인할 INFORMATION_SCHEMA 뷰를 사용 하지 마십시오. 형식의 스키마를 확인하는 신뢰할 수 있는 유일한 방법은 TYPEPROPERTY 함수를 사용하는 것입니다.|  
|**DOMAIN_NAME**|**sysname**|별칭 데이터 형식입니다.|  
|**IS_DEFERRABLE**|**varchar (** 2 **)**|제약 조건 검사를 연기할 수 있는지 여부를 지정합니다. 항상 NO를 반환합니다.|  
|**INITIALLY_DEFERRED**|**varchar (** 2 **)**|제약 조건 검사가 처음에 연기되는지 여부를 지정합니다. 항상 NO를 반환합니다.|  
  
## <a name="see-also"></a>관련 항목  
 [시스템 뷰 &#40;TRANSACT-SQL&#41;](https://msdn.microsoft.com/library/35a6161d-7f43-4e00-bcd3-3091f2015e90)   
 [정보 스키마 뷰 &#40;TRANSACT-SQL&#41;](~/relational-databases/system-information-schema-views/system-information-schema-views-transact-sql.md)   
 [sys.objects&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md)   
 [sys.types&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-types-transact-sql.md)  
  
  
