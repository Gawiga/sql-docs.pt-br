---
title: Precedência de tipo de dados (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 7/23/2017
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- precedence [SQL Server]
- data types [SQL Server], converting
- data types [SQL Server], precedence
- converting data types [SQL Server], precedence
- precedence [SQL Server], data types
ms.assetid: f4c804ab-ed3f-43b1-a024-c9ac6944b66b
caps.latest.revision: 21
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 14ed88abd883a06a3cc8c76c54460b552ea0bc68
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37416625"
---
# <a name="data-type-precedence-transact-sql"></a>Precedência de tipo de dados (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

Quando um operador combinar duas expressões com tipos de dados diferentes, as regras de precedência do tipo de dados especificam que o mesmo, com a precedência mais baixa, será convertido para o tipo de dado de maior precedência. Se a conversão não for uma conversão implícita com suporte, um erro será retornado. Quando ambas as expressões de operando tiverem o mesmo tipo de dados, o resultado da operação terá aquele tipo de dados.
  
O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa a seguinte ordem de precedência para tipos de dados:
  
1.  UDT (tipos de dados definidos pelo usuário) (maior)  
1.  **sql_variant**  
1.  **xml**  
1.  **datetimeoffset**  
1.  **datetime2**  
1.  **datetime**  
1.  **smalldatetime**  
1.  **date**  
1. **time**  
1. **float**  
1. **real**  
1. **decimal**  
1. **money**  
1. **smallmoney**  
1. **bigint**  
1. **int**  
1. **smallint**  
1. **tinyint**  
1. **bit**  
1. **ntext**  
1. **text**  
1. **imagem**  
1. **timestamp**  
1. **uniqueidentifier**  
1. **nvarchar** [incluindo **nvarchar(max)**]  
1. **nchar**  
1. **varchar** [incluindo **varchar(max)**]  
1. **char**  
1. **varbinary** [incluindo **varbinary(max)**]  
1. **binary** (mais baixo)  
  
## <a name="see-also"></a>Confira também
[Tipos de dados &#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)  
[Expressões &#40;Transact-SQL&#41;](../../t-sql/language-elements/expressions-transact-sql.md)  
[CAST e CONVERT &#40;Transact-SQL&#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)
  
  
