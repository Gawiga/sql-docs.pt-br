---
title: sys.dm_os_memory_pools (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.dm_os_memory_pools_TSQL
- dm_os_memory_pools
- dm_os_memory_pools_TSQL
- sys.dm_os_memory_pools
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_os_memory_pools dynamic management view
ms.assetid: 1ef053f3-c6f3-456e-82b6-26e4bd630d46
caps.latest.revision: 25
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 8c814f58f327598d6e5adcdd3fb30357aa9b6009
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43062147"
---
# <a name="sysdmosmemorypools-transact-sql"></a>sys.dm_os_memory_pools (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Retorna uma linha para cada repositório de objeto na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Você pode usar esta exibição para monitorar o uso de memória cache e identificar comportamento ruim de cache  
  
> [!NOTE]  
>  Chamá-lo partir [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] ou [!INCLUDE[ssPDW](../../includes/sspdw-md.md)], use o nome **sys.dm_pdw_nodes_os_memory_pools**.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**memory_pool_address**|**varbinary(8)**|Endereço de memória da entrada que representa o pool de memória. Não permite valor nulo.|  
|**pool_id**|**int**|ID de um pool específico em um conjunto de pools. Não permite valor nulo.|  
|**type**|**nvarchar(60)**|Tipo de pool de memória. Não permite valor nulo. Para obter mais informações, consulte [DM os_memory_clerks &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-os-memory-clerks-transact-sql.md).|  
|**name**|**nvarchar(256)**|Nome atribuído pelo sistema deste objeto de memória. Não permite valor nulo.|  
|**max_free_entries_count**|**bigint**|Número máximo de entradas livres que um pool pode ter. Não permite valor nulo.|  
|**free_entries_count**|**bigint**|Número de entradas livres atualmente no pool. Não permite valor nulo.|  
|**removed_in_all_rounds_count**|**bigint**|Número de entradas removidas do pool desde que a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] foi iniciada. Não permite valor nulo.|  
|**pdw_node_id**|**int**|**Aplica-se ao**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)], [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> O identificador para o nó que essa distribuição é no.|  
  
## <a name="permissions"></a>Permissões

Na [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)], requer `VIEW SERVER STATE` permissão.   
Na [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)], requer o `VIEW DATABASE STATE` permissão no banco de dados.   

## <a name="remarks"></a>Remarks  
 Os componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] às vezes usam uma estrutura de pool comum para armazenar em cache tipos de dados homogêneos e sem monitoração de estado. A estrutura de pool é mais simples que a estrutura de cache. Todas as entradas nos pools são consideradas iguais. Internamente, os pools são administradores de memória e podem ser usados em locais onde os administradores de memória são usados.  
  
## <a name="see-also"></a>Consulte também  
 
  [Sistema operacional SQL Server relacionados exibições de gerenciamento dinâmico &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-server-operating-system-related-dynamic-management-views-transact-sql.md)  
  
  


