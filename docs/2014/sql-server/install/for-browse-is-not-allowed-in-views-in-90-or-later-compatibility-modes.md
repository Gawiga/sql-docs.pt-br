---
title: PARA procurar não é permitida em exibições nos modos de compatibilidade 90 ou posterior | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], FOR BROWSE clause
- FOR BROWSE clause
ms.assetid: 8f49b1c1-d877-4c46-b988-f8cdd8ac0925
caps.latest.revision: 13
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: b309f79379bacbca6cfc4d3b134b31ead8e9e506
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37247916"
---
# <a name="for-browse-is-not-allowed-in-views-in-90-or-later-compatibility-modes"></a>FOR BROWSE não é permitido em exibições nos modos de compatibilidade 90 ou posterior
  O Supervisor de Atualização detectou o uso da cláusula FOR BROWSE em uma exibição. A cláusula FOR BROWSE é permitida (e ignorada) em exibições quando o modo de compatibilidade do banco de dados está definido como 80. Entretanto, essa cláusula não é permitida em exibições quando o modo de compatibilidade do banco de dados está definido como 90 ou posterior.  
  
## <a name="component"></a>Componente  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a>Ação corretiva  
 Quando você faz a atualização, os bancos de dados de usuários mantêm seus modos de compatibilidade. Antes de alterar o modo de compatibilidade do banco de dados para 90 ou posterior, remova a cláusula FOR BROWSE das definições de exibição. Para obter mais informações, consulte ‘sp_dbcmptlevel’ nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="see-also"></a>Consulte também  
 [Problemas de atualização de mecanismo de banco de dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md)   
 [Supervisor de atualização do SQL Server 2014 &#91;novo&#93;](/sql/2014/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
