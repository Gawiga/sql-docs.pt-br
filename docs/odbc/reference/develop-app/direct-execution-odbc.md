---
title: Direcionar execução ODBC | Microsoft Docs
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
- SQL statements [ODBC], direct execution
- direct execution [ODBC]
- SQL statements [ODBC], executing
ms.assetid: dd00a535-b136-494f-913b-410838e3de7e
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: e506f856fff84065b0026e3e3629a4299d14dae2
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32912031"
---
# <a name="direct-execution-odbc"></a>Execução direta ODBC
Execução direta é a maneira mais simples para executar uma instrução. Quando a instrução é enviada para execução, a fonte de dados compila em um plano de acesso e, em seguida, executa esse plano de acesso.  
  
 Execução direta é normalmente usada por aplicativos genéricos que criar e executam instruções em tempo de execução. Por exemplo, o código a seguir cria uma instrução SQL e executa uma única vez:  
  
```  
SQLCHAR *SQLStatement;  
  
// Build an SQL statement.  
BuildStatement(SQLStatement);  
  
// Execute the statement.  
SQLExecDirect(hstmt, SQLStatement, SQL_NTS);  
```  
  
 Execução direta funciona melhor para instruções que serão executadas uma vez. Sua principal desvantagem é que a instrução SQL é analisada toda vez que ele é executado. Além disso, o aplicativo não é possível recuperar informações sobre o conjunto de resultados criado pela instrução (se houver) até a instrução é executada; Isso é possível se a instrução é preparada e executada em duas etapas separadas.  
  
 Para executar uma instrução diretamente, o aplicativo executa as seguintes ações:  
  
1.  Define os valores de quaisquer parâmetros. Para obter mais informações, consulte [parâmetros de instrução](../../../odbc/reference/develop-app/statement-parameters.md), mais adiante nesta seção.  
  
2.  Chamadas **SQLExecDirect** e passa uma cadeia de caracteres que contém a instrução SQL.  
  
3.  Quando **SQLExecDirect** é chamado, o driver:  
  
    -   Modifica a instrução SQL para usar a gramática SQL da fonte de dados sem analisar a instrução; Isso inclui substituindo as sequências de escape discutidas [sequências de Escape no ODBC](../../../odbc/reference/develop-app/escape-sequences-in-odbc.md). O aplicativo pode recuperar o formulário de modificação de uma instrução SQL chamando **SQLNativeSql**. Sequências de escape não são substituídas, se o atributo de instrução SQL_ATTR_NOSCAN está definido.  
  
    -   Recupera os valores de parâmetro atuais e converte-os conforme necessário. Para obter mais informações, consulte [parâmetros de instrução](../../../odbc/reference/develop-app/statement-parameters.md), mais adiante nesta seção.  
  
    -   Envia a instrução e valores de parâmetro convertido para a fonte de dados para execução.  
  
    -   Retorna erros. Esses incluem sequenciamento ou diagnóstico de estado como SQLSTATE 24000 (estado de cursor inválido), erros sintáticos como SQLSTATE 42000 (sintaxe ou violação de acesso) e erros semânticos como SQLSTATE 42S02 (Base a tabela ou exibição não encontrado).
