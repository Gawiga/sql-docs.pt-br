---
title: Opções de instrução | Microsoft Docs
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
- custom statement options [ODBC]
- statement options [ODBC]
- ODBC driver for Oracle [ODBC], statement options
ms.assetid: cd73b769-c8b5-43e0-9f80-b3011b7a6162
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 9402bb45fbd995aedc53e4d490709e1e6504a5f9
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32904361"
---
# <a name="statement-options"></a>Opções de instrução
> [!IMPORTANT]  
>  Este recurso será removido em uma versão futura do Windows. Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam. Em vez disso, use o driver ODBC fornecido pela Oracle.  
  
 Essas opções permitem a personalização de uma instrução de execução específica dentro de um aplicativo.  
  
|Opção de instrução|Observações|  
|----------------------|-----------|  
|SQL_BIND_TYPE|Não pode exceder 2.147.483.647 bytes ou a memória disponível.|  
|SQL_CONCURRENCY|Para obter os valores permitidos, consulte o [combinações de simultaneidade e o tipo de Cursor](../../odbc/microsoft/cursor-type-and-concurrency-combinations.md).|  
|SQL_CURSOR_TYPE|O driver não permite SQL_CURSOR_DYNAMIC. Consulte [SQLSetScrollOptions](../../odbc/microsoft/level-2-api-functions-odbc-driver-for-oracle.md) para obter mais informações. Para obter os valores permitidos, consulte o [combinações de simultaneidade e o tipo de Cursor](../../odbc/microsoft/cursor-type-and-concurrency-combinations.md).|  
|SQL_GET_BOOKMARK|Retorna um valor inteiro de 32 bits que é o indicador para o número do registro atual. Obter. não é possível definir.|  
|SQL_KEYSET_SIZE|Pode ser definido somente como 0.|  
|SQL_MAX_ROWS|O número máximo de linhas a serem retornadas de um resultado definido.|  
|SQL_ROW_NUMBER|Retorna um inteiro de 32 bits que especifica a posição da linha atual no conjunto de resultados. Obter. não é possível definir.|  
|SQL_ROWSET_SIZE|Não pode ter mais de 4.294.967.296 linhas; No entanto, você deve ter memória virtual insuficiente no seu computador a sua solicitação.|  
|SQL_USE_BOOKMARKS|Oferece suporte à configuração SQL_USE_BOOKMARKS para SQL_UB_ON e expõe os indicadores de comprimento fixo.|
