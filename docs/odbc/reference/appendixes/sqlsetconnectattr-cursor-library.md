---
title: SQLSetConnectAttr (biblioteca de Cursor) | Microsoft Docs
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
- SQLSetConnectAttr function [ODBC], Cursor Library
ms.assetid: 6f70bbd0-a057-49ef-8b05-4c80b58fc6e6
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d10356488b0a590fb065c49a36a05f0e9b976991
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32907701"
---
# <a name="sqlsetconnectattr-cursor-library"></a>SQLSetConnectAttr (biblioteca de Cursor)
> [!IMPORTANT]  
>  Este recurso será removido em uma versão futura do Windows. Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam. A Microsoft recomenda o uso da funcionalidade de cursor do driver.  
  
 Este tópico discute o uso do **SQLSetConnectAttr** função na biblioteca de cursor. Para obter informações gerais sobre **SQLSetConnectAttr**, consulte [função SQLSetConnectAttr](../../../odbc/reference/syntax/sqlsetconnectattr-function.md).  
  
 Um aplicativo chama **SQLSetConnectAttr** com o atributo SQL_ATTR_ODBC_CURSORS para especificar se a biblioteca de cursores é sempre usada, usada se o driver não dá suporte a cursores roláveis ou nunca foi usada. A biblioteca de cursores supõe que um driver oferece suporte a cursores roláveis se ela retorna SQL_CA1_RELATIVE para o tipo de informações de SQL_STATIC_CURSOR_ATTRIBUTES1 em **SQLGetInfo**.  
  
 O aplicativo deve chamar **SQLSetConnectAttr** para especificar o uso da biblioteca de cursor depois de chamar **SQLAllocHandle** com um *HandleType* SQL_HANDLE_DBC para alocar a conexão e antes de se conectar à fonte de dados. Se um aplicativo chamar **SQLSetConnectAttr** com o atributo SQL_ATTR_ODBC_CURSORS enquanto a conexão ainda está ativa, a biblioteca de cursores retornará um erro.  
  
 Para definir um atributo de instrução com suporte a biblioteca de cursores para todas as instruções associadas com uma conexão, um aplicativo deve chamar **SQLSetConnectAttr** para esse atributo de instrução depois que ele se conecta à fonte de dados e antes Abre o cursor. Se um aplicativo chamar **SQLSetConnectAttr** com uma declaração de atributo e um cursor está aberto em uma instrução associada com a conexão, o atributo de instrução não será aplicado a essa instrução até que o cursor seja fechado e reaberta.
