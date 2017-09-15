---
title: Drivers baseados em DBMS | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drivers [ODBC], DBMS-based drivers
- DBMS-based drivers [ODBC]
- ODBC architecture [ODBC], drivers
ms.assetid: e2208ee0-4cd6-4f0d-bb71-a0b54f7d9330
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 09265543685ea8fd573ee20bea90093f920b6e49
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="dbms-based-drivers"></a>Drivers baseados em DBMS
Drivers baseados em DBMS são usados com fontes de dados como Oracle ou SQL Server que fornecem um mecanismo de banco de dados independente para usar o driver. Esses drivers acessam os dados físicos por meio do mecanismo autônomo; ou seja, eles enviar instruções SQL e recuperar os resultados do mecanismo.  
  
 Como drivers baseados em DBMS usam um mecanismo de banco de dados existente, eles são geralmente mais fácil de escrever de drivers baseados em arquivo. Embora um driver de DBMS pode ser facilmente implementado traduzindo chamadas ODBC para chamadas à API nativas, isso resulta em um driver mais lento. Uma maneira melhor de como implementar um driver de DBMS é usar o protocolo de fluxo de dados subjacente, que normalmente é o que faz a API nativa. Por exemplo, um driver do SQL Server deve usar o protocolo TDS (o fluxo de protocolo para o SQL Server) em vez de biblioteca de banco de dados (a API nativa para o SQL Server). Uma exceção a essa regra é quando o ODBC é a API nativa. Por exemplo, Watcom SQL é um mecanismo autônomo que reside no mesmo computador que o aplicativo e é carregado diretamente, pois o driver.  
  
 Drivers baseados em DBMS atuam como o cliente em uma configuração de cliente/servidor em que a fonte de dados atua como um servidor. Na maioria dos casos, o cliente (driver) e o servidor (fonte de dados) residem em computadores diferentes, embora ambos podem residir no mesmo computador que executa um sistema operacional multitarefa. Uma terceira possibilidade é um *gateway,* que fica entre o driver e a fonte de dados. Um gateway é uma parte do software que faz com que um DBMS para se parecer com o outro. Por exemplo, aplicativos escritos para usar o SQL Server também podem acessar dados do DB2 por meio do Gateway de DB2 Micro Decisionware; Este produto faz com que o DB2 para se parecer com o SQL Server.  
  
 A ilustração a seguir mostra três diferentes configurações de drivers baseados em DBMS. A primeira configuração, o driver e a fonte de dados residem no mesmo computador. No segundo, o driver e a fonte de dados residem em computadores diferentes. No terceiro, o driver e a fonte de dados que residem em computadores diferentes e um gateway fica entre eles, que residem em outra máquina.  
  
 ![Três configurações para o DBMS &#45; drivers com base](../../odbc/reference/media/pr07.gif "pr07")