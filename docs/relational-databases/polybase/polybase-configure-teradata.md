---
title: Teradata의 외부 데이터에 액세스하도록 PolyBase 구성 | Microsoft Docs
ms.custom: ''
ms.date: 09/24/2018
ms.prod: sql
ms.reviewer: ''
ms.technology: polybase
ms.topic: conceptual
author: Abiola
ms.author: aboke
manager: craigg
monikerRange: '>= sql-server-ver15 || = sqlallproducts-allversions'
ms.openlocfilehash: 7abd9873b3aeefb5644ade0497fe89c47d7cd343
ms.sourcegitcommit: 41979c9d511b3eeb45134d30ccb0dbc6bba70f1a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2018
ms.locfileid: "50757958"
---
# <a name="configure-polybase-to-access-external-data-in-teradata"></a>Teradata의 외부 데이터에 액세스하도록 PolyBase 구성

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

이 문서에서는 SQL Server 인스턴스에서 PolyBase를 사용하여 Teradata에서 외부 데이터를 쿼리하는 방법을 설명합니다.

## <a name="prerequisites"></a>사전 요구 사항

PolyBase를 설치하지 않은 경우 [PolyBase 설치](polybase-installation.md)를 참조하세요. 설치 문서에서는 필수 구성 요소를 설명합니다.

Teradata에서 PolyBase를 사용하려면 VC++ 재배포 가능 패키지가 필요합니다.
 
## <a name="configure-an-external-table"></a>외부 테이블 구성

Teradata 데이터 원본의 데이터를 쿼리하려면 외부 데이터를 참조하는 외부 테이블을 만들어야 합니다. 이 섹션에서는 이러한 외부 테이블을 만들기 위한 샘플 코드를 제공합니다. 

이 섹션에서 이러한 개체를 만듭니다.

- CREATE DATABASE SCOPED CREDENTIAL(Transact-SQL)
- CREATE EXTERNAL DATA SOURCE(Transact-SQL) 
- CREATE EXTERNAL TABLE(Transact-SQL) 
- CREATE STATISTICS(Transact-SQL)

1. 마스터 키가 없는 경우 데이터베이스에 마스터 키를 만듭니다. 마스터 키는 자격 증명 비밀을 암호화하는 데 필요합니다.

     ```sql
      CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'password';  
     ```
    **인수**

    PASSWORD ='password'

    데이터베이스의 마스터 키를 암호화하는 데 사용되는 암호인가요? 암호는 SQL Server 인스턴스를 호스팅하는 컴퓨터의 Windows 암호 정책 요구 사항을 충족해야 합니다.

1. 데이터베이스 범위 자격 증명을 만듭니다.
 
     ```sql
     /*  specify credentials to external data source
      *  IDENTITY: user name for external source.  
     *  SECRET: password for external source.
     */
     CREATE DATABASE SCOPED CREDENTIAL credential_name
     WITH IDENTITY = 'username', Secret = 'password'
     ```

1. [CREATE EXTERNAL DATA SOURCE](../../t-sql/statements/create-external-data-source-transact-sql.md)를 사용하여 외부 데이터 원본을 만듭니다.

     ```sql
    /*  LOCATION: Location string should be of format '<vendor>://<server>[:<port>]'.
    *  PUSHDOWN: specify whether computation should be pushed down to the source. ON by default.
    * CONNECTION_OPTIONS: Specify driver location
    *  CREDENTIAL: the database scoped credential, created above.
    */  
    CREATE EXTERNAL DATA SOURCE external_data_source_name
    WITH ( 
    LOCATION = teradata://<server address>[:<port>],
   -- PUSHDOWN = ON | OFF,
    CREDENTIAL =credential_name
    );

     ```

1.  [CREATE EXTERNAL TABLE](../../t-sql/statements/create-external-table-transact-sql.md)을 사용하여 외부 Teradata 시스템에 저장된 데이터를 나타내는 외부 테이블을 만듭니다.
 
     ```sql
     /*  LOCATION: Teradata table/view in '<database_name>.<object_name>' format
      *  DATA_SOURCE: the external data source, created above.
      */
     CREATE EXTERNAL TABLE customer(
      L_ORDERKEY INT NOT NULL,
      L_PARTKEY INT NOT NULL,
     L_SUPPKEY INT NOT NULL,
     L_LINENUMBER INT NOT NULL,
     L_QUANTITY DECIMAL(15,2) NOT NULL,
     L_EXTENDEDPRICE DECIMAL(15,2) NOT NULL,
     L_DISCOUNT DECIMAL(15,2) NOT NULL,
     L_TAX DECIMAL(15,2) NOT NULL,
     L_RETURNFLAG CHAR NOT NULL,
     L_LINESTATUS CHAR NOT NULL,
     L_SHIPDATE DATE NOT NULL,
     L_COMMITDATE DATE NOT NULL,
     L_RECEIPTDATE DATE NOT NULL,
     L_SHIPINSTRUCT CHAR(25) NOT NULL,
     L_SHIPMODE CHAR(10) NOT NULL,
     L_COMMENT VARCHAR(44) NOT NULL
     )
     WITH (
     LOCATION='customer',
     DATA_SOURCE= external_data_source_name
     );
     ```

1. *선택 사항:* 외부 테이블에 대한 통계를 만듭니다.

    최적의 쿼리 성능을 위해서는 특히 조인, 필터 및 집계에 사용되는 외부 테이블 열에 대해 통계를 만듭니다.

     ```sql
      CREATE STATISTICS statistics_name ON customer (C_CUSTKEY) WITH FULLSCAN; 
     ```

## <a name="next-steps"></a>다음 단계

PolyBase에 대한 자세한 내용은 [SQL Server PolyBase 개요](polybase-guide.md)를 참조하세요.
