---
title: DBCC TRACESTATUS (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/17/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DBCC_TRACESTATUS_TSQL
- DBCC TRACESTATUS
- TRACESTATUS_TSQL
- TRACESTATUS
dev_langs:
- TSQL
helpviewer_keywords:
- global trace flags [SQL Server]
- status information [SQL Server], trace flags
- trace flags [SQL Server], status information
- DBCC TRACESTATUS statement
- session trace flags [SQL Server]
- displaying trace flag status
ms.assetid: 9be51199-78b4-4b87-ae6e-557246b7e29a
caps.latest.revision: 36
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 75d78069427891cfab6f7aaef7192d498912611a
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="dbcc-tracestatus-transact-sql"></a>DBCC TRACESTATUS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

Exibe o status de sinalizadores de rastreamento.
  
![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Sintaxe  
  
```sql
DBCC TRACESTATUS ( [ [ trace# [ ,...n ] ] [ , ] [ -1 ] ] )   
[ WITH NO_INFOMSGS ]  
```  
  
## <a name="arguments"></a>Argumentos  
*Trace #*  
É o número do sinalizador de rastreamento para o qual o status é exibido. Se *trace #*e -1 não forem especificados, todos os sinalizadores de rastreamento estão habilitados para a sessão são exibidos.
  
*n*  
É um espaço reservado que indica que vários sinalizadores de rastreamento podem ser especificados.
  
-1  
Exibe o status dos sinalizadores de rastreamento habilitados globalmente. Se -1 for especificado sem *trace #*, todos os sinalizadores de rastreamento globais habilitados são exibidos.
  
WITH NO_INFOMSGS  
Suprime todas as mensagens informativas com níveis de severidade de 0 a 10.
  
## <a name="result-sets"></a>Conjuntos de resultados  
A tabela a seguir descreve as informações do conjunto de resultados.
  
|Nome da coluna|Description|  
|---|---|
|**Sinalizador de rastreamento**|Nome do sinalizador de rastreamento|  
|**Status**|Indica se o sinalizador de rastreamento está definido como ON ou OFF, globalmente ou para a sessão.<br /><br /> 1 = ON<br /><br /> 0 = OFF|  
|**Global**|Indica se o sinalizador de rastreamento está definido globalmente<br /><br /> 1 = True<br /><br /> 0 = False|  
|**Sessão**|Indica se o sinalizador de rastreamento está definido para a sessão<br /><br /> 1 = True<br /><br /> 0 = False|  
  
DBCC TRACESTATUS retorna uma coluna para o número de sinalizador de rastreamento e uma coluna para o status. Isso indica se o sinalizador de rastreamento é ON (1) ou OFF (0). O cabeçalho da coluna para o número do sinalizador de rastreamento é **sinalizador de rastreamento Global** ou **sinalizador de rastreamento de sessão**, dependendo se você está verificando o status global ou de um sinalizador de rastreamento de sessão.
  
## <a name="remarks"></a>Comentários  
No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], há dois tipos de sinalizadores de rastreamento: sessão e global. Os sinalizadores de rastreamento de sessão são ativos para uma conexão e são visíveis apenas para essa conexão. Sinalizadores de rastreamento globais são definidos no nível do servidor e são visíveis em todas as conexões no servidor.
  
## <a name="permissions"></a>Permissões  
Requer associação à função **pública** .
  
## <a name="examples"></a>Exemplos  
O exemplo a seguir exibe o estado de todos os sinalizadores de rastreamento atuais habilitados globalmente.
  
```sql  
DBCC TRACESTATUS(-1);  
GO  
```  
  
O exemplo a seguir exibe o status dos indicadores de rastreamento `2528` e `3205`.
  
```sql  
DBCC TRACESTATUS (2528, 3205);  
GO  
```  
  
O exemplo a seguir exibe se o sinalizador de rastreamento `3205` está habilitado globalmente.
  
```sql  
DBCC TRACESTATUS (3205, -1);  
GO  
```  
  
O exemplo a seguir lista todos os sinalizadores de rastreamento habilitados para a sessão atual.
  
```sql  
DBCC TRACESTATUS();  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
[DBCC &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-transact-sql.md)  
[DBCC TRACEOFF &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-traceoff-transact-sql.md)  
[DBCC TRACEON &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-traceon-transact-sql.md)  
[Sinalizadores de rastreamento &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql.md)
  
  
