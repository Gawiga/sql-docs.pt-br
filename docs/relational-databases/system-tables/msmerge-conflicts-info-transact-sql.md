---
title: MSmerge_conflicts_info (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/16/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-tables
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- MSmerge_conflicts_info_TSQL
- MSmerge_conflicts_info
dev_langs:
- TSQL
helpviewer_keywords:
- MSmerge_conflicts_info system table
ms.assetid: 6b76ae96-737a-4000-a6b6-fcc8772c2af4
caps.latest.revision: 19
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 41388cd1cc2d7a33f0b976ad62eca5e7f55aeade
ms.sourcegitcommit: a431ca21eac82117492d7b84c398ddb3fced53cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39103634"
---
# <a name="msmergeconflictsinfo-transact-sql"></a>MSmerge_conflicts_info (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  O **MSmerge_conflicts_info** tabela rastreia conflitos que ocorrem ao sincronizar uma assinatura para uma publicação de mesclagem. Os dados de linha está em conflito são armazenados na [MSmerge_conflict_publication_article](../../relational-databases/system-tables/msmerge-conflict-publication-article-transact-sql.md) tabela para o artigo no qual o conflito ocorreu. Essa tabela é armazenada no Publicador, no banco de dados de publicação, e no Assinante, no banco de dados de assinatura.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**tablenick**|**int**|O apelido da tabela publicada.|  
|**ROWGUID**|**uniqueidentifier**|O identificador para a linha de conflito.|  
|**origin_datasource**|**nvarchar(255)**|O nome do banco de dados onde a alteração conflitante teve origem.|  
|**conflict_type**|**int**|O tipo de conflito ocorrido, que pode ser um dos seguintes:<br /><br /> **1** = conflito de atualização: O conflito é detectado no nível de linha.<br /><br /> **2** = conflito de atualização de coluna: O conflito é detectado no nível de coluna.<br /><br /> **3** = conflito de atualização exclusão Wins: A exclusão ganha o conflito.<br /><br /> **4** = conflito de exclusão vence atualização: O rowguid excluído que perde o conflito é registrado nessa tabela.<br /><br /> **5** = carregar Falha na inserção: A inserção do assinante não puderam ser aplicada no publicador.<br /><br /> **6** = baixar Falha na inserção: A inserção do publicador não pôde ser aplicada no assinante.<br /><br /> **7** = carregar Falha na exclusão: A exclusão no assinante não pôde ser carregada no publicador.<br /><br /> **8** = baixar Falha na exclusão: A exclusão no publicador não pôde ser baixada no assinante.<br /><br /> **9** = carregar Falha na atualização: A atualização do assinante não puderam ser aplicada no publicador.<br /><br /> **10** = baixar Falha na atualização: A atualização do publicador não pôde ser aplicada ao assinante.<br /><br /> **11** = resolução<br /><br /> **12** = lógico registro atualização vence exclusão: O registro lógico excluído que perde o conflito é registrado nessa tabela.<br /><br /> **13** = lógico registro conflito de inserção de atualização: inserção em um registro lógico conflita com uma atualização.<br /><br /> **14** = lógico registro Wins atualização conflito de exclusão: O registro lógico atualizado que perde o conflito é registrado nessa tabela.|  
|**reason_code**|**int**|O código de erro que pode ser sensível ao contexto. No caso de conflitos de atualização-atualização e exclusão de atualização, o valor usado para esta coluna é igual a **conflict_type**. No entanto, em conflitos de alteração com falha, o código da razão é o erro que impediu o Merge Agent de aplicar a alteração. Por exemplo, se o agente de mesclagem não é possível aplicar uma inserção no assinante devido a uma violação de chave primária, ele registrará uma **conflict_type** de 6 ("na inserção do download") e uma **reason_code** de 2627, que é o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mensagem de erro interno de uma violação de chave primária: "violação da restrição %ls ' %. * ls'. Não é possível inserir chave duplicada no objeto ' %. \*ls'. "|  
|**reason_text**|**nvarchar(720)**|A descrição do erro que pode ser sensível ao contexto.|  
|**pubid**|**uniqueidentifier**|O identificador para a publicação.|  
|**MSrepl_create_time**|**datetime**|A hora em que o conflito ocorreu.|  
|**origin_datasource_id**|**uniqueidentifier**|O identificador do banco de dados onde a alteração conflitante teve origem.|  
  
## <a name="see-also"></a>Consulte também  
 [Tabelas de replicação &#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Exibições de replicação &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
