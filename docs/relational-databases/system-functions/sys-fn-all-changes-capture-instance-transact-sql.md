---
title: sys.fn_all_changes_&lt;capture_instance&gt; (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 06/02/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-functions
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server (starting with 2008)
f1_keywords:
- fn_all_changes
- sys.fn_all_changes
- fn_all_changes_TSQL
- sys.fn_all_changes_TSQL
dev_langs: TSQL
helpviewer_keywords:
- fn_all_changes_<capture_instance>
- sys.fn_all_changes_<capture_instance>
ms.assetid: 564fae96-b88c-4f22-9338-26ec168ba6f5
caps.latest.revision: "15"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 9e0ec7fbd660a9664f6d2e54f4756dd85c1bac9a
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="sysfnallchangesltcaptureinstancegt-transact-sql"></a>sys.fn_all_changes_&lt;capture_instance&gt; (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Wrappers para o **todas as alterações** funções de consulta. Os scripts necessários para criar essas funções são gerados pelo procedimento armazenado sys.sp_cdc_generate_wrapper_function.  
  
||  
|-|  
|**Aplica-se a**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] até a [versão atual](http://go.microsoft.com/fwlink/p/?LinkId=299658)).|  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
fn_all_changes_<capture_instance> ('start_time' ,'end_time', '<row_filter_option>' )  
  
<capture_instance> ::= The name of the capture instance.  
<row_filter_option> ::=  
{ all  
  | all update old  
}  
```  
  
## <a name="arguments"></a>Argumentos  
 *start_time*  
 O **datetime** valor que representa o ponto de extremidade inferior do intervalo de entradas de tabela de alteração para incluir no conjunto de resultados.  
  
 Apenas as linhas no cdc. < capture_instance > _CT alteração de tabela que tem uma hora de confirmação associada maior que *start_time* são incluídos no conjunto de resultados.  
  
 Se um valor NULL for fornecido para este argumento, o ponto de extremidade inferior do intervalo da consulta corresponderá ao ponto de extremidade inferior de um intervalo válido para a instância de captura.  
  
 *end_time*  
 O **datetime** valor que representa o ponto de extremidade superior do intervalo de entradas de tabela de alteração para incluir no conjunto de resultados.  
  
 Esse parâmetro pode assumir um dos dois significados possíveis, dependendo do valor escolhido para @closed_high_end_point quando sys. sp_cdc_generate_wrapper_function é chamado para gerar o script de criação da função de wrapper:  
  
-   @closed_high_end_point = 1  
  
     Apenas linhas da tabela de alteração cdc.<capture_instance>_CT que têm uma hora de confirmação associada menor ou igual a end_time são incluídas no conjunto de resultados.  
  
-   @closed_high_end_point = 0  
  
     Apenas linhas da tabela de alteração cdc.capture_instance_CT que têm uma hora de confirmação associada estritamente menor que end_time são incluídas no conjunto de resultados.  
  
 Se um valor NULL for fornecido para este argumento, o ponto de extremidade superior do intervalo da consulta corresponderá ao ponto de extremidade superior de um intervalo válido para a instância de captura.  
  
 <row_filter_option> ::= { all | all update old }  
 Um opção que rege o conteúdo das colunas de metadados e as linhas retornadas no conjunto de resultados.  
  
 Pode ser uma das seguintes opções:  
  
 all  
 Retorna todas as alterações do intervalo LSN especificado. Para alterações que ocorrem devido a uma operação de atualização, essa opção retorna apenas a linha que contém os novos valores após a aplicação da atualização.  
  
 all update old  
 Retorna todas as alterações do intervalo LSN especificado. Para alterações que ocorrem devido a uma operação de atualização, essa opção retorna duas linhas que contêm os valores de coluna de antes e depois da atualização.  
  
## <a name="table-returned"></a>Tabela retornada  
  
|Nome da coluna|Tipo de coluna|Description|  
|-----------------|-----------------|-----------------|  
|__CDC_STARTLSN|**binary(10)**|O LSN de confirmação da transação que é associado à alteração. Todas as alterações são confirmadas na mesma transação compartilham o mesmo LSN de confirmação.|  
|__CDC_SEQVAL|**binary(10)**|Valor de sequência usado para organizar as alterações de linha em uma transação.|  
|\<colunas de @column_list>|**varia de acordo**|As colunas que são identificadas no *column_list* argumento para a sp_cdc_generate_wrapper_function quando ela é chamada para gerar o script que cria a função de wrapper.|  
|__CDC_OPERATION|**nvarchar(2)**|Um código de operação que indica qual operação é necessária para aplicar a linha ao ambiente de destino. Ele pode variar com base no valor do argumento *row_filter_option* fornecido na chamada:<br /><br /> *row_filter_option* = 'todos'<br /><br /> 'D' – exclui a operação<br /><br /> 'I' – insere a operação<br /><br /> 'UN' – atualiza os novos valores da operação<br /><br /> *row_filter_option* = 'all update old'<br /><br /> 'D' – exclui a operação<br /><br /> 'I' – insere a operação<br /><br /> 'UN' – atualiza os novos valores da operação<br /><br /> 'UO' – atualiza os valores antigos da operação|  
|\<colunas de @update_flag_list>|**bit**|Um sinalizador de bit é nomeado acrescentando uflag ao nome da coluna. O sinalizador é sempre definido como NULL quando \__CDC_OPERATION for ', 'I', de 'UO'. Quando \__CDC_OPERATION é 'UN', ele é definido como 1 se a atualização produziu uma alteração na coluna correspondente. Caso contrário, será 0.|  
  
## <a name="remarks"></a>Comentários  
 A função fn_all_changes_<capture_instance> serve como um wrapper para a função de consulta cdc.fn_cdc_get_all_changes_<capture_instance>. O procedimento armazenado sys.sp_cdc_generate_wrapper é usado para gerar o script para criar o wrapper.  
  
 As funções de wrapper não são criadas automaticamente. Há duas coisas que você precisa fazer para criar funções de wrapper:  
  
1.  Executar o procedimento armazenado para gerar o script para criar o wrapper.  
  
2.  Executar o script para realmente criar a função de wrapper.  
  
 Funções de wrapper permitem que os usuários consultem sistematicamente as alterações que ocorreram dentro de um intervalo limitado por **datetime** valores em vez de por valores LSN. As funções de wrapper executam todas as conversões necessárias entre fornecido **datetime** valores e os valores LSN necessários internamente como argumentos para as funções de consulta. Quando as funções de wrapper são usadas em série para processar um fluxo de dados de alteração, elas garantem que nenhum dado seja perdido ou repetido desde que a seguinte convenção seja seguida: o @end_time valor do intervalo associado a uma chamada é fornecido como o @start_time valor para o intervalo associado à chamada subsequente.  
  
 Usando o parâmetro @closed_high_end_point ao criar o script, você pode gerar wrappers para oferecer suporte a um limite superior fechado ou a um limite superior em aberto na janela de consulta especificada. Ou seja, você pode decidir se as entradas que têm uma hora de confirmação igual ao limite superior do intervalo de extração devem ser incluídas no intervalo. Por padrão, o limite superior é incluído.  
  
 O conjunto de resultados retornado pelo **todas as alterações** função de invólucro retorna o _ $start_lsn e \_ \_$seqval a colunas da tabela de alteração como colunas \__CDC_STARTLSN e \__ CDC_SEQVAL, respectivamente. Isso acontece com somente aquelas colunas rastreadas que eram exibidos no  *@column_list*  parâmetro quando o wrapper foi gerado. Se  *@column_list*  for NULL, todos os origem rastreadas, as colunas serão retornadas. As colunas de origem são seguidas por uma coluna de operação, \__CDC_OPERATION, que é uma coluna de um ou dois caracteres que identifica a operação.  
  
 Em seguida, os sinalizadores de bit são acrescentados ao conjunto de resultados para cada coluna identificada no parâmetro @update_flag_list. Para o **todas as alterações** wrapper, os sinalizadores de bit sempre será NULL se cdc_operation for tinha ', 'I' ou 'UO'. Se \__CDC_OPERATION é 'UN', o sinalizador será definido como 1 ou 0, dependendo se a operação de atualização causou uma alteração na coluna.  
  
 O modelo de configuração do Change Data Capture 'Criar uma instância de TVFs de wrapper CDC para esquema' mostra como usar o procedimento armazenado sp_cdc_generate_wrapper_function para obter scripts CREATE para todas as funções de wrapper para funções de consulta definidas por um esquema. Em seguida, o modelo cria esses scripts. Para obter mais informações sobre modelos, consulte [Explorador](http://msdn.microsoft.com/library/b9ee55c5-bb44-4f76-90ac-792d8d83b4c8).  
  
## <a name="see-also"></a>Consulte também  
 [sys. sp_cdc_generate_wrapper_function &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-generate-wrapper-function-transact-sql.md)   
 [CDC. fn_cdc_get_all_changes_ &#60; capture_instance &#62;  &#40; Transact-SQL &#41;](../../relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql.md)  
  
  