---
title: SQLDescribeCol | Microsoft Docs
ms.custom: 
ms.date: 03/17/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: native-client-odbc-api
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apitype: DLLExport
helpviewer_keywords: SQLDescribeCol function
ms.assetid: ffbf34c6-8268-434f-829a-82009a6cda59
caps.latest.revision: "40"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 41bedf7d6dd15d4b7168c339385560c07ff48733
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="sqldescribecol"></a>SQLDescribeCol
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  Para instruções executadas, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC Native Client não precisa consultar o servidor para descrever colunas em um conjunto de resultados. Nesse caso, **SQLDescribeCol** não faz com que uma resposta do servidor. Como [SQLColAttribute](../../relational-databases/native-client-odbc-api/sqlcolattribute.md)e[SQLNumResultCols](../../relational-databases/native-client-odbc-api/sqlnumresultcols.md), chamar **SQLDescribeCol** na preparadas mas instruções não executadas gera uma resposta do servidor.  
  
 Quando uma instrução ou um lote de instruções do [!INCLUDE[tsql](../../includes/tsql-md.md)] retorna vários conjuntos de linha de resultado, é possível para uma coluna referenciada por ordinal ser originada em uma tabela separada ou consultar uma coluna inteiramente diferente no conjunto de resultados. **SQLDescribeCol** deve ser chamado para cada conjunto. Quando o conjunto de resultados for alterado, o aplicativo deverá associar novamente os valores de dados antes de buscar os resultados da linha. Para obter mais informações sobre como lidar com resultados de vários retornos de conjunto, consulte [SQLMoreResults](../../relational-databases/native-client-odbc-api/sqlmoreresults.md).  
  
 Os atributos de coluna são informados somente para o primeiro conjunto de resultados quando vários conjuntos são gerados por um lote preparado de instruções SQL.  
  
 Para tipos de dados de valor grande, o valor retornado em *DataTypePtr* é SQL_VARCHAR, SQL_VARBINARY ou SQL_NVARCHAR. Um valor de SQL_SS_LENGTH_UNLIMITED em *ColumnSizePtr* indica que o tamanho é "ilimitado".  
  
 Melhorias no mecanismo de banco de dados, começando com [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permitir SQLDescribeCol Obtenha descrições mais precisas dos resultados esperados. Esses resultados mais precisos podem ser diferentes dos valores retornados por SQLDescribeCol nas versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Para obter mais informações, consulte [descoberta de metadados](../../relational-databases/native-client/features/metadata-discovery.md).  
  
## <a name="sqldescribecol-support-for-enhanced-date-and-time-features"></a>Suporte de SQLDescribeCol a recursos aprimorados de data e hora  
 Os valores retornados para tipos de data/hora são os seguintes:  
  
||*DataTypePtr*|*ColumnSizePtr*|*DecimalDigitsPtr*|  
|-|-------------------|---------------------|------------------------|  
|datetime|SQL_TYPE_TIMESTAMP|23|3|  
|smalldatetime|SQL_TYPE_TIMESTAMP|16|0|  
|date|SQL_TYPE_DATE|10|0|  
|time|SQL_SS_TIME2|8, 10..16|0..7|  
|datetime2|SQL_TYPE_TIMESTAMP|19, 21..27|0..7|  
|datetimeoffset|SQL_SS_TIMESTAMPOFFSET|26, 28..34|0..7|  
  
 Para obter mais informações, consulte [data e hora melhorias &#40; ODBC &#41;](../../relational-databases/native-client-odbc-date-time/date-and-time-improvements-odbc.md).  
  
## <a name="sqldescribecol-support-for-large-clr-udts"></a>Suporte de SQLDescribeCol para CLR UDTs grandes  
 **SQLDescribeCol** oferece suporte a grandes CLR definido pelo usuário (UDTs tipos). Para obter mais informações, consulte [Large CLR User-Defined tipos &#40; ODBC &#41;](../../relational-databases/native-client/odbc/large-clr-user-defined-types-odbc.md).  
  
## <a name="see-also"></a>Consulte também  
 [Função SQLDescribeCol](http://go.microsoft.com/fwlink/?LinkID=59338)   
 [Detalhes da implementação da API do ODBC](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  
