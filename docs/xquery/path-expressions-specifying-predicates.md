---
title: "경로 식 단계에서 조건자 지정 | Microsoft Docs"
ms.custom: 
ms.date: 03/17/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
dev_langs:
- XML
helpviewer_keywords:
- axis step [XQuery]
- predicates [XQuery]
- qualifiers [XQuery]
- path expressions [XQuery]
ms.assetid: 2660ceca-b8b4-4a1f-98a0-719ad5f89f81
caps.latest.revision: 31
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: a5b417b2bfe5d995657ad86cf44b650b751f6a30
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="path-expressions---specifying-predicates"></a>경로 식에서 조건자 지정
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  항목에 설명 된 대로 [xquery에서 경로 식](../xquery/path-expressions-xquery.md), 경로 식의 축 단계에는 다음 구성 요소가 포함 됩니다.  
  
-   [축](../xquery/path-expressions-specifying-axis.md)합니다.  
  
-   노드 테스트. 자세한 내용은 참조 [경로 식 단계에서 노드 테스트 지정](../xquery/path-expressions-specifying-node-test.md)합니다.  
  
-   0개 이상의 조건자. 이 구성 요소는 선택 사항입니다.  
  
 선택적 조건자는 경로 식의 축 단계에서 세 번째 부분입니다.  
  
## <a name="predicates"></a>조건자  
 조건자는 지정된 테스트를 적용하여 노드 시퀀스를 필터링하는 데 사용됩니다. 조건자 식은 대괄호로 묶여 있으며 경로 식의 마지막 노드에 바인딩됩니다.  
  
 예를 들어의 SQL 매개 변수 값 (x)는 **xml** 데이터 형식이 선언 다음에 표시 된 대로:  
  
```  
declare @x xml  
set @x = '  
<People>  
  <Person>  
    <Name>John</Name>  
    <Age>24</Age>  
  </Person>  
  <Person>  
    <Name>Goofy</Name>  
    <Age>54</Age>  
  </Person>  
  <Person>  
    <Name>Daffy</Name>  
    <Age>30</Age>  
  </Person>  
</People>  
'  
```  
  
 이 경우 다음은 3개의 서로 다른 노드 수준에서 조건자 값 [1]을 사용하는 유효한 식입니다.  
  
```  
select @x.query('/People/Person/Name[1]')  
select @x.query('/People/Person[1]/Name')  
select @x.query('/People[1]/Person/Name')  
```  
  
 각 경우에 조건자는 적용되는 경로 식의 노드에 바인딩됩니다. 예를 들어 첫 번째 경로 식은 각 /People/Person 노드 내에서 첫 번째 <`Name`> 요소를 선택하고 제공된 XML 인스턴스에 대해 다음을 반환합니다.  
  
```  
<Name>John</Name><Name>Goofy</Name><Name>Daffy</Name>  
```  
  
 하지만 두 번째 경로 식은 첫 번째 People/Person 노드 아래에 있는 모든 <`Name`> 요소를 선택합니다. 따라서 다음을 반환합니다.  
  
```  
<Name>John</Name>  
```  
  
 괄호를 사용하여 조건자의 평가 순서를 바꿀 수도 있습니다. 예를 들어 다음 식에서는 괄호를 사용하여 (/People/Person/Name)의 경로를 조건자 [1]과 구분합니다.  
  
```  
select @x.query('(/People/Person/Name)[1]')  
```  
  
 이 예에서는 조건자가 적용되는 순서가 바뀝니다. 이러한 이유는 괄호로 묶인 경로가 먼저 평가되고(/People/Person/Name) 괄호로 묶인 경로와 일치하는 모든 노드가 포함된 집합에 조건자 [1] 연산자가 적용되기 때문입니다. 괄호를 사용하지 않으면 첫 번째 경로 식 예와 마찬가지로 [1]이 `child::Name` 노드 테스트에서와 같이 다르게 적용될 것입니다.  
  
### <a name="quantifiers-and-predicates"></a>한정자 및 조건자  
 한정자는 조건자의 중괄호 자체 내에서 한 번 이상 사용 및 추가될 수 있습니다. 예를 들어 이전 예를 사용할 경우 다음과 같이 복잡한 조건자 하위 식 내에서 하나 이상의 한정자를 사용할 수 있습니다.  
  
```  
select @x.query('/People/Person[contains(Name[1], "J") and xs:integer(Age[1]) < 40]/Name/text()')  
```  
  
 조건자 식의 결과는 부울 값으로 변환되며 조건자의 진리 값으로 참조됩니다. 조건자의 진리 값이 True인 시퀀스의 노드만 결과에 반환됩니다. 다른 모든 노드는 무시됩니다.  
  
 예를 들어 다음 경로 식에는 두 번째 단계에 조건자가 포함됩니다.  
  
```  
/child::root/child::Location[attribute::LocationID=10]  
```  
  
 이 조건자에 의해 지정된 조건은 모든 <`Location`> 요소 노드의 자식에 적용됩니다. 그 결과 LocationID 특성 값이 10인 작업 센터 위치만 반환됩니다.  
  
 이전 경로 식은 다음 SELECT 문에서 실행됩니다.  
  
```  
SELECT Instructions.query('  
declare namespace AWMI="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
 /child::AWMI:root/child::AWMI:Location[attribute::LocationID=10]  
')  
FROM Production.ProductModel  
WHERE ProductModelID=7  
```  
  
### <a name="computing-predicate-truth-values"></a>조건자 진리 값 계산  
 XQuery 사양에 따라 조건자 진리 값을 확인하기 위해 다음 규칙이 적용됩니다.  
  
1.  조건자 식의 값이 비어 있는 시퀀스인 경우 해당 조건자의 진리 값은 False입니다.  
  
     예를 들어  
  
    ```  
    SELECT Instructions.query('  
    declare namespace AWMI="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
     /child::AWMI:root/child::AWMI:Location[attribute::LotSize]  
    ')  
    FROM Production.ProductModel  
    WHERE ProductModelID=7  
    ```  
  
     이 쿼리의 경로 식은 LotSize 특성이 지정된 <`Location`> 요소 노드만 반환합니다. 조건자가 특정 <`Location`>에 대해 비어 있는 시퀀스를 반환하는 경우 작업 센터 위치는 결과에 반환되지 않습니다.  
  
2.  Xs: integer, xs: boolean 또는 노드 값만 될 수 조건자\*합니다. 노드에 대 한\*, 조건자는 모든 노드가 있으면 True이 고 빈 시퀀스에 대해 False로 계산 합니다. double 및 float 유형과 같은 다른 모든 숫자 유형은 정적 형식 지정 오류를 발생시킵니다. 식의 조건자 진리 값은 결과 정수가 컨텍스트 위치의 값과 동일한 경우에만 True입니다. 또한 정수 리터럴 값 및 **last ()** 함수를 1로 필터링 된 단계 식의 카디널리티를 줄입니다.  
  
     예를 들어 다음 쿼리는 <`Features`> 요소의 세 번째 자식 요소 노드를 검색합니다.  
  
    ```  
    SELECT CatalogDescription.query('  
    declare namespace PD="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
    declare namespace wm="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain";  
     /child::PD:ProductDescription/child::PD:Features/child::*[3]  
    ')  
    FROM Production.ProductModel  
    WHERE ProductModelID=19  
    ```  
  
     이전 쿼리에서 다음을 유의하세요.  
  
    -   식에서 세 번째 단계는 값이 3인 조건자 식을 지정합니다. 따라서 이 식의 조건자 진리 값은 컨텍스트 위치가 3인 노드에 대해서만 True입니다.  
  
    -   세 번째 단계는 또한 노드 테스트의 모든 노드를 나타내는 와일드카드 문자(*)를 지정합니다. 하지만 조건자는 노드를 필터링하고 세 번째 위치에 있는 노드만 반환합니다.  
  
    -   쿼리는 문서 루트의 <`ProductDescription`> 요소 자식에 대한 <`Features`> 요소 자식의 세 번째 자식 요소 노드를 반환합니다.  
  
3.  조건자 식의 값이 부울 유형의 간단한 유형 값인 경우 조건자 진리 값은 조건자 식의 값과 동일합니다.  
  
     에 대해 다음 쿼리는 지정 하는 예를 들어 한 **xml**XML 인스턴스인 고객 조사 XML 인스턴스를 보유 하는 유형 변수입니다. 쿼리는 자식이 있는 고객을 검색합니다. 이 쿼리에서 되는 \<HasChildren > 1\</HasChildren > 합니다.  
  
    ```  
    declare @x xml  
    set @x='  
    <Survey>  
      <Customer CustomerID="1" >  
      <Age>27</Age>  
      <Income>20000</Income>  
      <HasChildren>1</HasChildren>  
      </Customer>  
      <Customer CustomerID="2" >  
      <Age>27</Age>  
      <Income>20000</Income>  
      <HasChildren>0</HasChildren>  
      </Customer>  
    </Survey>  
    '  
    declare @y xml  
    set @y = @x.query('  
      for $c in /child::Survey/child::Customer[( child::HasChildren[1] cast as xs:boolean ? )]  
      return   
          <CustomerWithChildren>  
              { $c/attribute::CustomerID }  
          </CustomerWithChildren>  
    ')  
    select @y  
    ```  
  
     이전 쿼리에서 다음을 유의하세요.  
  
    -   식에는 **에 대 한** 루프는 두 단계로 및 두 번째 단계는 조건자를 지정 합니다. 이 조건자의 값은 부울 유형의 값입니다. 이 값이 True이면 조건자의 진리 값도 True입니다.  
  
    -   쿼리에서 반환 된 <`Customer`> 요소 자식을, 조건자 값이 True 이면의 \<설문 조사 > 문서 루트의 요소 자식을 합니다. 다음은 결과입니다.  
  
        ```  
        <CustomerWithChildren CustomerID="1"/>   
        ```  
  
4.  조건자 식의 값이 적어도 하나 이상의 노드가 포함된 시퀀스인 경우 조건자 진리 값은 True입니다.  
  
 다음 쿼리에서 XML 카탈로그 설명이의 자식 요소인 기능이 적어도 하나를 포함 하는 제품 모델에 대 한 ProductModelID를 검색 하는 예를 들어는 <`Features`> 요소와 연결 된 네임 스페이스에서는 **wm**접두사입니다.  
  
```  
SELECT ProductModelID  
FROM   Production.ProductModel  
WHERE CatalogDescription.exist('  
             declare namespace PD="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
             declare namespace wm="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain";  
             /child::PD:ProductDescription/child::PD:Features[wm:*]  
             ') = 1  
```  
  
 이전 쿼리에서 다음을 유의하세요.  
  
-   WHERE 절은 지정 된 [exist () 메서드 (XML 데이터 형식)](../t-sql/xml/exist-method-xml-data-type.md)합니다.  
  
-   경로 식 내에서 **exist ()** 메서드는 두 번째 단계에서 조건자를 지정 합니다. 조건자 식이 적어도 하나의 기능이 포함된 시퀀스를 반환하는 경우 이 조건자 식의 진리 값은 True입니다. 이 경우 때문에 **exist ()** True를 반환 하는 메서드, ProductModelID가 반환 됩니다.  
  
## <a name="static-typing-and-predicate-filters"></a>정적 형식 지정 및 조건자 필터  
 조건자는 또한 정적으로 유추된 식의 유형에 영향을 줄 수 있습니다. 정수 리터럴 값 및 **last ()** 함수는 최대 1로 필터링 된 단계 식의 카디널리티를 줄입니다.  
  
  