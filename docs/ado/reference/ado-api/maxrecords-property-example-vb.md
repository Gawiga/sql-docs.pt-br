---
title: Exemplo da propriedade MaxRecords (VB) | Microsoft Docs
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- MaxRecords property [ADO], Visual Basic example
ms.assetid: 630a3be4-7a87-41cf-997e-8bb50d89db1e
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 89a1d7e9ecc360bb5a92cb4a9584c93cbc2ca8ce
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2018
---
# <a name="maxrecords-property-example-vb"></a>Exemplo da propriedade MaxRecords (VB)
Este exemplo usa o [MaxRecords](../../../ado/reference/ado-api/maxrecords-property-ado.md) propriedade para abrir um [registros](../../../ado/reference/ado-api/recordset-object-ado.md) que contém os títulos mais caros 10 no ***títulos*** tabela.  
  
```  
'BeginMaxRecordsVB  
  
    'To integrate this code  
    'replace the data source and initial catalog values  
    'in the connection string  
  
Public Sub Main()  
    On Error GoTo ErrorHandler  
  
    Dim rstTitles As ADODB.Recordset  
    Dim Cnxn As ADODB.Connection  
    Dim strCnxn As String  
    Dim strSQLTitles As String  
  
    ' Open a connection  
    Set Cnxn = New ADODB.Connection  
    strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _  
        "Initial Catalog='Pubs';Integrated Security='SSPI';"  
    Cnxn.Open strCnxn  
  
    ' Open recordset containing the 10 most expensive  
    ' titles in the Titles table  
    Set rstTitles = New ADODB.Recordset  
    rstTitles.MaxRecords = 10  
  
    strSQLTitles = "SELECT Title, Price FROM Titles ORDER BY Price DESC"  
    rstTitles.Open strSQLTitles, strCnxn, adOpenStatic, adLockReadOnly, adCmdText  
  
    ' Display the contents of the recordset  
    Debug.Print "Top Ten Titles by Price:"  
  
    Do Until rstTitles.EOF  
        Debug.Print "  " & rstTitles!Title & " - " & rstTitles!Price  
        rstTitles.MoveNext  
    Loop  
  
    ' clean up  
    rstTitles.Close  
    Cnxn.Close  
    Set rstTitles = Nothing  
    Set Cnxn = Nothing  
    Exit Sub  
  
ErrorHandler:  
    ' clean up  
    If Not rstTitles Is Nothing Then  
        If rstTitles.State = adStateOpen Then rstTitles.Close  
    End If  
    Set rstTitles = Nothing  
  
    If Not Cnxn Is Nothing Then  
        If Cnxn.State = adStateOpen Then Cnxn.Close  
    End If  
    Set Cnxn = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Sub  
'EndMaxRecordsVB  
```  
  
## <a name="see-also"></a>Consulte também  
 [Propriedade MaxRecords (ADO)](../../../ado/reference/ado-api/maxrecords-property-ado.md)   
 [Objeto Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)
