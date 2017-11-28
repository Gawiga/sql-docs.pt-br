---
title: server_event_sessions (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- server_event_sessions
- server_event_sessions_TSQL
- sys.server_event_sessions_TSQL
- sys.server_event_sessions
dev_langs: TSQL
helpviewer_keywords:
- sys.server_event_sessions catalog view
- xe
ms.assetid: 796f3093-6a3e-4d67-8da6-b9810ae9ef5b
caps.latest.revision: "15"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 041fe01f163a29df7f070d3c16650dcd32646676
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="sysservereventsessions-transact-sql"></a>sys.server_event_sessions (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Lista todas as definições de sessão de evento que existem no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
||  
|-|  
|**Aplica-se a**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] até a [versão atual](http://go.microsoft.com/fwlink/p/?LinkId=299658)).|  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|event_session_id|**int**|A ID exclusiva da sessão de evento. Não permite valor nulo.|  
|name|**sysname**|O nome definido pelo usuário para identificar a sessão de evento. nome é exclusivo. Não permite valor nulo.|  
|event_retention_mode|**nchar (1)**|Determina como a perda de evento é tratada. O padrão é S. Não é anulável. É um dos seguintes:<br /><br /> S. Mapeia para event_retention_mode_desc = ALLOW_SINGLE_EVENT_LOSS<br /><br /> M. Mapeia para event_retention_mode_desc = ALLOW_MULTIPLE_EVENT_LOSS<br /><br /> N. Mapeia para event_retention_mode_desc = NO_EVENT_LOSS|  
|event_retention_mode_desc|**sysname**|Descreve como a perda de evento é tratada. O padrão é ALLOW_SINGLE_EVENT_LOSS. Não permite valor nulo. É um dos seguintes:<br /><br /> ALLOW_SINGLE_EVENT_LOSS. Os eventos podem ser perdidos da sessão. Eventos únicos serão descartados somente quando todos os buffers de evento estiverem cheios. A perda de um único evento quando os buffers de evento estiverem cheios permite características de desempenho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aceitáveis, enquanto minimiza a perda no fluxo de eventos processados.<br /><br /> ALLOW_MULTIPLE_EVENT_LOSS. Os buffers de evento cheios podem ser perdidos da sessão. O número de eventos depende do tamanho de memória alocado à sessão, do particionamento da memória e do tamanho dos eventos no buffer. Essa opção minimiza o impacto de desempenho no servidor quando os buffers de evento forem rapidamente cheios. No entanto, números elevados de eventos podem ser perdidos da sessão.<br /><br /> NO_EVENT_LOSS. Nenhuma perda de evento é permitida. Essa opção assegura que todos os eventos gerados serão retidos. Usando essa opção força todas as tarefas que acionam eventos a esperar até que haja espaço disponível em um buffer de evento. Isso pode causar redução no desempenho detectável enquanto a sessão de evento está ativa.|  
|max_dispatch_latency|**int**|A quantidade de tempo, em milissegundos, em que haverá buffer de eventos na memória antes que sejam entregues para destinos de sessão. Os valores válidos são de 1 a 2147483648 e -1. Um valor de -1 indica que a latência de distribuição é infinita. Permite valor nulo.|  
|max_memory|**int**|A quantidade de memória alocada à sessão para buffer de evento. O valor padrão é de 4 MB. Permite valor nulo.|  
|max_event_size|**int**|A quantidade de memória definida separadamente para eventos que não se ajustam em buffers de sessão de evento. Se max_event_size exceder o tamanho do buffer calculado, serão alocados dois buffers adicionais de max_event_size à sessão de evento. Permite valor nulo.|  
|memory_partition_mode|**nchar (1)**|O local na memória no qual são criados buffers de evento. O modo de partição padrão é G. Não é anulável. memory_partition_mode é um de:<br /><br /> G - NONE<br /><br /> C - PER_CPU<br /><br /> N - PER_NODE|  
|memory_partition_mode_desc|**sysname**|O padrão é NONE. Não permite valor nulo. É um dos seguintes:<br /><br /> NONE. Um único conjunto de buffers é criado na instância do SQL Server.<br /><br /> PER_CPU. Um conjunto de buffers é criado para cada CPU.<br /><br /> PER_NODE. Um conjunto de buffers é criado para nó NUMA (acesso de memória não uniforme).|  
|track_causality|**bit**|Habilita ou desabilita o rastreamento de causalidade. Se definido como 1 (ON), o rastreamento será habilitado e eventos relacionados em conexões de servidor diferentes podem ser correlacionados. A configuração padrão é 0 (OFF). Não permite valor nulo.|  
|startup_state|**bit**|O valor determina se a sessão é ou não iniciada automaticamente quando o servidor for iniciado. O padrão é 0. Não permite valor nulo. É um dentre:<br /><br /> 0 (OFF). A sessão não inicia quando o servidor iniciar.<br /><br /> 1 (ON). A sessão de evento inicia quando o servidor iniciar.|  
  
## <a name="permissions"></a>Permissões  
 , é necessário ter permissão VIEW SERVER STATE no servidor.  
  
## <a name="see-also"></a>Consulte também  
 [Exibições de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Exibições de catálogo de eventos estendidos &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/extended-events-catalog-views-transact-sql.md)   
 [Eventos estendidos](../../relational-databases/extended-events/extended-events.md)  
  
  