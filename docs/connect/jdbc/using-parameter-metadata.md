---
title: Usando metadados de parâmetro | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: db2c1957-91c6-4989-a07b-9f8be6d2033a
caps.latest.revision: 17
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 825494c70ea9ed5d36cbf1c16ed4cdedfbfbd87d
ms.sourcegitcommit: 2f9cafc1d7a3773a121bdb78a095018c8b7c149f
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39661728"
---
# <a name="using-parameter-metadata"></a>Usando metadados de parâmetro

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

Para consultar um objeto [SQLServerPreparedStatement](../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) ou [SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md) sobre os parâmetros que eles contêm, o [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] implementa a classe [SQLServerParameterMetaData](../../connect/jdbc/reference/sqlserverparametermetadata-class.md). Esta classe contém diversos campos e métodos que retornam informações como um único valor.

Para criar um objeto SQLServerParameterMetaData, você pode usar o [getParameterMetaData](../../connect/jdbc/reference/getparametermetadata-method-sqlserverpreparedstatement.md) métodos das classes SQLServerPreparedStatement e SQLServerCallableStatement.

No exemplo a seguir, uma conexão aberta para o [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)] banco de dados de exemplo é passado para a função, o método getParameterMetaData da classe SQLServerCallableStatement é usado para retornar um objeto SQLServerParameterMetaData e, em seguida, várias métodos do objeto SQLServerParameterMetaData são usados para exibir informações sobre o tipo e o modo dos parâmetros que estão contidos dentro do procedimento armazenado de Uspupdateemployeehireinfo.

[!code[JDBC#UsingParamMetaData1](../../connect/jdbc/codesnippet/Java/using-parameter-metadata_1.java)]  

> [!NOTE]  
> Há algumas limitações ao usar a classe SQLServerParameterMetaData com instruções preparadas.
>
> **Com o Microsoft JDBC Driver 6.0 (ou superior) para SQL Server**: ao usar o SQL Server 2008 ou 2008 R2, o driver JDBC dá suporte para as instruções SELECT, DELETE, INSERT e UPDATE, uma vez que essas instruções não contêm subconsultas e/ou junções.

Consultas de mesclagem também não têm suporte para a classe SQLServerParameterMetaData ao usar o SQL Server 2008 ou 2008 R2. Para o SQL Server 2012 e metadados de parâmetro de versões anteriores com consultas complexas que têm suporte.

Não há suporte para a recuperação de metadados de parâmetro para colunas criptografadas. **Com o Microsoft JDBC Driver 4.1 ou 4.2 para SQL Server**: o driver JDBC dá suporte para as instruções SELECIONAR, EXCLUIR, INSERIR e ATUALIZAR, uma vez que essas instruções não contêm subconsultas e/ou junções. Mesclar consultas também não têm suporte para a classe SQLServerParameterMetaData.
