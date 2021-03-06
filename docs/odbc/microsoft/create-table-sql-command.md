---
title: Criar tabela - comando SQL | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- CREATE TABLE [ODBC]
ms.assetid: be2143ba-fc16-42c9-84f7-8985cd924860
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 35a23b8c648b5ffbf2a2000c949f1cb097ba91ca
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32905081"
---
# <a name="create-table---sql-command"></a>Criar tabela - comando SQL
Cria uma tabela com os campos especificados.  
  
 O Driver de ODBC do Visual FoxPro oferece suporte a sintaxe de linguagem do Visual FoxPro nativo para este comando. Para obter informações específicas do driver, consulte **comentários de Driver**.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
CREATE TABLE | DBF TableName1 [NAME LongTableName] [FREE]  
   (FieldName1FieldType [(nFieldWidth [, nPrecision])]  
      [NULL | NOT NULL]   
      [CHECK lExpression1 [ERROR cMessageText1]]  
      [DEFAULT eExpression1]  
      [PRIMARY KEY | UNIQUE]  
      [REFERENCES TableName2 [TAG TagName1]]  
      [NOCPTRANS]  
   [, FieldName2 ...]  
      [, PRIMARY KEY eExpression2 TAG TagName2  
      |, UNIQUE eExpression3 TAG TagName3]  
      [, FOREIGN KEY eExpression4 TAG TagName4 [NODUP]  
            REFERENCES TableName3 [TAG TagName5]]  
      [, CHECK lExpression2 [ERROR cMessageText2]])  
| FROM ARRAY ArrayName  
```  
  
## <a name="arguments"></a>Argumentos  
 Criar tabela &#124; DBF *TableName1*  
 Especifica o nome da tabela a ser criada. As opções de tabela e DBF são idênticas.  
  
 NOME *LongTableName*  
 Especifica um nome longo para a tabela. Um nome de tabela de tempo pode ser especificado somente quando um banco de dados é aberto, como nomes de tabela de tempo são armazenados em bancos de dados.  
  
 Nomes longos podem conter até 128 caracteres e podem ser usados no lugar de nomes de arquivos curtos no banco de dados.  
  
 GRATUITO  
 Especifica que a tabela não será adicionada a um banco de dados aberto. LIVRE não é necessário se um banco de dados não estiver aberto.  
  
 *(FieldType FieldName1* [( *nFieldWidth* [, *nPrecision*])]  
 Especifica o nome do campo, tipo de campo, largura de campo e a precisão do campo (número de casas decimais), respectivamente.  
  
 *FieldType* é uma única letra indicando que o campo [tipo de dados](../../odbc/microsoft/visual-foxpro-field-data-types.md). Alguns tipos de dados do campo exigem que você especifique *nFieldWidth* ou *nPrecision* ou ambos.  
  
 *nFieldWidth* e *nPrecision* para D, G, I, L, M, P, T e Y são ignoradas tipos. *nPrecision* padrão é zero (sem casas decimais) se *nPrecision* não está incluído para os tipos de B, F ou N.  
  
 NULL  
 Permite valores nulos no campo.  
  
 NOT NULL  
 Impede que valores nulos no campo.  
  
 Se você omite NULL e NOT NULL, a configuração atual de SET NULL determina se valores nulos são permitidos no campo. No entanto, se você omite NULL e NOT NULL e incluem a chave primária ou exclusiva cláusula, a configuração atual de SET NULL é ignorada e o campo padrão é não nulo.  
  
 VERIFICAR *lExpression1*  
 Especifica uma regra de validação para o campo. *lExpression1* pode ser uma função definida pelo usuário. Sempre que é anexado a um registro em branco, a regra de validação é verificada. Um erro será gerado se a regra de validação não permite que um valor de campo em branco em um registro anexado.  
  
 Erro *cMessageText1*  
 Especifica a mensagem de erro que do Visual FoxPro exibe quando a regra de campo gera um erro. A mensagem é exibida somente quando os dados são alterados em uma janela Procurar ou uma janela de edição.  
  
 PADRÃO *eExpression1*  
 Especifica um valor padrão para o campo. O tipo de dados *eExpression1* deve ser o mesmo tipo de dados do campo.  
  
 PRIMARY KEY  
 Cria um índice primário para o campo. A marca de índice primário tem o mesmo nome do campo.  
  
 UNIQUE  
 Cria um índice de candidato para o campo. A marca de índice candidato tem o mesmo nome do campo.  
  
> [!NOTE]  
>  Candidato índices (criados, incluindo a opção exclusiva em CREATE TABLE ou ALTER TABLE - SQL) não são os mesmos índices criados com a opção exclusiva no comando de índice. Um índice criado com a opção exclusiva no comando índice permite que chaves de índice duplicadas; índices de candidato não permitem chaves de índice duplicadas. Consulte [índice](../../odbc/microsoft/index-command.md) para obter informações adicionais sobre a opção exclusiva.  
  
 Valores nulos e registros duplicados não são permitidos em um campo usado para um índice primárias ou candidatas. No entanto, o Visual FoxPro não irá gerar um erro se você criar um índice primárias ou candidatas para um campo que oferece suporte a valores nulos. Do Visual FoxPro gerará um erro se você tentar inserir um valor nulo ou duplicado em um campo usado para um índice primárias ou candidatas.  
  
 REFERÊNCIAS *TableName2*[marca *TagName1*]  
 Especifica a tabela pai ao qual será estabelecida uma relação persistente. Se você omitir marca *TagName1*, a relação é estabelecida usando a chave de índice primário da tabela pai. Se a tabela pai não tiver um índice primário, o Visual FoxPro gerará um erro.  
  
 MARCA include *TagName1* para estabelecer uma relação com base em uma marca de índice existente para a tabela pai. Nomes de marca de índice podem conter até 10 caracteres.  
  
 A tabela pai não pode ser uma tabela livre.  
  
 NOCPTRANS  
 Impede que a conversão em uma página de código diferente para campos de caractere e de memorando. Se a tabela é convertida em outra página de código, os campos para os quais foi especificado NOCPTRANS não são traduzidos. NOCPTRANS pode ser especificado apenas para campos de caractere e de memorando.  
  
 O exemplo a seguir cria uma tabela chamada mytable que contém dois campos de caractere e dois campos de memorando. O segundo campo de caractere, char2 e o segundo campo de memorando, memo2, incluem NOCPTRANS para evitar a conversão.  
  
```  
CREATE TABLE mytable (char1 C(10), char2 C(10) NOCPTRANS,;  
   memo1 M, memo2 M NOCPTRANS)  
```  
  
 CHAVE primária *eExpression2* marca *TagName2*  
 Especifica um índice primário para criar. *eExpression2* Especifica qualquer campo ou uma combinação de campos na tabela. MARCA *TagName2 s*Especifica o nome da marca de índice primário é criado. Nomes de marca de índice podem conter até 10 caracteres.  
  
 Como uma tabela pode ter apenas um índice primário, você não pode incluir essa cláusula se você já tiver criado um índice primário para um campo. Do Visual FoxPro gerará um erro se você incluir mais de uma cláusula de chave primária em CREATE TABLE.  
  
 EXCLUSIVO *eExpression3*marca *TagName3*  
 Cria um índice de candidato. *eExpression3* Especifica qualquer campo ou uma combinação de campos na tabela. No entanto, se você tiver criado um índice primário com uma das opções de chave primária, você não pode incluir o campo que foi especificado para o índice primário. MARCA *TagName3 s*Especifica um nome de marca para a marca de índice de candidato é criado. Nomes de marca de índice podem conter até 10 caracteres.  
  
 Uma tabela pode ter vários índices de candidato.  
  
 CHAVE estrangeira *eExpression4*marca *TagName4*[NODUP]  
 Cria um índice (as) externo e estabelece uma relação com uma tabela pai. *eExpression4* Especifica a expressão de chave estrangeira de índice, e *TagName4* Especifica o nome da marca chave estrangeira de índice é criado *.* Nomes de marca de índice podem conter até 10 caracteres. Inclua NODUP para criar um índice externo do candidato.  
  
 Você pode criar vários índices da tabela externos, mas as expressões de índice externa devem especificar campos diferentes na tabela.  
  
 REFERÊNCIAS *TableName3*[marca *TagName5*]  
 Especifica a tabela pai ao qual será estabelecida uma relação persistente. MARCA include *TagName5* para estabelecer uma relação com base em uma marca de índice para a tabela pai. Nomes de marca de índice podem conter até 10 caracteres. Por padrão, se você omitir marca *TagName5,* a relação é estabelecida usando a chave de índice primário da tabela pai.  
  
 VERIFICAR *eExpression2*[erro *cMessageText2*]  
 Especifica a regra de validação da tabela. Erro *cMessageText2* Especifica a mensagem de erro do Visual FoxPro exibe quando a regra de validação da tabela é executada. A mensagem é exibida somente quando os dados são alterados em uma janela Procurar ou janela de edição.  
  
 DA matriz *ArrayName*  
 Especifica o nome de uma matriz existente cujo conteúdo é o nome, tipo, precisão e escala para cada campo na tabela. O conteúdo da matriz pode ser definido com o **AFIELDS**função ().  
  
## <a name="remarks"></a>Remarks  
 A nova tabela é aberta na área de menor trabalho disponíveis e pode ser acessada por seu alias. A nova tabela é aberta exclusivamente, independentemente da configuração atual de um conjunto exclusivo.  
  
 Se um banco de dados está aberto e você não incluir a cláusula livre, a nova tabela será adicionada ao banco de dados. Você não pode criar uma nova tabela com o mesmo nome de uma tabela no banco de dados.  
  
 Se um banco de dados estiver aberto, CREATE TABLE - SQL requer o uso exclusivo do banco de dados. Para abrir um banco de dados para uso exclusivo, incluem exclusivo no banco de dados aberto.  
  
 Se um banco de dados não estiver aberto quando você cria uma nova tabela, incluindo as cláusulas de nome, verificação, padrão, chave estrangeira, chave primária ou referências gera um erro.  
  
> [!NOTE]  
>  Sintaxe de CREATE TABLE usa vírgulas para separar determinadas opções CREATE TABLE. Além disso, NULL, não NULL, verificação, padrão, chave primária e exclusiva cláusula devem ser colocados entre parênteses que contém as definições de coluna.  
  
## <a name="driver-remarks"></a>Comentários de driver  
 Quando o aplicativo envia a instrução ODBC SQL CREATE TABLE para a fonte de dados, o Driver de ODBC do Visual FoxPro converte o comando para o comando de tabela FoxProCREATE Visual usando a sintaxe mostrada na tabela a seguir.  
  
|Sintaxe ODBC|Sintaxe do Visual FoxPro|  
|-----------------|--------------------------|  
|CREATE TABLE *nome da tabela de base*<br /><br /> (*tipo de dados de identificador de coluna*<br /><br /> [NÃO NULL]<br /><br /> [,*tipo de dados de identificador de coluna*<br /><br /> [NÃO NULL]...)|Criar tabela *TableName1* [nome *LongTableName*]<br /><br /> (*FieldName1* *FieldType*<br /><br /> [(*nFieldWidth* [, *nPrecision*])]<br /><br /> [NÃO NULL)]|  
  
 Quando você cria uma tabela usando o driver, o driver fecha a tabela imediatamente após a criação para permitir o acesso à tabela por outros usuários. Isso difere do Visual FoxPro, o que deixa a tabela aberta exclusivamente no momento da criação. No entanto, se um procedimento armazenado em sua fonte de dados que contém uma instrução CREATE TABLE for executada, a tabela é deixada em aberto.  
  
 Se a fonte de dados for um banco de dados (arquivo. dbc), o Driver de ODBC do Visual FoxPro cria uma tabela denominada *LongTableName* com o mesmo nome que o *nome da tabela de base*.  
  
### <a name="using-data-definition-language-ddl"></a>Usando a linguagem de definição de dados (DDL)  
 Você não pode incluir DDL nos seguintes locais:  
  
-   Em um lote de instrução SQL que requer uma transação  
  
-   No modo de confirmação manual, após uma instrução que exigia uma transação, a menos que o aplicativo primeiro chama **SQLTransact**.  
  
 Por exemplo, se você quiser criar uma tabela temporária, você deve criar a tabela antes de começar a instrução que requer uma transação. Se você incluir a instrução CREATE TABLE em um lote de instrução SQL que requer uma transação, o driver retornará uma mensagem de erro.  
  
## <a name="see-also"></a>Consulte também  
 [ALTER TABLE - comando SQL](../../odbc/microsoft/alter-table-sql-command.md)   
 [Tipos de dados com suporte (Driver ODBC do Visual FoxPro)](../../odbc/microsoft/supported-data-types-visual-foxpro-odbc-driver.md)   
 [Insira - o comando SQL](../../odbc/microsoft/insert-sql-command.md)   
 [SELECT – comando SQL](../../odbc/microsoft/select-sql-command.md)
