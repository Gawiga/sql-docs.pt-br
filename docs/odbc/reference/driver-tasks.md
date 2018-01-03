---
title: Tarefas de driver | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: odbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ODBC architecture [ODBC], drivers
- drivers [ODBC], tasks
ms.assetid: 184c795a-c2e8-4d20-9902-12e60b2f0e45
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 43111027bc82c15d80505d3ffbe25ba4d25e633e
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="driver-tasks"></a>Tarefas de driver
As tarefas específicas realizadas por drivers incluem:  
  
-   A conexão e desconexão da fonte de dados.  
  
-   Verificação de erros de função não verificados pelo Gerenciador de Driver.  
  
-   Iniciando transações; Isso é transparente para o aplicativo.  
  
-   Enviar instruções SQL para a fonte de dados para execução. O driver deve modificar ODBC SQL para SQL DBMS específico; Isso geralmente é limitado a substituição de cláusulas de fuga definidas pelo ODBC com o SQL DBMS específico.  
  
-   Enviar dados para e recuperar dados da fonte de dados, incluindo conversão de tipos de dados conforme especificado pelo aplicativo.  
  
-   Mapeando erros específicos de DBMS para SQLSTATEs do ODBC.
