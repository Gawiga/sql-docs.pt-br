---
title: Usar dados XML em aplicativos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-xml
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- parameters [XML in SQL Server]
- XML [SQL Server], ADO
- columns [XML in SQL Server], ADO.NET
- ADO [XML in SQL Server]
- columns [XML in SQL Server], SQL Server Native Client
- xml data type [SQL Server], ADO
- SQLNCLI, XML
- xml data type [SQL Server], SQL Server Native Client
- SQL Server Native Client, XML
- ADO.NET [XML in SQL Server]
- XML [SQL Server], ADO.NET
- columns [XML in SQL Server], ADO
- xml data type [SQL Server], ADO.NET
- XML [SQL Server], SQL Server Native Client
ms.assetid: 5dabf7e0-c6df-451d-a070-4661f84607fd
caps.latest.revision: 26
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 13440d6941d05fd02c1c98c8a75d538adbf749de
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37293946"
---
# <a name="use-xml-data-in-applications"></a>Usar dados XML em aplicativos
  Este tópico descreve as opções que estão disponíveis para trabalhar com o `xml` tipo de dados em seu aplicativo. O tópico contém informações sobre o seguinte:  
  
-   Tratando XML de uma coluna de tipo `xml` usando o ADO e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client  
  
-   Tratando XML de um `xml` coluna de tipo usando o ADO.NET  
  
-   Tratando tipo `xml` em parâmetros usando o ADO.NET  
  
## <a name="handling-xml-from-an-xml-type-column-by-using-ado-and-sql-server-native-client"></a>Tratando XML de uma coluna de tipo xml usando o ADO e o SQL Server Native Client  
 Para usar componentes MDAC para acessar os tipos e recursos introduzidos no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a propriedade de inicialização DataTypeCompatibility deve estar definida na cadeia de conexão do ADO.  
  
 Por exemplo, o exemplo de Visual Basic Scripting Edition (VBScript) a seguir mostra os resultados da consulta um `xml` coluna de tipo de dados `Demographics`, no `Sales.Store` a tabela do `AdventureWorks2012` banco de dados de exemplo. Especificamente, a consulta procura o valor da instância dessa coluna para a linha em que o `CustomerID` é igual a `3`.  
  
```  
Const DS = "MyServer"  
Const DB = "AdventureWorks2012"  
  
Set objConn = CreateObject("ADODB.Connection")  
Set objRs = CreateObject("ADODB.Recordset")  
  
CommandText = "SELECT Demographics" & _  
              " FROM Sales.Store" & _  
              " INNER JOIN Sales.Customer" & _  
              " ON Sales.Store.BusinessEntityID = sales.customer.StoreID" & _  
              " WHERE Sales.Customer.CustomerID = 3" & _  
              " OR Sales.Customer.CustomerID = 4"  
  
ConnectionString = "Provider=SQLNCLI11" & _  
                   ";Data Source=" & DS & _  
                   ";Initial Catalog=" & DB & _  
                   ";Integrated Security=SSPI;" & _  
                   "DataTypeCompatibility=80"  
  
'Connect to the data source.  
objConn.Open ConnectionString  
  
'Execute command through the connection and display  
Set objRs = objConn.Execute(CommandText)  
  
Dim rowcount  
rowcount = 0  
Do While Not objRs.EOF  
   rowcount = rowcount + 1  
   MsgBox "Row " & rowcount & _  
           vbCrLf & vbCrLf & objRs(0)  
   objRs.MoveNext  
Loop  
  
'Clean up.  
objRs.Close  
objConn.Close  
Set objRs = Nothing  
Set objConn = Nothing  
```  
  
 Esse exemplo mostra como definir a propriedade de compatibilidade de tipo de dados. Por padrão, isso é definido como 0 ao usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client. Se você definir o valor como 80, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fará com que o provedor de cliente nativo `xml` e colunas de tipo definido pelo usuário são exibidas como [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] tipos de dados. Esses tipos são DBTYPE_WSTR e DBTYPE_BYTES, respectivamente.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] O Native Client também deve estar instalado no computador cliente e a cadeia de conexão deve especificá-lo para uso como o provedor de dados com "`Provider=SQLNCLI11;...`".  
  
#### <a name="to-test-this-example"></a>Para testar este exemplo  
  
1.  Verifique se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client está instalado e se o MDAC 2.6.0 ou posterior está disponível no computador cliente.  
  
     Para obter mais informações, veja [Programação do SQL Server Native Client](../native-client/sql-server-native-client-programming.md).  
  
2.  Verifique se o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] de exemplo no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está instalado.  
  
     Esse exemplo requer o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] de exemplo.  
  
3.  Copie o código mostrado anteriormente neste tópico e cole-o em seu editor de texto ou de código. Salve o arquivo como HandlingXmlDataType.vbs.  
  
4.  Modifique o script conforme necessário para sua instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e salve as alterações.  
  
     Por exemplo, quando `MyServer` estiver especificado, ele deve ser substituído pelo nome `(local)` ou real do servidor no qual o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está instalado.  
  
5.  Execute HandlingXmlDataType.vbs e execute o script.  
  
 Os resultados devem ser semelhantes à seguinte saída de exemplo:  
  
```  
Row 1  
  
<StoreSurvey xmlns="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>1500000</AnnualSales>  
  <AnnualRevenue>150000</AnnualRevenue>  
  <BankName>Primary International</BankName>  
  <BusinessType>OS</BusinessType>  
  <YearOpened>1974</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>38000</SquareFeet>  
  <Brands>3</Brands>  
  <Internet>DSL</Internet>  
  <NumberEmployees>40</NumberEmployees>  
</StoreSurvey>  
  
Row 2  
  
<StoreSurvey xmlns="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>300000</AnnualSales>  
  <AnnualRevenue>30000</AnnualRevenue>  
  <BankName>United Security</BankName>  
  <BusinessType>BM</BusinessType>  
  <YearOpened>1976</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>6000</SquareFeet>  
  <Brands>2</Brands>  
  <Internet>DSL</Internet>  
  <NumberEmployees>5</NumberEmployees>  
</StoreSurvey>  
```  
  
## <a name="handling-xml-from-an-xml-type-column-by-using-adonet"></a>Tratando XML de uma coluna de tipo xml usando o ADO.NET  
 Para tratar XML de um `xml` coluna de tipo de dados usando o ADO.NET e o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] você pode usar o comportamento padrão da `SqlCommand` classe. Por exemplo, um `xml` dados de coluna de tipo e seus valores podem ser recuperados da mesma maneira como qualquer coluna SQL é recuperada usando um `SqlDataReader`. No entanto, se você quiser trabalhar com o conteúdo de um `xml` coluna de tipo de dados como XML, você primeiro precisará atribuir o conteúdo a um `XmlReader` tipo.  
  
 Para obter mais informações e um código de exemplo, confira “Valores de coluna XML em um Leitor de Dados” na documentação do SDK do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] .  
  
## <a name="handling-an-xml-type-column-in-parameters-by-using-adonet"></a>Tratando uma coluna de tipo xml em parâmetros usando o ADO.NET  
 Para tratar um tipo de dados xml passado como um parâmetro no ADO.NET e no [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], é possível fornecer o valor como uma instância do tipo de dados `SqlXml`. Nenhum tratamento especial está envolvido porque `xml` colunas do tipo de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode aceitar valores de parâmetro da mesma maneira que outras colunas e tipos de dados, como `string` ou `integer`.  
  
 Para obter mais informações e um código de exemplo, confira “Valores XML como parâmetros de comando” na documentação do SDK do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] .  
  
## <a name="see-also"></a>Consulte também  
 [Dados XML &#40;SQL Server&#41;](xml-data-sql-server.md)  
  
  
