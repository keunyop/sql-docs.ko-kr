---
title: "NextRecordset 메서드 예제 (VB) | Microsoft Docs"
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
- NextRecordset method [ADO], Visual Basic example
ms.assetid: b14806da-80d9-4da4-bb87-f558b36a6ac0
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 8876682f825febe1deaf1a00867d543120e83af7
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="nextrecordset-method-example-vb"></a>NextRecordset 메서드 예제 (VB)
사용 하 여이 예제는 [NextRecordset](../../../ado/reference/ado-api/nextrecordset-method-ado.md) 메서드를 세 개의 개별 이루어진 복합 명령문을 사용 하는 레코드 집합의 데이터를 볼 **선택** 문.  
  
```  
'BeginNextRecordsetVB  
  
    'To integrate this code  
    'replace the data source and initial catalog values  
    'in the connection string  
  
Public Sub Main()  
    On Error GoTo ErrorHandler  
  
    ' connection and recordset variables  
    Dim rstCompound As ADODB.Recordset  
    Dim Cnxn As ADODB.Connection  
    Dim strCnxn As String  
    Dim SQLCompound As String  
  
    Dim intCount As Integer  
  
    ' Open connection  
    Set Cnxn = New ADODB.Connection  
    strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _  
        "Initial Catalog='Pubs';Integrated Security='SSPI';"  
    Cnxn.Open strCnxn  
  
    ' Open compound recordset  
    Set rstCompound = New ADODB.Recordset  
    SQLCompound = "SELECT * FROM Authors; " & _  
        "SELECT * FROM stores; " & _  
        "SELECT * FROM jobs"  
    rstCompound.Open SQLCompound, Cnxn, adOpenStatic, adLockReadOnly, adCmdText  
  
    ' Display results from each SELECT statement  
    intCount = 1  
    Do Until rstCompound Is Nothing  
        Debug.Print "Contents of recordset #" & intCount  
  
        Do Until rstCompound.EOF  
            Debug.Print , rstCompound.Fields(0), rstCompound.Fields(1)  
            rstCompound.MoveNext  
        Loop  
  
        Set rstCompound = rstCompound.NextRecordset  
        intCount = intCount + 1  
    Loop  
  
    ' clean up  
    Cnxn.Close  
    Set rstCompound = Nothing  
    Set Cnxn = Nothing  
    Exit Sub  
  
ErrorHandler:  
    ' clean up  
    If Not rstCompound Is Nothing Then  
        If rstCompound.State = adStateOpen Then rstCompound.Close  
    End If  
    Set rstCompound = Nothing  
  
    If Not Cnxn Is Nothing Then  
        If Cnxn.State = adStateOpen Then Cnxn.Close  
    End If  
    Set Cnxn = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Sub  
'EndNextRecordsetVB  
```  
  
## <a name="see-also"></a>관련 항목:  
 [NextRecordset 메서드 (ADO)](../../../ado/reference/ado-api/nextrecordset-method-ado.md)   
 [레코드 집합 개체(ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)