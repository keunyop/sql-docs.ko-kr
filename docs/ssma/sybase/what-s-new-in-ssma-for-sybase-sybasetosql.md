---
title: SAP ASE (SybaseToSQL) 용 SSMA의 새로운 기능 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2019
ms.prod: sql
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 2be0cf8d-6dbe-443a-abbd-036249922205
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 875f89a53963633a267ada1ae1563360cbebf7d8
ms.sourcegitcommit: d7ed341b2c635dcdd6b0f5f4751bb919a75a6dfe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57527096"
---
# <a name="whats-new-in-ssma-for-sap-ase-sybasetosql"></a>SAP ASE (SybaseToSQL) 용 SSMA의 새로운 기능
이 문서에서는 SAP ASE (이전의 Sybase 용 SSMA) 각 릴리스의 변경 내용에 대 한 SQL Server Migration Assistant (SSMA)를 나열 합니다.

## <a name="ssma-v81"></a>SSMA v8.1
SAP ASE 용 SSMA의 v8.1 릴리스에서 품질 및 변환 메트릭을 향상 하도록 설계 된 대상된 수정 사항을 사용 하 여 향상 되었습니다.

> [!NOTE]
> 자동 업데이트를 사용 하 여 알려진된 문제 v8.1를 SSMA v8.0에서 업데이트 오류가 발생할 수 있습니다. 이 오류가 발생 하면 새 버전을 다운로드 하 고 수동으로 설치 하세요.

> [!IMPORTANT]
> SSMA v7.4 및 이후 버전에서는.Net 4.5.2는 설치 필수입니다.

## <a name="ssma-v80"></a>SSMA v8.0
SAP ASE 용 SSMA의 v8.0 릴리스에서 품질 및 변환 메트릭을 개선 하기 위한 대상된 수정 사항을 사용 하 여 향상 되었습니다. 또한이 릴리스에 다음과 같은 새로운 기능을 제공합니다.

* 에 대 한 지원 **Azure SQL Database Managed Instance** 대상으로 합니다. 이제 Azure SQL Database Managed Instance를 대상으로 하는 새 프로젝트를 만들 수 있습니다.

    ![SQL DB MI 프로젝트](../media/ssma-newproject-sqldbmi.png)

*   변환 후 **수정 advisor**합니다. 자세한 내용을 알아보세요 [여기](https://blogs.msdn.microsoft.com/datamigration/2019/02/17/%20accelerate-your-oracle-migrations-with-new-machine-learning-capabilities-in-ssma/)합니다.

*   임시 데이터베이스/스키마 선택 합니다.

    원본에 연결할 때 사용자가 데이터베이스/스키마 관심 이제 선택할 수 있습니다. 마이그레이션하려는 스키마만 선택 하면 초기 연결 중 시간이 절약 되 고 전반적인 SSMA 성능을 개선 합니다.

    ![SSMA 필터 개체](../media/ssma-filter-objects.png)

## <a name="ssma-v710"></a>SSMA v7.10
SSMA v7.10 릴리스 SAP ASE에 대 한 추가 보안 및 글로벌 요구 사항 변화에에서 맞게 개인 정보 보호를 제공 하도록 설계 하는 대상된 수정 사항을 향상 되었습니다.

## <a name="ssma-v79"></a>SSMA v7.9
SAP ASE에 대 한 v7.9 릴리스의 SSMA 같은 변경 내용이 포함 됩니다.
- 품질 및 변환 메트릭을 개선 하는 대상된 수정 되었습니다.
- 데이터 형식 매핑 및 프로젝트 기본 설정을 변경 하려면 SSMA 명령줄에서 지원 합니다.
- 마이그레이션에 대 한 지원 SQL Server Integration Services (SSIS)를 사용 하 여 데이터입니다. 스키마를 변환한 후 마우스 오른쪽 단추 클릭 상황에 맞는 메뉴 옵션을 사용 하 여 SSIS 패키지를 만들 수는 있습니다.
- 정규화 된 서버 이름을 지정 하려면 SSMA에서 Azure SQL Database 연결 대화 상자도 변경 되었습니다. SSMA의 이전 버전에서는 Azure SQL Database 접두사 프로젝트 설정 내에서 명시적으로 언급 해야 했습니다.

## <a name="ssma-v78"></a>SSMA v7.8
SAP ASE 용 SSMA의 v 7.8 릴리스에서 다음 변경 내용을 포함 되어 있습니다.
- 프로젝트 설정에서 강조 표시 하는 형식 매핑을 변경 합니다.
- 원격 분석을 사용 하지 않도록 설정 하는 작업을 할 수 있습니다.

## <a name="ssma-v77"></a>SSMA v7.7
SAP ASE에 대 한 v7.7 릴리스의 SSMA 같은 변경 내용이 포함 됩니다.
- SSMA SAP ASE에 대 한 품질 및 변환 메트릭을 개선 하는 대상된 수정 사항을 사용 하 여 향상 되었습니다.
- 인기 있는 필요에 따라 SAP ASE 용 SSMA의 32 비트 버전은 다시 합니다. 이전 구현에 비해 (하기 전에 v7.4에), 두 개의 설치 관리자 패키지 있지만 나란히 설치할 수 없습니다. 결과적으로, 해야 연결 구성 요소에 따라 가장 적합 한 버전을 선택 해야 합니다. 항상 가능한 경우 64 비트 버전을 사용 하는 것이 좋습니다.

## <a name="ssma-v76"></a>SSMA v7.6
SAP ASE에 대 한 v7.6 릴리스의 SSMA 같은 변경 내용이 포함 됩니다.
- 수정 하 여 변환 및 품질 메트릭을 개선 대상와 SQL Server 2017 (공개 미리 보기)을 지원 합니다. Windows 및 Linux에서 SQL Server 2017에 대 한 지원을 공개 미리 보기로 제공 않으며 프로덕션 마이그레이션에 사용할 수 없습니다.
- Sybase 함수 변환 지원 합니다.

## <a name="ssma-v75"></a>SSMA v7.5
SAP ASE (이전의 Sybase 용 SSMA) 용 SSMA의 v7.5 릴리스에서 다음 변경 내용을 포함 되어 있습니다.
-   장애가 있는 사용자에 큰 액세스 가능성을 보장 하기 위해 여러 기능이 향상 되었습니다.
-   만들기 또는 교체 구문 지원 합니다.

## <a name="ssma-v74"></a>SSMA v7.4
Sybase 용 SSMA의 v7.4 릴리스는 다음 변경 내용을 포함 되어 있습니다.
- 합니다 **쿼리 제한 시간** 옵션을 원본 및 대상 스키마 개체 검색 하는 동안 제공 됩니다.

    ![쿼리 제한 시간 옵션](../media/query-timeout_red.png)
- 품질 및 변환 메트릭, 고객 피드백에 따라 대상된 수정 사항을 사용 하 여 향상 되었습니다.

> [!IMPORTANT]
> .NET 4.5.2 v7.4 SSMA를 설치 하기 위한 필수 조건입니다. 또한 v7.4 부터는 32 비트 버전의 SSMA이 이제 중단 됩니다.  

## <a name="ssma-v73"></a>SSMA v7.3
Sybase 용 SSMA의 v7.3 릴리스는 다음 변경 내용을 포함 되어 있습니다.
- 향상 된 품질 및 변환 메트릭 고객 피드백에 따라 대상된 수정 사항 사용 하 여입니다.
- SSMA 확장성 프레임 워크는 다음 항목을 통해 노출 합니다.
  - SQL Server Data Tools (SSDT) 프로젝트에 기능을 내보냅니다.
    -   이제 SSDT 프로젝트 SSMA에서 스키마 스크립트를 내보낼 수 있습니다. 추가 스키마 변경을 수행 하 여 데이터베이스를 배포 하는 스키마 스크립트를 사용할 수 있습니다.

        ![SSDT 프로젝트 명령으로 저장](../media/export-schema-scripts_red.png)
  - SSMA 사용자 지정 변환을 수행 하는 데 사용할 수 있는 라이브러리입니다.
    - 이제 사용자 지정 구문 변환 및 SSMA 이전에 처리 되지 않은 변환을 처리할 수 있는 코드를 생성할 수 있습니다.
      - 이 블로그 게시물에서는 사용자 지정 변환기를 생성 하는 방법에 사용할 [확장 SQL Server Migration Assistant의 변환 기능](https://blogs.msdn.microsoft.com/datamigration/2017/02/21/2185/)합니다.
      - 이 변환에 대 한 샘플 프로젝트를 다운로드 [블로그 게시물](https://blogs.msdn.microsoft.com/datamigration/ssmafororacleconversionsample/)합니다.

## <a name="ssma-v72"></a>SSMA v7.2
Sybase 용 SSMA의 v 7.2가 사전 릴리스는 다음 변경 내용이 포함 되어 있습니다.
- 향상 된 품질 및 변환 메트릭 고객 피드백에 따라 대상된 수정 사항 사용 하 여입니다.
- 더 나은 데이터 요소를 고객 문제를 해결 하 여 SSMA의 전환율을 향상 시킬 수 있도록 원격 분석 향상 된 기능입니다.

## <a name="ssma-v71"></a>SSMA v7.1
Sybase 용 SSMA의 v7.1 릴리스는 다음 변경 내용을 포함 되어 있습니다.
- Windows 및 Linux CTP1에서 SQL Server 2017 마이그레이션에 대 한 지원 되는 대상 플랫폼 되었습니다. 이 기능은 기술 미리 보기 상태에서 이며 대상 SQL server에 스키마 및 데이터 이동을 지원 합니다.
- 이 제품은 즉시 최신 버전의 SSMA 다운로드 하려면 자동 업데이트를 지원 합니다.
- SSMA 설치 가능 이진 파일은 이제 Windows installer 패키지 파일 (.msi)를 통해 전달 됩니다.

**리소스**

[SQL Server Migration Assistant의 변환 기능 확장](https://blogs.msdn.microsoft.com/datamigration/2017/02/21/2185/)

[평가 및 비 Microsoft 데이터 플랫폼에서 데이터를 SQL Server로 마이그레이션 *(사용 하 여 Oracle 예제)*](https://blogs.msdn.microsoft.com/datamigration/2016/11/16/sql-server-migration-assistant-how-to-assess-and-migrate-databases-from-non-microsoft-data-platforms-to-sql-server/) 

## <a name="may-2016"></a>2016 년 5 월  
Sybase 용 SSMA의 2016 년 5 월 릴리스는 다음 변경 내용이 포함 되어 있습니다.  

-  SQL Server 2016에 대 한 지원이 추가 되었습니다.
-  .NET 2.0에 대 한 설치 관리자 검사를 제거 합니다.
-  업데이트 된 확장 팩 종속성.Net 3.5에서에서.net 4.0입니다.
-  "저장"프로젝트 수정 및 SSMA 콘솔에 대 한 프로젝트 열기 명령입니다.
-  SSMA 콘솔에 대 한 고정된 "securepassword" 명령입니다.
-  초기 로드에 대 한 개체의 계산을 고정 합니다.
-  전역 설정에 대 한 버그가 수정 되었습니다.

## <a name="march-2016"></a>2016 년 3 월  
Sybase 용 SSMA의 2016 년 3 월 미리 보기 릴리스의 SQL Server 2016으로 마이그레이션에 대 한 지원을 추가합니다.  
  
## <a name="january-2016"></a>2016 년 1 월  
Sybase 용 SSMA의 2016 년 1 월 유지 관리 릴리스는 다음 변경 내용을 포함 되어 있습니다.  
  
-  추가 뷰는 메뉴 항목을 로그 하 SSMA (RFC 5706203)입니다.  
-  추가 원격 분석입니다. 
  
## <a name="july-2014"></a>2014 년 7 월  
Sybase 용 SSMA의 2014 년 7 월 릴리스는 다음 변경 내용이 포함 되어 있습니다.  
  
-  향상 된 Azure SQL DB 코드 변환 합니다.  
-  Azure SQL DB를 지원 하도록 스키마를 확장 팩 기능을 이동 합니다.  
-  추가 성능 향상 10k를 사용 하 여 데이터베이스에 대 한 개체를 테스트 합니다.  
-  많은 수의 개체를 처리 하기 위한 향상 된 UI가 추가 되었습니다.  
-  (따라서 변환에서 무시) "알려진" LOB 스키마를 강조 표시 하는 기능을 추가 합니다.  
-  변환 속도 향상을 추가 합니다.  
-  UI에서 개체 수를 표시 하는 기능을 추가 합니다. 
-  25% 이상 감소 보고서 크기입니다.  
-  구문 분석 되지 않은 구문에 대 한 향상 된 오류 메시지입니다.  
  
## <a name="april-2014"></a>2014 년 4 월  
Sybase 용 SSMA의 2014 년 4 월 릴리스는 다음 변경 내용이 포함 되어 있습니다.  
  
-   MS SQL Server 2014 지원이 추가 되었습니다.  
-   Azure에 변환에 대 한 수정 된 버그입니다.  
-   IE 10에서 보이지 않는 보고서 페이지에 대 한 수정 된 버그입니다.  
  
## <a name="january-2012"></a>2012 년 1 월  
Sybase 용 SSMA의 2012 년 1 월 릴리스에서 다음 변경 내용을 포함 되어 있습니다.  
  
-   롤백 트리거 변환에 대 한 지원이 추가 되었습니다.  
-   변환에 대 한 수정 프로그램을 제공@ROWCOUNT 및 @@ERROR 동일한 SET 문의 합니다.  
  
## <a name="july-2011"></a>2011 년 7 월  
Sybase 용 SSMA의 2011 년 7 월 릴리스는 향상 된 오류 데이터 마이그레이션 중에 보고 기능을 제공 합니다.  
  
## <a name="april-2011"></a>2011 년 4 월  
Sybase 용 SSMA의 2011 년 4 월 릴리스에서 다음 변경 내용을 포함 되어 있습니다.  
  
-   지 원하는 통합된 "Sybase SSMA" 제품 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2008 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] "Denali" 및 Azure SQL입니다.  
-   연결 및 마이그레이션에 대 한 지원이 추가 되었습니다 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] "Denali"로 지정 합니다.  
-   Sybase 데이터베이스를 Azure SQL로 변환 하는 새 기능이 추가 되었습니다.  
-   데이터의 병렬 마이그레이션을 지 원하는 향상 된 클라이언트 쪽 데이터 마이그레이션 엔진입니다.  
-   향상 된 데이터 마이그레이션 성능을 단순 및 대량 로그 복구 모델.  
-   올바르게 변환 하 고 대/소문자 구분 SQL Server에 대/소문자 구분 Sybase 데이터베이스를 마이그레이션하는 기능을 추가 합니다.  
-   삭제 및 방침을 업데이트 하려면 SQL Server ANSI 조인 문에 조인 문이 ANSI가 아닌 Sybase ASE는 변환에 대 한 지원이 추가 되었습니다 확장 되었습니다.  
-   Sybase ASE ODBC 공급자 및 Sybase ASE ADO.Net 공급자를 사용 하 여 Sybase ASE 서버에 연결 하기 위한 추가 연결 옵션을 제공 합니다.  
-   라는 별도 데이터베이스에 대 한 종속성을 제거 **SysDB**, Sybase 에뮬레이션 함수 (확장 팩의 일부로 설치)를 포함 하는 합니다.  
-   SSMA for Sybase 확장 팩 설치 하는 기능을 추가 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 클러스터.  
-   SSMA (v4.0 및 v4.2)의 이전 버전에서 만든 프로젝트의 이전 버전과 호환성을 추가 합니다.  
-   이전 버전의 SSMA (v4.0 및 v4.2)를 사용 하 여 Sybase v5.0 제품에서 나란히 (SxS) 용 SSMA를 설치 하는 기능을 추가 합니다.  
  
## <a name="july-2010"></a>2010 년 7 월  
Sybase 용 SSMA의 2010 년 7 월 릴리스는 다음 변경 내용이 포함 되어 있습니다.  
  
-   SQL Server 2008 R2로 마이그레이션에 대 한 지원이 추가 되었습니다.  
-   명령줄 실행에 대 한 새 SSMA 콘솔 응용 프로그램을 추가 합니다.  
-   서버 쪽 및 클라이언트 쪽 데이터 마이그레이션 엔진을 사용 하 여 데이터 마이그레이션에 대 한 지원이 추가 되었습니다.  
-   데이터 마이그레이션에 대 한 "사용자 지정 선택" 문에 대 한 지원이 추가 되었습니다.  
-   Sybase ASE 15.0.3 및 15.5에서에서 마이그레이션에 대 한 지원이 추가 되었습니다.  
  
## <a name="june-2008"></a>2008 년 6 월  
Sybase 용 SSMA의 2008 년 6 월 릴리스는 다음 변경 내용이 포함 되어 있습니다.  
  
-   데이터베이스 개체를 변환 하 고 SSMA 수행한 데이터 마이그레이션이 자동으로 테스트 하는 추가 SSMA 테스터. 모든 SSMA 마이그레이션 단계가 완료 되 면 모든 데이터가 제대로 전송 된 및 변환 된 개체가 동일한 방식으로 작동 하는지 확인 하려면 SSMA 테스터를 사용 합니다.  
-   추가 사전 SQL 변환 합니다. 이제 지정할 수 있습니다 임시 테이블 (및 다른 개체) 변환에 사용할 각 원본 프로시저에 대 한 선언 합니다.  
-   개체 변환에 추가 된 향상 된 기능:  
    -   조인 수정 변환 합니다.  
    -   집계 및 없이 비 집계 하지/그룹화 절.  
    -   SELECT INTO 문 사용 하 여 IDENTITY 함수입니다.  
    -   클러스터형된 제약 조건 및 데이터에만 잠금이 설정의 인덱스입니다.  
    -   SELECT INTO에서 만든 임시 테이블입니다.  
    -   제약 조건 / 임시 테이블에 대 한 인덱스입니다.  
    -   새 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2008 날짜/시간 형식이 지원 됩니다.  
    -   Sybase 15.0 연결 및 데이터 형식을 지원 합니다.  
  
## <a name="may-2007"></a>2007 년 5 월  
Sybase 용 SSMA의 2007 년 5 월 릴리스는 다음 변경 내용이 포함 되어 있습니다.  
  
-   프로젝트를 저장할 때 데이터베이스 콘텐츠를 더 빠르게 로드 하는 기능을 추가 합니다.  
-   SQL 모드를 포맷 하는 SQL Server에서 사용자가 입력 한 주석에 대 한 지원이 추가 되었습니다.  
-   개체 변환에 추가 된 개선 사항입니다.  
  
이 릴리스에 대 한 도움말 파일 업데이트 되지 않았습니다. 자세한 내용은이 문서의 뒷부분에 나오는 설명서 참고 사항 섹션을 참조 합니다.  
  
## <a name="november-2006"></a>2006 년 11 월  
Sybase 용 SSMA의 2006 년 11 월 릴리스에서 다음 변경 내용을 포함 되어 있습니다.  
  
-   새 전역 설정을 추가 합니다.  
    -   편집기 창에서 줄 번호를 표시 하도록 선택할 수 있습니다.  
    -   SSMA 중복 개체를 바꿀 것인지 묻는 메시지를 구성 하거나 항상 하지 않았거나 전혀 스키마 변환 하는 동안 중복 된 개체를 바꿀 수 있습니다.  
-   SSMA에서 다음과 같은 경우를 처리 하는 방법을 구성할 수 있는 새 변환 옵션을 추가 합니다.  
    -   CAST 또는 CONVERT 문의 이진 문자열을 포함 합니다.  
    -   같음 식의 null 값을 확인 합니다.  
    -   프록시 테이블입니다.  
    -   RAISERROR에 대 한 사용자 메시지의 오류 번호입니다.  
    -   확인 되지 않은 식별자를 포함 하는 UPDATE 문입니다.  
-   SSMA에서 외부에 있는 날짜를 처리 하는 방법을 지정할 수 있는 새 마이그레이션 옵션을 추가 합니다 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 날짜 범위입니다.  
-   추가 **서식이 지정 된 SQL** 에 설정 합니다 **SQL** 탭이 가독성 향상된을 위해 코드 형식입니다.  
-   포함 되는 버그 수정:  
    -   SSMA는 이제 잠금이 테이블 변환 *테이블* 에 {0} 공유 | 후속에 TABLOCK 또는 TABLOCKX 힌트를 추가 하 여 단독} 모드 문은 테이블에 대 한 쿼리를 선택 합니다.  
    -   문자 식에서 이진 형식을 사용 하는 경우에 이제 필요한 캐스트 추가 됩니다.  
    -   메모리 및 성능 개선 사항입니다.  
  
## <a name="july-2006"></a>2006 년 7 월  
SSMA for Sybase의 2006년 7월 릴리스가 첫 버전입니다.  
  
## <a name="see-also"></a>관련 항목  
[Sybase 용 SSMA 시작 &#40;SybaseToSQL&#41;](../../ssma/sybase/getting-started-with-ssma-for-sybase-sybasetosql.md)
