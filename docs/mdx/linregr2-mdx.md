---
title: LinRegR2 (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 42c703e703e8c557b4de8466a0cd1b686217fd4b
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34742055"
---
# <a name="linregr2-mdx"></a>LinRegR2 (MDX)


  Calcula a regressão linear de um conjunto e retorna o coeficiente de determinação, R<sup>2</sup>.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
LinRegR2(Set_Expression, Numeric_Expression_y [ ,Numeric_Expression_x ] )  
```  
  
## <a name="arguments"></a>Argumentos  
 *Set_Expression*  
 Uma expressão MDX (Multidimensional Expressions) válida que retorna um conjunto.  
  
 *Numeric_Expression_y*  
 Uma expressão numérica válida, geralmente uma linguagem MDX de coordenadas de célula, que retorna um número que representa valores do eixo y.  
  
 *Numeric_Expression_x*  
 Uma expressão numérica válida, geralmente uma linguagem MDX de coordenadas de célula, que retorna um número que representa valores do eixo x.  
  
## <a name="remarks"></a>Remarks  
 A regressão linear, que usa o método dos mínimos quadrados, calcula a equação de uma linha de regressão (ou seja, a linha mais adequada para uma série de pontos). A linha de regressão tem a seguinte equação, onde um é a inclinação e b é a interceptação:  
  
 y = ax+b  
  
 O **LinRegR2** função avalia o setagainst especificado o expressionto numérico primeiro obter os valores do eixo y. Em seguida, a função avalia o conjunto especificado em relação à segunda expressão numérica, se especificada, para obter os valores para o eixo x. O segundo expressionis numéricos se não for especificado, a função usa o contexto atual das células no conjunto especificado como valores para o eixo x. Não especificar o axisargument x frequentemente é usada com a dimensão de tempo.  
  
 Depois de obter o conjunto de pontos, o **LinRegR2** função retorna a estatística R<sup>2</sup> que descreve o ajuste da equação linear aos pontos.  
  
> [!NOTE]  
>  O **LinRegR2** função ignora células vazias ou células que contêm texto ou valores lógicos. Porém, a função contém células com valores zero.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir retorna a estatística R<sup>2</sup> que descreve a adequação do ajuste da equação de regressão linear aos pontos para as vendas de unidade e as medidas de vendas de armazenamento.  
  
```  
LinRegR2(LastPeriods(10), [Measures].[Unit Sales],[Measures].[Store Sales])  
```  
  
## <a name="see-also"></a>Consulte também  
 [Referência de função MDX &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
