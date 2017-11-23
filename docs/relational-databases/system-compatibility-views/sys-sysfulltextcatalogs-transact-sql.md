---
title: sys. sysfulltextcatalogs (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, pdw
ms.service: 
ms.component: system-compatibility-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sysfulltextcatalogs
- sys.sysfulltextcatalogs_TSQL
- sysfulltextcatalogs_TSQL
- sys.sysfulltextcatalogs
dev_langs: TSQL
helpviewer_keywords:
- sys.sysfulltextcatalogs compatibility view
- sysfulltextcatalogs system table
ms.assetid: 18ac6ad5-01e8-428f-8422-a9ca29626977
caps.latest.revision: "38"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: efaebceaa5a23c755ecde56044ca3974dbeec3d9
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="syssysfulltextcatalogs-transact-sql"></a>sys.sysfulltextcatalogs (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-pdw-md.md)]

  Contém informações sobre os catálogos de texto completo.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
||  
|-|  
|**Aplica-se a**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] até a [versão atual](http://go.microsoft.com/fwlink/p/?LinkId=299658)), [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)].|  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**ftcatid**|**smallint**|Identificador do catálogo de texto completo.|  
|**name**|**sysname**|Nome do catálogo de texto completo especificado pelo usuário.|  
|**status**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**caminho**|**nvarchar (260)**|Caminho raiz especificado pelo usuário.<br /><br /> NULL = Caminho não foi especificado. Foi utilizado o caminho (de instalação) padrão.|  
  
## <a name="see-also"></a>Consulte também  
 [Mapeando tabelas do sistema para exibições do sistema &#40; Transact-SQL &#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Exibições de compatibilidade &#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
