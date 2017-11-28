---
title: sp_help_jobschedule (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 08/09/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_help_jobschedule
- sp_help_jobschedule_TSQL
dev_langs: TSQL
helpviewer_keywords: sp_help_jobschedule
ms.assetid: 2cded902-9272-4667-ac4b-a4f95a9f008e
caps.latest.revision: "34"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 1f111a04bfe27fad284157082ec1bbbeadfb92c8
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="sphelpjobschedule-transact-sql"></a>sp_help_jobschedule (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retorna informações sobre o agendamento de trabalhos usado pelo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para executar atividades automatizadas.  
 
 
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_help_jobschedule { [ @job_id = ] job_id | [ @job_name = ] 'job_name' }  
     [ , [ @schedule_name = ] 'schedule_name' ]  
     [ , [ @schedule_id = ] schedule_id ]  
     [ , [ @include_description = ] include_description ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@job_id=** ] *job_id*  
 O número de identificação do trabalho. *job_id*é **uniqueidentifier**, com um padrão NULL.  
  
 [  **@job_name=** ] **'***job_name***'**  
 O nome do trabalho. *job_name*é **sysname**, com um padrão NULL.  
  
> **Observação:** ou *job_id* ou *job_name* devem ser especificados, mas não é possível especificar ambos.  
  
 [  **@schedule_name=** ] **'***schedule_name***'**  
 O nome do item de agenda que será definido para o trabalho. *schedule_name*é **sysname**, com um padrão NULL.  
  
 [  **@schedule_id=** ] *schedule_id*  
 O número de identificação do item de agenda do trabalho. *schedule_id*é **int**, com um padrão NULL.  
  
 [  **@include_description=** ] *include_description*  
 Especifica se deve ser incluída a descrição da agenda no conjunto de resultados. *include_description* é **bit**, com um padrão de **0**. Quando *include_description* é **0**, a descrição da agenda não está incluída no conjunto de resultados. Quando *include_description* é **1**, a descrição da agenda será incluída no conjunto de resultados.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 0 (êxito) ou 1 (falha)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**schedule_id**|**int**|Número do identificador de agenda.|  
|**schedule_name**|**sysname**|Nome da agenda.|  
|**habilitado**|**int**|Se a agenda foi habilitada (**1**) ou não habilitado (**0**).|  
|**freq_type**|**int**|Valor que indica quando o trabalho a ser executado.<br /><br /> **1** = uma vez<br /><br /> **4** = diariamente<br /><br /> **8** = semanalmente<br /><br /> **16** = mensalmente<br /><br /> **32** = mensalmente, relativo a **freq_interval**<br /><br /> **64** = executar quando **SQLServerAgent** inicia o serviço.|  
|**freq_interval**|**int**|Dias em que o trabalho é executado. O valor depende do valor de **freq_type**. Para obter mais informações, consulte [sp_add_schedule &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-add-schedule-transact-sql.md).|  
|**freq_subday_type**|**int**|Unidades de **freq_subday_interval**. Para obter mais informações, consulte [sp_add_schedule &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-add-schedule-transact-sql.md).|  
|**freq_subday_interval**|**int**|Número de **freq_subday_type** períodos devem ocorrer entre cada execução do trabalho. Para obter mais informações, consulte [sp_add_schedule &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-add-schedule-transact-sql.md).|  
|**freq_relative_interval**|**int**|Ocorrência do trabalho de agendado a **freq_interval** em cada mês. Para obter mais informações, consulte [sp_add_schedule &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-add-schedule-transact-sql.md).|  
|**freq_recurrence_factor**|**int**|Número de meses entre a execução agendada do trabalho.|  
|**active_start_date**|**int**|Data em que a agenda foi ativada.|  
|**active_end_date**|**int**|Data de término da agenda.|  
|**active_start_time**|**int**|Hora do dia em que a agenda é iniciada.|  
|**active_end_time**|**int**|Hora do dia em que a agenda é encerrada.|  
|**Date_Created**|**datetime**|Data em que a agenda foi criada.|  
|**schedule_description**|**nvarchar(4000)**|Uma descrição em inglês da agenda que é derivada dos valores de **sysschedules**. Quando *include_description* é **0**, esta coluna contém o texto que informando que a descrição não foi solicitada.|  
|**next_run_date**|**int**|Próxima data em que a agenda fará com que o trabalho seja executado.|  
|**next_run_time**|**int**|Próxima hora em que a agenda fará com que o trabalho seja executado.|  
|**schedule_uid**|**uniqueidentifier**|Identificador da agenda.|  
|**job_count**|**int**|Contagem de trabalhos retornados.|  
  
> **Observação:****sp_help_jobschedule** retorna valores da **dbo. sysjobschedules** e **dbo. sysschedules** tabelas do sistema em **msdb** .   **sysjobschedules** atualizado a cada 20 minutos. Isso pode afetar os valores que são retornados por esse procedimento armazenado.  
  
## <a name="remarks"></a>Comentários  
 Os parâmetros de **sp_help_jobschedule** pode ser usado somente em determinadas combinações. Se *schedule_id* for especificada, nem *job_id* nem *job_name* pode ser especificado. Caso contrário, o *job_id* ou *job_name* parâmetros podem ser usados com *schedule_name*.  
  
## <a name="permissions"></a>Permissões  
 Exige associação à função de servidor fixa **sysadmin** . Deve ser concedida a outros usuários uma das seguintes funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no banco de dados **msdb** :  
  
-   **SQLAgentUserRole**  
  
-   **SQLAgentReaderRole**  
  
-   **SQLAgentOperatorRole**  
  
 Para obter detalhes sobre as permissões dessas funções, consulte [Funções de banco de dados fixas do SQL Server Agent](http://msdn.microsoft.com/library/719ce56b-d6b2-414a-88a8-f43b725ebc79).  
  
 Membros de **SQLAgentUserRole** só pode exibir as propriedades de agendas de trabalho que eles possuem.  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-returning-the-job-schedule-for-a-specific-job"></a>A. Retornando a agenda de trabalho para um trabalho específico  
 O exemplo a seguir retorna todas as informações de agendamento do trabalho chamado `BackupDatabase`.  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_help_jobschedule  
    @job_name = N'BackupDatabase' ;  
GO  
```  
  
### <a name="b-returning-the-job-schedule-for-a-specific-schedule"></a>B. Retornando a agenda de trabalho de uma agenda específica  
 O exemplo a seguir retorna as informações da agenda chamada `NightlyJobs` e do trabalho chamado `RunReports`.  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_help_jobschedule   
    @job_name = N'RunReports',  
    @schedule_name = N'NightlyJobs' ;  
GO  
```  
  
### <a name="c-returning-the-job-schedule-and-schedule-description-for-a-specific-schedule"></a>C. Retornando a agenda de trabalho e a descrição de uma agenda específica  
 O exemplo a seguir retorna as informações da agenda chamada `NightlyJobs` e do trabalho chamado `RunReports`. O conjunto de resultados retornado inclui uma descrição da agenda.  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_help_jobschedule  
    @job_name = N'RunReports',  
    @schedule_name = N'NightlyJobs',  
    @include_description = 1 ;  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
 [sp_add_schedule &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-add-schedule-transact-sql.md)   
 [sp_delete_schedule &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-delete-schedule-transact-sql.md)   
 [sp_update_schedule &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-update-schedule-transact-sql.md)   
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  