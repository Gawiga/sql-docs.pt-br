---
title: Vs regulares. Conexões de contexto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: clr
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: a1dead02-be88-4b16-8cb2-db1284856764
caps.latest.revision: 13
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 3ba21a813e019b94a51ad6a43e45faf64cd9f7b2
ms.sourcegitcommit: 022d67cfbc4fdadaa65b499aa7a6a8a942bc502d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37352548"
---
# <a name="regular-vs-context-connections"></a>Vs regulares. Conexões de contexto
  Se você estiver conectando a um servidor remoto, sempre use conexões normais, em vez de conexões de contexto. Se você precisar se conectar ao mesmo servidor em que o procedimento armazenado ou a função está sendo executado, use a conexão de contexto na maioria dos casos. Isto tem benefícios, como executar no mesmo espaço de transação e não precisar se autenticar novamente.  
  
 Além disso, o uso da conexão de contexto normalmente resulta em melhor desempenho e menos uso de recurso. A conexão de contexto é uma conexão apenas em processo, portanto, ela pode contatar o servidor "diretamente", ignorando o protocolo de rede e as camadas de transporte, para enviar instruções Transact-SQL e receber resultados. O processo de autenticação é ignorado também. A figura a seguir mostra os principais componentes do provedor gerenciado por `SqlClient`, e também como os diferentes componentes interagem entre si durante o uso de uma conexão normal e da conexão de contexto.  
  
 ![Caminhos de código de um contexto e uma conexão regular. ] (../../../database-engine/dev-guide/media/clrintdataaccess.gif "Caminhos de código de um contexto e uma conexão regular.")  
  
 A conexão de contexto segue um caminho de código mais curto e envolve menos componentes. Dessa forma, você pode esperar que as solicitações e os resultados sejam enviados e recebidos do servidor mais rapidamente do que em uma conexão normal. O tempo de execução da consulta no servidor é o mesmo para conexões de contexto e normais.  
  
 Há alguns casos em que você pode precisar abrir uma conexão normal separada para o mesmo servidor. Por exemplo, há certas restrições sobre como usar a conexão de contexto, descrito em [restrições em conexões de contexto e normais](context-connections-and-regular-connections-restrictions.md).  
  
## <a name="see-also"></a>Consulte também  
 [Conexão de contexto](context-connection.md)  
  
  
