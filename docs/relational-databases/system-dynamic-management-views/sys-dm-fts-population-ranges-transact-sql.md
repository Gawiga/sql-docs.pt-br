---
title: sys.dm_fts_population_ranges (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/29/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.dm_fts_population_ranges
- sys.dm_fts_population_ranges_TSQL
- dm_fts_population_ranges_TSQL
- dm_fts_population_ranges
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_fts_population_ranges dynamic management view
ms.assetid: 58d8564b-9c43-4965-a31c-2893890334ef
caps.latest.revision: 31
author: douglaslMS
ms.author: douglasl
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 901363a42da09424a232c03b96213edf4dc8ebce
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43071937"
---
# <a name="sysdmftspopulationranges-transact-sql"></a>sys.dm_fts_population_ranges (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retorna informações sobre os intervalos específicos relacionados a uma população de índice de texto completo atualmente em andamento.  
   
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**memory_address**|**varbinary(8)**|Endereço de buffers de memória alocado para atividade relacionada a este subintervalo de uma população de índice de texto completo.|  
|**parent_memory_address**|**varbinary(8)**|Endereço de buffers de memória que representam o objeto pai de todos os intervalos de população relacionados a um índice de texto completo.|  
|**is_retry**|**bit**|Se o valor for 1, este subintervalo será responsável por repetir as linhas que encontraram erros.|  
|**session_id**|**smallint**|ID da sessão que está processando esta tarefa atualmente.|  
|**processed_row_count**|**int**|Número de linhas que foram processadas por este intervalo. O progresso é persistido e contado a cada cinco minutos, em vez de a cada confirmação de lote.|  
|**error_count**|**int**|Número de linhas que encontraram erros neste intervalo. O progresso é persistido e contado a cada cinco minutos, em vez de a cada confirmação de lote.|  
  
## <a name="permissions"></a>Permissões  

Na [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)], requer `VIEW SERVER STATE` permissão.   
Na [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)], requer o `VIEW DATABASE STATE` permissão no banco de dados.   
 
## <a name="physical-joins"></a>Junções físicas  
 ![Junções significativas dessa exibição de gerenciamento dinâmico](../../relational-databases/system-dynamic-management-views/media/join-dm-fts-population-ranges-1.gif "junções significativas dessa exibição de gerenciamento dinâmico")  
  
## <a name="relationship-cardinalities"></a>Cardinalidades de relações  
  
|De|Para|Relação|  
|----------|--------|------------------|  
|dm_fts_population_ranges.parent_memory_address|dm_fts_index_population.memory_address|Muitos para um|  
  
## <a name="see-also"></a>Consulte também  
  [Pesquisa de texto completo e funções e exibições de gerenciamento dinâmico de pesquisa semântica &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/full-text-and-semantic-search-dynamic-management-views-functions.md)  
  
  

