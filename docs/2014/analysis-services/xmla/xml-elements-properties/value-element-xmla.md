---
title: Valor de elemento (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- Value Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- microsoft.xml.analysis.value
- urn:schemas-microsoft-com:xml-analysis#Value
- http://schemas.microsoft.com/analysisservices/2003/engine#Value
helpviewer_keywords:
- Value element
ms.assetid: f87ca7f8-d9fe-4730-a706-5d50fcfe21df
caps.latest.revision: 14
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 8defb7fe2115bd1ea9ccb7b3f23b0717db8b9aef
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37263242"
---
# <a name="value-element-xmla"></a>Elemento Value (XMLA)
  Contém o valor desejado de um [atributo](attribute-element-xmla.md) elemento a ser adicionado por um [inserir](../xml-elements-commands/insert-element-xmla.md) comando, ou uma [célula](cell-element-xmla.md) elemento a ser atualizada por um [UpdateCells](../xml-elements-commands/updatecells-element-xmla.md)comando.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Attribute> <!-- or Cell --!>  
   ...  
   <Value>...</Value>  
   ...  
</Attribute>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Any (qualquer)|  
|Valor padrão|Nenhum|  
|Cardinalidade|1-1: elemento obrigatório que ocorre apenas uma única vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Atributo](attribute-element-xmla.md), [célula](cell-element-xmla.md)|  
|Elementos filho|Nenhum|  
  
## <a name="remarks"></a>Remarks  
 Para os elementos `Attribute`, o elemento `Value` contém o valor desejado que o membro deve conter depois que o comando `Insert` é confirmado. Para obter mais informações sobre a inserção de membros, consulte [inserindo, atualizando e descartando membros &#40;XMLA&#41;](../../multidimensional-models-scripting-language-assl-xmla/inserting-updating-and-dropping-members-xmla.md).  
  
 Para os elementos `Cell`, o elemento `Value` contém o valor desejado que a célula deve conter depois que o comando `UpdateCells` é confirmado. O valor real armazenado na tabela de writeback para aquela célula é a diferença entre o valor original da célula e o valor desejado da célula.  
  
 O tipo de dados usado por este elemento deve corresponder ao tipo de dados da célula a ser atualizado.  
  
 Para obter mais informações sobre atualização de células, consulte [Atualizando células &#40;XMLA&#41;](../../multidimensional-models-scripting-language-assl-xmla/updating-cells-xmla.md).  
  
## <a name="see-also"></a>Consulte também  
 [Elemento CellOrdinal &#40;XMLA&#41;](cellordinal-element-xmla.md)   
 [Inserir o elemento &#40;XMLA&#41;](../xml-elements-commands/insert-element-xmla.md)   
 [Elemento UpdateCells &#40;XMLA&#41;](../xml-elements-commands/updatecells-element-xmla.md)   
 [Propriedades &#40;XMLA&#41;](xml-elements-properties.md)  
  
  
