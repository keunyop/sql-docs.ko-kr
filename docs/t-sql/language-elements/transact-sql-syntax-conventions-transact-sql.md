---
title: "TRANSACT-SQL 구문 표기 규칙 (Transact SQL) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sql13.TSQLExpandPortal.f1
dev_langs:
- TSQL
helpviewer_keywords:
- conventions [SQL Server]
- Applies to section in Transact-SQL topics
- code example conventions [SQL Server]
- objects [SQL Server], names
- code [SQL Server], conventions
- multipart names [SQL Server]
- Transact-SQL syntax conventions
- syntax conventions [SQL Server]
- code [SQL Server]
- Transact-SQL
- naming conventions [SQL Server]
- syntax [SQL Server], Transact-SQL
ms.assetid: 35fbcf7f-8b55-46cd-a957-9b8c7b311241
caps.latest.revision: 55
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 9a1c60d865d1b18eae1cd89ea226e91e8e7b5b9e
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="transact-sql-syntax-conventions-transact-sql"></a>TRANSACT-SQL 구문 표기 규칙-TRANSACT-SQL
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  다음 표에서는 [!INCLUDE[tsql](../../includes/tsql-md.md)] 참조의 구문 다이어그램에 사용되는 규칙을 나열하고 설명합니다.  
  
|규칙|사용 대상|  
|----------------|--------------|  
|대문자|[!INCLUDE[tsql](../../includes/tsql-md.md)] 키워드입니다.|  
|*기울임꼴*|사용자가 제공하는 [!INCLUDE[tsql](../../includes/tsql-md.md)] 구문 매개 변수입니다.|  
|**굵게**|표시된 그대로 입력해야 하는 데이터베이스 이름, 테이블 이름, 열 이름, 인덱스 이름, 저장 프로시저, 유틸리티, 데이터 형식 이름 및 텍스트입니다.|  
|**밑줄**|밑줄 친 값이 포함된 절이 문에 지정되지 않을 때 적용되는 기본값을 나타냅니다.|  
|&#124;(세로 막대)|대괄호 또는 중괄호 내에서 구문 항목을 구분합니다. 항목 중 하나만 사용할 수 있습니다.|  
|`[ ]`(대괄호)|선택적 구문 항목입니다. 대괄호는 입력하지 않습니다.|  
|{}(중괄호)|필수 구문 항목입니다. 중괄호는 입력하지 않습니다.|  
|[**,**...*n*]|앞의 항목이 *n* 번 반복될 수 있음을 나타냅니다. 각 항목은 쉼표로 구분됩니다.|  
|[...*n*]|앞의 항목이 *n* 번 반복될 수 있음을 나타냅니다. 각 항목은 공백으로 구분됩니다.|  
|;|[!INCLUDE[tsql](../../includes/tsql-md.md)] 문 종결자입니다. 이 버전의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서는 대부분의 문에 세미콜론이 필요하지 않지만 이후 버전에서는 필요합니다.|  
|\<레이블 >:: =|구문 블록의 이름입니다. 이 규칙은 문에서 한 번 이상 사용될 수 있는 긴 구문의 섹션 또는 구문 단위를 그룹화하고 레이블을 붙일 때 사용됩니다. 구문 블록이 사용 될 수 있는 각 위치 모양의 레이블로 표시 됩니다: \<레이블 > 합니다.<br /><br /> 예를 들어 집합은 식 집합이 \<그룹화 집합 >; 목록이 고 컬렉션 집합의 예를 들어 \<복합 요소 목록 > 합니다.|  
  
## <a name="multipart-names"></a>다중 부분 이름  
 다른 지침이 없으면 데이터베이스 개체 이름에 대한 모든 [!INCLUDE[tsql](../../includes/tsql-md.md)] 참조는 다음 형식과 같이 네 부분으로 된 이름으로 구성됩니다.  
  
 *server_name* **.** [*database_name*]**.** [*schema_name*]**.** *object_name*  
  
 | *a s e _***.** [*schema_name*]**.** *object_name*  
  
 | *schema_name***.** *object_name*  
  
 *| object_name*  
  
 *server_name*  
 연결된 서버 이름 또는 원격 서버 이름을 지정합니다.  
  
 *database_name*  
 개체가 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]의 로컬 인스턴스에 있을 때 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스의 이름을 지정합니다. 연결된 된 서버에 개체가 있으면 *database_name* OLE DB 카탈로그를 지정 합니다.  
  
 *schema_name*  
 개체가 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스에 있을 경우 해당 개체가 포함된 스키마의 이름을 지정합니다. 연결된 된 서버에 개체가 있으면 *schema_name* OLE DB 스키마 이름을 지정 합니다.  
  
 *object_name*  
 개체의 이름을 참조합니다.  
  
 특정 개체를 참조할 때 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]에서 개체를 식별하기 위해 항상 서버, 데이터베이스 및 스키마를 지정할 필요는 없습니다. 그러나 개체를 찾을 수 없는 경우 오류가 반환 됩니다.  
  
> [!NOTE]  
>  이름 확인 오류를 방지하기 위해서는 스키마 범위 개체를 지정할 때 항상 스키마를 지정하는 것이 좋습니다.  
  
 중간 노드를 생략하려면 마침표를 사용해 이 위치를 표시하십시오. 다음 표에서는 개체 이름의 유효한 형식을 보여 줍니다.  
  
|개체 참조 형식|Description|  
|-----------------------------|-----------------|  
|*서버* **합니다.** *데이터베이스* **합니다.** *스키마* **합니다.** *개체*|네 부분으로 이루어진 이름입니다.|  
|*서버* **합니다.** *데이터베이스* **...** *개체*|스키마 이름이 생략됩니다.|  
|*서버* **...** *스키마* **합니다.** *개체*|데이터베이스 이름이 생략됩니다.|  
|*서버* **...**  *개체*|데이터베이스 및 스키마 이름이 생략됩니다.|  
|*데이터베이스* **합니다.** *스키마* **합니다.** *개체*|서버 이름이 생략됩니다.|  
|*데이터베이스* **...** *개체*|서버 및 스키마 이름이 생략됩니다.|  
|*스키마* **합니다.** *개체*|서버 및 데이터베이스 이름이 생략됩니다.|  
|*개체*|서버, 데이터베이스 및 스키마 이름이 생략됩니다.|  
  
## <a name="code-example-conventions"></a>코드 예 표기 규칙  
 특별한 언급이 없으면 [!INCLUDE[tsql](../../includes/tsql-md.md)] 참조에서 제공되는 예는 다음 옵션에 대해 기본 설정을 사용하여 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]에서 테스트되었습니다.  
  
-   ANSI_NULLS  
  
-   ANSI_NULL_DFLT_ON  
  
-   ANSI_PADDING  
  
-   ANSI_WARNINGS  
  
-   CONCAT_NULL_YIELDS_NULL  
  
-   QUOTED_IDENTIFIER  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] 참조에 있는 대부분의 코드 예는 정렬 시 대/소문자를 구분하는 서버에서 테스트되었으며 일반적으로 테스트 서버에서는 ANSI/ISO 1252 코드 페이지가 실행됩니다.  
  
 많은 코드 예에서 문자를 가진 유니코드 문자열 상수의 접두사로 **N**합니다. 없이 **N** 접두사, 문자열이 데이터베이스의 기본 코드 페이지로 변환 됩니다. 이 기본 코드 페이지는 일부 문자를 인식하지 않을 수 있습니다.  
  
## <a name="applies-to-references"></a>'적용 대상' 참조  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] 참조와 관련 된 항목에 포함 [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)], 및 [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]합니다. 각 항목의 위쪽에는 항목의 제목을 지원하는 제품을 나타내는 섹션이 있습니다. 제품이 생략되어 있다면 항목에서 설명하는 기능을 해당 제품에서 사용할 수 없습니다. 예를 들어 가용성 그룹이 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]에서 도입되었습니다. **CREATE AVAILABILTY GROUP** 항목에 적용 됨 **SQL Server (SQL Server 2012부터 현재 버전)** 에 적용 되지 않는 [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], 또는 [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].  
  
 경우에 따라 항목의 일반적인 주제를 제품에서 사용할 수 있지만 모든 인수가 지원되지는 않습니다. 예를 들어 포함된 데이터베이스 사용자가 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]에서 도입되었습니다. **CREATE USER** 문을 사용할 수 있습니다 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 제품 있지만 **WITH PASSWORD** 구문은 이전 버전으로 사용할 수 없습니다. 이 경우, 추가 **에 적용 됩니다** 섹션 항목의 본문에 해당 인수 설명에 삽입 됩니다.  
  
## <a name="see-also"></a>관련 항목:  
 [Transact-SQL 참조&#40;데이터베이스 엔진&#41;](../../t-sql/transact-sql-reference-database-engine.md)  
  
  


