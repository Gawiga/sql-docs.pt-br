---
title: Início rápido que mostra o R funciona com dados do SQL Server (aprendizado de máquina do SQL Server) | Microsoft Docs
description: Neste início rápido, saiba como escrever uma função R que usa dados do SQL Server.
ms.prod: sql
ms.technology: machine-learning
ms.date: 07/15/2018
ms.topic: quickstart
author: HeidiSteen
ms.author: heidist
manager: cgronlun
ms.openlocfilehash: 5785b8b8162fdde25dea13eb3aead55c10dbfc3b
ms.sourcegitcommit: c8f7e9f05043ac10af8a742153e81ab81aa6a3c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39086668"
---
# <a name="quickstart-using-r-functions-with-sql-server-data"></a>Guia de início rápido: Usando funções de R com dados do SQL Server
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

Se você concluiu os inícios rápidos anteriores, você está familiarizado com operações básicas e pronto para algo mais complexo, como as funções estatísticas. Funções estatísticas avançadas que são complicadas para implementar em T-SQL podem ser feitas em R com apenas uma única linha de código.

Neste início rápido, você inserirá R matemático e procedimento armazenado de funções de utilitário em um SQL Server.

## <a name="prerequisites"></a>Prerequisites

Um início rápido anterior, [Olá, mundo em R e SQL](rtsql-using-r-code-in-transact-sql-quickstart.md), fornece informações e links para configurar o ambiente de R necessários para este início rápido.

## <a name="create-a-stored-procedure-to-generate-random-numbers"></a>Criar um procedimento armazenado para gerar números aleatórios

Para simplificar, vamos usar o R `stats` pacote, que é instalado e carregado por padrão quando você instala o suporte ao recurso de R no SQL Server. O pacote contém centenas de funções para tarefas estatísticas comuns, entre elas, a função `rnorm`, que gera um número específico de números aleatórios usando a distribuição normal, dado um desvio padrão e uma média.

Por exemplo, esse código R retorna 100 números em uma média de 50, dado um desvio padrão de 3.

```R
as.data.frame(rnorm(100, mean = 50, sd = 3));
```

Para chamar esta linha de R de T-SQL, execute sp_execute_external_script e adicione a função R no parâmetro de script de R, como este:

```sql
EXEC sp_execute_external_script
      @language = N'R'
    , @script = N'
         OutputDataSet <- as.data.frame(rnorm(100, mean = 50, sd =3));'
    , @input_data_1 = N'   ;'
      WITH RESULT SETS (([Density] float NOT NULL));
```

E se você quiser facilitar a geração de um conjunto de números aleatórios diferente?

Isso é fácil quando combinado com o SQL Server: defina um procedimento armazenado que obtém os argumentos do usuário. Em seguida, passe esses argumentos para o script de R como variáveis.

```sql
CREATE PROCEDURE MyRNorm (@param1 int, @param2 int, @param3 int)
AS
    EXEC sp_execute_external_script
      @language = N'R'
    , @script = N'
         OutputDataSet <- as.data.frame(rnorm(mynumbers, mymean, mysd));'
    , @input_data_1 = N'   ;'
    , @params = N' @mynumbers int, @mymean int, @mysd int'
    , @mynumbers = @param1
    , @mymean = @param2
    , @mysd = @param3
    WITH RESULT SETS (([Density] float NOT NULL));
```

+ A primeira linha define cada um dos parâmetros de entrada SQL necessários quando o procedimento armazenado é executado.

+ A linha que começa com `@params` define todas as variáveis usadas pelo código R e os tipos de dados SQL correspondentes.

+ As linhas imediatamente após mapeiam os nomes de parâmetro SQL para os nomes de variável R correspondentes.

Agora que você encapsulou a função R em um procedimento armazenado, pode facilmente chamar a função e passar valores diferentes, como este:

```sql
EXEC MyRNorm @param1 = 100,@param2 = 50, @param3 = 3
```

## <a name="use-r-utility-functions-for-troubleshooting"></a>Usar funções de utilitário de R para solução de problemas

Por padrão, uma instalação do R inclui o `utils` pacote, que fornece uma variedade de funções de utilitário para investigar o atual ambiente de R. Isso poderá ser útil se você estiver encontrando discrepâncias na maneira como o código R é executado no SQL Server e em ambientes externos.

Por exemplo, você pode usar a função R `memory.limit()` para obter memória para o ambiente atual de R. Uma vez que o pacote `utils` é instalado, mas não carregado por padrão, primeiro é necessário usar a função `library()` para carregá-lo.

```sql
EXECUTE sp_execute_external_script
      @language = N'R'
    , @script = N'
        library(utils);
        mymemory <- memory.limit();
        OutputDataSet <- as.data.frame(mymemory);'
    , @input_data_1 = N' ;'
WITH RESULT SETS (([Col1] int not null));
```

Muitos usuários gostam de usar as funções de tempo do sistema em R, como `system.time` e `proc.time`, para capturar o tempo usado por processos de R e analisar problemas de desempenho.

Para obter um exemplo, consulte este tutorial: [Criar recursos de dados](../tutorials/walkthrough-create-data-features.md). Neste passo a passo, funções de tempo R são inseridas na solução para comparar o desempenho de dois métodos para criar recursos de dados: funções R vs. funções T-SQL.

## <a name="next-steps"></a>Próximas etapas

Em seguida, você criará um modelo de previsão usando R no SQL Server.

> [!div class="nextstepaction"]
> [Início rápido: Criar um modelo de previsão](rtsql-create-a-predictive-model-r.md)
