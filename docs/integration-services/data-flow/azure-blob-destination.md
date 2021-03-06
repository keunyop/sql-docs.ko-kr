---
title: Azure Blob 대상 | Microsoft Docs
ms.custom: ''
ms.date: 07/25/2016
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql13.dts.designer.afpblobdest.f1
- sql14.dts.designer.afpblobdest.f1
ms.assetid: 820a1e7a-7182-4c7b-ab56-5b4097a7e042
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: 8bc17975628068266c31bde014e6645dd6c61c7c
ms.sourcegitcommit: 7ccb8f28eafd79a1bddd523f71fe8b61c7634349
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2019
ms.locfileid: "58279257"
---
# <a name="azure-blob-destination"></a>Azure Blob 대상
 SSIS 패키지는 **Azure Blob 대상** 구성 요소를 통해 Azure Blob에 데이터를 쓸 수 있습니다. 지원되는 파일 형식은 다음과 같습니다. CSV와 AVRO. 
   
 **Azure Blob 대상** 을 데이터 흐름 디자이너에 끌어서 놓은 다음 두 번 클릭하여 편집기를 표시합니다.  
  
 **Azure Blob 대상**은 [Azure용 SSIS(SQL Server Integration Services) 기능 팩](../../integration-services/azure-feature-pack-for-integration-services-ssis.md)의 구성 요소입니다.  
  
1.  **Azure 스토리지 연결 관리자** 필드에서는 기존 Azure 스토리지 연결 관리자를 지정하거나 Azure 스토리지 계정을 참조하는 스토리지 연결 관리자를 새로 만듭니다.  
  
2.  **Blob 컨테이너 이름** 필드에서는 원본 파일을 포함하는 Blob 컨테이너의 이름을 지정합니다.  
  
3.  **Blob 이름** 필드에서는 Blob의 경로를 지정합니다.  
  
4.  **Blob 파일 형식** 필드에서는 사용할 Blob 형식을 지정합니다.  
  
5.  파일 형식이 CSV이면 **열 구분 기호 문자** 값을 지정해야 합니다. 파일의 첫 행에 열 이름을 포함하려는 경우에는 **첫 번째 데이터 행의 열 이름** 도 선택합니다.  
  
6.  연결 정보를 지정한 다음 **열** 페이지로 전환하여 SSI 데이터 흐름에 대해 원본 열을 대상 열에 매핑합니다.  
  
  
