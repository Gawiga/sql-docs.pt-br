---
title: Habilitar o detalhamento para um modelo de mineração | Microsoft Docs
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
- data mining [Analysis Services], how-to topics
- drillthrough [Analysis Services]
ms.assetid: 4fa44f60-ef9a-4b59-98c0-c0baf1195c8e
caps.latest.revision: 27
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 93793f4a13d3d590ecf031addb8e11f1d93f11e3
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37273522"
---
# <a name="enable-drillthrough-for-a-mining-model"></a>Habilitar o detalhamento para um modelo de mineração
  Se você habilitou o detalhamento para um modelo de mineração, quando você procurar o modelo, poderá recuperar informações detalhadas sobre os casos usados para criar o modelo. Para exibir essas informações, você deve ter as permissões necessárias e a estrutura já deve ter sido processada.  
  
 **Permissões** Para que um usuário analise detalhadamente os dados do modelo ou da estrutura, ele deve ser membro de uma função que tenha permissões [AllowDrillThrough](../scripting/properties/allowdrillthrough-element-assl.md) no modelo ou na estrutura de mineração. As permissões de detalhamento são definidas separadamente na estrutura e no modelo.  
  
-   As permissões de detalhamento no modelo lhe permitem detalhar do modelo, mesmo que você não tenha permissões na estrutura.  
  
-   As permissões para detalhamento na estrutura fornecem a capacidade adicional de incluir colunas de estrutura em consultas de detalhamento do modelo, usando a função [StructureColumn &#40;DMX&#41;](/sql/dmx/structurecolumn-dmx). Você também pode consultar os casos de teste e treinamento na estrutura usando a sintaxe SELECT… DE \<estrutura >. Sintaxe de casos.  
  
 **Cache de casos de treinamento** O detalhamento funciona recuperando informações sobre os casos de treinamento na estrutura de mineração. Essas informações são armazenadas em cache quando a estrutura é processada. Portanto, se você optar por limpar todos os dados em cache alterando a <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> propriedade para `ClearAfterProcessing`, detalhamento não funcionará.  
  
> [!NOTE]  
>  Se os casos de treinamento não tiverem sido armazenados em cache, você deverá alterar a propriedade <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> para **KeepTrainingCases** e processar o modelo novamente, antes de exibir os dados do caso.  
  
 Para obter mais informações, consulte [Drillthrough Queries &#40;Data Mining&#41;](drillthrough-queries-data-mining.md).  
  
### <a name="to-enable-drillthrough-on-a-mining-model"></a>Como habilitar o detalhamento em um modelo de mineração  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], na guia **Modelos de Mineração** do Designer de Mineração de Dados, clique com o botão direito do mouse no nome do modelo de mineração no qual você deseja habilitar o detalhamento e selecione **Propriedades**.  
  
2.  Nas janelas **Propriedades** , clique em **AllowDrillthrough**e selecione **True**.  
  
3.  Na guia **Modelos de Mineração** , clique com o botão direito do mouse no modelo e selecione **Modelo de Processo**.  
  
### <a name="to-enable-caching-for-a-mining-structure"></a>Para habilitar o cache para uma estrutura de mineração  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], na guia **Estrutura de Mineração** do Designer de Mineração de Dados, clique com o botão direito do mouse no nome da estrutura de mineração.  
  
2.  Abra a janela **Propriedades** .  
  
3.  Na janela **Propriedades** , localize a propriedade **CacheMode** e selecione **KeepTrainingCases** na lista.  
  
4.  No menu **Banco de Dados** , selecione **Processo**.  
  
## <a name="see-also"></a>Consulte também  
 [Consultas de detalhamento &#40;mineração de dados&#41;](drillthrough-queries-data-mining.md)  
  
  
