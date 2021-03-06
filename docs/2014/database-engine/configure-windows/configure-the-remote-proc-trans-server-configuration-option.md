---
title: Configurar a opção de configuração de servidor remote proc trans | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- remote proc trans option
- distributed transactions [SQL Server], enforcing
ms.assetid: cfbc6158-ab96-44b4-87eb-ea278c1b0c6b
caps.latest.revision: 22
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: cb1e0a127ca94ce6cac8a668c577e433c1e9086a
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37178464"
---
# <a name="configure-the-remote-proc-trans-server-configuration-option"></a>Configurar a opção remote proc trans de configuração de servidor
  Este tópico descreve como configurar a opção de configuração de servidor **remote proc trans** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)]. A opção **remote proc trans** ajuda a proteger as ações de um procedimento servidor-para-servidor por meio de uma transação MS DTC (Coordenador de Transações Distribuídas da [!INCLUDE[msCoName](../../includes/msconame-md.md)] ).  
  
 Defina o valor de **remote proc trans** como 1 para fornecer uma transação distribuída coordenada pelo MS DTC que protege as propriedades ACID (atômica, consistente, isolada e durável) das transações. As sessões iniciadas após a definição dessa opção como 1 herdam os parâmetros de configuração como padrão.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextAvoid](../../includes/ssnotedepnextavoid-md.md)]  
  
 **Neste tópico**  
  
-   **Antes de começar:**  
  
     [Pré-requisitos](#Prerequisites)  
  
     [Recomendações](#Recommendations)  
  
     [Segurança](#Security)  
  
-   **Para configurar a opção remote proc trans, usando:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
-   **Acompanhamento:**  [depois de configurar a opção remote proc trans](#FollowUp)  
  
##  <a name="BeforeYouBegin"></a> Antes de começar  
  
###  <a name="Prerequisites"></a> Pré-requisitos  
  
-   Devem ser permitidas conexões de servidor remoto antes que este valor possa ser definido.  
  
###  <a name="Recommendations"></a> Recomendações  
  
-   Essa opção é fornecida para compatibilidade com versões anteriores do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para aplicativos que usam procedimentos armazenados remotos. Em vez de emitir chamadas a procedimentos armazenados remotos, use consultas distribuídas que fazem referência a servidores vinculados, definidos com [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).  
  
###  <a name="Security"></a> Segurança  
  
####  <a name="Permissions"></a> Permissões  
 Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão. Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor. A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .  
  
##  <a name="SSMSProcedure"></a> Usando o SQL Server Management Studio  
  
#### <a name="to-configure-the-remote-proc-trans-option"></a>Para configurar a opção remote proc trans  
  
1.  No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.  
  
2.  Clique no nó **Conexões** .  
  
3.  Em **Conexões de servidor remoto**, marque a caixa de seleção **Requer transações distribuídas para servidor para comunicação de servidor** .  
  
##  <a name="TsqlProcedure"></a> Usando o Transact-SQL  
  
#### <a name="to-configure-the-remote-proc-trans-option"></a>Para configurar a opção remote proc trans  
  
1.  Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  Na barra Padrão, clique em **Nova Consulta**.  
  
3.  Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**. Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `remote proc trans` como `1`.  
  
```tsql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote proc trans', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).  
  
##  <a name="FollowUp"></a> Acompanhamento: depois de configurar a opção remote proc trans  
 A configuração entra em vigor imediatamente sem reiniciar o servidor.  
  
## <a name="see-also"></a>Consulte também  
 [RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql)   
 [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md)   
 [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
