---
title: Resumo de Interface de provedor de serviço ODBC | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: ace6085b-355b-435b-8734-503fc3c12ec2
caps.latest.revision: 4
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: bea3ed9605ae079a7ee1dce68c778c908ebf2fbd
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32916671"
---
# <a name="odbc-service-provider-interface-summary"></a>Resumo de Interface de provedor de serviço ODBC
A tabela a seguir descreve as funções de interface de provedor de serviços de ODBC. Para obter mais informações sobre a sintaxe e semântica para cada função, consulte [referência de Interface de provedor de serviço do ODBC (IDA)](../../../odbc/reference/syntax/odbc-service-provider-interface-spi-reference.md).  
  
|Nome da função|Finalidade|  
|-------------------|-------------|  
|[SQLSetConnectAttrForDbcInfo](../../../odbc/reference/syntax/sqldatasourcetodriver-function.md)|Mesmo que [SQLSetConnectAttr](../../../odbc/reference/syntax/sqlsetconnectattr-function.md), mas ela define o atributo no token de informações de conexão em vez de no identificador da conexão.|  
|[SQLSetDriverConnectInfo](../../../odbc/reference/syntax/sqldrivertodatasource-function.md)|Define a cadeia de caracteres de conexão para o token de informações de conexão para um aplicativo [SQLDriverConnect](../../../odbc/reference/syntax/sqldriverconnect-function.md) chamar.|  
|[SQLSetConnectInfo](../../../odbc/reference/syntax/sqldatasourcetodriver-function.md)|Define a fonte de dados, ID de usuário e senha para o token de informações de conexão para um aplicativo [SQLConnect](../../../odbc/reference/syntax/sqlconnect-function.md) chamar.|  
|[SQLGetPoolID](../../../odbc/reference/syntax/sqldatasourcetodriver-function.md)|Recupera a ID do pool.|  
|[SQLRateConnection](../../../odbc/reference/syntax/sqldatasourcetodriver-function.md)|Determina se um driver pode reutilizar uma conexão existente no pool de conexão.|  
|[SQLPoolConnect](../../../odbc/reference/syntax/sqldatasourcetodriver-function.md)|Crie uma nova conexão se nenhuma conexão no pool pode ser reutilizada.|  
|[SQLCleanupConnectionPoolID](../../../odbc/reference/syntax/sqldatasourcetodriver-function.md)|Informa um driver que uma ID do pool foi atingida.|
