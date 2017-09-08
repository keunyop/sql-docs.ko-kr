---
title: "Azure Blob 저장소 (SQL Server 가져오기 및 내보내기 마법사)에 연결 | Microsoft Docs"
ms.custom: 
ms.date: 02/17/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2e482b8-5f90-48c5-93fb-b412ed52659f
caps.latest.revision: 8
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 36b992b5141799d4e168b2e990643e6a515a8d69
ms.contentlocale: ko-kr
ms.lasthandoff: 08/03/2017

---
# <a name="connect-to-azure-blob-storage-sql-server-import-and-export-wizard"></a>Azure Blob 저장소 (SQL Server 가져오기 및 내보내기 마법사)에 연결
이 항목에 연결 하는 방법을 보여 줍니다.는 **Azure Blob 저장소** 에서 데이터 소스는 **데이터 원본을 선택** 또는 **대상 선택** SQL Server 가져오기 및 내보내기 마법사의 페이지입니다.

>   [!NOTE]
> Azure Blob 원본 또는 대상을 사용 하려면 SQL Server Integration Services에 대 한 Azure 기능 팩을 설치 해야 합니다.
> - 기능 팩을 다운로드 하려면 참조 [Microsoft SQL Server 2016 Integration Services 기능 팩 azure](https://www.microsoft.com/download/details.aspx?id=49492)합니다.
>
> - 자세한 내용은 [Integration Services용 Azure 기능 팩&#40;SSIS&#41;](../../integration-services/azure-feature-pack-for-integration-services-ssis.md)을 참조하세요.

다음 스크린 샷은 Azure Blob 저장소에 연결 하기 위한 구성 옵션을 보여 줍니다.

![Azure Blob Storage 연결](../../integration-services/import-export-data/media/azure-blob-storage-connection.png)

## <a name="options-to-specify"></a>지정 하는 옵션

> [!NOTE]
> 이 데이터 공급자에 대 한 연결 옵션은 Azure Blob 저장소 소스 또는 대상 인지는 동일 합니다. 즉, 표시 되는 옵션은 둘 다에 동일한는 **데이터 원본을 선택** 및 **대상 선택** 마법사의 페이지입니다.

 **Azure 계정 사용**  
 온라인 계정을 사용할지 여부를 지정합니다.
  
 **Storage 계정 이름**  
 Azure 저장소 계정 이름을 입력 합니다.  
  
**계정 키**  
Azure 저장소 계정에 대 한 키를 입력 합니다.  
  
 **HTTPS 사용**  
 저장소 계정에 연결할 때 사용할 프로토콜(HTTP 또는 HTTPS)을 지정합니다.  
  
 **로컬 개발자 계정 사용**  
 로컬 컴퓨터의 저장소 에뮬레이터를 사용할지 여부를 지정합니다.  
  
 **Blob 컨테이너 이름**  
 지정된 저장소 계정에서 사용할 수 있는 저장소 컨테이너 목록에서 컨테이너를 선택합니다.  
  
 **Blob 파일 형식**  
 텍스트 또는 Avro 파일 형식을 선택합니다.  
  
 **열 구분 기호 문자**  
 텍스트 형식을 선택한 경우 열 구분 기호 문자를 입력 합니다.  
  
 **첫 행은 열 이름으로**  
 첫 번째 데이터 행에 열 이름을 포함할지 여부를 지정합니다.  

## <a name="see-also"></a>참고 항목
[데이터 원본 선택](../../integration-services/import-export-data/choose-a-data-source-sql-server-import-and-export-wizard.md)  
[대상 선택](../../integration-services/import-export-data/choose-a-destination-sql-server-import-and-export-wizard.md)

