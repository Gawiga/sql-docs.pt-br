---
title: "Escolhendo uma gramática SQL | Microsoft Docs"
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
- SQL statements [ODBC], interoperability
- interoperability of SQL statements [ODBC], SQL grammar
- SQL grammar [ODBC], selecting
ms.assetid: 4e0d189b-e407-47e0-92a9-f9982230dd0e
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: cc1da3dfbe7f06e7d98430c5cec8fbaab3176971
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="choosing-an-sql-grammar"></a>Escolhendo uma gramática SQL
A primeira decisão a tomar quando construindo instruções SQL é qual gramática para usar. Além de gramáticas disponíveis de vários corpos de padrões, como Open Group, ANSI e ISO, praticamente todos os fornecedores DBMS define sua própria gramática, cada um deles varia do padrão.  
  
 [Apêndice c: gramática SQL](../../../odbc/reference/appendixes/appendix-c-sql-grammar.md), descreve a gramática SQL mínima que devem dar suporte a todos os drivers ODBC. Esta gramática é um subconjunto do nível de entrada do SQL-92. Os drivers podem suportar gramática adicional de acordo com o intermediário, completo ou FIPS 127-2 níveis de transição definidos por SQL-92. Para obter mais informações, consulte [SQL mínimo gramática](../../../odbc/reference/appendixes/sql-minimum-grammar.md) no Apêndice c: à gramática de SQL e SQL-92.  
  
 Apêndice C também define *sequências de escape* contendo gramática padrão para recursos de idioma disponíveis, como junções externas, que não são cobertos pela gramática de SQL-92. Para obter mais informações, consulte [sequências de Escape de ODBC](../../../odbc/reference/appendixes/odbc-escape-sequences.md) na gramática de SQL do apêndice c:, e [sequências de Escape](../../../odbc/reference/develop-app/escape-sequences.md), mais adiante nesta seção.  
  
 A gramática escolhido afeta como o driver processa a instrução. Drivers modifique SQL-92 SQL e as sequências de escape definidas pelo ODBC para SQL DBMS específico. Como a maioria das gramáticas do SQL se baseiam em um ou mais dos vários padrões, a maioria dos drivers fazer pouco ou nenhum para atender a esse requisito. Ele geralmente consiste apenas procurando as sequências de escape definidas pelo ODBC e substituí-los com a gramática de DBMS específico. Quando um driver de encontra a gramática não reconhece, ele pressupõe que a gramática é específico do DBMS e passa a instrução SQL sem modificação para a fonte de dados para execução.  
  
 Portanto, há realmente duas opções de gramática usar: a gramática de SQL-92 (e o sequências de escape de ODBC) e uma gramática DBMS específico. Dos dois, apenas a gramática de SQL-92 é interoperável, para que todos os aplicativos interoperáveis devem usá-lo. Aplicativos que não são interoperáveis podem usar a gramática de SQL-92 ou uma gramática DBMS específico. Específicas do DBMS gramáticas tem duas vantagens: eles podem explorar os recursos não cobertos por SQL-92, e eles são um pouco mais rápidos porque o driver não precisa modificá-las. O segundo recurso pode ser imposto parcialmente, definindo o atributo de instrução SQL_ATTR_NOSCAN, que interrompe o driver de pesquisa e substituição das sequências de escape.  
  
 Se a gramática de SQL-92 for usada, o aplicativo pode descobrir como ele é modificado pelo driver chamando **SQLNativeSql**. Isso geralmente é útil ao depurar aplicativos. **SQLNativeSql** aceita uma instrução SQL e retorna depois que o driver tenha modificado. Como essa função está no nível de conformidade a principal interface, há suporte por todos os drivers.