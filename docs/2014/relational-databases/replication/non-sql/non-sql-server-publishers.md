---
title: Publicadores não SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- heterogeneous database replication, non-SQL Server Publishers
- non-SQL Server Publishers
- heterogeneous data sources, non-SQL Server Publishers
- Publishers [SQL Server replication], Oracle
ms.assetid: 08a160a6-33be-46b5-bc7b-d53180d8bdf1
caps.latest.revision: 30
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: fbb2694932b20c38bee4bc7b3978abfab1472b43
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37299906"
---
# <a name="non-sql-server-publishers"></a>editores não SQL Server
  Publicar dados de origens que não são do[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] permite consolidar dados no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. O[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pode assinar um instantâneo ou dados transacionais publicados de um banco de dados Oracle. Para obter mais informações sobre a publicação do Oracle, consulte [Oracle Publishing Overview](oracle-publishing-overview.md) (Visão geral de publicação do Oracle).  
  
 A replicação heterogênea para assinantes que não são do SQL Server foi preterida. A publicação Oracle foi preterida. Para mover dados, crie soluções usando a captura de dados de alterações e o [!INCLUDE[ssIS](../../../includes/ssis-md.md)].  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
 Publicar de banco de dados não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] é o ideal para os seguintes cenários:  
  
|Cenário|Description|  
|--------------|-----------------|  
|Implantações de aplicativos do[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework|Desenvolva com o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio e [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] enquanto estiver operando em dados replicados de banco de dados que não são do[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .|  
|Servidores de preparo de data warehouse|Mantenha os bancos de dados de preparo do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sincronizado com um banco de dados não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .|  
|Migração para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]|Teste o seu aplicativo em tempo real com relação ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] enquanto estiver reproduzindo as alterações do sistema de fonte. Alterne para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quando estiver satisfeito com a migração.|  
  
## <a name="see-also"></a>Consulte também  
 [Heterogeneous Database Replication](heterogeneous-database-replication.md)  
  
  
