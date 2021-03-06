---
title: sys. remote_data_archive_tables (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: stored-procedures
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.remote_data_archive_tables
- sys.remote_data_archive_tables_TSQL
- remote_data_archive_tables
- remote_data_archive_tables_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.remote_data_archive_tables catalog view
ms.assetid: 765069b7-60fd-414c-875f-3455460b75cd
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: d94d4788c071a9c5acc006afad9fe119bc0e9c77
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37425555"
---
# <a name="stretch-database-catalog-views---sysremotedataarchivetables"></a>Stretch Database exibições do catálogo – sys. remote_data_archive_tables
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Contém uma linha para cada tabela remota que armazena dados de uma tabela local habilitada para Stretch.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**object_id**|**int**|A ID de objeto da tabela local habilitada para Stretch.|  
|**remote_database_id**|**int**|O identificador de local gerado automaticamente do banco de dados remoto.|  
|**remote_table_name**|**sysname**|O nome da tabela no banco de dados remoto que corresponde à tabela local habilitada para Stretch.|  
|**filter_predicate**|**nvarchar(max)**|O predicado de filtro, se houver, que identifica as linhas na tabela a serem migrados. Se o valor for nulo, a tabela inteira será qualificada para ser migrada.<br /><br /> Para obter mais informações, consulte [habilitar o Stretch Database para uma tabela](../../sql-server/stretch-database/enable-stretch-database-for-a-table.md) e [selecionar linhas para migrar usando um predicado de filtro](~/sql-server/stretch-database/select-rows-to-migrate-by-using-a-filter-function-stretch-database.md).|  
|**migration_direction**|**tinyint**|A direção na qual os dados no momento estão sendo migrados. Os valores disponíveis são as seguintes.<br/>1 (saída)<br/>2 (entrada)|  
|**migration_direction_desc**|**nvarchar(60)**|A descrição da direção em que os dados no momento estão sendo migrados. Os valores disponíveis são as seguintes.<br/>saída (1)<br/>(2) de entrada|  
|**is_migration_paused**|**bit**|Indica se a migração estiver em pausa.|  
|**is_reconciled**|**bit**| Indica se a tabela remota e a tabela do SQL Server estão em sincronia.<br/><br/>Quando o valor de **is_reconciled** é 1 (verdadeiro), a tabela remota e a tabela do SQL Server estão em sincronia e você pode executar consultas que incluem os dados remotos.<br/><br/>Quando o valor de **is_reconciled** é 0 (false), a tabela remota e a tabela do SQL Server não estão em sincronia. Recentemente linhas migradas precisa ser migrado novamente. Isso ocorre quando você restaura o banco de dados remoto do Azure, ou quando você exclui manualmente linhas da tabela remota. Até que você reconcilie as tabelas, será possível executar consultas que incluem os dados remotos. Para reconciliar as tabelas, execute [sp_rda_reconcile_batch](../../relational-databases/system-stored-procedures/sys-sp-rda-reconcile-batch-transact-sql.md). |  
  
## <a name="see-also"></a>Consulte também  
 [Stretch Database](../../sql-server/stretch-database/stretch-database.md)  
  
  

