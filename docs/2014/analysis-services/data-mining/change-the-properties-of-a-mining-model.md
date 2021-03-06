---
title: Alterar as propriedades de um modelo de mineração | Microsoft Docs
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
- mining models [Analysis Services], properties
- properties [data mining]
ms.assetid: aefaeb7f-d174-48d1-a188-0987a3b1196b
caps.latest.revision: 38
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: ed77c0d87fc6fb62497cc68c52dd3fabeb50d2ab
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37279803"
---
# <a name="change-the-properties-of-a-mining-model"></a>Alterar as propriedades de um modelo de mineração
  Algumas propriedades de modelo de mineração se aplicam ao modelo como um todo, enquanto outras propriedades de modelo se aplicam a colunas individuais. Exemplos de propriedades que se aplicam ao modelo inteiro seriam a `Drillthrough` propriedade, que especifica se os dados de caso devem estar disponíveis para consulta, e o `Description` propriedade. Propriedades que se aplicam à coluna incluem `Usage` e `ModelingFlags`, que controlam como os dados na coluna são usados no modelo.  
  
 As propriedades modelo a seguir têm editores avançados que você pode usar para criar expressões ou configurar propriedades de modelo complexas. Estas propriedades oferecem:  
  
-   `Filter` propriedade: abre a [Data Set filtro or Model filtro Dialog Box](../data-set-filter-or-model-filter-dialog-box.md).  
  
-   `AlgorithmParameters` propriedade: abre a [caixa de diálogo de parâmetros de algoritmo &#40;exibição de modelos de mineração&#41;](../algorithm-parameters-dialog-box-mining-models-view.md).  
  
 Para obter informações sobre como definir as propriedades em um modelo de mineração, consulte [Colunas do modelo de mineração](mining-model-columns.md).  
  
### <a name="to-change-the-properties-of-a-mining-model"></a>Para alterar as propriedades de um modelo de mineração  
  
1.  Na guia **Modelos de Mineração** do Designer de Data Mining, clique com o botão direito do mouse no cabeçalho da coluna que contém o nome do modelo de mineração ou na linha da grade que contém o nome do algoritmo de mineração e selecione **Propriedades**.  
  
2.  Na janela **Propriedades** na lateral direita da tela, realce o valor que corresponde à propriedade que você deseja alterar e digite o novo valor.  
  
     O novo valor entrará em vigor quando você selecionar um elemento diferente no designer.  
  
### <a name="to-change-the-properties-of-a-mining-model-column"></a>Para alterar as propriedades de uma coluna de modelo de mineração  
  
1.  Na guia **Modelos de Mineração** no Designer de Data Mining, clique com o botão direito do mouse na célula da grade na interseção da coluna da estrutura de mineração e do modelo de mineração e selecione **Propriedades**.  
  
2.  Na janela **Propriedades** na lateral direita da tela, realce o valor que corresponde à propriedade que você deseja alterar e digite o novo valor.  
  
    > [!NOTE]  
    >  Se o uso da coluna for definido como `Ignore`, o **propriedades** janela para a coluna está em branco.  
  
     O novo valor entrará em vigor quando você selecionar um elemento diferente no designer.  
  
## <a name="see-also"></a>Consulte também  
 [Tarefas e instruções do modelo de mineração](mining-model-tasks-and-how-tos.md)  
  
  
