---
title: 'Lição 2: Especificando informações de conexão (Reporting Services) | Microsoft Docs'
ms.date: 05/23/2016
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: reporting-services
ms.suite: pro-bi
ms.topic: conceptual
applies_to:
- SQL Server 2016
ms.assetid: 54405a3a-d7fa-4d95-8963-9aa224e5901e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 9ca21419e841482747410f50809d0d502f495f06
ms.sourcegitcommit: d96b94c60d88340224371926f283200496a5ca64
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43274767"
---
# <a name="lesson-2-specifying-connection-information-reporting-services"></a>Lição 2: Especificando informações sobre conexão (Reporting Services)
Depois de adicionar um relatório paginado do [!INCLUDE[ssRSnoversion_md](../includes/ssrsnoversion-md.md)] ao de projeto de Tutorial na Lição 1, agora você precisa definir uma *fonte de dados*, que são informações de conexão usadas pelo relatório para acessar dados de um banco de dados relacional, banco de dados multidimensional ou outra origem.  
  
Nesta lição, você usa o banco de dados de exemplo [!INCLUDE[ssSampleDBAdventureworks2014_md](../includes/sssampledbadventureworks2014-md.md)] como a fonte de dados. Este tutorial pressupõe que esse banco de dados esteja localizado em uma instância padrão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] instalado no computador local.  
  
### <a name="to-set-up-a-connection"></a>Para configurar uma conexão  
  
1.  No painel **Dados do Relatório** , clique em **Nova** e em **Data Source**.  
Se o painel **Dados do Relatório** não estiver visível, no menu **Exibir** , clique em **Dados do Relatório**.  

    ![ssrs-table-tutorial-2-new-data-source](../reporting-services/media/ssrs-table-tutorial-2-new-data-source.png)
  
   2.  Em **Nome**, digite *AdventureWorks2014*.  
  
3.  Garanta que a opção **Conexão inserida** está selecionada.  
  
4.  Em **Tipo**, selecione **Microsoft SQL Server**.  
  
5.  Em **Cadeia de conexão**, digite o seguinte:  
  
    ```  
    Data source=localhost; initial catalog=AdventureWorks2014  
    ```  
  
     Esta cadeia de conexão assume que o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], o servidor de relatório e o banco de dados [!INCLUDE[ssSampleDBAdventureworks2014_md](../includes/sssampledbadventureworks2014-md.md)] estão instalados no computador local e que você tem permissão para fazer logon no banco de dados [!INCLUDE[ssSampleDBAdventureworks2014_md](../includes/sssampledbadventureworks2014-md.md)] . Se o banco de dados AdventureWorks2014 não estiver no computador local, altere a cadeia de conexão e substitua *localhost* pelo nome da instância do servidor de banco de dados.
  
     >[!NOTE]  
    >Se estiver usando o [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] com Serviços Avançados ou uma instância nomeada, a cadeia de conexão deverá incluir informações da instância:  
    >  
    >`Data source=localhost\SQLEXPRESS; initial catalog=AdventureWorks2014`  
    >  
    >Para obter mais informações sobre cadeias de conexão, consulte: [Conexões de dados, fontes de dados e cadeias de conexão no Reporting Services](../reporting-services/report-data/data-connections-data-sources-and-connection-strings-report-builder-and-ssrs.md).  
     
  
6.  Clique em **Credenciais** no painel esquerdo e clique em **Usar Autenticação do Windows (segurança integrada)**.  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)] A fonte de dados do **AdventureWorks2014** é adicionada ao painel **Dados do Relatório** .  
![ssrs_adventureworks_datasource](../reporting-services/media/ssrs-adventureworks-datasource.png)  
## <a name="next-task"></a>Próxima tarefa  
Você definiu uma conexão com o banco de dados de exemplo [!INCLUDE[ssSampleDBAdventureworks2014_md](../includes/sssampledbadventureworks2014-md.md)] com êxito. Em seguida, você criará o relatório. Consulte [Lição 3: Definindo um conjunto de dados para o relatório de tabela &#40;Reporting Services&#41;](../reporting-services/lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md).  
  
## <a name="see-also"></a>Consulte Também  
[Conexões de dados, fontes de dados e cadeias de conexão no Reporting Services](../reporting-services/report-data/data-connections-data-sources-and-connection-strings-report-builder-and-ssrs.md)  
  
  
  

