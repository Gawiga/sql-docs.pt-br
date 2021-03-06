---
title: Representação de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 16a233fb-f83b-4ca1-acb5-6186eca0a62c
caps.latest.revision: 9
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: e288ccfb3cee35ef1506fe46d2128dd6ab43480a
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37197766"
---
# <a name="database-representationtabular"></a>Representação de banco de dados (de tabela)
  No Modo de Tabela, o banco de dados é o contêiner de todos os objetos no modelo de tabela.  
  
## <a name="database-representation"></a>Representação de banco de dados  
 O banco de dados é o local onde residem todos os objetos que constituem um modelo de tabela. O desenvolvedor localiza no banco de dados objetos como conexões, tabelas, funções e muito mais.  
  
### <a name="database-in-amo"></a>Banco de dados no AMO  
 Ao usar o AMO para gerenciar um banco de dados modelo de tabela, o objeto <xref:Microsoft.AnalysisServices.Database> no AMO coincide um-para-um ao objeto lógico de banco de dados em um modelo de tabela.  
  
> [!NOTE]  
>  Para obter acesso a um objeto de banco de dados, no AMO, o usuário precisa ter acesso a um objeto de servidor e conectar-se a ele.  
  
### <a name="database-in-adomdnet"></a>Banco de dados no ADOMD.Net  
 Ao usar o ADOMD para consultar um banco de dados modelo de tabela, a conexão com um banco de dados específico é obtida por meio do objeto <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection>.  
  
 Você pode se conectar diretamente a determinado banco de dados usando o seguinte trecho de código:  
  
```csharp  
using ADOMD = Microsoft.AnalysisServices.AdomdClient;  
…  
   ADOMD.AdomdConnection currrentCnx = new ADOMD.AdomdConnection("Data Source=<<server\instance>>;Catalog=<<database>>");  
   currrentCnx.Open();  
…  
  
```  
  
 Além disso, em um objeto de conexão existente (que não foi fechado), você pode alterar o banco de dados atual para outro, conforme mostrado no seguinte trecho de código:  
  
```csharp  
currentCnx.ChangeDatabase("myOtherDatabase");  
  
```  
  
## <a name="database-in-amo"></a>Banco de dados no AMO  
 Ao usar o AMO para gerenciar um objeto de banco de dados, comece com um objeto <xref:Microsoft.AnalysisServices.Server>. Em seguida, procure seu banco de dados na coleção de banco de dados ou crie um novo banco de dados adicionando um à coleção.  
  
 O trecho de código a seguir mostra as etapas para conectar-se a um servidor e criar um banco de dados vazio, depois de verificar que o banco de dados não existe:  
  
```  
  
AMO.Server CurrentServer = new AMO.Server();  
try  
{  
    CurrentServer.Connect(currentServerName);  
}  
catch (Exception cnxException)  
{  
    MessageBox.Show(string.Format("Error while trying to connect to server: [{0}]\nError message: {1}", currentServerName, cnxException.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
    return;  
}  
newDatabaseName = DatabaseName.Text;  
if (CurrentServer.Databases.Contains(newDatabaseName))  
{  
    return;  
}  
try  
{  
    AMO.Database newDatabase = CurrentServer.Databases.Add(newDatabaseName);  
  
    CurrentServer.Update();  
}  
catch (Exception createDBxc)  
{  
    MessageBox.Show(String.Format("Database [{0}] couldn't be created.\n{1}", newDatabaseName, createDBxc.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
    newDatabaseAvailable = false;  
}  
  
```  
  
 Para obter um entendimento prático de como usar o AMO para criar e manipular representações de banco de dados, consulte o código-fonte do exemplo Tabular AMO 2012; Verifique especificamente o seguinte arquivo de origem: Database.cs. O código de exemplo é fornecido apenas como um suporte aos conceitos lógicos explicados aqui e não deve ser usado em um ambiente de produção.  
  
  
