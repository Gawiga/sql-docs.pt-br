---
title: SQL estático | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- static SQL [ODBC]
- SQL [ODBC], embedded SQL
- SQL statements [ODBC], embedded SQL
- SQL statements [ODBC], static SQL
- embedded SQL [ODBC]
- SQL [ODBC], static SQL
ms.assetid: 667d92ec-fed9-4028-81d4-bb9ba867356a
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: ff2144ae69c48098324bc0b97ca9c33d5159adc3
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32915171"
---
# <a name="static-sql"></a>SQL Estático
O embedded SQL mostrado na [exemplo do Embedded SQL](../../odbc/reference/embedded-sql-example.md) é conhecido como SQL estático. Ele é chamado SQL estático porque as instruções SQL no programa são estáticas; ou seja, elas não se alteram cada vez que o programa é executado. Conforme descrito na seção anterior, essas instruções são compiladas quando o restante do programa é compilado.  
  
 SQL estático funciona bem em muitas situações e pode ser usado em qualquer aplicativo para o qual o acesso a dados pode ser determinado em tempo de design do programa. Por exemplo, um programa de entrada de ordem sempre usa a mesma instrução para inserir um novo pedido e um sistema de reserva aérea sempre usa a mesma instrução para alterar o status de uma estação de disponível reservada. Cada uma dessas instruções deve ser generalizada com o uso de variáveis do host; valores diferentes podem ser inseridos em uma ordem de venda e estações diferentes podem ser reservadas. Como tais instruções podem ser codificados no programa, esses programas têm a vantagem de que as instruções precisam ser analisado, validado e otimização de uma só vez, em tempo de compilação. Isso resulta em código relativamente rápido.
