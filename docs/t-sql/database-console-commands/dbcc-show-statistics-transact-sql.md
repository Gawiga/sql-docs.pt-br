---
title: DBCC SHOW_STATISTICS (Transact-SQL) | Microsoft Docs
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
- SHOW_STATISTICS_TSQL
- DBCC SHOW_STATISTICS
- SHOW_STATISTICS
- DBCC_SHOW_STATISTICS_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- query optimization statistics [SQL Server], densities
- histograms [SQL Server]
- statistical information [SQL Server], viewing statistics objects
- current distribution statistics
- query optimization statistics [SQL Server], histograms
- DBCC SHOW_STATISTICS statement
- distribution statistics
- statistical information [SQL Server], densities
- statistics objects
- statistical information [SQL Server], histograms
- query optimization statistics [SQL Server], viewing statistics objects
- statistical information [SQL Server], distribution
- densities [SQL Server]
- displaying distribution statistics
ms.assetid: 12be2923-7289-4150-b497-f17e76a50b2e
caps.latest.revision: 75
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 03651b89f8cc8b7694e9e07531804053e64568ac
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="dbcc-showstatistics-transact-sql"></a>DBCC SHOW_STATISTICS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

DBCC SHOW_STATISTICS exibe as estatísticas de otimização de consulta atuais de uma tabela ou exibição indexada. O otimizador de consulta usa as estatísticas para calcular a cardinalidade ou o número de linhas no resultado da consulta, o que permite a esse otimizador criar um plano de consulta de alta qualidade. Por exemplo, o otimizador de consulta pode usar estimativas de cardinalidade para escolher o operador de busca do índice, em vez do operador de verificação do índice no plano de consulta, melhorando o desempenho da consulta ao evitar uma verificação de índice que consome muitos recursos.
  
O otimizador de consulta armazena estatísticas para uma tabela ou exibição indexada em um objeto de estatísticas. Para uma tabela, o objeto de estatísticas é criado em um índice ou uma lista de colunas de tabela. O objeto de estatísticas inclui um cabeçalho com metadados sobre as estatísticas, um histograma com a distribuição de valores na primeira coluna de chave do objeto de estatísticas e um vetor de densidade para medir a correlação entre colunas. O [!INCLUDE[ssDE](../../includes/ssde-md.md)] pode calcular estimativas de cardinalidade com qualquer dos dados no objeto de estatísticas.
  
DBCC SHOW_STATISTICS exibe o cabeçalho, o histograma e o vetor de densidade com base nos dados armazenados no objeto de estatísticas. A sintaxe lhe permite especificar uma tabela ou exibição indexada junto com um nome de índice de destino, nome de estatísticas ou nome da coluna. Este tópico descreve como exibir as estatísticas e como entender os resultados apresentados.
  
Para obter mais informações, consulte [Statistics](../../relational-databases/statistics/statistics.md).
  
![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Sintaxe  
  
```
-- Syntax for SQL Server and Azure SQL Database  
  
DBCC SHOW_STATISTICS ( table_or_indexed_view_name , target )   
[ WITH [ NO_INFOMSGS ] < option > [ , n ] ]  
< option > :: =  
    STAT_HEADER | DENSITY_VECTOR | HISTOGRAM | STATS_STREAM  
```  
  
```
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  

DBCC SHOW_STATISTICS ( table_name , target )   
    [ WITH {STAT_HEADER | DENSITY_VECTOR | HISTOGRAM } [ ,...n ] ]  
[;]  
```  
  
## <a name="arguments"></a>Argumentos  
 *table_or_indexed_view_name*  
 O nome da tabela ou exibição indexada das quais exibir informações de estatísticas.  
  
 *table_name*  
 Nome da tabela que contém as estatísticas para exibir. A tabela não pode ser uma tabela externa.  
  
 *Destino*  
 O nome do índice, das estatísticas ou da coluna para a qual exibir informações de estatísticas. *destino* entre colchetes, único aspas, double aspas ou sem aspas. Se *destino* é um nome de um índice existente ou estatísticas em uma tabela ou exibição indexada, as informações estatísticas sobre esse destino será retornada. Se *destino* é o nome de uma coluna existente e estatísticas criadas automaticamente nessa coluna existir, serão retornadas informações sobre estatísticas criadas automaticamente. Se uma estatística criada automaticamente não existir para um destino de coluna, a mensagem de erro 2767 será retornada.  
 Em [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] e [!INCLUDE[ssPDW](../../includes/sspdw-md.md)], *destino* não pode ser um nome de coluna.  
  
 NO_INFOMSGS  
 Suprime todas as mensagens informativas com níveis de severidade de 0 a 10.  
  
 STAT_HEADER | DENSITY_VECTOR | HISTOGRAMA | STATS_STREAM [ **,**  *n*  ]  
 A especificação de um ou mais desses parâmetros limita os conjuntos de resultados retornados pela instrução para a opção ou as opções especificadas. Se nenhuma opção for especificada, todas as informações de estatísticas serão retornadas.  
  
 STATS_STREAM é [!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]  
  
## <a name="result-sets"></a>Conjuntos de resultados  
A tabela a seguir descreve as colunas retornadas no conjunto de resultados quando STAT_HEADER está especificado.
  
|Nome da coluna|Description|  
|-----------------|-----------------|  
|Nome|O nome do objeto de estatísticas.|  
|Atualizado|Data e hora da última atualização de estatísticas. O [STATS_DATE](../../t-sql/functions/stats-date-transact-sql.md) função é uma forma alternativa de recuperar essas informações.|  
|Linhas|O número total de linhas na tabela ou exibição indexada quando as estatísticas foram atualizadas pela última vez. Se as estatísticas forem filtradas ou corresponderem a um índice filtrado, o número de linhas talvez seja menor do que o número de linhas na tabela. Para obter mais informações, consulte[estatísticas](../../relational-databases/statistics/statistics.md).|  
|Linhas Amostradas|O número total de linhas amostradas para cálculos de estatísticas. Se Linhas Amostradas < Linhas, o histograma e os resultados de densidade exibidos serão estimativas com base nas linhas amostradas.|  
|Etapas|O número de etapas no histograma. Cada etapa abrange uma gama de valores de colunas seguidos por um valor de coluna associada superior. As etapas do histograma são definidas na primeira coluna de chave nas estatísticas. O número máximo de etapas é 200.|  
|Densidade|Calculado como 1 / *valores distintos* para todos os valores na primeira coluna de chave do objeto de estatísticas, excluindo os valores de limite de histograma. Esse valor de Densidade não é usado pelo otimizador de consulta e é exibido para fins de compatibilidade com versões anteriores ao [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].|  
|Comprimento Médio de Chave|O número médio de bytes por valor para todas as colunas de chave do objeto de estatísticas.|  
|Índice de Cadeia de Caracteres|Sim indica que o objeto de estatísticas contém estatísticas do resumo da cadeia de caracteres para melhorar a estimativa de cardinalidade para predicados de consulta que usam o operador LIKE; por exemplo, `WHERE ProductName LIKE '%Bike'`. Cadeia de caracteres de estatísticas de resumo são armazenadas separadamente do histograma e são criadas na primeira coluna de chave do objeto de estatísticas quando ele é do tipo **char**, **varchar**, **nchar**, **nvarchar**, **varchar (max)**, **nvarchar (max)**, **texto**, ou **ntext.**.|  
|Expressão de filtro|Predicado do subconjunto de linhas de tabela incluído no objeto de estatísticas. NULL = estatísticas não filtradas. Para obter mais informações sobre predicados filtrados, consulte [criar índices filtrados](../../relational-databases/indexes/create-filtered-indexes.md). Para obter mais informações sobre estatísticas filtradas, consulte [estatísticas](../../relational-databases/statistics/statistics.md).|  
|Linhas não filtradas|O número total de linhas na tabela antes da aplicação da expressão de filtro. Se o valor da Expressão de Filtro for NULL, as Linhas Não Filtradas serão iguais a Linhas.|  
|Persistentes por cento de exemplo|Persistir a porcentagem de exemplo usada para as atualizações de estatísticas que não especificam explicitamente um percentual de amostragem. Se o valor for zero, nenhuma porcentagem de exemplo persistente é definida para essa estatística.<br /><br /> **Aplica-se a:** [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] SP1 atualização cumulativa 4| 
  
A tabela a seguir descreve as colunas retornadas no conjunto de resultados quando DENSITY_VECTOR é especificado.
  
|Nome da coluna|Description|  
|-----------------|-----------------|  
|Toda Densidade|A densidade é 1 / *valores distintos*. Os resultados exibem a densidade de cada prefixo de colunas no objeto de estatísticas, uma linha por densidade. Um valor distinto é uma lista distinta dos valores de coluna por linha e por prefixo de colunas. Por exemplo, se o objeto de estatísticas contiver colunas de chave (A, B, C), os resultados reportarão a densidade de listas distintas de valores em cada um desses prefixos de colunas: (A), (A,B) e (A, B, C). Com o uso do prefixo (A, B, C), cada uma dessas listas é uma lista de valores distintos: (3, 5, 6), (4, 4, 6), (4, 5, 6), (4, 5, 7). Com o uso do prefixo (A, B) os mesmos valores de colunas têm estas listas de valores distintos: (3, 5), (4, 4) e (4, 5)|  
|Comprimento Médio|O comprimento médio, em bytes, para armazenar uma lista dos valores das colunas para o prefixo da coluna. Por exemplo, se os valores na lista (3, 5, 6) exigirem cada um 4 bytes, o comprimento será de 12 bytes.|  
|Colunas|Os nomes das colunas no prefixo para o qual as opções Toda a densidade e Comprimento médio são exibidos.|  
  
A tabela a seguir descreve as colunas retornadas no conjunto de resultados quando a opção HISTOGRAM está especificada.
  
|Nome da coluna|Description|  
|---|---|
|RANGE_HI_KEY|Valor da coluna associada superior de uma etapa do histograma. O valor da coluna também será denominado um valor de chave.|  
|RANGE_ROWS|Número estimado de linhas cujo valor de coluna fica dentro de uma etapa do histograma, excluindo-se o limite superior.|  
|EQ_ROWS|Número estimado de linhas cujo valor de coluna é igual ao limite superior da etapa do histograma.|  
|DISTINCT_RANGE_ROWS|Número estimado de linhas com um valor de coluna distinto dentro de uma etapa do histograma, excluindo-se o limite superior.|  
|AVG_RANGE_ROWS|Número médio de linhas com valores de colunas duplicados em uma etapa do histograma, excluindo o limite superior (RANGE_ROWS / DISTINCT_RANGE_ROWS para DISTINCT_RANGE_ROWS > 0).| 
  
## <a name="remarks"></a>Comentários  
  
## <a name="histogram"></a>Histograma  
Um histograma mede a frequência de ocorrência de cada valor distinto em um conjunto de dados. O otimizador de consulta calcula um histograma com base nos valores de coluna na primeira coluna de chave do objeto de estatísticas, selecionando os valores de coluna por amostragem estatística das linhas ou pela execução de uma verificação completa de todas as linhas na tabela ou na exibição. Se o histograma for criado com base em um conjunto amostrado de linhas, os totais armazenados para o número de linhas e o número de valores distintos são estimativas e não precisam ser números inteiros.
  
Para criar o histograma, o otimizador de consulta classifica os valores de colunas, calcula o número de valores que correspondem a cada valor de coluna distinta e agrega os valores de colunas em um máximo de 200 etapas de histograma contíguas. Cada etapa inclui uma gama de valores de colunas seguidos por um valor de coluna associada superior. O intervalo inclui todos os possíveis valores de coluna entre valores de limite, excluindo-se os próprios valores de limite em si. O mais baixo dos valores de coluna classificados é o valor do limite superior da primeira etapa do histograma.
  
O diagrama a seguir mostra um histograma com seis etapas: A área à esquerda do primeiro valor do limite superior corresponde à primeira etapa.
  
![](../../relational-databases/system-dynamic-management-views/media/a0ce6714-01f4-4943-a083-8cbd2d6f617a.gif "a0ce6714-01f4-4943-a083-8cbd2d6f617a")
  
Para cada etapa do histograma:
-   A linha em negrito representa o valor do limite superior (RANGE_HI_KEY) e o número de vezes que ele ocorre (EQ_ROWS)  
-   A área sólida à esquerda de RANGE_HI_KEY representa o intervalo de valores de coluna e o número médio de vezes em que cada valor de coluna ocorre (AVG_RANGE_ROWS). AVG_RANGE_ROWS para a primeira etapa do histograma é sempre 0.  
-   As linhas pontilhadas representam os valores amostrados usados para estimar o número total de valores distintos no intervalo (DISTINCT_RANGE_ROWS) e o número total de valores no intervalo (RANGE_ROWS). O otimizador de consulta usa RANGE_ROWS e DISTINCT_RANGE_ROWS para calcular AVG_RANGE_ROWS e não armazena os valores amostrados.  
  
O otimizador de consulta define as etapas do histograma de acordo com o significado estatístico delas. Ele usa um algoritmo de diferença máxima para minimizar o número de etapas no histograma, enquanto maximiza a diferença entre os valores de limite. O número máximo de etapas é 200. O número de etapas do histograma pode ser menor do que o número de valores distintos, até mesmo para colunas com menos de 200 pontos de limite. Por exemplo, uma coluna com 100 valores distintos pode ter um histograma com menos de 100 pontos de limite.
  
## <a name="density-vector"></a>Vetor de densidade  
O otimizador de consulta usa densidades para aprimorar as estimativas de cardinalidade de consultas que retornam várias colunas da mesma tabela ou exibição indexada. O vetor de densidade contém uma densidade para cada prefixo de colunas no objeto de estatísticas. Por exemplo, se o objeto de estatísticas tiver as colunas de chave CustomerId, ItemId e Price, a densidade será calculada com base em cada um dos prefixos de coluna a seguir.
  
|Prefixo de coluna|Densidade calculada em|  
|---|---|
|(CustomerId)|Linhas com valores correspondentes para CustomerId.|  
|(CustomerId, ItemId)|Linhas com valores correspondentes para CustomerId e ItemId|  
|(CustomerId, ItemId, Price)|Linhas com valores correspondentes para CustomerId, ItemId e Price|  
  
## <a name="restrictions"></a>Restrições  
 DBCC SHOW_STATISTICS não fornece estatísticas para índices espaciais ou de columnstore xVelocity de memória otimizada.  
  
## <a name="permissions-for-includessnoversionincludesssnoversion-mdmd-and-includesssdsincludessssds-mdmd"></a>Permissões para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e[!INCLUDE[ssSDS](../../includes/sssds-md.md)]  
Para exibir o objeto de estatísticas, o usuário deve possuir a tabela ou o usuário deve ser um membro do `sysadmin` função fixa de servidor a `db_owner` função de banco de dados fixa ou `db_ddladmin` função fixa de banco de dados.
  
O SQL Server 2012 SP1 modifica as restrições de permissão e permite que os usuários com a permissão SELECT utilizem esse comando. Para que as permissões SELECT sejam suficientes para executar o comando, é necessário atender aos seguintes requisitos:
-   Os usuários devem ter permissões em todas as colunas do objeto de estatísticas  
-   Os usuários devem ter permissão em todas as colunas em uma condição de filtro (se houver)  
-   A tabela não pode ter uma política de segurança de nível de linha.  
  
Para desabilitar esse comportamento, use o traceflag 9485.
  
## <a name="permissions-for-includesssdwincludessssdw-mdmd-and-includesspdwincludessspdw-mdmd"></a>Permissões para [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] e[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
DBCC SHOW_STATISTICS requer a permissão SELECT na tabela ou associação em um dos seguintes:
-   função de servidor fixa sysadmin  
-   função de banco de dados fixa db_owner  
-   função de banco de dados fixa db_ddladmin  
  
## <a name="limitations-and-restrictions-for-includesssdwincludessssdw-mdmd-and-includesspdwincludessspdw-mdmd"></a>Limitações e restrições para [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] e[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
DBCC SHOW_STATISTICS mostra as estatísticas armazenadas no banco de dados Shell no nível de nó de controle. Ela não mostra as estatísticas são criadas automaticamente pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em nós de computação.
  
DBCC SHOW_STATISTICS não é suportada em tabelas externas.
  
## <a name="examples-includessnoversionincludesssnoversion-mdmd-and-includesssdsincludessssds-mdmd"></a>Exemplos: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e[!INCLUDE[ssSDS](../../includes/sssds-md.md)]  
### <a name="a-returning-all-statistics-information"></a>A. Retornando todas as informações de estatísticas  
O exemplo a seguir exibe todas as informações de estatísticas para o `AK_Address_rowguid` índice da `Person.Address` tabela o [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] banco de dados.
  
```t-sql
DBCC SHOW_STATISTICS ("Person.Address", AK_Address_rowguid);  
GO  
```  
  
### <a name="b-specifying-the-histogram-option"></a>B. Especificando a opção HISTROGRAM  
O exemplo a seguir limita as informações de estatísticas exibidas para o índice `AK_Address_rowguid` aos dados de HISTOGRAM.
  
```t-sql
DBCC SHOW_STATISTICS ("Person.Address", AK_Address_rowguid) WITH HISTOGRAM;  
GO  
```  
  
## <a name="examples-includesssdwincludessssdw-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemplos: [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] e[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
### <a name="c-display-the-contents-of-one-statistics-object"></a>C. Exibir o conteúdo de estatísticas de um objeto  
 O exemplo a seguir exibe o conteúdo das estatísticas Customer_LastName na tabela DimCustomer.  
  
```t-sql
-- Uses AdventureWorks  
--First, create a statistics object  
CREATE STATISTICS Customer_LastName   
ON AdventureWorksPDW2012.dbo.DimCustomer (LastName);  
GO  
DBCC SHOW_STATISTICS ("dbo.DimCustomer",Customer_LastName);  
GO  
```  
  
Os resultados mostram o cabeçalho, o vetor de densidade e parte do histograma.
  
![Resultados DBCC SHOW_STATISTICS](../../t-sql/database-console-commands/media/aps-sql-dbccshow-statistics.JPG "resultados DBCC SHOW_STATISTICS")
  
### <a name="d-specifying-the-histogram-option"></a>D. Especificando a opção HISTROGRAM  
Isso limita as informações de estatísticas exibidas para Customer_LastName para os dados de HISTOGRAMA.
  
```t-sql
DBCC SHOW_STATISTICS ("dbo.DimCustomer",Customer_LastName) WITH HISTOGRAM;  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
[Estatísticas](../../relational-databases/statistics/statistics.md)  
[CREATE INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/create-index-transact-sql.md)  
[CREATE STATISTICS &#40;Transact-SQL&#41;](../../t-sql/statements/create-statistics-transact-sql.md)  
[DROP STATISTICS &#40; Transact-SQL &#41;](../../t-sql/statements/drop-statistics-transact-sql.md)  
[sp_autostats &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-autostats-transact-sql.md)  
[sp_createstats &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-createstats-transact-sql.md)  
[STATS_DATE &#40; Transact-SQL &#41;](../../t-sql/functions/stats-date-transact-sql.md)  
[UPDATE STATISTICS &#40;Transact-SQL&#41;](../../t-sql/statements/update-statistics-transact-sql.md)  
[sys.DM db_stats_properties (Transact-SQL)](../../relational-databases/system-dynamic-management-views/sys-dm-db-stats-properties-transact-sql.md)  
[sys.dm_db_stats_histogram (Transact-SQL)](../../relational-databases/system-dynamic-management-views/sys-dm-db-stats-histogram-transact-sql.md)   
