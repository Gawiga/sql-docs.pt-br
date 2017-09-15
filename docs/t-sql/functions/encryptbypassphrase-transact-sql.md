---
title: ENCRYPTBYPASSPHRASE (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ENCRYPTBYPASSPHRASE
- ENCRYPTBYPASSPHRASE_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- ENCRYPTBYPASSPHRASE function
- encryption [SQL Server], symmetric keys
- symmetric keys [SQL Server], ENCRYPTBYPASSPHRASE function
ms.assetid: f8dbb9e6-94d6-40d7-8b38-6833a409d597
caps.latest.revision: 35
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: ddfbea4ac550f21787eb88db6119c391f2b1b85a
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="encryptbypassphrase-transact-sql"></a>ENCRYPTBYPASSPHRASE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Criptografe os dados com uma senha com o uso do algoritmo TRIPLE DES com um comprimento de chave de 128 bits.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
EncryptByPassPhrase ( { 'passphrase' | @passphrase }   
    , { 'cleartext' | @cleartext }  
  [ , { add_authenticator | @add_authenticator }  
    , { authenticator | @authenticator } ] )  
```  
  
## <a name="arguments"></a>Argumentos  
 *frase secreta*  
 Uma frase secreta a partir da qual gerar uma chave simétrica.  
  
 @passphrase  
 Uma variável do tipo **nvarchar**, **char**, **varchar**, **binário**, **varbinary**, ou **nchar** contendo uma frase secreta da qual gerar uma chave simétrica.  
  
 *texto não criptografado*  
 O texto não criptografado a ser criptografado.  
  
 @cleartext  
 Uma variável do tipo **nvarchar**, **char**, **varchar**, **binário**, **varbinary**, ou **nchar** que contém o texto não criptografado. O tamanho máximo é 8.000 bytes.  
  
 *add_authenticator*  
 Indica se um autenticador será criptografado junto com o texto não criptografado. 1 se um autenticador for adicionado. **int**.  
  
 @add_authenticator  
 Indica se um hash será criptografado junto com o texto não criptografado.  
  
 *autenticador*  
 Dados do qual derivar um autenticador. **sysname**.  
  
 @authenticator  
 Uma variável contendo dados a partir dos quais o autenticador será derivado.  
  
## <a name="return-types"></a>Tipos de retorno  
 **varbinary** com tamanho máximo de 8.000 bytes.  
  
## <a name="remarks"></a>Comentários  
 Uma frase secreta é uma senha que inclui espaços. A vantagem de usar uma frase secreta é o fato de ser mais fácil lembrar uma frase ou sentença significativa do que uma cadeia de caracteres comparavelmente longa.  
  
 Esta função não verifica a complexidade da senha.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir atualiza um registro na tabela `SalesCreditCard` e criptografa o valor do número de cartão de crédito armazenado na coluna `CardNumber_EncryptedbyPassphrase`, usando a chave primária como um autenticador.  
  
```  
USE AdventureWorks2012;  
GO  
-- Create a column in which to store the encrypted data.  
ALTER TABLE Sales.CreditCard   
    ADD CardNumber_EncryptedbyPassphrase varbinary(256);   
GO  
-- First get the passphrase from the user.  
DECLARE @PassphraseEnteredByUser nvarchar(128);  
SET @PassphraseEnteredByUser   
    = 'A little learning is a dangerous thing!';  
  
-- Update the record for the user's credit card.  
-- In this case, the record is number 3681.  
UPDATE Sales.CreditCard  
SET CardNumber_EncryptedbyPassphrase = EncryptByPassPhrase(@PassphraseEnteredByUser  
    , CardNumber, 1, CONVERT( varbinary, CreditCardID))  
WHERE CreditCardID = '3681';  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
 [DECRYPTBYPASSPHRASE &#40; Transact-SQL &#41;](../../t-sql/functions/decryptbypassphrase-transact-sql.md)   
 [Hierarquia de criptografia](../../relational-databases/security/encryption/encryption-hierarchy.md)  
  
  