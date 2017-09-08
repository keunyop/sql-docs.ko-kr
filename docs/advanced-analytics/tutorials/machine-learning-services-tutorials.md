---
title: "SQL Server 컴퓨터 학습 자습서 | Microsoft Docs"
ms.custom:
- SQL2016_New_Updated
ms.date: 08/29/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- r-services
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- SQL Server 2016
dev_langs:
- Python
ms.assetid: 5ccc75f6-6703-47d9-b879-9a740569b45e
caps.latest.revision: 32
author: jeannt
ms.author: jeannt
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 0ebeae12d6987154baa7ccb7c9417e9f92b2bbe0
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="sql-server-machine-learning-tutorials"></a>SQL Server 기계 학습 자습서

이 문서에는 자습서, 데모 및 SQL Server 2016 또는 SQL Server 2017 컴퓨터 학습 기능을 사용 하는 예제 응용 프로그램의 한 포괄적인 목록을 제공 합니다. T-SQL에서 Python 또는 R을 실행할 원격 및 로컬 계산 컨텍스트를 사용 하 고 SQL 프로덕션 환경에 대 한 R 및 Python 코드를 최적화 하는 방법에 알아보려면 여기를 시작 합니다.

## <a name="start-here"></a>여기에서 시작

+ [Python 자습서](../tutorials/sql-server-python-tutorials.md)

+ [R 자습서](../tutorials/sql-server-r-tutorials.md)

요구 사항 및 설정 하는 방법에 대 한 자세한 내용은 참조 [필수 구성 요소](#bkmk_prerequisites)합니다.

## <a name="samples-and-solutions"></a>샘플 및 솔루션

+ [샘플](#bkmk_samples) 

    SQL Server 개발 팀에서 이러한 실제 시나리오는 응용 프로그램에서 기계 학습을 포함 하는 방법을 보여 줍니다. 모든 샘플 프로덕션 환경에서 다운로드, 수정 및 사용 하는 코드를 포함 합니다.

+ [솔루션](#bkmk_solutions) 

    Microsoft 데이터 과학 팀에서 템플릿은 기계 학습 빠른 시작 하도록 사용자 지정할 수 있습니다. 각 솔루션은 특정 작업이 나 업계 문제; 맞게 또한 대부분의 솔루션은 SQL Server 또는 Azure 기계 학습 등 클라우드 환경에서 실행 하도록 설계 되었습니다. 다른 솔루션을 Microsoft R Server 또는 HDI Spark 클러스터에서 실행할 수 있습니다.

### <a name ="bkmk_samples"></a>SQL Server 제품 샘플

이러한 샘플 및 데모는 SQL Server 및 R Server 개발 팀에서 제공한 실제 응용 프로그램에 포함 된 분석을 사용할 수 있는 방법으로 강조 표시 합니다.

+ [고객 수행 R 및 SQL Server를 사용 하 여 클러스터링](https://microsoft.github.io/sql-ml-tutorials/R/customerclustering/)

  판매 데이터를 기반으로 하는 세그먼트 고객에 게 자율된 학습을 사용 합니다. 이 예제는 클러스터링 모델을 만드는 데 Microsoft R에서 확장 가능한 rxKmeans 알고리즘을 사용 합니다. 
  
  적용 대상: SQL Server 2016 또는 SQL Server 2017

+ [새로운! 고객 수행 Python 및 SQL Server를 사용 하 여 클러스터링](https://microsoft.github.io/sql-ml-tutorials/python/customerclustering/)

    알고리즘을 사용 하 여 Kmeans 고객의 감독 되지 않은 클러스터링을 수행 하는 방법을 알아봅니다. 이 예제에서는 Python 언어에서-데이터베이스를 사용 합니다. 
    
    적용 대상: SQL Server 2017

+ [R 및 SQL Server를 사용 하 여 예상 모델을 작성](https://microsoft.github.io/sql-ml-tutorials/R/rentalprediction)

  Ski 임대 비즈니스 비즈니스 계획 및 교직원 향후 요구를 충족 하는 데 도움이 되는 기계 학습 이후 대 여 예측을 사용 하는 방법을 알아봅니다. 이 예제에서는 로지스틱 회귀 및 의사 결정 트리 모델을 빌드하의 Microsoft R 알고리즘을 사용 합니다. 
  
  적용 대상: SQL Server 2016 또는 SQL Server 2017

+ [Python 및 SQL Server를 사용 하 여 예상 모델을 작성](https://microsoft.github.io/sql-ml-tutorials/python/rentalprediction/)

   Python을 사용 하 여 이후 요청에 대 한 계획 ski 임대 분석 응용 프로그램을 빌드하십시오. 이 예제에서는 새 Python 라이브러리를 사용 하 여 **revoscalepy**, 선형 회귀 모델을 만듭니다. 
   
   적용 대상: SQL Server 2017

### <a name="bkmk_solutions"></a>솔루션 템플릿

Microsoft 데이터 과학 팀은 일반적인 시나리오에 대 한 솔루션을 빠르게 시작 하는 데 사용할 수 있는 솔루션 템플릿을 제공 했습니다. 모든 코드 학습 하 고 SQL Server 저장 프로시저를 사용 하 여 점수 매기기에 대 한 모델을 배포 하는 방법에 대 한 지침과 함께 제공 됩니다.

+ [사기 검색](https://gallery.cortanaanalytics.com/Tutorial/Online-Fraud-Detection-Template-with-SQL-Server-R-Services-1)
+ [사용자 지정 이탈 예측](https://gallery.cortanaanalytics.com/Tutorial/Customer-Churn-Prediction-Template-with-SQL-Server-R-Services-1)
+ [예측 유지 관리](https://gallery.cortanaanalytics.com/Tutorial/Predictive-Maintenance-Template-with-SQL-Server-R-Services-1)
+ [예측의 병원 지속](https://gallery.cortanaintelligence.com/Solution/Predicting-Length-of-Stay-in-Hospitals-1)

자세한 내용은 [SQL Server 2016 R Services를 사용하는 Machine Learning 템플릿](https://blogs.technet.microsoft.com/machinelearning/2016/03/23/machine-learning-templates-with-sql-server-2016-r-services/)을 참조하세요.

## <a name="more-resources-and-reading"></a>더 많은 리소스 및 읽기

+ [왜 빌드 않은 म?](https://blogs.msdn.microsoft.com/sqlserverstorageengine/2017/01/10/sql-server-r-services-why-did-we-build-it/)

    R Services와 관련된 실제 이야기를 알고 싶으세요? 개발 및 출처와 SQL Server R Services의 목표에 설명 하는 오후 팀에서이 문서를 읽습니다.

+ [자습서 및 Microsoft R에 대 한 예제 데이터](https://docs.microsoft.com/r-server/r/tutorial-introduction)

    Microsoft R 및, RevoScaleR 패키지는이 컬렉션의 빠른 자습서에서 제공 하는 기능에 대해 알아봅니다. RevoScaleR 데이터 원본 및 원격 계산 컨텍스트를 사용 하 여 R 코드를 한 번 작성 하 고 어디에서 든 지 배포 하는 방법에 알아봅니다.

+ [MicrosoftML 시작](https://docs.microsoft.com/r-server/r/concept-what-is-the-microsoftml-package)

  고급 모델링 및 확장 가능한 데이터 변환, 여러 계산 컨텍스트를 위한 최적화 된 MicrosoftML 패키지의 새 알고리즘을 사용 하는 방법을 알아봅니다.

## <a name="bkmk_Prerequisites"></a>필수 구성 요소

이 자습서를 실행 하려면 다운로드 하 고 여기에 설명 된 대로 SQL Server 기계 학습 구성 요소를 설치 해야 합니다.

+ [SQL Server R Services 설치](../r/set-up-sql-server-r-services-in-database.md)
+ [SQL Server Python 서비스 설정](../python/setup-python-machine-learning-services.md)

SQL Server 2017 년 R, Python, 또는 둘 다 설치할 수 있습니다. 그렇지 않으면 전체 설치 과정, 아키텍처 및 요구 사항이 동일합니다.

SQL Server 설치 프로그램을 실행 한 후 이러한 중요 한 단계를 잊지 마십시오.

1. 외부 스크립트 실행 기능을 사용 하 여 활성화 `sp_configure 'external scripts enabled', 1`합니다. 지침에 따라를 다시 구성 하 고 SQL Server 다시 시작 합니다.
2. 실행 패드 서비스 실행 되 고 SQL Server 인스턴스에 연결할 수 있는지 작업자 계정 것 사용 하 여 확인 합니다.
3. SQL 로그인 및 Python 또는 R 스크립트를 실행 하는 Windows 사용자 계정에 연관 된 사용 권한을 검토 합니다. 모든 Python 또는 R 스크립트를 실행 하 고 인스턴스에 연결할 권한이 필요 합니다. 샘플을 따라 데이터를 읽고 쓰는 하 고 데이터베이스 개체를 만드는 권한을 할 수도 있습니다.

자세한 내용은 몇 가지 일반적인 설치 및 구성 문제에 대 한이 문서를 참조 하세요.: [컴퓨터 학습 서비스 문제 해결](../machine-learning-troubleshooting-faq.md)

> [!NOTE]
> 다른 오픈 소스 R, Python 도구를 사용 하 여이 자습서를 실행할 수 없습니다. 개발 환경의 SQL Server 컴퓨터와 기계 학습 Python 또는 R 하는 라이브러리, Microsoft에서 제공한 통합 SQL 서버 및 원격 계산 컨텍스트 사용을 지 원하는 있어야 합니다.
