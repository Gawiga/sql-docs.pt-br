---
title: 'Lição 2: Criando um cenário de previsão (Tutorial de mineração de dados intermediário) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- time series [Analysis Services]
- data mining [Analysis Services], tutorials
- tutorials [Data Mining]
ms.assetid: 9a988156-c900-4c22-97fa-f6b0c1aea9e2
caps.latest.revision: 31
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 5db75cbdabd62b569c782bd48755ce817819a475
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37155497"
---
# <a name="lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial"></a>Lição 2: Criando um cenário de previsão (Tutorial de data mining intermediário)
  Como analista de vendas da [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], foi solicitado que você fizesse a previsão das vendas de produtos para o próximo ano. Em particular, você deverá comparar previsões para regiões e linhas de produto diferentes. Adicionalmente, foi pedido que você determinasse se há variação nas vendas de produtos diferentes, dependendo da época do ano.  
  
 Para localizar as informações solicitadas, nesta lição você resumirá os dados de vendas da empresa, mês a mês, e também resumirá os valores de vendas por três regiões: Europa, América do Norte e Pacífico.  
  
 Depois que completar as tarefas desta lição, você estará apto a responder às seguintes perguntas:  
  
-   Como as vendas de diferentes modelos de bicicleta mudam ao longo do tempo?  
  
-   Há diferenças entre os padrões para vendas nas três regiões?  
  
-   Podemos prever picos de vendas?  
  
 A lição pode ser concluída em duas partes:  
  
-   A parte Um apresenta os fundamentos de como criar e usar um modelo de série temporal.  
  
-   A Parte Dois orienta você na criação de um modelo de série temporal geral, baseado em todas as regiões. Você pode usar esse modelo geral para *previsão cruzada*.  
  
 Para concluir as tarefas nesta lição, que estão listados abaixo, você usará o [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] da fonte de dados que você criou na [lição 1: Criando a solução de mineração de dados intermediário &#40;Tutorial intermediário de mineração de dados&#41; ](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md).  
  
> [!WARNING]  
>  As datas no [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] banco de dados de exemplo foram atualizados para esta versão. Se você usar uma versão anterior do [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], poderá criar o modelo seguindo estas etapas, mas poderá ver resultados diferentes.  
  
 **Criando um modelo de previsão Simple**  
  
-   [Adicionando dados de um exibição da fonte para a previsão de &#40;Tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial.md)  
  
-   [Criando uma estrutura de previsão e um modelo &#40;Tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/creating-a-forecasting-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [Modificando a estrutura de previsão &#40;Tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/modifying-the-forecasting-structure-intermediate-data-mining-tutorial.md)  
  
-   [Personalizando e processando o modelo de previsão &#40;Tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/customize-process-forecasting-model-intermediate-data-mining-tutorial.md)  
  
-   [Explorando o modelo de previsão &#40;Tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/exploring-the-forecasting-model-intermediate-data-mining-tutorial.md)  
  
-   [Criando previsões de série temporal &#40;Tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/creating-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
 **Criando um modelo de previsão geral para previsão cruzada**  
  
-   [Advanced previsões de série temporal &#40;Tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/advanced-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
-   [Usando dados atualizados de previsões de série temporal &#40;Tutorial intermediário de mineração de dados&#41;](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
-   [Usando dados de substituição de previsões de série temporal &#40;Tutorial intermediário de mineração de dados&#41;](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
-   [Comparando previsões para modelos de previsão &#40;Tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/comparing-predictions-for-forecasting-models-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a>Próxima tarefa da lição  
 [Adicionando dados de um exibição da fonte para a previsão de &#40;Tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial.md)  
  
 [Noções básicas sobre os requisitos para uma série de tempo de modelo &#40;Tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/time-series-model-requirements-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a>Todas as lições  
 [Lição 1: Criando a solução de mineração de dados intermediário &#40;Tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 Lição 2: Cenário de previsão (tutorial de data mining intermediário)  
  
 [Lição 3: Criando um cenário de cesta de compras &#40;Tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 [Lição 4: Criando um cenário de Clustering de sequências &#40;Tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [Lição 5: Criando a rede Neural e modelos de regressão logística &#40;Tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a>Consulte também  
 [Tutorial de mineração de dados básicos](../../2014/tutorials/basic-data-mining-tutorial.md)   
 [Tutorial de mineração de dados intermediário &#40;Analysis Services - mineração de dados&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)   
 [Algoritmo Microsoft Time Series](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
