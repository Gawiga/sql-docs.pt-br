---
title: sp_rda_set_query_mode (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: dbe-stretch
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.sp_rda_set_query_mode
- sys.sp_rda_set_query_mode_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.sp_rda_set_query_mode stored procedure
ms.assetid: 65a0b390-cf87-4db7-972a-1fdf13456c88
caps.latest.revision: "11"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: a98d67b6d6cec581cdfcff31f7f9c0fd692b2520
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="syssprdasetquerymode-transact-sql"></a>sp_rda_set_query_mode (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Especifica se as consultas em relação a ampliação habilitada banco de dados atual e suas tabelas retornam dados locais e remotos (o padrão) ou apenas os dados locais.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_rda_set_query_mode [ @mode = ] @mode   
    [ , [ @force = ]  @force ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [ @mode = ] *@mode*  
 É um dos valores a seguir.  
  
-   **DESABILITADO** todas as consultas em tabelas habilitadas para Stretch falharem.  
  
-   **LOCAL_ONLY** consultas em tabelas habilitadas para Stretch retornam apenas os dados locais.  
  
-   **LOCAL_AND_REMOTE** consultas em tabelas habilitadas para Stretch retornam dados locais e remotos. Esse é o comportamento padrão.  
  
 [ @force = ]  *@force*  
 É um valor de bit opcional que pode ser definido como 1 se você quiser alterar o modo de consulta sem validação.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 0 (êxito) ou >0 (falha)  
  
## <a name="permissions"></a>Permissões  
 Requer permissões db_owner.  
  
## <a name="remarks"></a>Comentários  
 Os seguintes procedimentos armazenados estendidos também definem o modo de consulta para um banco de dados habilitado para Stretch.  
  
-   **sp_rda_deauthorize_db**  
  
     Depois de executar **sp_rda_deauthorize_db** , todas as consultas em tabelas e bancos de dados habilitados para Stretch falharem. Ou seja, o modo de consulta é definido como desabilitado. Para sair deste modo, siga um destes procedimentos.  
  
    -   Executar [sys. sp_rda_reauthorize_db &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sys-sp-rda-reauthorize-db-transact-sql.md) reconectar-se ao banco de dados remoto do Azure. Esta operação redefine automaticamente o modo de consulta como LOCAL_AND_REMOTE, que é o comportamento padrão para o Stretch Database. Ou seja, consultas retornam resultados de dados locais e remotos.  
  
    -   Executar [sp_rda_set_query_mode](../../relational-databases/system-stored-procedures/sys-sp-rda-set-query-mode-transact-sql.md) com o argumento LOCAL_ONLY para permitir que consultas continue executar apenas dados locais.  
  
-   **sp_rda_reauthorize_db**  
  
     Quando você executa [sys. sp_rda_reauthorize_db &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sys-sp-rda-reauthorize-db-transact-sql.md) para se reconectar ao banco de dados remoto do Azure, essa operação redefine automaticamente o modo de consulta para LOCAL_AND_REMOTE, que é o comportamento padrão para o Stretch Database. Ou seja, consultas retornam resultados de dados locais e remotos.  
  
## <a name="see-also"></a>Consulte também  
 [sys. sp_rda_deauthorize_db &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-rda-deauthorize-db-transact-sql.md)   
 [Stretch Database](../../sql-server/stretch-database/stretch-database.md)  
  
  