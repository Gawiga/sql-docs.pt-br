---
title: Noções básicas sobre transações em tabelas com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: in-memory-oltp
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 06075248-705e-4563-9371-b64cd609793c
caps.latest.revision: 7
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 931eaa8ad51c277657c3a9f86402d4759ad0d671
ms.sourcegitcommit: 79d4dc820767f7836720ce26a61097ba5a5f23f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2018
ms.locfileid: "40395207"
---
# <a name="understanding-transactions-on-memory-optimized-tables"></a>Compreendendo transações em tabelas com otimização de memória
  As transações acessam as tabelas com otimização de memória usando um formulário de controle de simultaneidade otimista e de várias versões. Isso significa que há versões diferentes de dados. Cada transação opera sua própria versão do banco de dados consistente transacionalmente, independentemente de outras transações simultaneamente em execução. Além disso, as transações operam sob a suposição otimista de que não haverá conflitos com outras transações simultâneas. Isso evita a necessidade de usar bloqueios, mas exige que o sistema detecte conflitos e encerre uma das transações conflitantes. Conflitos podem ocorrer apenas em transações de gravação/gravação e em transações de leitura/gravação. Se houver um conflito de gravação/gravação, uma transação de gravação será encerrada.  
  
 Há semelhanças entre o controle de simultaneidade para tabelas com otimização de memória e o controle de simultaneidade para tabelas baseadas em disco, para os níveis de isolamento da transação READ_COMMITTED_SNAPSHOT e SNAPSHOT. (Para obter mais informações sobre tabelas baseadas em disco, consulte [Níveis de isolamento com base em controle de versão de linha no mecanismo de banco de dados](http://msdn.microsoft.com/library/ms177404\(v=sql.100\).aspx).)  
  
## <a name="topics-in-this-section"></a>Tópicos desta seção  
 Esta seção sobre transações em tabelas com otimização de memória inclui os seguintes tópicos:  
  
-   [Diretrizes para níveis de isolamento da transação com tabelas com otimização de memória](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
-   [Diretrizes para lógica de repetição das transações em tabelas com otimização de memória](guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)  
  
-   [Transações em tabelas com otimização de memória](transactions-in-memory-optimized-tables.md)  
  
-   [Níveis de isolamento da transação](transaction-isolation-levels.md)  
  
-   [Transações entre contêineres](cross-container-transactions.md)  
  
 Para obter mais informações, veja [Controlar a durabilidade da transação](../relational-databases/logs/control-transaction-durability.md).  
  
## <a name="see-also"></a>Consulte também  
 [Tabelas com otimização de memória](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
  
