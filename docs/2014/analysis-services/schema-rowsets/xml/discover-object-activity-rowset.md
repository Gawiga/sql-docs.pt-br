---
title: Conjunto de linhas DISCOVER_OBJECT_ACTIVITY | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- DISCOVER_OBJECT_ACTIVITY rowset
ms.assetid: 100f7de1-ad5c-4973-b863-3c10df1245c4
caps.latest.revision: 14
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 09aec1da2c7e9001585b0793b12f0faf89feaf27
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37235696"
---
# <a name="discoverobjectactivity-rowset"></a>Conjunto de linhas DISCOVER_OBJECT_ACTIVITY
  Oferece uso de recursos por objeto desde o início do serviço.  
  
## <a name="rowset-columns"></a>Colunas do conjunto de linhas  
 O `DISCOVER_OBJECT_ACTIVITY` linhas contém as colunas a seguir.  
  
|Nome da coluna|Indicador de tipo|Comprimento|Description|  
|-----------------|--------------------|------------|-----------------|  
|`OBJECT_AGGREGATION_HIT`|`DBTYPE_I8`||O número de vezes que uma agregação do objeto foi atingida desde o início do serviço.|  
|`OBJECT_AGGREGATION_MISS`|`DBTYPE_I8`||O número de vezes que uma agregação existente, do objeto, não foi ignorada (ou seja, não foi usada) desde o início do serviço.|  
|`OBJECT_CPU_TIME_MS`|`DBTYPE_I8`||O tempo de CPU, em milissegundos, consumidos pelo objeto desde o início do serviço.|  
|`OBJECT_DATA_VERSION`|`DBTYPE_I4`||O número de linhagem dos dados no objeto; este número será incrementado sempre que o objeto for processado.|  
|`OBJECT_HIT`|`DBTYPE_I8`||O número de vezes que o objeto foi atingido no cache desde o início do serviço.|  
|`OBJECT_ID`|`DBTYPE_WSTR`||A ID do objeto como definida na hora de criação|  
|`OBJECT_MISS`|`DBTYPE_I8`||O número de vezes que o objeto foi ignorado no cache desde o início do serviço.|  
|`OBJECT_PARENT_PATH`|`DBTYPE_WSTR`||O caminho para o pai do objeto atual.|  
|`OBJECT_READ_KB`|`DBTYPE_I8`||O valor acumulado de leitura de dados pelo objeto desde o início do serviço, em quilobytes.|  
|`OBJECT_READS`|`DBTYPE_I8`||O número acumulado de operações de leitura pelo objeto desde o início do serviço.|  
|`OBJECT_ROWS_RETURNED`|`DBTYPE_I8`||O número de linhas retornado pelo objeto ao chamador desde o início do serviço.|  
|`OBJECT_ROWS_SCANNED`|`DBTYPE_I8`||O número de linhas verificadas pelo objeto desde o início do serviço.|  
|`OBJECT_VERSION`|`DBTYPE_I4`||O número de versão de metadados do objeto; esse número mudará sempre que o objeto for alterado.|  
|`OBJECT_WRITE_KB`|`DBTYPE_I8`||O valor acumulado dos dados gravados pelo objeto desde o início do serviço, em quilobytes.|  
|`OBJECT_WRITES`|`DBTYPE_I8`||O número acumulado de operações de gravação pelo objeto desde o início do serviço.|  
  
 Este conjunto de linhas do esquema não é classificado.  
  
## <a name="restriction-columns"></a>Colunas de restrição  
 O conjunto de linhas `DISCOVER_OBJECT_ACTIVTY` pode ser restringido nas colunas listadas na tabela a seguir.  
  
|Nome da coluna|Indicador de tipo|Estado de restrição|  
|-----------------|--------------------|-----------------------|  
|OBJECT_PARENT_PATH|DBTYPE_WSTR|Opcional.|  
|OBJECT_ID|DBTYPE_WSTR|Opcional.|  
  
## <a name="see-also"></a>Consulte também  
 [Conjunto de linhas de esquema do XML](xml-for-analysis-schema-rowsets.md)  
  
  
