---
title: DESCARTAR CLASSIFICAÇÃO DE CONFIDENCIALIDADE (Transact-SQL) | Microsoft Docs
ms.date: 06/17/2018
ms.reviewer: ''
ms.prod: sql
ms.prod_service: sql-database
ms.service: sql-database
ms.technology: t-sql
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
ms.custom: ''
ms.manager: craigg
ms.author: giladm
author: giladmit
f1_keywords:
- DROP SENSITIVITY CLASSIFICATION
- DROP_SENSITIVITY_CLASSIFICATION
dev_langs:
- TSQL
helpviewer_keywords:
- DROP SENSITIVITY CLASSIFICATION statement
- dropping labels
- drop labels
- removing labels
- remove labels
- classification [SQL]
- labels [SQL]
- information types
- data classification
monikerRange: = azuresqldb-current || = sqlallproducts-allversions
ms.openlocfilehash: 7571742d0484065a90734ad9d9972e37076e20d3
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38058665"
---
# <a name="drop-sensitivity-classification-transact-sql"></a>DESCARTAR CLASSIFICAÇÃO DE CONFIDENCIALIDADE (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md.md)]

Descarta metadados de classificação de confidencialidade de uma ou mais colunas do banco de dados.

## <a name="syntax"></a>Sintaxe

```sql
DROP SENSITIVITY CLASSIFICATION FROM
    <object_name> [, ...n ]

<object_name> ::=
{
    [schema_name.]table_name.column_name
}
```  

## <a name="arguments"></a>Argumentos  

*object_name* ([schema_name.]table_name.column_name)

É o nome da coluna do banco de dados a partir da qual remover a classificação. Atualmente, há suporte apenas para a classificação da coluna.
    - *schema_name* (opcional) - é o nome do esquema ao qual a coluna classificada pertence.
    - *table_name* - é o nome da tabela à qual a coluna classificada pertence.
    - *column_name* - é o nome da coluna da qual remover a classificação.

## <a name="remarks"></a>Remarks  

- Várias classificações de objetos podem ser descartadas usando uma única instrução 'DESCARTAR CLASSIFICAÇÃO DE CONFIDENCIALIDADE'.

## <a name="permissions"></a>Permissões  

Requer a permissão ALTERAR QUALQUER CLASSIFICAÇÃO DE CONFIDENCIALIDADE. ALTERAR QUALQUER CLASSIFICAÇÃO DE CONFIDENCIALIDADE está implícita na permissão de banco de dados ALTERAR, ou pelo servidor de permissão SERVIDOR DE CONTROLE.


## <a name="examples"></a>Exemplos  


### <a name="a-dropping-classification-from-a-single-column"></a>A. Descartar a classificação de uma única coluna

O exemplo a seguir remove a classificação da coluna `dbo.sales.price`.  

```sql
DROP SENSITIVITY CLASSIFICATION FROM
    dbo.sales.price
```

### <a name="b-dropping-classification-from-multiple-columns"></a>B. Descartar a classificação de várias colunas

O exemplo a seguir remove a classificação das colunas `dbo.sales.price`, `dbo.sales.discount`, e `SalesLT.Customer.Phone`.  

```sql
DROP SENSITIVITY CLASSIFICATION FROM
    dbo.sales.price, dbo.sales.discount, SalesLT.Customer.Phone  
```

## <a name="see-also"></a>Consulte Também  

[ADICIONAR CLASSIFICAÇÃO DE CONFIDENCIALIDADE (Transact-SQL)](../../t-sql/statements/add-sensitivity-classification-transact-sql.md)

[sys.sensitivity_classifications (Transact-SQL)](../../relational-databases/system-catalog-views/sys-sensitivity-classifications-transact-sql.md)

[Introdução à Proteção de Informações do SQL](http://aka.ms/sqlip)
