---
title: sysssispackages (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-tables
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sysdtspackages90_TSQL
- sysdtspackages90
dev_langs:
- TSQL
helpviewer_keywords:
- sysssispackages system table
ms.assetid: 66155dcd-dcdb-4e33-a242-1625828ad8d2
caps.latest.revision: 43
author: douglasl
ms.author: douglasl
manager: craigg
ms.openlocfilehash: dfad4f28a2349ad6f3c5212ae26841a77b78e39b
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33259756"
---
# <a name="sysssispackages-transact-sql"></a>sysssispackages (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Contém uma linha para cada pacote que é salvo em [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Essa tabela é armazenada no **msdb** banco de dados.  
  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|O identificador exclusivo do pacote.|  
|**id**|**uniqueidentifier**|O GUID do pacote.|  
|**Descrição**|**nvarchar**|A descrição opcional do pacote.|  
|**createdate**|**datetime**|A data em que o pacote foi criado.|  
|**folderid**|**uniqueidentifier**|O GUID da pasta lógica na qual o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] lista o pacote.|  
|**ownersid**|**varbinary**|O identificador de segurança exclusivo do usuário que criou o pacote.|  
|**packagedata**|**image**|O pacote.|  
|**packageformat**|**Int**|O formato em que o pacote foi salvo:<br /><br /> Um valor de 2 indica que o pacote é salvo no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] formato.<br /><br /> Um valor de 3 indica que o pacote é salvo no formato de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]ou posterior.|  
|**packagetype**|**Int**|O cliente que criou o pacote. Os valores possíveis são os seguintes:<br /><br /> 0 (valor padrão)<br /><br /> 1 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] importar e exportar assistente)<br /><br /> 3 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replicação)<br /><br /> 5 ([!INCLUDE[ssIS](../../includes/ssis-md.md)] designer)<br /><br /> 6 (Assistente ou Designer do Plano de Manutenção).<br /><br /> <br /><br /> Observe que os valores nesta coluna correspondem do <xref:Microsoft.SqlServer.Dts.Runtime.DTSPackageType> enumeração.|  
|**vermajor**|**Int**|A versão principal mais recente do pacote.|  
|**verminor**|**Int**|A versão secundária mais recente do pacote.|  
|**verbuild**|**Int**|O versão mais recente do pacote.|  
|**vercomments**|**nvarchar**|Comentários sobre a versão do pacote.|  
|**Verid**|**uniqueidentifier**|O GUID da versão do pacote.|  
|**isencrypted**|**bit**|Um booliano que indica se o pacote é criptografado.|  
|**readrolesid**|**varbinary**|A função [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que pode carregar pacotes.|  
|**writerolesid**|**varbinary**|A função [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que pode salvar pacotes.|  
  
## <a name="see-also"></a>Consulte também  
 [Integration Services & #40; SSIS & #41; Pacotes](../../integration-services/integration-services-ssis-packages.md)  
  
  
