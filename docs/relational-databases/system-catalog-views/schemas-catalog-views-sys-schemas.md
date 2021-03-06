---
title: sys.schemas (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- schemas_TSQL
- sys.schemas_TSQL
- schemas
- sys.schemas
dev_langs:
- TSQL
helpviewer_keywords:
- sys.schemas catalog view
ms.assetid: 29af5ce5-2af7-4103-8f08-3ec92603ba05
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>=aps-pdw-2016||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 9a676eb3e9bf67d14e45ebc9973f5be7998e19cf
ms.sourcegitcommit: 9c6a37175296144464ffea815f371c024fce7032
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51665792"
---
# <a name="schemas-catalog-views---sysschemas"></a>스키마 카탈로그 뷰-sys.schemas
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-pdw-md.md)]

  각 데이터베이스 스키마당 하나의 행을 포함합니다.  
  
> [!NOTE]  
>  데이터베이스 스키마는 XML 문서의 콘텐츠 모델을 정의하는 XML 스키마와는 다릅니다.  
  
|열 이름|데이터 형식|설명|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|스키마의 이름입니다. 데이터베이스 내에서 고유합니다.|  
|**schema_id**|**int**|스키마의 ID입니다. 데이터베이스 내에서 고유합니다.|  
|**principal_id**|**int**|이 스키마를 소유하는 보안 주체의 ID입니다.|  
  
## <a name="remarks"></a>Remarks  
 데이터베이스 스키마 또는 역할을 할 네임 스페이스에 있는 테이블, 뷰, 프로시저 및 함수 등의 개체에 대 한 컨테이너를 **sys.objects** 카탈로그 뷰에 있습니다.  
  
## <a name="permissions"></a>사용 권한  
 **public** 역할의 멤버 자격이 필요합니다. 자세한 내용은 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)을 참조하세요.  
  
## <a name="see-also"></a>관련 항목  
 [카탈로그 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [스키마 카탈로그 뷰 &#40;TRANSACT-SQL&#41;](https://msdn.microsoft.com/library/c516fb1c-b6ed-48ae-99c7-a78bc4336c8e)   
 [sys.objects &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md)  
  
  
