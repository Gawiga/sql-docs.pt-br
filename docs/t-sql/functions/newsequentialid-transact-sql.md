---
title: NEWSEQUENTIALID (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 08/08/2015
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- NEWSEQUENTIALID
- NEWSEQUENTIALID_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- NEWSEQUENTIALID function
- GUIDs [SQL Server]
ms.assetid: e06d2cab-f1ff-42f1-8550-6aaec57be36f
caps.latest.revision: 33
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 2a453b99d7ab0512e57275b5ad1805f5a66522ba
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="newsequentialid-transact-sql"></a>NEWSEQUENTIALID (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Cria um GUID que é maior que qualquer GUID anteriormente gerado por esta função em um computador especificado desde o início do Windows. Após o reinício do Windows, o GUID poderá ser iniciado novamente a partir de um intervalo inferior, mas ainda será globalmente exclusivo. Quando uma coluna de GUID é usada como um identificador de linha, usar NEWSEQUENTIALID pode ser mais rápido do que usar a função NEWID. Isso ocorre porque a função NEWID provoca atividade aleatória e usa menos páginas de dados do cache. O uso de NEWSEQUENTIALID também ajuda a preencher completamente as páginas de dados e índice.  
  
> [!IMPORTANT]  
>  Se a privacidade for uma preocupação, não use esta função. É possível adivinhar o valor do próximo GUID gerado e, assim, acessar os dados associados ao GUID.  
  
 NEWSEQUENTIALID é um wrapper sobre o Windows [UuidCreateSequential](http://go.microsoft.com/fwlink/?LinkId=164027) função.  
  
> [!WARNING]  
>  A função UuidCreateSequential tem dependências de hardware. Em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], clusters de valores sequenciais podem desenvolver quando os bancos de dados (como bancos de dados independentes) são movidos para outros computadores. Ao usar o AlwaysOn e em [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)], clusters de valores sequenciais podem desenvolver se o banco de dados faz failover para um computador diferente.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
NEWSEQUENTIALID ( )  
```  
  
## <a name="return-type"></a>Tipo de retorno  
 **uniqueidentifier**  
  
## <a name="remarks"></a>Comentários  
 Newsequentialid () só pode ser usado com restrições padrão nas colunas da tabela do tipo **uniqueidentifier**. Por exemplo:  
  
```  
CREATE TABLE myTable (ColumnA uniqueidentifier DEFAULT NEWSEQUENTIALID());   
```  
  
 Quando NEWSEQUENTIALID() for usada em expressões DEFAULT, não pode ser combinada com outros operadores escalares. Por exemplo, não é possível executar a seguinte consulta:  
  
```  
CREATE TABLE myTable (ColumnA uniqueidentifier DEFAULT dbo.myfunction(NEWSEQUENTIALID()));  
```  
  
 No exemplo anterior, `myfunction()` é uma função escalar de escalar definida pelo usuário que aceita e retorna um valor `uniqueidentifier`.  
  
 NEWSEQUENTIALID() não pode ser referenciada em consultas.  
  
 Você pode usar NEWSEQUENTIALID para gerar GUIDs e reduzir a contenção da página no nível folha de índices.  
  
 Cada GUID gerado usando NEWSEQUENTIALID é exclusivo nesse computador. Os GUIDs gerados com NEWSEQUENTIALID serão exclusivos entre vários computadores somente se o computador de origem tiver uma placa de rede.  
  
## <a name="see-also"></a>Consulte também  
 [NEWID &#40; Transact-SQL &#41;](../../t-sql/functions/newid-transact-sql.md)   
 [Operadores de comparação &#40; Transact-SQL &#41;](../../t-sql/language-elements/comparison-operators-transact-sql.md)  
  
  
