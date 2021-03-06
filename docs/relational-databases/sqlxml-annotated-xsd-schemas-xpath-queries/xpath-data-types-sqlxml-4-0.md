---
title: XPath 데이터 형식 (SQLXML 4.0) | Microsoft 문서
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapping XDR types to XPath types [SQLXML]
- data types [XPath]
- arithmetic operators
- mapping data types [SQLXML]
- relational operators [SQLXML]
- node-set [SQLXML]
- data types [SQLXML], XPath
- XPath operators [SQLXML]
- XDR data type [SQLXML]
- equality operators [SQLXML]
- XPath conversions [SQLXML]
- converting data types [SQLXML]
- Boolean operators
- XPath queries [SQLXML], data types
- XPath data types [SQLXML]
- operators [SQLXML]
ms.assetid: a90374bf-406f-4384-ba81-59478017db68
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 0c5cb588e96bcabad464339b7227ada3aef86221
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56039924"
---
# <a name="xpath-data-types-sqlxml-40"></a>XPath 데이터 형식(SQLXML 4.0)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], XPath 및 XSD(XML 스키마)의 데이터 형식은 각각 다릅니다. 예를 들어 XPath에는 정수나 날짜 데이터 형식이 없지만 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]와 XSD에는 이러한 데이터 형식이 많습니다. XSD는 시간 값에 나노초 정밀도를 사용하지만 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서는 최대 1/300초의 정밀도를 사용합니다. 따라서 한 데이터 형식을 다른 데이터 형식에 매핑할 수 없는 경우도 있습니다. 매핑에 대 한 자세한 내용은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] XSD 데이터 형식에 데이터 형식을 참조 하십시오. [데이터 형식 강제 변환 및 주석 sql:datatype &#40;SQLXML 4.0&#41;](../../relational-databases/sqlxml-annotated-xsd-schemas-using/data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md).  
  
 XPath는 세 가지 데이터 형식: **문자열**를 **번호**, 및 **부울**합니다. 합니다 **번호** 데이터 형식은 항상를 IEEE 754 배정밀도 부동 소수점입니다. 합니다 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **float(53)** 데이터 형식에 가장 가까운 XPath **번호**합니다. 그러나 **float(53)** IEEE 754 정확히 같지 않습니다. 예를 들어 NaN(Not-a-Number)과 무한대는 모두 사용되지 않습니다. 숫자가 아닌 문자열을 변환 하려고 **번호** 오류가 0으로 나누려고 하려고 합니다.  
  
## <a name="xpath-conversions"></a>XPath 변환  
 `OrderDetail[@UnitPrice > "10.0"]` 같은 XPath 쿼리를 사용할 경우 암시적/명시적 데이터 형식 변환으로 인해 쿼리의 의미가 미세하게 변경될 수 있습니다. 따라서 XPath 데이터 형식의 구현 방법을 올바르게 이해하고 있어야 합니다. XPath 언어 사양, XML 경로 언어 (XPath) 버전 1.0 W3C 권장 8 1999 년 10 월, 제안 된 W3C 웹 사이트에서 찾을 수 있습니다 http://www.w3.org/TR/1999/PR-xpath-19991008.html.  
  
 XPath 연산자는 다음의 네 범주로 나뉩니다.  
  
-   부울 연산자(and, or)  
  
-   관계형 연산자 (\<, >, \<=, > =)  
  
-   같음 연산자(=, !=)  
  
-   산술 연산자(+, -, *, div, mod)  
  
 연산자 범주마다 해당 피연산자를 변환하는 방법이 다릅니다. XPath 연산자는 필요한 경우 피연산자를 암시적으로 변환합니다. 산술 연산자는 피연산자를 변환 **수**를 숫자 값을 반환 합니다. 부울 연산자는 피연산자를 변환 **부울**, 부울 값을 반환 합니다. 관계형 연산자와 같음 연산자는 부울 값을 반환합니다. 그러나 다음 표에서 볼 수 있듯이 피연산자의 원래 데이터 형식에 따라 서로 다른 변환 규칙이 적용됩니다.  
  
|피연산자|관계형 연산자|같음 연산자|  
|-------------|-------------------------|-----------------------|  
|두 피연산자가 모두 노드 집합입니다.|TRUE 및 경우에 하나의 집합에 노드가 있고 두 번째에서 노드 집합 등 해당 비교 해당 **문자열** 값은 TRUE입니다.|같습니다.|  
|노드 집합을 다른 것을 **문자열**합니다.|노드 집합의 한 노드인 경우에 TRUE 되도록 변환할 때 **수**를 사용 하 여 비교를 **문자열** 변환할 **수** 가 TRUE.|노드 집합의 한 노드인 경우에 TRUE 되도록 변환할 때 **문자열**를 사용 하 여 비교를 **문자열** 가 TRUE.|  
|노드 집합을 다른 것을 **번호**합니다.|노드 집합의 한 노드인 경우에 TRUE 되도록 변환할 때 **수**를 사용 하 여 비교를 **수** 가 TRUE.|같습니다.|  
|노드 집합을 다른 것을 **부울**합니다.|노드 집합의 한 노드인 경우에 TRUE 되도록 변환할 때 **부울** 하 고 **번호**과 비교 합니다 **부울** 변환할**번호** 은 TRUE입니다.|노드 집합의 한 노드인 경우에 TRUE 되도록 변환할 때 **부울**를 사용 하 여 비교를 **부울** 가 TRUE.|  
|둘 모두 노드 집합이 아닙니다.|두 피연산자를 변환 **수** 를 비교 합니다.|두 피연산자를 모두 일반 형식으로 변환한 다음 비교합니다. 변환할 **부울** 중 하나에 해당 하는 경우 **부울**, **번호** 중 하나에 해당 하는 경우 **번호**고, 그렇지 않으면 변환할 **문자열**.|  
  
> [!NOTE]  
>  XPath 관계형 연산자는 항상 해당 피연산자를 변환 하기 때문에 **수**하십시오 **문자열** 비교 가능 하지 않습니다. 날짜 비교를 포함하기 위해 SQL Server 2000에서는 XPath 사양에 대한 다음과 같은 변형을 제공합니다. 관계형 연산자를 비교 하는 경우는 **문자열** 에 **문자열**, 노드 집합이 **문자열**, 또는 문자열 값 노드 집합을 문자열 값 노드 집합에는  **문자열** 비교 (하지는 **번호** 비교) 수행 됩니다.  
  
## <a name="node-set-conversions"></a>노드 집합 변환  
 노드 집합 변환이 항상 직관적이지는 않습니다. 노드 집합으로 변환 됩니다는 **문자열** 집합의 첫 번째 노드의 문자열 값을 수행 하 여 합니다. 노드 집합으로 변환할 **수** 으로 변환 **문자열**, 변환 및 **문자열** 에 **번호**합니다. 노드 집합으로 변환할 **부울** 있는지 테스트 합니다.  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서는 노드 집합에 대해 위치 선택을 수행하지 않습니다. 예를 들어 XPath 쿼리 `Customer[3]`는 세 번째 고객을 의미하는데 이러한 종류의 위치 선택이 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서는 지원되지 않습니다. 따라서 노드-설정-에-**문자열** 또는 노드-설정-에-**번호** XPath 사양에 설명 된 대로 변환이 구현 되지 않습니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서는 XPath 사양에 "첫 번째" 의미 체계가 지정된 경우 항상 "임의" 의미 체계를 사용합니다. 예를 들어, XPath 쿼리는 W3C XPath 사양에 따라 `Order[OrderDetail/@UnitPrice > 10.0]` 해당 주문을 선택 하는 첫 번째 **OrderDetail** 가 **단가** 10.0 보다 큰. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], XPath 쿼리를 사용 하 여 해당 주문 선택 **OrderDetail** 에 **단가** 10.0 보다 큰.  
  
 변환할 **부울** 존재 생성 테스트 하므로 XPath 쿼리 `Products[@Discontinued=true()]` SQL 식과 같습니다 "Products.Discontinued is null", not SQL 식 "Products.Discontinued = 1". 하려면 쿼리를, 후자는 SQL 식과 동일 하도록 먼저 변환 된 노드 집합 이외**부울** 와 같은 입력 **번호**합니다. `Products[number(@Discontinued) = true()]`) 을 입력합니다.  
  
 대부분의 연산자는 노드 집합의 임의 노드 또는 특정 노드에 대해 TRUE이면 TRUE가 되도록 정의되어 있으므로 노드 집합이 비어 있으면 이러한 연산의 결과가 항상 FALSE입니다. 따라서 A가 비어 있으면 `A = B`와 `A != B`는 모두 FALSE이고 `not(A=B)`와 `not(A!=B)`는 TRUE입니다.  
  
 특성 또는 요소는 열에 매핑되는 경우에 데이터베이스에서 해당 열의 값이 존재 하는 일반적으로 **null**합니다. 행에 매핑되는 요소는 행의 자식이 있는 경우에만 존재합니다.  
  
> [!NOTE]  
>  요소가 주석을 달아야 **은 상수** 항상 존재 합니다. 따라서에서 XPath 조건자를 사용할 수 없습니다 **은 상수** 요소입니다.  
  
 노드 집합으로 변환 되 면 **문자열** 하거나 **번호**주석이 추가 된 스키마에서 (있는 경우) 해당 XDR 형식을 검사 하 고 해당 형식은 필요한 변환이 결정 하는 데 사용 됩니다.  
  
## <a name="mapping-xdr-data-types-to-xpath-data-types"></a>XDR 데이터 형식을 XPath 데이터 형식에 매핑  
 다음 표에 나와 있는 것 처럼 노드의 XPath 데이터 형식은 스키마의 XDR 데이터 형식에서 파생 됩니다 (노드 **EmployeeID** 설명을 위한 목적으로 사용 됩니다).  
  
|XDR 데이터 형식|해당<br /><br /> XPath 데이터 형식|사용되는 SQL Server 변환|  
|-------------------|------------------------------------|--------------------------------|  
|Nonebin.base64bin.hex|해당 사항 없음|NoneEmployeeID|  
|boolean|boolean|CONVERT(bit, EmployeeID)|  
|number, int, float,i1, i2, i4, i8,r4, r8ui1, ui2, ui4, ui8|number|CONVERT(float(53), EmployeeID)|  
|id, idref, idrefsentity, entities, enumerationnotation, nmtoken, nmtokens, chardate, Timedate, Time.tz, string, uri, uuid|string|CONVERT(nvarchar(4000), EmployeeID, 126)|  
|fixed14.4|해당 사항 없음(XPath에는 fixed14.4 XDR 데이터 형식에 해당하는 데이터 형식이 없음)|CONVERT(money, EmployeeID)|  
|date|string|LEFT(CONVERT(nvarchar(4000), EmployeeID, 126), 10)|  
|Time<br /><br /> time.tz|string|SUBSTRING(CONVERT(nvarchar(4000), EmployeeID, 126), 1 + CHARINDEX(N'T', CONVERT(nvarchar(4000), EmployeeID, 126)), 24)|  
  
 날짜 및 시간 변환 값을 사용 하 여 데이터베이스에 저장 됩니다 있는지 여부를 작동 하도록 설계 된 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **datetime** 데이터 형식 또는 **문자열**합니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **datetime** 데이터 형식을 사용 하지 **표준 시간대** 하며 XML 보다 작은 전체 자릿수 **시간** 데이터 형식입니다. 포함 하는 **표준 시간대** 데이터 형식 또는 전체 자릿수를 늘리려면, 데이터를 저장할 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 사용 하 여를 **문자열** 형식입니다.  
  
 노드가 해당 XDR 데이터 형식에서 XPath 데이터 형식으로 변환될 때 한 XPath 데이터 형식에서 다른 XPath 데이터 형식으로의 추가 변환이 필요한 경우가 있습니다. 예를 들어 다음과 같은 XPath 쿼리를 살펴봅니다.  
  
```  
(@m + 3) = 4  
```  
  
 경우 @m 입니다. 합니다 **fixed14.4** XDR 데이터 형식에서 xpath 데이터 형식을 사용 하 여 이루어집니다 XDR 데이터 형식에서 변환 합니다.  
  
```  
CONVERT(money, m)  
```  
  
 이 변환에서는 노드 `m` 에서 변환할 **fixed14.4** 하려면 **money**합니다. 그러나 값 3을 추가하려면 추가 변환이 필요합니다.  
  
```  
CONVERT(float(CONVERT(money, m))  
```  
  
 이 XPath 식은 다음과 같이 계산됩니다.  
  
```  
CONVERT(float(CONVERT(money, m)) + CONVERT(float(53), 3) = CONVERT(float(53), 3)  
```  
  
 다음 표에서 볼 수 있듯이 이 변환은 리터럴 또는 복합 식과 같은 다른 XPath 식에 적용되는 변환과 같습니다.  
  
||||||  
|-|-|-|-|-|  
||X는 알 수 없는 형식입니다.|X가 **문자열**|X가 **수**|X는 **부울**|  
|string(X)|CONVERT (nvarchar(4000), X, 126)|-|CONVERT (nvarchar(4000), X, 126)|CASE WHEN X THEN N'true' ELSE N'false' END|  
|number(X)|CONVERT (float(53), X)|CONVERT (float(53), X)|-|CASE WHEN X THEN 1 ELSE 0 END|  
|boolean(X)|-|LEN(X) > 0|X != 0|-|  
  
## <a name="examples"></a>예  
  
### <a name="a-convert-a-data-type-in-an-xpath-query"></a>1. XPath 쿼리에서 데이터 형식 변환  
 주석이 추가 된 XSD 스키마에 대해 지정 된 다음 XPath 쿼리에서 쿼리 모두 선택 **직원** 사용 하 여 노드를 **EmployeeID** 특성 1 인 "E-"가 사용 하 여 지정 된 접두사의 값을 **그것이-접두사** 주석입니다.  
  
 `Employee[@EmployeeID="E-1"]`  
  
 쿼리의 조건자는 다음 SQL 식과 같습니다.  
  
 `N'E-' + CONVERT(nvarchar(4000), Employees.EmployeeID, 126) = N'E-1'`  
  
 때문에 **EmployeeID** 중 하나는 **id** (**idref**, **idrefs**, **nmtoken**,  **특성**등) XSD 스키마에 값을 입력 하는 데이터 **EmployeeID** 로 변환 되는 **문자열** 앞에서 설명한 변환 규칙을 사용 하 여 XPath 데이터 형식.  
  
 `CONVERT(nvarchar(4000), Employees.EmployeeID, 126)`  
  
 "E-" 접두사가 문자열에 추가된 다음 그 결과가 `N'E-1'`과 비교됩니다.  
  
### <a name="b-perform-several-data-type-conversions-in-an-xpath-query"></a>2. XPath 쿼리에서 몇 가지 데이터 형식 변환 수행  
 주석이 추가된 XSD 스키마에 대해 지정된 XPath 쿼리 `OrderDetail[@UnitPrice * @OrderQty > 98]`을 살펴봅니다.  
  
 모든 XPath 쿼리를 반환 하면  **\<OrderDetail >** 조건자에 맞는 요소 `@UnitPrice * @OrderQty > 98`. 경우는 **UnitPrice** 로 주석이 추가 된 **fixed14.4** 주석이 추가 된 스키마의 데이터 입력이 조건자가 같고 SQL 식:  
  
 `CONVERT(float(53), CONVERT(money, OrderDetail.UnitPrice)) * CONVERT(float(53), OrderDetail.OrderQty) > CONVERT(float(53), 98)`  
  
 XPath 쿼리에서 값 변환 시 첫 번째 변환에서는 XDR 데이터 형식을 XPath 데이터 형식으로 변환합니다. XSD 데이터 형식 때문 **UnitPrice** 됩니다 **fixed14.4**, 이것이 사용 되는 첫 번째 변환 이전 표와 같이:  
  
```  
CONVERT(money, OrderDetail.UnitPrice))   
```  
  
 산술 연산자는 피연산자를 변환 하기 때문에 해당 **번호** XPath 데이터 형식 (한 XPath 데이터 형식에서 다른 XPath 데이터 형식) 하 고 두 번째 변환 되는 값으로 변환 됩니다 적용 됩니다 **float(53)**  (**float(53)** XPath 가까운 **번호** 데이터 형식).  
  
```  
CONVERT(float(53), CONVERT(money, OrderDetail.UnitPrice))   
```  
  
 가정 하 고는 **OrderQty** 특성에는 XSD 데이터 형식이 없습니다 **OrderQty** 로 변환 됩니다는 **번호** 단일 변환에서 XPath 데이터 형식:  
  
```  
CONVERT(float(53), OrderDetail.OrderQty)  
```  
  
 마찬가지로 값 98은 변환할 합니다 **번호** XPath 데이터 형식:  
  
```  
CONVERT(float(53), 98)  
```  
  
> [!NOTE]  
>  스키마에 사용된 XSD 데이터 형식이 데이터베이스의 기본 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터 형식과 호환되지 않거나 허용되지 않는 XPath 데이터 형식 변환이 수행되면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 오류를 반환할 수 있습니다. 예를 들어, 경우는 **EmployeeID** 특성으로 추적이 **id 접두사** 주석을 XPath `Employee[@EmployeeID=1]` 에서 오류가 발생 하기 때문에 **EmployeeID** 에 **id 접두사** 주석으로 변환할 수 없습니다 **번호**.  
  
  
