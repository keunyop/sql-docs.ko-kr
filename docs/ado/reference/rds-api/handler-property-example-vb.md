---
title: "처리기 속성 예제 (VB) | Microsoft Docs"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Handler property [ADO], Visual Basic example
ms.assetid: 9664f9a6-65fc-4e7f-be3d-3e4b501b558a
caps.latest.revision: 14
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 8eaff81d3a43a36b671c31354948da2f54e3f199
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="handler-property-example-vb"></a>처리기 속성 예제 (VB)
> [!IMPORTANT]
>  Windows 8 및 Windows Server 2012 부터는 RDS 서버 구성 요소가 더 이상에 포함 Windows 운영 체제 (Windows 8 참조 및 [Windows Server 2012 호환성 설명서](https://www.microsoft.com/en-us/download/details.aspx?id=27416) 자세한 세부 정보에 대 한). RDS 클라이언트 구성 요소는 나중 버전의 Windows에서 제거 됩니다. 새 개발 작업에서는 이 기능을 사용하지 않도록 하고, 현재 이 기능을 사용하는 응용 프로그램은 수정하세요. RDS를 사용 하는 응용 프로그램을 마이그레이션해야 합니다. [WCF 데이터 서비스](http://go.microsoft.com/fwlink/?LinkId=199565)합니다.  
  
 이 예제에서는 [RDS DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) 개체 [처리기](../../../ado/reference/rds-api/handler-property-rds.md) 속성입니다. (참조 [DataFactory 사용자 지정](../../../ado/guide/remote-data-service/datafactory-customization.md) 내용을 확인 합니다.)  
  
 Msdfmap.ini, 매개 변수 파일의 다음 섹션에서는 서버에 있는 가정 합니다.  
  
```  
[connect AuthorDataBase]  
Access=ReadWrite  
Connect="DSN=Pubs"  
[sql AuthorById]  
SQL="SELECT * FROM Authors WHERE au_id = ?"  
```  
  
 코드는 다음과 같습니다. 에 지정 된 명령을 [SQL](../../../ado/reference/rds-api/sql-property.md) 속성은 일치는 ***AuthorById*** 식별자 및 Michael O'Leary 작성자에 대 한 행을 검색 합니다. **DataControl** 개체 **레코드 집합** 속성에 할당 되는 연결이 끊어진에 [레코드 집합](../../../ado/reference/ado-api/recordset-object-ado.md) 개체를 코딩 편의 위해도 순수 하 게 합니다.  
  
```  
'BeginHandlerVB  
Public Sub Main()  
    On Error GoTo ErrorHandler  
  
    Dim dc As New DataControl  
    Dim rst As ADODB.Recordset  
  
    dc.Handler = "MSDFMAP.Handler"  
    dc.ExecuteOptions = 1  
    dc.FetchOptions = 1  
    dc.Server = "http://MyServer"  
    dc.Connect = "Data Source=AuthorDataBase"  
    dc.SQL = "AuthorById('267-41-2394')"  
    dc.Refresh                  'Retrieve the record  
    Set rst = dc.Recordset      'Use another Recordset as a convenience  
    Debug.Print "Author is '" & rst!au_fname & " " & rst!au_lname & "'"  
  
    ' clean up  
    If rst.State = adStateOpen Then rst.Close  
    Set rst = Nothing  
    Set dc = Nothing  
    Exit Sub  
  
ErrorHandler:  
    ' clean up  
    If Not rst Is Nothing Then  
        If rst.State = adStateOpen Then rst.Close  
    End If  
    Set rst = Nothing  
    Set dc = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Sub  
'EndHandlerVB  
```  
  
## <a name="see-also"></a>관련 항목:  
 [DataControl 개체 (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)   
 [Handler 속성(RDS)](../../../ado/reference/rds-api/handler-property-rds.md)


