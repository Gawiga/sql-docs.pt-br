---
title: '&lt;(Menor que) (DMX) | Microsoft Docs'
ms.custom: 
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: DMX
helpviewer_keywords:
- less than (<)
- < (less than operator)
ms.assetid: 61d257ce-7ffd-4124-a795-49e5f8a6d72f
caps.latest.revision: "16"
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: 84e143bd63a0156d212336cac12ac932c4cb710d
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2017
---
# <a name="lt-less-than-dmx"></a>&lt;(Menor que) (DMX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Realiza uma operação de comparação que determina se o valor de uma expressão DMX (Data Mining Extensions) é menor do que o valor de outra expressão DMX.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
DMX_Expression < DMX_Expression  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *DMX_Expression*  
 Expressão DMX válida.  
  
## <a name="return-value"></a>Valor de retorno  
 Valor Booliano que conterá TRUE, se ambos os parâmetros forem não nulos, e se o primeiro parâmetro tiver um valor menor do que o valor do segundo parâmetro. O valor booliano conterá FALSE se ambos os parâmetros forem não nulos e se o primeiro parâmetro tiver um valor igual a ou maior do que o valor do segundo parâmetro. O valor Booliano conterá um valor nulo se um ou ambos os parâmetros forem avaliados como um valor nulo.  
  
## <a name="see-also"></a>Consulte também  
 [Operadores de comparação &#40; DMX &#41;](../dmx/operators-comparison.md)   
 [Extensões de mineração de dados &#40; DMX &#41; Referência de operador](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [Operadores &#40; DMX &#41;](../dmx/operators-dmx.md)  
  
  
