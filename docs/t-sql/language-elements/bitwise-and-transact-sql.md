---
title: '&amp;(AND bit a bit) (Transact-SQL) | Microsoft Docs'
ms.custom: 
ms.date: 01/10/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bitwise
- '&'
- '&_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- AND, bitwise AND
- '& (bitwise AND)'
- bitwise AND (&)
ms.assetid: 20275755-4fa7-47b1-a9be-ac85606d63b0
caps.latest.revision: 42
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: e862f742a97f0ea66edcfe32d28224c6fbbeff70
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="amp-bitwise-and-transact-sql"></a>&amp;(AND bit a bit) (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Executa uma operação lógica AND bit a bit entre dois valores inteiros.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
expression & expression  
```  
  
## <a name="arguments"></a>Argumentos  
 *expressão*  
 É qualquer [expressão](../../t-sql/language-elements/expressions-transact-sql.md) de qualquer um dos tipos de dados da categoria de tipo de dados inteiro, ou o **bit**, ou o **binário** ou **varbinary** dados tipos. *expressão* é tratado como um número binário para a operação bit a bit.  
  
> [!NOTE]  
>  Em uma operação bit a bit, apenas um *expressão* pode ser do **binário** ou **varbinary** tipo de dados.  
  
## <a name="result-types"></a>Tipos de resultado  
 **int** se os valores de entrada são **int**.  
  
 **smallint** se os valores de entrada são **smallint**.  
  
 **tinyint** se os valores de entrada são **tinyint** ou **bit**.  
  
## <a name="remarks"></a>Comentários  
 O  **&**  operador bit a bit executa um AND lógico bit a bit entre as duas expressões, usando cada bit para ambas as expressões correspondente. Os bits no resultado são definidos como 1 se e somente se os dois bits (para o bit atual a ser resolvido) nas expressões de entrada tiverem um valor de 1; caso contrário, o bit no resultado será definido como 0.  
  
 Se as expressões de esquerda e direita têm tipos de dados inteiros diferentes (por exemplo, à esquerda *expressão* é **smallint** e *expressão* é  **int**), o argumento do tipo de dados menor é convertido para o tipo de dados maior. Nesse caso, o **smallint***expressão* é convertido em um **int**.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir cria uma tabela usando o **int** tipo para armazenar os valores de dados e insere os dois valores em uma linha.  
  
```  
CREATE TABLE bitwise  
(   
a_int_value int NOT NULL,  
b_int_value int NOT NULL  
);  
GO  
INSERT bitwise VALUES (170, 75);  
GO  
```  
  
 Esta consulta executa o AND bit a bit nas colunas `a_int_value` e `b_int_value`.  
  
```  
SELECT a_int_value & b_int_value  
FROM bitwise;  
GO  
```  
  
 Este é o conjunto de resultados:  
  
```  
-----------   
10            
  
(1 row(s) affected)  
```  
  
 A representação binária de 170 (`a_int_value` ou `A`) é `0000 0000 1010 1010`. A representação binária de 75 (`b_int_value` ou `B`) é `0000 0000 0100 1011`. A execução da operação AND bit a bit nesses dois valores produz o resultado binário `0000 0000 0000 1010`, que é o decimal 10.  
  
```  
(A & B)  
0000 0000 1010 1010  
0000 0000 0100 1011  
-------------------  
0000 0000 0000 1010  
```  
  
  
## <a name="see-also"></a>Consulte também  
 [Expressões &#40; Transact-SQL &#41;](../../t-sql/language-elements/expressions-transact-sql.md)   
 [Operadores &#40; Transact-SQL &#41;](../../t-sql/language-elements/operators-transact-sql.md)   
 [Operadores bit a bit &#40; Transact-SQL &#41;](../../t-sql/language-elements/bitwise-operators-transact-sql.md)   
 [& = &#40; AND bit a bit EQUALS &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/bitwise-and-equals-transact-sql.md)   
 [Composta operadores &#40; Transact-SQL &#41;](../../t-sql/language-elements/compound-operators-transact-sql.md)  
  
  


