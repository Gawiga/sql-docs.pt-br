---
title: Adicionar uma expressão (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: a60ee091-b4ed-41e1-9b6a-032c316cd03f
caps.latest.revision: 8
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: 072af31ff2207822e7e9f1aa63e7d5582550d0dc
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37317947"
---
# <a name="add-an-expression-report-builder-and-ssrs"></a>Adicionar uma expressão (Construtor de Relatórios e SSRS)
  As expressões são usadas em um relatório inteiro para definir as propriedades de itens de relatório, os filtros, os grupos, a ordem de classificação, as cadeias de conexão e os valores de parâmetro. As expressões começam com o sinal de igual (=) e são gravadas no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]. Elas são avaliadas durante a execução pelo processador de relatório, que combina o resultado da avaliação com os elementos de layout do relatório.  
  
 As expressões podem ser simples ou complexas. Uma expressão simples faz referência a um único item de uma coleção interna. As expressões complexas podem conter constantes, operadores, itens de coleção global e chamadas de função. Para obter mais informações, consulte [Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md).  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-expression-to-a-text-box"></a>Para adicionar uma expressão a uma caixa de texto  
  
-   No modo **Design** , clique na caixa de texto na superfície de design à qual você deseja adicionar uma expressão.  
  
    -   No caso de uma expressão simples, digite na caixa de texto o texto para exibição da expressão. Por exemplo, para o campo de conjunto de dados Vendas, digite `[Sales]`.  
  
    -   No caso de uma expressão complexa, clique com o botão direito do mouse na caixa de texto e selecione **Expressão**. A caixa de diálogo **Expressão** é aberta. Digite ou crie a expressão interativamente após o sinal '=' no painel Expressão e clique em OK.  
  
         A expressão aparece na superfície de design como `<<Expr>>`.  
  
## <a name="see-also"></a>Consulte também  
 [Formatando texto e espaços reservados &#40;relatórios e SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md)   
 [Caixas de texto &#40;relatórios e SSRS&#41;](text-boxes-report-builder-and-ssrs.md)   
 [Usos de expressões em relatórios &#40;relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md)   
 [Exemplos de equações de filtro &#40;relatórios e SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md)   
 [Exemplos de expressões de grupo &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md)   
 [Caixa de diálogo Expressão &#40;Construtor de Relatórios&#41;](../expression-dialog-box-report-builder.md)   
 [Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md)   
 [Adicionar um código a um relatório &#40;SSRS&#41;](add-code-to-a-report-ssrs.md)  
  
  
