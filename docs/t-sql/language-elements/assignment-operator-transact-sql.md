---
title: = (Operador de atribuição) (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- operators [Transact-SQL], assignment
- assignment operators [Transact-SQL]
- headings [SQL Server columns]
- relationships [SQL Server], assignment operators
- column headings [SQL Server]
ms.assetid: c3040db6-21d6-40ac-a783-82c98ec006cc
caps.latest.revision: 29
author: douglaslMS
ms.author: douglasl
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 3c553318dd41c91dbeffa5f4bafc4866d755c80e
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43067289"
---
# <a name="-assignment-operator-transact-sql"></a>= (Operador de atribuição) (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-all_md](../../includes/tsql-appliesto-ss2012-all-md.md)]

  O sinal de igual (=) é o único operador de atribuição [!INCLUDE[tsql](../../includes/tsql-md.md)]. No exemplo a seguir, a variável `@MyCounter` é criada, e o operador de atribuição define `@MyCounter` com um valor retornado por uma expressão.  
  
```  
DECLARE @MyCounter INT;  
SET @MyCounter = 1;  
```  
  
 O operador de atribuição também pode ser usado para estabelecer a relação entre um título de coluna e a expressão que define os valores para a coluna. O exemplo a seguir exibe os títulos de coluna `FirstColumnHeading` e `SecondColumnHeading`. A cadeia de caracteres `xyz` é exibida no título de coluna `FirstColumnHeading` para todas as linhas. Depois, cada ID de produto da tabela `Product` é listada no título de coluna `SecondColumnHeading`.  
  
```  
-- Uses AdventureWorks  
  
SELECT FirstColumnHeading = 'xyz',  
       SecondColumnHeading = ProductID  
FROM Production.Product;  
GO  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Operadores &#40;Transact-SQL&#41;](../../t-sql/language-elements/operators-transact-sql.md)   
 [Operadores compostos &#40;Transact-SQL&#41;](../../t-sql/language-elements/compound-operators-transact-sql.md)   
 [Expressões &#40;Transact-SQL&#41;](../../t-sql/language-elements/expressions-transact-sql.md)  
  
  
