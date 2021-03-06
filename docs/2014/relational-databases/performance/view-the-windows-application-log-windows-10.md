---
title: Exibir o log de aplicativos do Windows (Windows) | Microsoft Docs
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
- viewing logs
- application logs [SQL Server]
- logs [SQL Server], application
- monitoring Windows NT application log [SQL Server]
- Windows NT application logs [SQL Server]
- displaying logs
- monitoring [SQL Server], events
- logs [SQL Server], viewing
ms.assetid: 168a6c6e-12df-46a9-9904-55d63ca8fe14
caps.latest.revision: 23
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 541bbb31e853e604bc56d707d74cc77a02f89753
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37307337"
---
# <a name="view-the-windows-application-log-windows"></a>Exibir o log de aplicativos do Windows (Windows)
  Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é configurado para usar o log de aplicativos do Windows, cada sessão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] grava novos eventos nesse log. Ao contrário do log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , não é criado um novo log de aplicativos cada vez que uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]é iniciada.  
  
### <a name="to-view-the-windows-application-log"></a>Para exibir o log de aplicativos do Windows  
  
1.  No menu **Iniciar** , aponte para **Todos os Programas**, **Ferramentas Administrativas**e clique em **Visualizador de Eventos**.  
  
2.  No Visualizador de Eventos, clique em **Aplicativo**.  
  
3.  Os eventos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são identificados pela entrada **MSSQLSERVER** (as instâncias nomeadas são identificadas com **MSSQL$***<instance_name>*) na coluna **Origem**. Os eventos do SQL Server Agent são identificados pela entrada SQLSERVERAGENT (para instâncias nomeadas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], os eventos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent são identificados com **SQLAgent$**\<*instance_name*>). Os eventos do serviço do Microsoft Search são identificados pela entrada **Microsoft Search**.  
  
4.  Para exibir o log de um computador diferente, clique com o botão direito do mouse em **Visualizador de Eventos**, clique em **Conectar-se a outro computador** e preencha a caixa de diálogo **Selecionar Computador**.  
  
5.  Opcionalmente, para exibir apenas eventos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , no menu **Exibir** clique em **Filtro**e, na lista **Origem do evento** , selecione **MSSQLSERVER**. Para exibir apenas eventos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, selecione **SQLSERVERAGENT** na lista **Origem do evento** .  
  
6.  Para exibir mais informações sobre um evento, clique duas vezes no evento.  
  
## <a name="see-also"></a>Consulte também  
 [Exibir o log de erros do SQL Server &#40;SQL Server Management Studio&#41;](../../ssms/sql-server-management-studio-ssms.md)  
  
  
