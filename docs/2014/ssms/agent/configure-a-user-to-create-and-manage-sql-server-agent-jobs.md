---
title: Configurar um usuário para criar e gerenciar trabalhos do SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, user configuration
- jobs [SQL Server Agent], user configuration
- SQLAgentUserRole database role
- proxy accounts [SQL Server Agent]
ms.assetid: 67897e3e-b7d0-43dd-a2e2-2840ec4dd1ef
caps.latest.revision: 24
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 2804168db65322d9c51219dad044ac0fe211163b
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37234346"
---
# <a name="configure-a-user-to-create-and-manage-sql-server-agent-jobs"></a>Configurar um usuário para criar e gerenciar trabalhos do SQL Server Agent
  Este tópico descreve como configurar um usuário para criar ou executar trabalhos do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.  
  
-   **Antes de começar:**  [Segurança](#Security)  
  
-   **Para configurar um usuário para criar e gerenciar trabalhos do SQL Server Agent, usando:**  [SQL Server Management Studio](#SSMS)  
  
##  <a name="BeforeYouBegin"></a> Antes de começar  
  
###  <a name="Security"></a> Segurança  
 Para configurar um usuário para criar ou executar trabalhos do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, primeiro você deve adicionar um logon existente do SQL Server ou uma função do msdb a uma das seguintes funções de banco de dados fixa do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no banco de dados msdb: SQLAgentUserRole, SQLAgentReaderRole ou SQLAgentOperatorRole.  
  
 Por padrão, os membros dessas funções de banco de dados podem criar suas próprias etapas de trabalho, executadas como eles mesmos. Se esses usuários não administrativos quiserem executar trabalhos que executam outros tipos de etapa de trabalho (por exemplo, pacotes [!INCLUDE[ssIS](../../includes/ssis-md.md)] ), eles precisarão ter acesso a uma conta proxy. Todos os membros da função de servidor fixa sysadmin têm permissão para criar, modificar e excluir contas proxy. Para obter mais informações sobre as permissões associadas a essas funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, consulte [Funções de banco de dados fixas do SQL Server Agent](sql-server-agent-fixed-database-roles.md).  
  
####  <a name="Permissions"></a> Permissões  
 Para obter informações detalhadas, consulte [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).  
  
##  <a name="SSMS"></a> Usando o SQL Server Management Studio  
 **Para adicionar um logon de SQL ou função msdb a uma função de banco de dados fixa do SQL Server Agent**  
  
1.  No **Pesquisador de Objetos**, expanda um servidor.  
  
2.  Expanda **Segurança**e, em seguida, **Logons**.  
  
3.  Clique com o botão direito do mouse no logon que deseja adicionar a uma função de banco de dados fixa do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e selecione **Propriedades**.  
  
4.  Sobre o **mapeamento de usuário** página do **propriedades de logon** caixa de diálogo, selecione a linha que contém `msdb`.  
  
5.  Em **Associação à função de banco de dados para: msdb**, selecione a função de banco de dados fixa apropriada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.  
  
 **Para configurar uma conta proxy para criar e gerenciar etapas de trabalho do SQL Server Agent**  
  
1.  No **Pesquisador de Objetos**, expanda um servidor.  
  
2.  Expanda o **SQL Server Agent**.  
  
3.  Clique com o botão direito do mouse em **Proxies** e selecione **Novo Proxy**.  
  
4.  Na página **Geral** da caixa de diálogo **Nova Conta Proxy** , especifique o nome do proxy, o nome da credencial e a descrição do novo proxy. Observe que primeiramente você deve criar uma credencial para poder criar um proxy do SQL Server Agent. Para obter mais informações sobre como criar uma credencial, consulte [criar uma credencial](../../relational-databases/security/authentication-access/create-a-credential.md) e [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).  
  
5.  Marque os subsistemas apropriados para esse proxy.  
  
6.  Na página **Entidades** , adicione ou remova logons ou funções para conceder ou remover acesso à conta proxy.  
  
## <a name="see-also"></a>Consulte também  
 [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md)  
  
  
