---
title: "프로젝트 설정 (변환) (MySQLToSQL) | Microsoft Docs"
ms.prod: sql-non-specified
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 7ad5fe44-6445-4ba8-a457-5af792631f11
caps.latest.revision: 19
author: sabotta
ms.author: carlasab
manager: lonnyb
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 68b16e7263c08c4941f6ad7c1f037de5a4fc0f30
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="project-settings-conversion-mysqltosql"></a>프로젝트 설정 (변환) (MySQLToSQL)
변환 페이지는 **프로젝트 설정** 대화 상자 SSMA MySQL 구문을 SQL Server 또는 SQL Azure 구문으로 변환 하는 방법을 사용자 지정 하는 설정이 포함 되어 있습니다.  
  
변환에서 제공 되는 **프로젝트 설정** 및 **기본 프로젝트 설정** 대화 상자.  
  
-   사용 하 여 **기본 프로젝트 설정** 모든 프로젝트에 대 한 구성 옵션을 설정 하려면 대화 상자. 변환 설정에 액세스 하려면는 **도구** 메뉴 선택 **기본 프로젝트 설정**, 설정 된 볼 /에서 변경 하는 데 필요한 마이그레이션 프로젝트 형식을 선택 **마이그레이션 대상 버전** 드롭다운을 클릭 **일반** 선택 고 왼쪽된 창 맨 아래에 **변환**합니다.  
  
-   에 현재 프로젝트에 대 한 설정을 지정 하려면는 **도구** 메뉴 클릭 **프로젝트 설정**, 클릭 **일반** 클릭 한 다음 확인 하 고 왼쪽된 창 맨 아래에 **변환**합니다.  
  
## <a name="options"></a>옵션  
  
### <a name="collate-clause"></a>Collate 절  
  
|||  
|-|-|  
|**용어**|**정의**|  
|**COLLATE 절에 변환 하는 명시적 변환**|명시적 COLLATE 절 변환 옵션에는 MySQL 코드에서 명시적 COLLATE 절을 변환 하는 방법을 지정 합니다. 무시 하 고 경고와 함께 Mark/오류를 생성 가능한 선택 사항:<br /><br />**기본 모드**: 무시 및 경고와 함께 표시<br /><br />**최적 모드**: 무시 및 경고와 함께 표시<br /><br />**전체 모드**: 무시 및 경고와 함께 표시|  
  
### <a name="column-constraints"></a>열 제약 조건  
  
|||  
|-|-|  
|**용어**|**정의**|  
|**열거형 데이터 형식의 열에 대 한 제약 조건 생성**|MySQL 테이블에 없는 경우 SQL Server 또는 SQL Azure 테이블에 열거형 데이터 형식의 열에 대 한 제약 조건을 생성 합니다. 그러한 경우 열거형 데이터 형식의 변환 된 모든 열 값을 제어 하는 CHECK 제약 조건이 있는 함께 합니다.<br /><br />**기본 모드**: 아니요<br /><br />**최적 모드**: 아니요<br /><br />**전체 모드**: 예|  
|**집합 데이터 형식의 열에 대 한 제약 조건 생성**|MySQL 테이블에 없는 경우 SQL Server 또는 SQL Azure 테이블의 집합 데이터 형식의 열에 대 한 제약 조건을 생성 합니다. 그러한 경우 값을 제어 하는 CHECK 제약 조건으로 모든 변환 된 열 집합 데이터 형식의 함께 제공 됩니다.<br /><br />**기본 모드**: 아니요<br /><br />**최적 모드**: 아니요<br /><br />**전체 모드**: 예|  
|**부호 없는 숫자 데이터 형식 열의 열에 대 한 제약 조건 생성**|부호 없는 숫자 데이터 형식의 열에 음수가 아닌 값에 대 한 검사를 추가 합니다.<br /><br />**기본 모드**: 아니요<br /><br />**최적 모드**: 아니요<br /><br />**전체 모드**: 예|  
|**연도 데이터 형식 열에 대 한 제약 조건 생성**|MySQL 테이블에 없는 경우 SQL Server 또는 SQL Azure 테이블의 연도 데이터 형식 열에 대 한 제약 조건을 생성 합니다. 모든 열을 변환 그렇다면 연도 데이터의 형식 값을 제어 하는 CHECK 제약 조건으로 수반 됩니다.<br /><br />**기본 모드**: 아니요<br /><br />**최적 모드**: 아니요<br /><br />**전체 모드**: 예|  
  
### <a name="data-types"></a>데이터 형식  
  
|||  
|-|-|  
|**용어**|**정의**|  
|**열거형 데이터 형식 변환**|NVARCHAR로 변환 또는 숫자 변환 MySQL 열거형 데이터 형식 변환 방법을 지정합니다<br /><br />**기본 모드**: NVARCHAR로 변환<br /><br />**최적 모드**: NVARCHAR로 변환<br /><br />**전체 모드**: NVARCHAR로 변환|  
|**설정 데이터 형식 변환**|데이터 형식 MySQL 설정 되어야 할 방법을 지정 NVARCHAR (L)를 변환으로 변환 BINARY(L) 변환할 /<br /><br />**기본 모드**: NVARCHAR(L) 변환<br /><br />**최적 모드**: NVARCHAR(L) 변환<br /><br />**전체 모드**: NVARCHAR(L) 변환|  
  
### <a name="generic"></a>제네릭  
  
|||  
|-|-|  
|**용어**|**정의**|  
|**INSERT 및 바꾸기 기본값 없는 열**|'예' MyISAM 및 InnoDb 이외의 저장된 엔진을 사용 하 여 테이블을 참조 하는 모든 문이 경고 변환 메시지와 함께 표시 되어야 합니다.<br /><br />**기본 모드**: 열 목록에 추가<br /><br />**최적 모드**: 열 목록에 추가<br /><br />**전체 모드**: 열 목록에 추가|  
|**0 변환으로 나누기를 생성합니다.**|MySQL ERROR_FOR_DIVISION_BY_ZERO 동작 없이 에뮬레이트하 것인지 여부를 지정 합니다.<br /><br />**기본 모드**: 오류<br /><br />**최적 모드**: 오류<br /><br />**전체 모드**: NULL|  
|**IN 연산자**|MySQL IN 연산자를 변환 하는 방법을 지정 합니다.<br /><br />**기본 모드**: IN를로 항상 변환<br /><br />**최적 모드**: IN를로 항상 변환<br /><br />**전체 모드**: 필요한 경우 확장|  
|**MySQL 함수 변환**|MySQL 표준 함수를 변환 하는 방법을 지정 합니다.<br /><br />**기본 모드**: 낙관적<br /><br />**최적 모드**: 낙관적<br /><br />**전체 모드**: 정확 하 게|  
|**저장소 엔진을 지원 되지 않습니다.**|'예' MyISAM 및 InnoDb 이외의 저장된 엔진을 사용 하 여 테이블을 참조 하는 모든 문이 경고 변환 메시지와 함께 표시 되어야 합니다.<br /><br />**기본 모드**: 아니요<br /><br />**최적 모드**: 아니요<br /><br />**전체 모드**: 예|  
|**ROWID 보조 열 생성이 되지 않습니다**|그러한 경우 대상 테이블에 ROWD 보조 열 만들기의 생성을 금지 합니다. 몇 가지 구조 마이그레이션의 영향을 줄 수 있습니다.<br /><br />**기본 모드**: 아니요<br /><br />**최적 모드**: 아니요<br /><br />**전체 모드**: 아니요|  
|**TRUNCATE 문 변환**|잘라내기 명령문을 변환 하는 방법을 지정 합니다.<br /><br />**기본 모드**: TRUNCATE<br /><br />**최적 모드**: TRUNCATE<br /><br />**전체 모드**: TRUNCATE|  
  
### <a name="misc"></a>기타  
  
|||  
|-|-|  
|**용어**|**정의**|  
|**기본 스키마 매핑**|MySQL 데이터베이스를 SQL Server 스키마로 매핑하는 방법을 지정 합니다.<br /><br />**기본 모드**: 데이터베이스<br /><br />**최적 모드**: 데이터베이스<br /><br />**전체 모드**: 데이터베이스|  
  
### <a name="procedures-and-functions"></a>프로시저 및 함수  
  
|||  
|-|-|  
|**용어**|**정의**|  
|**기본 함수 변환**|함수 수 기본적으로 변환 됩니다 T-SQL 함수 또는 저장된 프로시저를 지정 합니다.<br /><br />**기본 모드**: 함수 변환<br /><br />**최적 모드**: 함수 변환<br /><br />**전체 모드**: 함수 변환|  
|**SET XACT_ABORT를 생성 합니다.**|SET XACT_ABORT ON 변환 된 프로시저 또는 트리거의 시작 부분에 추가 해야 여부를 지정 합니다.<br /><br />**기본 모드**: 예<br /><br />**최적 모드**: 예<br /><br />**전체 모드**: 예|  
|**에 SET NOCOUNT를 생성 합니다.**|SET NOCOUNT ON 변환 된 프로시저 또는 트리거의 시작 부분에 추가 해야 여부를 지정 합니다.<br /><br />**기본 모드**: 예<br /><br />**최적 모드**: 예<br /><br />**전체 모드**: 예|  
  
### <a name="spatial-data-types"></a>공간 데이터 형식  
  
|||  
|-|-|  
|**용어**|**정의**|  
|**기본 {XMAX &#124; 경계 상자 XMIN &#124; YMAX &#124; YMIN} 공간 인덱스에 대 한**|{XMAX &#124;에 대 한 기본값을 정의합니다. XMIN &#124; YMAX &#124; 경계 상자 공간 인덱스에 사용 된 YMIN} 매개 변수입니다.<br /><br />**기본 모드**<br /><br />XMAX: 100<br /><br />XMIN: 0<br /><br />YMAX: 100<br /><br />YMIN: 0<br /><br />**최적 모드**<br /><br />XMAX: 100<br /><br />XMIN: 0<br /><br />YMAX: 100<br /><br />YMIN: 0<br /><br />**전체 모드**<br /><br />XMAX: 100<br /><br />XMIN: 0<br /><br />YMAX: 100<br /><br />YMIN: 0|  
|**공간 인덱스에 대 한 기본 표 밀도**|LEVEL_1, LEVEL_2, LEVEL_3, 및 공간 인덱스에 사용 되는 표 밀도의 LEVEL_4에 대 한 기본값을 정의 합니다.<br /><br />**기본 모드**<br /><br />LEVEL_1: 기본값<br /><br />LEVEL_2: 기본값<br /><br />LEVEL_3: 기본값<br /><br />LEVEL_4: 기본값<br /><br />**최적 모드**<br /><br />LEVEL_1: 기본값<br /><br />LEVEL_2: 기본값<br /><br />LEVEL_3: 기본값<br /><br />LEVEL_4: 기본값<br /><br />**전체 모드**<br /><br />LEVEL_1: 기본값<br /><br />LEVEL_2: 기본값<br /><br />LEVEL_3: 기본값<br /><br />LEVEL_4: 기본값|  
  
### <a name="transactions"></a>트랜잭션  
  
|||  
|-|-|  
|**용어**|**정의**|  
|**비트랜잭션 테이블**|경고 변환 메시지와 함께 트랜잭션을 지원 하지 않는 테이블에 모든 참조를 표시 해야 여부를 지정 합니다.<br /><br />**기본 모드**: 아니요<br /><br />**최적 모드**: 아니요<br /><br />**전체 모드**: 예|  
|**트랜잭션 격리 수준**|새 트랜잭션을에 사용할 트랜잭션 격리 수준을 지정 합니다.<br /><br />**기본 모드**: 기본값<br /><br />**최적 모드**: 기본값<br /><br />**전체 모드**: 반복 읽기|  
  
### <a name="value-control"></a>값 컨트롤  
  
|||  
|-|-|  
|**용어**|**정의**|  
|**숫자 변환에는 문자**|지정 숫자 데이터 형식으로 문자 데이터 형식에서 암시적 및 명시적 변환을 처리 하는 방법입니다.<br /><br />**기본 모드**: 낙관적<br /><br />**최적 모드**: 낙관적<br /><br />**전체 모드**: 정확 하 게|  
|**부호 없는 숫자 값을 제어 합니다.**|컨트롤에 부호 없는 숫자 변수 및 매개 변수 값을 지정 합니다.<br /><br />**기본 모드**: 아니요<br /><br />**최적 모드**: 아니요<br /><br />**전체 모드**: 예|  
|**서명 되지 않은 빼기를 제어 합니다.**|부호 없는 데이터 형식의 테이블 열에 삽입 하는 음수 값을 수정 합니다.<br /><br />**기본 모드**: 변환 '으로-는 '<br /><br />**최적 모드**: 변환 '으로-는 '<br /><br />**전체 모드**: 경고와 함께 표시|  
|**이진 데이터 형식에서 변환**|지정 이진 데이터 형식에서 암시적 및 명시적 변환을 처리 하는 방법입니다.<br /><br />**기본 모드**: 낙관적<br /><br />**최적 모드**: 낙관적<br /><br />**전체 모드**: 정확 하 게|  
|**날짜/시간 데이터 형식을**|지정 데이터 형식이 암시적 및 명시적 변환 날짜/시간을 처리 하는 방법입니다.<br /><br />**기본 모드**: 에뮬레이트하 MySQL 형식<br /><br />**최적 모드**: 사용 하 여 SQL Server 형식<br /><br />**전체 모드**: 에뮬레이트하 MySQL 형식|  
|**숫자 리터럴은 전체 자릿수가 38를 초과 합니다.**|숫자 리터럴은 전체 자릿수가 38 초과 변환 하는 방법을 지정 합니다.<br /><br />**기본 모드**: 가능 하면 반올림<br /><br />**최적 모드**: 가능 하면 반올림<br /><br />**전체 모드**: 가능 하면 반올림|  
|**NOT NULL 열에 0-날짜**|지정 NOT NULL 열 0-날짜의 날짜에 0 또는 잘못 된 날짜/시간 값에 대 한 할당을 처리 하는 방법입니다.<br /><br />**기본 모드**: getdate)<br /><br />**최적 모드**: getdate)<br /><br />**전체 모드**: getdate)|  
  
## <a name="see-also"></a>관련 항목:  
[사용자 인터페이스 참조 &#40; MySQLToSQL &#41;](../../ssma/mysql/user-interface-reference-mysqltosql.md)  
  
