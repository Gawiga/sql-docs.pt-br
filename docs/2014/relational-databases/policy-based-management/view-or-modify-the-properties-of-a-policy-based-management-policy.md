---
title: Exibir ou modificar as propriedades de uma política de gerenciamento baseado em políticas | Microsoft Docs
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
- Policy-Based Management, modify policies
- Policy-Based Management, view policies
ms.assetid: ba805504-5db5-4731-a8da-a0e89cb20c37
caps.latest.revision: 8
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 55279874fea6a3590f84ef5aad87a8d4f92fab19
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37258472"
---
# <a name="view-or-modify-the-properties-of-a-policy-based-management-policy"></a>Exibir ou modificar as propriedades de uma política de gerenciamento baseado em políticas
  Este tópico descreve como exibir ou modificar as propriedades de uma política de gerenciamento baseado em políticas [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
 **Neste tópico**  
  
-   **Antes de começar:**  
  
     [Segurança](#Security)  
  
-   **Para exibir ou modificar propriedades de uma política, usando:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Antes de começar  
  
###  <a name="Security"></a> Segurança  
  
####  <a name="Permissions"></a> Permissões  
 Requer a associação à função PolicyAdministratorRole no banco de dados msdb.  
  
##  <a name="SSMSProcedure"></a> Usando o SQL Server Management Studio  
  
#### <a name="to-view-the-properties-of-all-policies-on-an-object"></a>Para exibir as propriedades de todas as políticas em um objeto  
  
1.  Em Pesquisador de Objetos, clique com o botão direito do mouse em um servidor, objeto de servidor, banco de dados ou objeto de banco de dados, aponte para **Políticas** e selecione **Exibir**. Para obter mais informações sobre as opções disponíveis na caixa de diálogo **Exibir políticas –***object_name*, veja [Caixa de diálogo Exibir Políticas](view-policies-dialog-box.md).  
  
2.  Quando terminar, clique em **Fechar**.  
  
#### <a name="to-view-or-modify-a-specific-policys-properties"></a>Para exibir ou modificar as propriedades de uma política específica  
  
1.  No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém a Política de Gerenciamento Baseado em Políticas que você deseja exibir ou modificar.  
  
2.  Clique no sinal de adição para expandir a pasta **Gerenciamento** .  
  
3.  Clique no sinal de adição para expandir a pasta **Gerenciamento de Política**.  
  
4.  Clique no sinal de adição para expandir a pasta **Políticas** .  
  
5.  Clique com o botão direito do mouse na política que você deseja exibir ou modificar e selecione **Propriedades**. Para obter mais informações sobre as opções disponíveis na caixa de diálogo **Abrir Política –***policy_name*, consulte [Caixa de diálogo Criar Nova Política ou Abrir Política, Página Geral](../../integration-services/general-page-of-integration-services-designers-options.md) e [Caixa de diálogo Criar Nova Política ou Abrir Política, Página Descrição](create-new-policy-or-open-policy-dialog-box-description-page.md).  
  
6.  Quando terminar, clique em **OK**.  
  
##  <a name="TsqlProcedure"></a> Usando o Transact-SQL  
  
#### <a name="to-view-a-policys-properties"></a>Para exibir as propriedades de uma política  
  
1.  No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  Na barra Padrão, clique em **Nova Consulta**.  
  
3.  Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.  
  
    ```  
    USE msdb;  
    GO  
    SELECT name,  
       execution_mode,  
       description,  
       is_enabled,  
       job_id  
    FROM syspolicy_policies;  
    GO  
    ```  
  
 Para obter mais informações, veja [syspolicy_policies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-policies-transact-sql).  
  
  
