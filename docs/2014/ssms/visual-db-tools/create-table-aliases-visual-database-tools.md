---
title: Criar aliases de tabelas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- table aliases [SQL Server]
- aliases [SQL Server], tables
ms.assetid: 49e61e85-8abf-4ca7-8c70-7e9f8f1078bd
caps.latest.revision: 10
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: a98f093964ae44dbb6bc301585d8a37e3bc3c296
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37327016"
---
# <a name="create-table-aliases-visual-database-tools"></a>Criar aliases de tabelas (Visual Database Tools)
  Os aliases podem facilitar o trabalho com nomes de tabela. Usar aliases é útil quando:  
  
-   Você quer tornar a instrução no [Painel SQL](visual-database-tools.md) mais curta e fácil de ser lida.  
  
-   Você se refere frequentemente ao nome de tabela em sua consulta - como em nomes de coluna qualificativos - e quer estar seguro de estar dentro de um limite de comprimento de caracteres específico na sua consulta (alguns bancos de dados impõem um comprimento máximo para as consultas).  
  
-   Você está trabalhando com várias instâncias da mesma tabela (como em uma autojunção) e precisa um modo para se referir a uma instância ou a outra.  
  
 Por exemplo, você pode criar um alias `"e"` para um nome de tabela `employee`_`information`e então referir-se à tabela como `"e"` durante o resto da consulta.  
  
### <a name="to-create-an-alias-for-a-table-or-table-valued-object"></a>Para criar um alias para uma tabela ou objeto com valor de tabela  
  
1.  Adicione a tabela ou o objeto com valor de tabela à sua consulta.  
  
2.  No **Painel de Diagrama**, clique com o botão direito do mouse no objeto para o qual você deseja criar um alias e selecione **Propriedades** no menu de atalho.  
  
3.  Na janela **Propriedades** , digite o alias no campo **Alias** .  
  
## <a name="see-also"></a>Consulte também  
 [Adicionar tabelas a consultas &#40;Visual Database Tools&#41;](add-tables-to-queries-visual-database-tools.md)   
 [Classificar e agrupar resultados da consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md)   
 [Resumir resultados da consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md)   
 [Executar operações básicas com consultas &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
