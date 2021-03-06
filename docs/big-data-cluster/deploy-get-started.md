---
title: 시작
titleSuffix: SQL Server big data clusters
description: 단계 및 SQL Server 2019 빅 데이터 클러스터 (미리 보기) 배포에 대 한 리소스에 알아봅니다.
author: rothja
ms.author: jroth
manager: craigg
ms.date: 03/18/2019
ms.topic: conceptual
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: 69b5d9b69536243d371cb45c1c46620f5194657d
ms.sourcegitcommit: 2de5446fbc57787f18a907dd5deb02a7831ec07d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58860434"
---
# <a name="get-started-with-sql-server-big-data-clusters"></a>SQL Server 빅 데이터 클러스터 시작

[!INCLUDE[tsql-appliesto-ssver15-xxxx-xxxx-xxx](../includes/tsql-appliesto-ssver15-xxxx-xxxx-xxx.md)]

이 문서에서는 배포 하는 방법의 개요는 [SQL Server 2019 빅 데이터 클러스터 (미리 보기)](big-data-cluster-overview.md)합니다. 개념을이 섹션의 다른 배포 기사를 이해 하기 위한 프레임 워크를 제공 하는 것이 것입니다. 특정 배포 단계는 클라이언트와 서버 플랫폼 선택에 따라 다릅니다.

## <a id="tools"></a> 클라이언트 도구

빅 데이터 클러스터에는 특정 클라이언트 도구 집합이 필요합니다. Kubernetes에 빅 데이터 클러스터를 배포 하기 전에 다음 도구를 설치 해야 합니다.

| 도구 | Description |
|---|---|
| **mssqlctl** | 배포 하 고 빅 데이터 클러스터를 관리 합니다. |
| **Kubectl** | 만들고 기본 Kubernetes 클러스터를 관리 합니다. |
| **Azure Data Studio** | 빅 데이터 클러스터를 사용 하기 위한 그래픽 인터페이스입니다. |
| **SQL Server 2019 extension** | 빅 데이터 클러스터 기능을 사용할 수 있는 azure Data Studio 확장입니다. |

다른 도구는 다양 한 시나리오에 필요 합니다. 각 문서에는 특정 작업을 수행 하기 위한 필수 구성 요소 도구 설명 해야 합니다. 도구 및 설치 링크의 전체 목록을 참조 하세요 [SQL Server 설치 2019 빅 데이터 도구도](deploy-big-data-tools.md)합니다.

## <a name="kubernetes"></a>Kubernetes

일련의 상호 관련 된 컨테이너에서 관리 되는 빅 데이터 클러스터를 구축할 [Kubernetes](https://kubernetes.io/docs/home)합니다. 다양 한 방법에서에서 Kubernetes를 호스트할 수 있습니다. 기존 Kubernetes 환경에 이미 있는 경우에 빅 데이터 클러스터에 대 한 관련된 요구 사항을 검토 해야 합니다.

- **AKS (azure Kubernetes Service)**: AKS를 사용 하면 Azure에서 관리 되는 Kubernetes 클러스터를 배포할 수 있습니다. 만 관리 하 고 에이전트 노드를 유지 관리 합니다. AKS를 통해 클러스터에 대 한 고유한 하드웨어를 프로 비전 할 필요가 없습니다. 빅 데이터 클러스터를 사용 하기 쉬운 이기도 [배포 스크립트](quickstart-big-data-cluster-deploy.md) AKS 클러스터를 만들고 1 단계에서 빅 데이터 클러스터를 배포 합니다. AKS를 사용 하 여 빅 데이터 클러스터에 대 한 자세한 내용은 참조 하세요. [SQL Server 2019 빅 데이터 클러스터 (미리 보기) 배포에 대 한 Azure Kubernetes Service 구성](deploy-on-aks.md)합니다.

- **여러 컴퓨터**: Kubernetes 물리적 서버 또는 가상 컴퓨터 일 수 있는 여러 Linux 컴퓨터에 배포할 수도 있습니다. 합니다 [kubeadm](https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/) 도구는 Kubernetes 클러스터를 만드는 데 사용할 수 있습니다. 이 메서드는 빅 데이터 클러스터에 사용 하려는 기존 인프라를 이미 있는 경우에 작동 합니다. 사용에 대 한 자세한 내용은 **kubeadm** 빅 데이터 클러스터를 사용 하 여 배포 참조 [SQL Server 2019 빅 데이터 클러스터 (미리 보기) 배포에 대 한 여러 컴퓨터에서 Kubernetes 구성](deploy-with-kubeadm.md)합니다.

- **Minikube**: Minikube를 사용 하면 단일 서버에서 Kubernetes를 로컬로 실행할 수 있습니다. 빅 데이터 클러스터를 시도해 또는 테스트 또는 개발 시나리오에서 사용 해야 하는 경우는 좋은 옵션입니다. Minikube를 사용 하는 방법에 대 한 자세한 내용은 참조는 [Minikube 설명서](https://kubernetes.io/docs/setup/minikube/)합니다. Minikube를 사용 하 여 빅 데이터 클러스터에 대 한 특정 요구 사항을 참조 하세요 [minikube SQL Server 2019 빅 데이터 클러스터 배포에 대 한 구성](deploy-on-minikube.md)합니다.

## <a name="deployment-scripts"></a>배포 스크립트

배포 스크립트는 Kubernetes와 단일 단계에서 빅 데이터 클러스터를 배포 하는 데 도움이 됩니다. 또한 종종 필수 환경 변수에 대 한 기본값 제공합니다. Azure Kubernetes Service (AKS)에서 빅 데이터 클러스터에 대 한 배포 스크립트의 예제를 참조 하세요 [배포 스크립트 (AKS)를 사용 하 여 빅 데이터 클러스터를 SQL Server 2019 배포](quickstart-big-data-cluster-deploy.md)합니다.

빅 데이터 클러스터 환경 변수를 다르게 구성 하는 고유한 버전을 만들어 배포 스크립트를 사용자 지정할 수 있습니다.

## <a name="deploy-a-big-data-cluster"></a>빅 데이터 클러스터 배포

Kubernetes 및 빅 데이터 클러스터를 AKS 단일 스크립트를 사용 하 여 배포를 다음 예제를 참조 하세요.

- [배포 스크립트 (AKS)를 사용 하 여 SQL Server 2019 빅 데이터 클러스터를 배포 합니다.](quickstart-big-data-cluster-deploy.md)

AKS, kubeadm, 및 MiniKube를 사용 하 여 빅 데이터 클러스터를 배포 하는 것에 대 한 자세한 배포 지침은 다음 문서를 참조 합니다.

- [Kubernetes에서 SQL Server 빅 데이터 클러스터를 배포 하는 방법](deployment-guidance.md)

## <a name="next-steps"></a>다음 단계

빅 데이터 클러스터를 성공적으로 배포 하 고 나면 [클러스터에 연결](connect-to-big-data-cluster.md) 고려 [샘플 데이터를 로드](tutorial-load-sample-data.md) 여러 연습에 사용 합니다.