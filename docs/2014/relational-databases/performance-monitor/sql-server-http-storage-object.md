---
title: SQL Server, HTTP_STORAGE_OBJECT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: ae849f79-c581-42a5-a5cc-0a9ebea171b9
caps.latest.revision: 4
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: da3d1374fb0a1cf3e283129a24a8638867499e32
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37158267"
---
# <a name="sql-server-httpstorageobject"></a>SQL Server, HTTP_STORAGE_OBJECT
  O objeto de desempenho **SQLServer:HTTP_STORAGE_OBJECT** consiste nos contadores de desempenho que monitoram a conta de Armazenamento do Microsoft Azure. Usando o [arquivos de dados do SQL Server no Windows Azure](../databases/sql-server-data-files-in-microsoft-azure.md) recurso, você pode armazenar arquivos de banco de dados no armazenamento de Blobs do Windows Azure. Esse objeto de desempenho trata cada conta de Armazenamento do Windows Azure como uma unidade diferente.  
  
|Nome do contador|Description|  
|------------------|-----------------|  
|**Leitura de bytes/s**|Quantidade de dados que estão sendo transferidos do armazenamento HTTP por segundo durante operações de leitura.|  
|**Gravação de bytes/s**|Quantidade de dados que estão sendo transferidos do armazenamento HTTP por segundo durante operações de gravação.|  
|**Total de bytes/s**|Quantidade de dados que estão sendo transferidos do armazenamento HTTP por segundo durante operações de leitura ou gravação.|  
|**Leituras/s**|Número de leituras por segundo no armazenamento HTTP.|  
|**Gravações/s**|Número de gravações por segundo no armazenamento HTTP.|  
|**Transferências/s**|Número de operações de leitura e gravação por segundo no armazenamento HTTP.|  
|**Méd. de Bytes/leitura**|Número médio de bytes transferidos do armazenamento HTTP por leitura.|  
|**Méd. de Bytes/gravação**|Número médio de bytes transferidos do armazenamento HTTP por gravação.|  
|**Méd. de Bytes/transferência**|Número médio de bytes transferidos do armazenamento HTTP durante operações de leitura ou gravação.|  
|**Média de microssegundos/leitura**|O número médio de microssegundos que leva para realizar cada leitura do armazenamento HTTP.|  
|**Média de microssegundos/gravação**|O número médio de microssegundos que leva para realizar cada gravação no armazenamento HTTP.|  
|**Média de microssegundos/transferência**|O número médio de microssegundos que leva para realizar cada transferência para o armazenamento HTTP.|  
|**E/S de armazenamento HTTP pendente**|O número total de E/S pendente para um armazenamento HTTP.|  
|**Tentativa/s de E/S de armazenamento HTTP**|Número de solicitações de tentativa enviadas para o armazenamento HTTP por segundo.|  
  
## <a name="see-also"></a>Consulte também  
 [Monitorar o uso de recursos &#40;Monitor do Sistema&#41;](monitor-resource-usage-system-monitor.md)  
  
  
