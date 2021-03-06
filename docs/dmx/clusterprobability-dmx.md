---
title: ClusterProbability (DMX) | Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: d4d8ce16bb07af07bd2bfd651cf5fc1ae15b7e08
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38030272"
---
# <a name="clusterprobability-dmx"></a>ClusterProbability (DMX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Retorna a probabilidade de que o caso de entrada pertença ao cluster especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
ClusterProbability([<Node_Caption>])  
```  
  
## <a name="applies-to"></a>Aplica-se a  
 Essa função só pode ser usada se o modelo de mineração de dados subjacente oferecer suporte a clustering.  
  
## <a name="return-type"></a>Tipo de retorno  
 Valor escalar.  
  
## <a name="remarks"></a>Remarks  
 A sintaxe a seguir usa o conjunto de linhas do esquema de conteúdo do modelo de mineração para retornar as legendas de nó que existem no modelo de mineração.  
  
```  
SELECT NODE_CAPTION FROM <model>.CONTENT  
```  
  
 Para obter mais informações sobre como usar essa sintaxe, consulte [SELECT FROM &#60;modelo&#62;. CONTEÚDO &#40;DMX&#41;](../dmx/select-from-model-content-dmx.md). Para obter mais informações sobre o conjunto de linhas de esquema de conteúdo de modelo de mineração, consulte [conjunto de linhas DMSCHEMA_MINING_MODEL_CONTENT](../analysis-services/schema-rowsets/data-mining/dmschema-mining-model-content-rowset.md).  
  
 Se um \<legenda de nó > não for especificado, a função retorna a probabilidade de que os casos de entrada pertencem ao cluster mais provável. Use o **Cluster** função para retornar o cluster mais provável.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir retorna a probabilidade de que caso especificado exista no cluster rotulado de Cluster 2.  
  
```  
SELECT  
  ClusterProbability('Cluster 2')  
From  
  [TM Clustering]  
NATURAL PREDICTION JOIN  
(SELECT 28 AS [Age],  
  '2-5 Miles' AS [Commute Distance],  
  'Graduate Degree' AS [Education],  
  0 AS [Number Cars Owned],  
  0 AS [Number Children At Home]) AS t  
```  
  
## <a name="see-also"></a>Consulte também  
 [Cluster &#40;DMX&#41;](../dmx/cluster-dmx.md)   
 [Extensões de mineração de dados &#40;DMX&#41; referência de função](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Funções &#40;DMX&#41;](../dmx/functions-dmx.md)   
 [Funções de previsão gerais &#40;DMX&#41;](../dmx/general-prediction-functions-dmx.md)  
  
  
