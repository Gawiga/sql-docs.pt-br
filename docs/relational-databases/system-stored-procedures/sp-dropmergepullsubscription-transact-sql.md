---
title: sp_dropmergepullsubscription (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- sp_dropmergepullsubscription
- sp_dropmergepullsubscription_TSQL
helpviewer_keywords:
- sp_dropmergepullsubscription
ms.assetid: 9301dd80-72f7-4adb-9b13-87e7f9114248
caps.latest.revision: 31
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 1fa2a31c5ef60b869fe387e4a3ac8155a73d3690
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43017952"
---
# <a name="spdropmergepullsubscription-transact-sql"></a>sp_dropmergepullsubscription (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Descarta uma assinatura pull de mesclagem. Esse procedimento armazenado é executado no assinante, no banco de dados de assinatura.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_dropmergepullsubscription [ @publication= ] 'publication'   
        , [ @publisher= ] 'publisher'   
        , [ @publisher_db= ] 'publisher_db'   
    [ , [ @reserved= ] 'reserved' ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@publication=**] **'***publicação***'**  
 É o nome da publicação. *publicação* está **sysname**, com um padrão NULL. Este parâmetro é obrigatório. Especifique um valor de **todos os** para remover assinaturas de todas as publicações  
  
 [  **@publisher=**] **'***publisher***'**  
 É o nome do Publicador. *Publisher*está **sysname**, com um padrão NULL. Este parâmetro é obrigatório.  
  
 [  **@publisher_db=**] **'***publisher_db***'**  
 É o nome do banco de dados Publicador. *publisher_db*está **sysname**, com um padrão NULL. Este parâmetro é obrigatório.  
  
 [  **@reserved=**] **'***reservado***'**  
 É reservado para uso futuro. *reservado* está **bit**, com um padrão de **0**.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Remarks  
 **sp_dropmergepullsubscription** é usado em replicação de mesclagem.  
  
 **sp_dropmergepullsubscription** descarta o Merge Agent para essa assinatura pull de mesclagem, embora o agente de mesclagem não é criado no **sp_addmergepullsubscription**.  
  
## <a name="example"></a>Exemplo  
 [!code-sql[HowTo#sp_dropmergepullsubscription](../../relational-databases/replication/codesnippet/tsql/sp-dropmergepullsubscrip_1.sql)]  
  
## <a name="permissions"></a>Permissões  
 Somente os membros dos **sysadmin** função de servidor fixa ou o usuário que criou a assinatura pull de mesclagem pode executar **sp_dropmergepullsubscription**. O **db_owner** função de banco de dados fixa só é capaz de executar **sp_dropmergepullsubscription** se o usuário que criou a assinatura pull de mesclagem pertence a essa função.  
  
## <a name="see-also"></a>Consulte também  
 [Excluir uma assinatura Pull](../../relational-databases/replication/delete-a-pull-subscription.md)   
 [sp_addmergepullsubscription &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addmergepullsubscription-transact-sql.md)   
 [sp_changemergepullsubscription &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-changemergepullsubscription-transact-sql.md)   
 [sp_dropmergesubscription &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dropmergesubscription-transact-sql.md)   
 [sp_helpmergepullsubscription &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-helpmergepullsubscription-transact-sql.md)  
  
  
