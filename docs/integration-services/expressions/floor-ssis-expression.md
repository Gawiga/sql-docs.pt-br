---
title: FLOOR (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- largest integer less than or equal to expression
- FLOOR function [SSIS]
ms.assetid: 168084db-badd-40f2-87b4-1f5bc45c3e24
caps.latest.revision: 33
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 3a79328a87c3b28f814c70c394b8a3e92aeaa6c7
ms.sourcegitcommit: cc46afa12e890edbc1733febeec87438d6051bf9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2018
ms.locfileid: "35411388"
---
# <a name="floor-ssis-expression"></a>FLOOR (Expressão SSIS)
  Retorna o maior inteiro que é menor que ou igual a uma expressão numérica.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
FLOOR(numeric_expression)  
```  
  
## <a name="arguments"></a>Argumentos  
 *numeric_expression*  
 É uma expressão numérica válida.  
  
## <a name="result-types"></a>Tipos de resultado  
 O tipo de dados numérico da expressão do argumento. O resultado é a parte inteira do valor calculado no mesmo tipo de dados que *numeric_expression.*  
  
## <a name="remarks"></a>Remarks  
 FLOOR retornará um resultado nulo se o argumento for nulo.  
  
## <a name="expression-examples"></a>Exemplos de expressões  
 Estes exemplos aplicam a função FLOOR aos valores positivos, negativos e zerados.  
  
```  
FLOOR(123.45)  
```  
  
 Retorna 123.00  
  
```  
FLOOR(-123.45)  
```  
  
 Retorna -124.00  
  
```  
FLOOR(0.00)  
```  
  
 Retorna 0.00  
  
## <a name="see-also"></a>Consulte Também  
 [CEILING &#40;Expressão do SSIS&#41;](../../integration-services/expressions/ceiling-ssis-expression.md)   
 [Funções &#40;Expressão do SSIS&#41;](../../integration-services/expressions/functions-ssis-expression.md)  
  
  
