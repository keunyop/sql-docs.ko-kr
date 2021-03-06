---
title: '옵션 (텍스트 편집기: XML:Tabs 페이지) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XML.Tabs
ms.assetid: 13bf5f8c-aba3-4c05-b8bb-eb475797c9bd
author: craigg-msft
ms.author: craigg
manager: craigg
ms.openlocfilehash: 30842eec745c87848e4eb1c78c4806639da3ac0b
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48050153"
---
# <a name="options-text-editorxmltabs-page"></a>옵션(텍스트 편집기:XML:탭 페이지)
  이 대화 상자에서는 XML 문서를 편집하는 데 사용되는 XML 편집기의 탭 이동 동작을 변경할 수 있습니다. 이 설정을 표시하려면 **도구** 메뉴에서 **옵션** 을 클릭하고 **텍스트 편집기** 폴더와 **XML** 하위 폴더를 차례로 확장한 다음 **탭**을 클릭합니다.  
  
## <a name="setting-options-in-multiple-locations"></a>여러 위치에서 옵션 설정  
 XML 편집기에 대한 옵션은 **모든 언어** 대화 상자(일반)에서도 설정할 수 있습니다. **모든 언어** 대화 상자를 사용하여 DMX 또는 MDX 편집기 등의 다른 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] 편집기에 대해 다른 옵션을 설정하는 경우에는 이 대화 상자를 사용하여 XML 편집기 옵션을 다시 설정해야 합니다.  
  
## <a name="indenting"></a>들여쓰기  
 **없음**  
 이 옵션을 선택하면 Enter 키를 누를 때 생성되는 새 줄을 들여쓰지 않습니다. 커서는 새 줄의 첫 번째 열에 배치됩니다.  
  
 **블록**  
 이 옵션을 선택하면 Enter 키를 누를 때 생성되는 새 줄을 자동으로 앞 줄과 동일하게 들여씁니다.  
  
 **스마트**  
 이 옵션을 선택하면 Enter 키를 누를 때 생성되는 새 줄의 위치가 컨텍스트에 따라 지정됩니다. 예를 들어 여는 중괄호({) 뒤에 포함되는 줄은 자동으로 추가 탭 정지를 사용하여 들여씁니다. 닫는 중괄호(})의 위치는 해당 여는 중괄호에 맞게 다시 조정됩니다.  
  
## <a name="tabs"></a>탭  
 **탭 크기**  
 탭 정지 간의 거리를 공백 수로 설정합니다. 기본값은 공백 4개입니다.  
  
 **들여쓰기 크기**  
 자동 들여쓰기의 크기를 공백 수로 설정합니다. 기본값은 공백 4개입니다. 탭 문자나 공백 문자 또는 두 가지 문자 모두를 삽입하여 지정한 크기를 채웁니다.  
  
 **공백 삽입**  
 이 옵션을 선택하면 들여쓰기 작업에서 탭 문자 대신 공백 문자만 삽입합니다. 예를 들어 **들여쓰기 크기** 를 5로 설정하면 Tab 키를 누르거나 기본 **창에서 도구 모음의** 들여쓰기 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] 단추를 클릭할 때마다 5개의 공백 문자가 삽입됩니다.  
  
 **탭 유지**  
 이 옵션을 선택하면 들여쓰기 작업에서 가능한 한 많은 탭 문자를 삽입합니다. 각 탭 문자는 **탭 크기**에 지정된 공백 수를 채웁니다. **들여쓰기 크기** 가 **탭 크기**의 짝수 배수가 아니면 공백 문자가 추가되어 차이를 메웁니다.  
  
  
