---
title: Usando funções de membro | Microsoft Docs
ms.custom: ''
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- kbMDX
helpviewer_keywords:
- member functions [MDX]
ms.assetid: 094c443f-0daa-4af7-801c-d2e1d686d755
caps.latest.revision: 24
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: 7df4670e57def09628b0ccca1be2c2b567aef3bb
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2018
---
# <a name="using-member-functions"></a>Usando as funções de membro
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Uma função de membro é uma função MDX válida que retorna um membro. As funções de membro, assim como as funções de tupla e de conjunto, são essenciais para negociar as estruturas multidimensionais encontradas no [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].  
  
 De muitas funções de membro em MDX, o mais importante é o **CurrentMember** função, que é usada para determinar o membro atual em uma hierarquia. A consulta a seguir ilustra como usá-lo, juntamente com o **pai**, **ancestral**, e **Prevmember** funções:  
  
 `WITH`  
  
 `//Returns the name of the currentmember on the Calendar hierarchy`  
  
 `MEMBER MEASURES.[CurrentMemberDemo] AS [Date].[Calendar].CurrentMember.Name`  
  
 `//Returns the name of the parent of the currentmember on the Calendar hierarchy`  
  
 `MEMBER MEASURES.[ParentDemo] AS [Date].[Calendar].CurrentMember.Parent.Name`  
  
 `//Returns the name of the ancestor of the currentmember on the Calendar hierarchy at the Year level`  
  
 `MEMBER MEASURES.[AncestorDemo] AS ANCESTOR([Date].[Calendar].CurrentMember, [Date].[Calendar].[Calendar Year]).Name`  
  
 `//Returns the name of the member before the currentmember on the Calendar hierarchy`  
  
 `MEMBER MEASURES.[PrevMemberDemo] AS [Date].[Calendar].CurrentMember.Prevmember.Name`  
  
 `SELECT{MEASURES.[CurrentMemberDemo],MEASURES.[ParentDemo],MEASURES.[AncestorDemo],MEASURES.[PrevMemberDemo] } ON 0,`  
  
 `[Date].[Calendar].MEMBERS ON 1`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>Consulte Também  
 [Funções &#40; Sintaxe MDX &#41;](../mdx/functions-mdx-syntax.md)   
 [Usando funções de tupla](../mdx/using-tuple-functions.md)   
 [Usando funções de conjunto](../mdx/using-set-functions.md)  
  
  
