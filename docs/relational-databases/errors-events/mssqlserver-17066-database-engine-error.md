---
title: MSSQLSERVER_17066 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 17066 (Database Engine error)
ms.assetid: 7d650bbf-c583-4af8-9e22-993ee2880d95
caps.latest.revision: 16
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: dd503d14e1bcea86f155fd8926f87658deca94aa
ms.sourcegitcommit: ee661730fb695774b9c483c3dd0a6c314e17ddf8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2018
ms.locfileid: "34319707"
---
# <a name="mssqlserver17066"></a>MSSQLSERVER_17066
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|17066|  
|Origem do evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|SQLASSERT_ONLY|  
|Texto da mensagem|Declaração do SQL Server: arquivo: \<%s>, linha=%d falha de declaração = '%s'. Talvez esse erro esteja relacionado à temporização. Se o erro persistir após a repetição da instrução, use DBCC CHECKDB para verificar a integridade estrutural do banco de dados ou reinicie o servidor para assegurar que as estruturas de dados na memória não estejam corrompidas.|  
  
## <a name="explanation"></a>Explicação  
Talvez o erro seja causado por erros transitórios relacionados à temporização ou por dados corrompidos na memória ou no disco.  
  
## <a name="user-action"></a>Ação do usuário  
Exiba novamente a instrução que causou o disparo da exceção. Se o erro foi causado por um evento relacionado à temporização, talvez ele não ocorra novamente. Se o problema persistir, execute DBCC CHECKDB para verificar se há dados corrompidos no disco. Reinicie o servidor para garantir que as estruturas de dados na memória não estão corrompidas.  
  
## <a name="see-also"></a>Consulte Também  
[DBCC CHECKDB &#40;Transact-SQL&#41;](~/t-sql/database-console-commands/dbcc-checkdb-transact-sql.md)  
  
