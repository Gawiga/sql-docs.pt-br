---
title: Exemplo de propriedades de DateModified (VC + +) e DateCreated | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DateCreated property [ADOX], VC++ example
- DateModified property [ADOX], VC++ example
ms.assetid: b964beee-83c7-4f91-8255-3ba864c9adfd
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 7919bd3e51ad685416ff35d99cb961988334dd15
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35285605"
---
# <a name="datecreated-and-datemodified-properties-example-vc"></a>DateCreated e DateModified propriedades exemplo (VC + +)
Este exemplo demonstra o [DateCreated](../../../ado/reference/adox-api/datecreated-property-adox.md) e [DateModified](../../../ado/reference/adox-api/datemodified-property-adox.md) propriedades adicionando um novo [coluna](../../../ado/reference/adox-api/column-object-adox.md) um existente [tabela](../../../ado/reference/adox-api/table-object-adox.md) e por Criando um novo **tabela**. O procedimento DateOutput é necessário para executar este exemplo.  
  
```  
// BeginDateCreatedCpp.cpp  
// compile with: /EHsc  
#import "msado15.dll" rename("EOF", "EndOfFile")  
#import "msadox.dll" no_namespace  
  
#include "iostream"  
using namespace std;  
  
// Function declarations  
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);};  
void DateCreatedX();  
void DateOutPut(_bstr_t strTemp, _TablePtr tblTemp);  
  
int main() {  
    if ( FAILED(::CoInitialize(NULL) ) )  
        return -1;  
    DateCreatedX();  
    ::CoUninitialize();  
}  
  
void DateCreatedX() {  
    HRESULT hr = S_OK;  
  
    // Define ADOX object pointers, initialize pointers. These are in ADODB  namespace.  
    _CatalogPtr m_pCatalog = NULL;  
    _TablePtr m_pTblEmployees = NULL;  
    _TablePtr m_pTblNew = NULL;  
  
    // Set ActiveConnection of Catalog to this string  
    _bstr_t strCnn("Provider='Microsoft.JET.OLEDB.4.0';Data Source= 'c:\\Northwind.mdb';");  
  
    try {  
        TESTHR(hr = m_pCatalog.CreateInstance(__uuidof (Catalog)));  
  
        // Connect the catalog.  
        m_pCatalog->PutActiveConnection(strCnn);  
        m_pTblEmployees = m_pCatalog->Tables->GetItem("Employees");  
  
        // Print current information about the Employees table.  
        DateOutPut((_bstr_t)"Current properties", m_pTblEmployees);  
  
        // Create and append column to the Employees table.  
        m_pTblEmployees->Columns->Append("NewColumn", adInteger,0);  
        m_pCatalog->Tables->Refresh();  
  
        // Print new information about the Employees table.  
        DateOutPut((_bstr_t)"After creating a new column", m_pTblEmployees);  
  
        // Delete new column because this is a demonstration.  
        m_pTblEmployees->Columns->Delete("NewColumn");  
  
        // Create and append new Table object to the Northwind database.  
        TESTHR(hr = m_pTblNew.CreateInstance(__uuidof(Table)));  
  
        m_pTblNew->Name = "NewTable";  
        m_pTblNew->Columns->Append("NewColumn", adInteger,0);  
        m_pCatalog->Tables->Append(_variant_t((IDispatch*)m_pTblNew));  
        m_pCatalog->Tables->Refresh();  
  
        // Print information about the new Table object.  
        DateOutPut((_bstr_t)"After creating a new table", m_pCatalog->Tables->GetItem("NewTable"));  
  
        // Delete new Table object because this is a demonstration.  
        m_pCatalog->Tables->Delete(m_pTblNew->Name);  
    }  
  
    catch(_com_error &e) {  
        // Notify the user of errors if any.  
        _bstr_t bstrSource(e.Source());  
        _bstr_t bstrDescription(e.Description());  
  
        printf("\n\tSource :  %s \n\tdescription : %s \n ", (LPCSTR)bstrSource, (LPCSTR)bstrDescription);  
    }  
  
    catch(...) {  
        cout << "Error occured in include files...." << endl;  
    }  
}  
  
void DateOutPut(_bstr_t strTemp , _TablePtr tblTemp) {  
    // Print DateCreated and DateModified information about specified Table object.  
    cout << strTemp << endl;  
    cout << "    Table: " << tblTemp->GetName() << endl;  
    cout << "        DateCreated = " << (_bstr_t)tblTemp->GetDateCreated() << endl;  
    cout << "        DateModified = " << (_bstr_t)tblTemp->GetDateModified() << endl;  
}  
```  
  
## <a name="see-also"></a>Consulte também  
 [Objeto de coluna (ADOX)](../../../ado/reference/adox-api/column-object-adox.md)   
 [Propriedade DateCreated (ADOX)](../../../ado/reference/adox-api/datecreated-property-adox.md)   
 [Propriedade DateModified (ADOX)](../../../ado/reference/adox-api/datemodified-property-adox.md)   
 [Objeto Table (ADOX)](../../../ado/reference/adox-api/table-object-adox.md)
