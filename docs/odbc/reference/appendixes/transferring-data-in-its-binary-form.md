---
title: "Transferência de dados em seu formato binário | Microsoft Docs"
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
- data types [ODBC], transferring in binary form
- transferring data in binary form [ODBC]
- binary data transfers [ODBC]
ms.assetid: 4b12a9de-51d0-416a-87f4-9bf84959cad9
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 8c54b61ec668e9282d723e48f1c50d1005740ac1
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="transferring-data-in-its-binary-form"></a>Transferência de dados em seu formato binário
Um aplicativo com segurança pode transferir dados (no formato interno usado por um DBMS especificado) entre duas fontes de dados que usam o mesmo DBMS e a plataforma de hardware. Para uma determinada parte dos dados, os tipos de dados SQL devem ser o mesmo em fontes de dados de origem e destino. O tipo de dados C é SQL_C_BINARY.  
  
 Quando o aplicativo chama **SQLFetch**, **SQLFetchScroll**, ou **SQLGetData** para recuperar os dados da fonte de dados de origem, o driver recupera os dados dos dados origem e a transfere, sem conversão para um local de armazenamento do tipo SQL_C_BINARY. Quando o aplicativo chama **SQLBulkOperations**, **SQLExecute**, **SQLExecDirect**, **SQLPutData ou SQLSetPos** para enviar os dados para a fonte de dados de destino, o driver recupera os dados do local de armazenamento e a transfere, sem conversão para a fonte de dados de destino.  
  
> [!NOTE]  
>  Aplicativos que transferir os dados (exceto dados binários) dessa maneira não são interoperáveis entre DBMSs.  
  
 **SQLCopyDesc** pode ser usado para copiar associações de linha de DBMS de origem para associações de parâmetro no DBMS de destino.