---
title: 도메인 규칙 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dm.rules.f1
- sql12.dqs.dm.testdomainrule.f1
ms.assetid: 339fa10d-e22c-4468-b366-080c33f1a23f
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 750773c728b2cbe026aac404f90a13928802a4bc
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56022954"
---
# <a name="create-a-domain-rule"></a>도메인 규칙 만들기
  이 항목에서는 DQS( [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] )에서 도메인 규칙을 만드는 방법에 대해 설명합니다. 도메인 규칙은 도메인 값의 유효성 검사, 수정 및 표준화를 수행하는 데 사용되는 조건입니다. 도메인 값이 정확하고 비즈니스 요구 사항에 맞는 것으로 간주되려면 도메인 규칙이 도메인 전체에서 유효해야 합니다. 도메인 규칙은 도메인 값의 유효성을 검사하는 데 사용되는 유효성 검사 규칙을 포함할 수 있지만 데이터 품질 프로젝트의 데이터를 수정하는 데 사용되지는 않습니다. 규칙은 또한 유효한 데이터에 대해 적용되고 데이터 수정에 사용되는 표준화 규칙을 포함합니다.  
  
##  <a name="BeforeYouBegin"></a> 시작하기 전에  
  
###  <a name="Prerequisites"></a> 필수 구성 요소  
 도메인 규칙을 만들려면 도메인 관리 작업에 기술 자료와 도메인이 열려 있어야 합니다.  
  
###  <a name="Security"></a> 보안  
  
####  <a name="Permissions"></a> Permissions  
 도메인 규칙을 만들려면 DQS_MAIN 데이터베이스에 대한 dqs_kb_editor 또는 dqs_administrator 역할이 있어야 합니다.  
  
##  <a name="Build"></a> 도메인 규칙 작성  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)] [Data Quality Client 응용 프로그램을 실행합니다](../../2014/data-quality-services/run-the-data-quality-client-application.md).  
  
2.  [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] 홈 화면에서 기술 자료를 열거나 만듭니다. **도메인 관리** 를 작업으로 선택한 다음 **열기** 또는 **만들기**를 클릭합니다. 자세한 내용은 [기술 자료 만들기](../../2014/data-quality-services/create-a-knowledge-base.md) 또는 [기술 자료 열기](../../2014/data-quality-services/open-a-knowledge-base.md)를 참조하세요.  
  
    > [!NOTE]  
    >  도메인 관리는 별도의 도메인 관리 작업을 위한 5개 탭이 포함된 Data Quality Services 클라이언트의 페이지에서 수행됩니다. 도메인 관리는 마법사 기반 프로세스가 아닙니다. 모든 관리 작업은 별도로 수행할 수 있습니다.  
  
3.  **도메인 관리** 페이지의 **도메인 목록** 에서 도메인 규칙을 만들 도메인을 선택하거나 새 도메인을 만듭니다. 새 도메인을 만들어야 하는 경우 [도메인 만들기](../../2014/data-quality-services/create-a-domain.md)를 참조하세요.  
  
4.  **도메인 규칙** 탭을 클릭합니다.  
  
5.  **새 도메인 규칙 추가**를 클릭한 다음 기술 자료에서 고유한 이름과 규칙에 대한 설명을 입력합니다.  
  
6.  **활성** 을 선택하여 해당 규칙이 실행되도록 지정하거나(기본값) 선택 취소하여 규칙이 실행되지 않도록 합니다.  
  
7.  **규칙 작성** 창의 규칙 절 상자에 있는 드롭다운 목록에서 조건을 선택합니다.  
  
8.  조건에 값이 필요한 경우 해당 입력란에 값을 입력합니다.  
  
9. 다른 절이 필요한 경우 **선택한 절에 새 조건 추가** 아이콘을 클릭합니다.  
  
10. **AND** 또는 **OR** 을 연산자로 선택합니다.  
  
11. 드롭다운 목록에서 조건을 선택한 다음 필요한 경우 피연산자의 값을 입력합니다.  
  
12. 목록에서 절이 표시되는 순서를 변경하려면 특정 절을 선택한 다음 위쪽 또는 아래쪽 화살표를 클릭합니다. 이렇게 하면 실행 순서가 변경되어 결과에 영향을 줄 수 있습니다.  
  
13. 필요에 따라 절을 더 추가합니다. 필요한 경우 절을 선택한 다음 **선택한 절 삭제**를 클릭하여 절을 삭제합니다.  
  
14. 필요에 따라 위 단계를 반복하여 새 규칙을 추가합니다.  
  
15. 유효성 검사 규칙이 값에 미치는 영향을 보려면(구현된 경우) **도메인 규칙이 도메인 값에 미치는 영향을 분석합니다** 아이콘을 클릭합니다.  
  
16. 다음 테스트 절차를 진행합니다.  
  
##  <a name="Test"></a> 도메인 규칙 테스트  
  
1.  규칙을 하나 선택한 상태에서 **테스트 데이터에서 선택한 도메인 규칙 실행** 아이콘을 클릭합니다.  
  
2.  도메인 규칙 테스트 대화 상자에서 **도메인 규칙의 새 테스트 용어 추가** 아이콘을 클릭합니다. 테스트할 값을 입력합니다. 필요에 따라 다른 값을 입력합니다. 필요한 경우 값을 선택하고 **선택한 테스트 용어 제거** 아이콘을 클릭합니다.  
  
3.  **모든 용어에 대해 도메인 규칙 테스트** 아이콘을 클릭합니다.  
  
4.  각 용어의 유효성을 검사합니다. 확인 표시는 "올바름"을, 십자 표시는 "오류"를, 삼각형은 "잘못됨"을 의미합니다.  
  
5.  테스트 대화 상자에서 작업이 완료되면 **닫기** 를 클릭합니다.  
  
6.  필요에 따라 다른 규칙에 대해 위의 단계를 반복합니다.  
  
7.  다음 적용 절차를 진행합니다.  
  
##  <a name="Apply"></a> 도메인 규칙 적용  
  
1.  도메인 값에 규칙을 적용하려면 **모든 규칙 적용** 을 클릭합니다. **모든 규칙 적용**을 클릭하면 이 규칙의 영향을 받는 특정 상태의 값 개수를 나타내는 팝업이 표시됩니다. 그래도 규칙을 적용하려는 경우 **예** 를 클릭하고, 그렇지 않을 경우 **아니요** 를 클릭합니다. **예**를 클릭한 경우 **확인** 을 클릭하여 결과 팝업을 닫습니다.  
  
    > [!NOTE]  
    >  규칙을 만들거나 변경할 때는 변경 내용을 저장하지 않아도 됩니다. 그러나 규칙을 적용해야 변경 내용이 적용됩니다.  
  
2.  **모든 변경 내용 취소** 를 클릭하면 도메인 규칙에 대한 모든 변경 내용이 제거되고 이전에 적용된 규칙을 되돌리므로 규칙의 마지막 적용 이후에 변경된 내용이 더 이상 적용되지 않습니다. 각 도메인 값의 유효성은 취소된 변경 내용이 아니라 이전에 적용된 규칙에 따라 업데이트됩니다.  
  
3.  **마침** 을 클릭하여 [도메인 관리 작업 종료](../../2014/data-quality-services/end-the-domain-management-activity.md)에 설명된 대로 도메인 관리 작업을 완료합니다.  
  
##  <a name="FollowUp"></a> 후속 작업: 도메인 규칙을 만든 후  
 도메인 규칙을 만든 후 도메인에 대해 다른 도메인 관리 태스크를 수행하거나, 기술 자료 검색을 수행하여 도메인에 정보를 추가하거나, 도메인에 일치 정책을 추가할 수 있습니다. 자세한 내용은 [기술 자료 검색 수행](../../2014/data-quality-services/perform-knowledge-discovery.md), [도메인 관리](../../2014/data-quality-services/managing-a-domain.md) 또는 [일치 정책 만들기](../../2014/data-quality-services/create-a-matching-policy.md)를 참조하세요.  
  
##  <a name="Conditions"></a> 도메인 규칙 조건  
 다음 표에서는 도메인 규칙에 적용될 수 있는 조건을 설명하고 조건을 적용하는 방법을 설명하는 예를 제공합니다.  
  
 도메인 규칙을 적용하고 도메인 값이 규칙에 실패하면 값이 잘못됨으로 지정됩니다. 잘못됨으로 지정된 값은 해당 값을 잘못된 것으로 판정한 규칙이 삭제되거나, 비활성화되거나 해당 값이 더 이상 규칙에 실패하지 않도록 규칙이 변경된 경우 올바름으로 변경됩니다. 도메인 관리 작업의 도메인 값 탭에서 수동으로 값을 잘못됨으로 지정한 경우 값이 실패한 규칙이 삭제되거나 비활성화되거나 변경되면 수동 지정에 따라 값은 계속 잘못됨으로 지정됩니다.  
  
 선언적 조건이 있는 도메인 규칙은 조건 값의 동의어와 값 자체에 규칙 논리를 적용합니다. 선언적 조건은 값이 다음 값과 같음, 값이 다음 값과 같지 않음, 값이 다음에 속함 또는 값이 다음에 포함되지 않음입니다. 예를 들어 다음과 같은 도메인 규칙이 있다고 가정합니다. "'City' 값은 'Los angeles'"입니다. 'Los Angeles'와 'LA'가 동의어인 경우 둘 다 유효합니다. 반면 규칙에 "구/군/시에 대해 값이 다음으로 종료 's'"와 같은 선언적 조건이 포함되지 않은 경우 "Los Angeles"는 유효하지만 동의어 "LA"는 오류가 됩니다.  
  
 도메인 규칙을 만들 때 대체 방법 중 하나를 선택할 수 있습니다. 예를 들어 값이 A, B 또는 C 문자로 시작하는지 확인하려면 복잡한 조건이 하나 있는 단순한 규칙(예: 파이프 문자가 있는 정규식)을 만들거나 단순한 조건이 여러 개 포함된 복잡한 규칙을 만들면 됩니다. 첫 번째 규칙의 예는 "값이 다음을 포함 정규식 (^A|^B|^C)"입니다. 두 번째 규칙의 예는 "'값이 다음으로 시작 A' OR '값이 다음으로 시작 B' OR '값이 다음으로 시작 C'"입니다.  
  
|조건|Description|예제|  
|---------------|-----------------|-------------|  
|길이가 다음 값과 같음|피연산자에 지정된 문자 수로 구성된 값만 유효합니다.|피연산자 예: 3<br /><br /> 유효한 값: BB1<br /><br /> 유효하지 않은 값: AA|  
|길이가 다음 값보다 크거나 같음|피연산자에 지정된 문자 수 또는 그보다 큰 문자 수로 구성된 값만 유효합니다.|피연산자 예: 3<br /><br /> 유효한 값: BB1, BBAA<br /><br /> 유효하지 않은 값: AA|  
|길이가 다음 값보다 작거나 같음|피연산자에 지정된 문자 수 또는 그보다 작은 문자 수로 구성된 값만 유효합니다.|피연산자 예: 3<br /><br /> 유효한 값: BB1, AA<br /><br /> 유효하지 않은 값: BBAA|  
|값이 다음 값과 같음|피연산자와 동일한 값만 유효합니다.|피연산자 예: BB1<br /><br /> 유효한 값: BB1<br /><br /> 유효하지 않은 값: BB, BB1#|  
|값이 다음 값과 같지 않음|피연산자와 동일하지 않은 값만 유효합니다.|피연산자 예: BB1<br /><br /> 유효한 값: BB, BB1#<br /><br /> 유효하지 않은 값: BB1|  
|값이 다음을 포함|모든 문자가 순서에 관계없이 피연산자 내에 포함된 값만 유효합니다.|피연산자 예: A1<br /><br /> 유효한 값: A1, AA1<br /><br /> 유효하지 않은 값: 1A, AA|  
|값이 다음을 포함하지 않음|피연산자 내에 포함되지 않은 값만 유효합니다.|피연산자 예: A1<br /><br /> 유효한 값: 1A, AA<br /><br /> 유효하지 않은 값: A1, AA1|  
|값이 다음으로 시작|피연산자의 문자로 시작하는 값만 유효합니다.|피연산자 예: AA<br /><br /> 유효한 값: AA1<br /><br /> 유효하지 않은 값: 1AAB|  
|값이 다음으로 종료|피연산자의 문자로 끝나는 값만 유효합니다.|피연산자 예: AA<br /><br /> 유효한 값: 1AA<br /><br /> 유효하지 않은 값: 1AAB|  
|값이 숫자임|SQL Server 숫자 데이터 형식이 있는 값만 유효합니다. 여기에는 int, decimal, float 등이 포함됩니다.|피연산자 예: 해당 사항 없음<br /><br /> 유효한 값: 1, 25, 345.1234<br /><br /> 유효하지 않은 값: 2b, bcdef|  
|값이 날짜/시간임|SQL Server date/time 데이터 형식이 있는 값만 유효합니다. 여기에는 datetime, time, date 등이 포함됩니다.|피연산자 예: 해당 사항 없음<br /><br /> 유효한 값: 1916-06-04; 1916-06-04 18:24:24; March 21, 2001; 5/18/2011; 18:24:24<br /><br /> 유효하지 않은 값: March 213, 2006|  
|값이 다음에 속함|피연산자의 집합에 있는 값만 유효합니다.<br /><br /> 집합에 값을 입력하려면 피연산자 입력란을 클릭하고 첫 번째 값을 입력한 후 Enter 키를 누르고 두 번째 값을 입력하는 식으로 집합에 입력하고자 하는 만큼의 값에 대해 이 작업을 반복한 다음 다시 피연산자 입력란을 클릭합니다. DQS는 집합의 값 사이에 쉼표를 추가합니다. 캐리지 리턴 없이 쉼표로 구분된 단일 문자열을 입력하면(예: "A1, B1") DQS가 해당 문자열을 세트의 단일 값으로 간주하게 됩니다.|피연산자 예: [A1, B1]<br /><br /> 유효한 값: A1, B1<br /><br /> 유효하지 않은 값: AA, 11|  
|값이 다음에 포함되지 않음|피연산자의 집합에 없는 값만 유효합니다.|피연산자 예: [A1, B1]<br /><br /> 유효한 값: AA, 11<br /><br /> 유효하지 않은 값: A1, B1|  
|값이 패턴과 일치|피연산자의 문자, 숫자 또는 특수 문자 패턴과 일치하는 값만 유효합니다.<br /><br /> 모든 문자(A...Z)를 문자에 대한 패턴으로 사용할 수 있으며 대/소문자는 구분하지 않습니다. 모든 숫자(0...9)를 숫자에 대한 패턴으로 사용할 수 있습니다. 문자 또는 숫자를 제외하고 모든 특수 문자를 자체 패턴으로 사용할 수 있습니다. 대괄호([])는 선택적 일치를 정의합니다.|피연산자 예: AA:000 (패턴 *모든* 두 문자 뒤에 콜론 (:), 다시 이어집니다 *모든* 세 자리 숫자입니다.<br /><br /> 유효한 값: AB:012, df:257<br /><br /> 유효하지 않은 값: abc:123, FJ-369<br /><br /> DQS의 패턴 규칙과 예에 대한 자세한 내용은 [DQS 도메인 규칙의 패턴 일치](https://blogs.msdn.com/b/dqs/archive/2012/10/08/pattern-matching-in-dqs-domain-rules.aspx)를 참조하세요.|  
|값이 패턴과 일치하지 않음|피연산자의 문자, 숫자 또는 특수 문자 패턴과 일치하지 않는 값만 유효합니다.|피연산자 예: A1 (값의 패턴과 일치 해서는 *모든* 문자 하나 뒤 *모든* 숫자가 하나.)<br /><br /> 유효한 값: AB1, A, A:5<br /><br /> 유효하지 않은 값: B7, c9|  
|값이 패턴 포함|피연산자의 문자, 숫자 또는 특수 문자 패턴을 포함하는 값만 유효합니다.|피연산자 예: Aa-12 (값 패턴을 포함 *모든* 뒤에 하이픈 (-) 뒤에 2 자 *모든* 두 자리 숫자입니다.)<br /><br /> 유효한 값: AAA-01, ab-975<br /><br /> 유효하지 않은 값: A7, AA-6, C-45, aa;98|  
|값이 패턴 포함 안 함|피연산자의 문자 패턴을 포함하지 않는 값만 유효합니다.|피연산자 예: Ab-12 (값의 패턴을 포함 하지 않아야 *모든* 뒤에 하이픈 (-) 뒤에 2 자 *모든* 두 자리 숫자입니다.)<br /><br /> 유효한 값: A7, AA-6, C-45, aa;98<br /><br /> 유효하지 않은 값: AAA-01, ab-975|  
|값이 정규식과 일치합니다.|피연산자의 정규식과 같은 값만 유효한 것으로 간주됩니다.<br /><br /> 정규식에 "^" 앵커 또는 "$" 앵커를 포함하지 마세요. DQS가 정규식과 일치하는 값을 포함하는 절에 이러한 앵커를 자동으로 추가합니다. (또는 "^" 및 "$" 앵커를 포함하는 정규식을 괄호로 묶을 수 있습니다.) 정규식에 대한 자세한 내용은 [정규식 언어 요소](https://go.microsoft.com/fwlink/?LinkId=225561)를 참조하세요.|피연산자 예: [1-5]+(각 문자는 1에서 5 사이의 숫자가 한 번 이상 사용되는 숫자여야 함)<br /><br /> 유효한 값: 123, 12345, 14352<br /><br /> 유효하지 않은 값: 456, ABC|  
|값이 정규식과 일치하지 않습니다.|피연산자의 정규식과 일치하지 않는 값만 유효한 것으로 간주됩니다.|피연산자 예: [1-5]+(1에서 5 사이의 숫자로만 구성된 문자열이 아니어야 함)<br /><br /> 유효한 값: 456, ABC<br /><br /> 유효하지 않은 값: 123, 123456, 14352|  
  
  
