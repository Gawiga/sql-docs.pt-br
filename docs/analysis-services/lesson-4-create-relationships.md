---
title: "Lição 5: Criar relações | Microsoft Docs"
ms.custom: 
ms.date: 03/27/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: get-started-article
applies_to:
- SQL Server 2016
ms.assetid: abac1a00-f827-4c3e-a473-6db5c8a3a66f
caps.latest.revision: 29
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 096f19dc25973b2d515c6ccfb9961e7b0fe07c21
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="lesson-4-create-relationships"></a>Lição 4: Criar relações
[!INCLUDE[ssas-appliesto-sql2016-later-aas](../includes/ssas-appliesto-sql2016-later-aas.md)]

Nesta lição você verificará as relações que foram criadas automaticamente quando você importou os dados e adicionar novas relações entre tabelas diferentes. Uma relação é uma conexão criada entre duas tabelas que estabelece como os dados dessas tabelas devem ser correlacionados. Por exemplo, a tabela DimProduct e a tabela DimProductSubcategory têm uma relação baseada no fato de que cada produto pertence a uma subcategoria. Para obter mais informações, consulte [relações](../analysis-services/tabular-models/relationships-ssas-tabular.md).
  
Tempo estimado para concluir esta lição: **10 minutos**  
  
## <a name="prerequisites"></a>Pré-requisitos  
Este tópico faz parte de um tutorial de modelo de tabela, que deve ser concluído na ordem. Antes de executar as tarefas nesta lição, você deve ter concluído a lição anterior: [lição 3: marcar como tabela de data](../analysis-services/lesson-3-mark-as-date-table.md). 
  
## <a name="review-existing-relationships-and-add-new-relationships"></a>Revisar relações existentes e adicionar novas relações  
Quando você importar dados usando o Assistente de importação de tabela, você tem sete tabelas do banco de dados AdventureWorksDW. Em geral, quando você importa dados de uma fonte relacional, as relações existentes são importadas automaticamente junto com os dados. No entanto, antes de dar continuidade à criação do modelo, você deve verificar se essas relações entre tabelas foram criadas corretamente. Para este tutorial, você adicionará também três novas relações.  
  
#### <a name="to-review-existing-relationships"></a>Para revisar relações existentes  
  
1.  Clique o **modelo** menu > **exibição do modelo de** > **exibição de diagrama**.  

    Agora, o designer de modelos aparece em Exibição de Diagrama, um formato gráfico que exibe todas as tabelas que você importou com linhas entre elas. As linhas entre tabelas indicam as relações que foram criadas automaticamente quando você importar os dados.
    
    ![como-tabela-lesson4-diagrama](../analysis-services/media/as-tabular-lesson4-diagram.png)
  
    Use os controles de minimapa no canto inferior direito do designer de modelos para ajustar a exibição para que ela inclua o máximo de tabelas possível. Você também pode clicar e arrastar tabelas para locais diferentes, colocando-as mais próximas umas das outras ou colocando-as em uma ordem específica. A movimentação de tabelas não afeta as relações já existentes entre elas. Para exibir todas as colunas em uma tabela específica, clique e arraste em uma borda de tabela expandi-la ou reduzi-la.  
  
2.  Clique na linha sólida entre o **DimCustomer** tabela e o **DimGeography** tabela. A linha sólida entre essas duas tabelas mostra que essa relação está ativa, ou seja, ela é usada por padrão durante o cálculo das fórmulas DAX.  
  
    Observe o **GeographyKey** coluna no **DimCustomer** tabela e o **GeographyKey** coluna o **DimGeography** agora aparecem cada dentro de uma caixa de tabela. Isso mostra que elas são as colunas usadas na relação. Agora, as propriedades da relação também são exibidas na janela **Propriedades** .  
  
    > [!TIP]  
    > Além de usar o designer de modelo na exibição de diagrama, você também pode usar a caixa de diálogo Gerenciar relações para mostrar as relações entre todas as tabelas em um formato de tabela. Clique com botão direito **relações** no Gerenciador de modelos de tabela e clique **gerenciar relações**. A caixa de diálogo Gerenciar relações mostra as relações que foram criadas automaticamente quando você importou os dados.  
  
3.  Use o designer de modelo na exibição de diagrama ou a caixa de diálogo Gerenciar relações, para verificar se as seguintes relações foram criadas quando cada uma das tabelas foi importada do banco de dados AdventureWorksDW:  
  
    |Ativa|Tabela|Tabela de Pesquisa Relacionada|  
    |----------|---------|------------------------|  
    |Sim|**DimCustomer [GeographyKey]**|**DimGeography [GeographyKey]**|  
    |Sim|**DimProduct [ProductSubcategoryKey]**|**DimProductSubcategory [ProductSubcategoryKey]**|  
    |Sim|**DimProductSubcategory [ProductCategoryKey]**|**DimProductCategory [ProductCategoryKey]**|  
    |Sim|**FactInternetSales [CustomerKey]**|**DimCustomer [CustomerKey]**|  
    |Sim|**FactInternetSales [ProductKey]**|**DimProduct [ProductKey]**|  
  
    Se qualquer uma das relações na tabela acima estiver ausente, verifique se o modelo inclui as tabelas a seguir: DimCustomer, DimDate, DimGeography, DimProduct, DimProductCategory, DimProductSubcategory e FactInternetSales. Se as tabelas da mesma conexão de fonte de dados forem importadas em momentos distintos, não será criada nenhuma relação entre essas tabelas; essa relações deverão ser criadas manualmente.  

### <a name="take-a-closer-look"></a>Uma visão mais detalhada
Na exibição de diagrama, você pode notar uma seta, um asterisco e um número de linhas que mostram a relação entre tabelas.

![como-tabela-lesson4-line](../analysis-services/media/as-tabular-lesson4-line.png)

A seta mostra a direção do filtro, que o asterisco mostra essa tabela é o lado muitos de cardinalidade da relação, e o 1 mostra que essa tabela é o um lado da relação. Se você precisar editar um relacionamento; Por exemplo, altere a direção da relação de filtro ou cardinalidade, clique duas vezes na linha da relação na exibição de diagrama para abrir a caixa de diálogo Editar relação.

![como tabular-lesson4-edição](../analysis-services/media/as-tabular-lesson4-edit.png)

Provavelmente, você nunca precisará editar um relacionamento. Esses recursos destinam-se para modelagem de dados avançados e estão fora do escopo deste tutorial. Para obter mais informações, consulte [bidirecional entre os filtros para modelos de tabela no SQL Server 2016 Analysis Services](../analysis-services/tabular-models/bi-directional-cross-filters-tabular-models-analysis-services.md).

Em alguns casos, talvez seja necessário criar relações adicionais entre tabelas no modelo para oferecer suporte a uma lógica corporativa específica. Para este tutorial, você precisa criar três relações adicionais entre as tabelas FactInternetSales e a tabela DimDate.  
  
#### <a name="to-add-new-relationships-between-tables"></a>Para adicionar novas relações entre tabelas  
  
1.  No designer de modelo, no **FactInternetSales** de tabela, clique e mantenha o **OrderDate** coluna, em seguida, arraste o cursor para o **data** coluna no  **DimDate** da tabela e, em seguida, solte.  

    Uma linha sólida aparece, indicando que você criou uma relação ativa entre o **OrderDate** coluna o **vendas pela Internet** tabela e o **data** coluna o **Data** tabela. 
  
      ![como tabular-lesson4-novo](../analysis-services/media/as-tabular-lesson4-new.png) 
  
    > [!NOTE]  
    > Ao criar relações, a direção de filtro e de cardinalidade entre a tabela primária e a tabela de pesquisa relacionada é selecionada automaticamente.  
  
2.  No **FactInternetSales** , clique e mantenha o **DueDate** coluna, em seguida, arraste o cursor para o **data** coluna no **DimDate** de tabela e, em seguida, solte.  
  
    Uma linha pontilhada aparece, indicando que você criou uma relação inativa entre a **DueDate** coluna o **FactInternetSales** tabela e o **data** coluna o  **DimDate** tabela. Você pode ter várias relações entre tabelas, mas só uma relação pode estar ativa por vez.  
  
3.  Finalmente, crie uma relação mais; no **FactInternetSales** de tabela, clique e mantenha o **ShipDate** coluna, em seguida, arraste o cursor para o **data** coluna no **DimDate** tabela e, em seguida, solte.  
    
     ![como-tabela-lesson4-newinactive](../analysis-services/media/as-tabular-lesson4-newinactive.png)
  
## <a name="whats-next"></a>O que vem a seguir?
Vá para a próxima lição: [lição 5: criar colunas calculadas](../analysis-services/lesson-5-create-calculated-columns.md).
  
  
  
