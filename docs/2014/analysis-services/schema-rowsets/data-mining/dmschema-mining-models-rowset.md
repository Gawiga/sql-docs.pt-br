---
title: Conjunto de linhas DMSCHEMA_MINING_MODELS | Microsoft Docs
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
api_name:
- DMSCHEMA_MINING_MODELS
topic_type:
- apiref
helpviewer_keywords:
- DMSCHEMA_MINING_MODELS rowset
ms.assetid: 1636f4cf-b342-4e2e-93b4-04136e2d41ef
caps.latest.revision: 40
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 9af1a9817ad116561b57b1d04b2e3df1d7313bb2
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37208026"
---
# <a name="dmschemaminingmodels-rowset"></a>Conjunto de linhas DMSCHEMA_MINING_MODELS
  Enumera os modelos de mineração de dados no catálogo atual. O conjunto de linhas `DMSCHEMA_MINING_MODELS` inclui informações como os nomes de modelos, a data de processamento e o algoritmo de mineração associados a cada modelo de mineração.  
  
 para obter informações sobre a ferramenta de configuração e recursos adicionais. O `DMSCHEMA_MINING_MODELS` de linhas de esquema é muito semelhante de [DBSCHEMA_TABLES](../ole-db/dbschema-tables-rowset.md) linhas de esquema e pode ser usado da mesma maneira.  
  
## <a name="rowset-columns"></a>Colunas do conjunto de linhas  
 O `DMSCHEMA_MINING_MODELS` linhas contém as colunas a seguir.  
  
|Nome da coluna|Indicador de tipo|Comprimento|Description|  
|-----------------|--------------------|------------|-----------------|  
|`MODEL_CATALOG`|`DBTYPE_WSTR`||O nome do catálogo. Preenchido com o nome do banco de dados do qual o modelo é membro.|  
|`MODEL_SCHEMA`|`DBTYPE_WSTR`||O nome do esquema não qualificado. Esta coluna não é suportada pelo [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]; sempre conterá `NULL`.|  
|`MODEL_NAME`|`DBTYPE_WSTR`||O nome do modelo de mineração. Esta coluna contém o nome do modelo de mineração e nunca está vazia.|  
|`MODEL_TYPE`|`DBTYPE_WSTR`||O tipo de modelo.|  
|`MODEL_GUID`|`DBTYPE_GUID`||O GUID do modelo.|  
|`DESCRIPTION`|`DBTYPE_WSTR`||Uma descrição amigável do modelo.|  
|`MODEL_PROPID`|`DBTYPE_UI4`||A ID de propriedade do modelo. Esta coluna não é suportada pelo [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]; sempre conterá `NULL`.|  
|`DATE_CREATED`|`DBTYPE_DBTIMESTAMP`||A data em que o modelo foi criado.|  
|`DATE_MODIFIED`|`DBTYPE_DBTIMESTAMP`||A data na qual a definição do modelo foi modificada pela última vez.|  
|`SERVICE_TYPE_ID`|`DBTYPE_UI4`||Uma enumeração que identifica o tipo de algoritmo de mineração de dados usado pelo modelo. Esse tipo pode ser um dos seguintes valores:<br /><br /> -   `DM_SERVICETYPE_CLASSIFICATION` (1)<br />-   `DM_SERVICETYPE_SEGMENTATION`(2)<br />-   `DM_SERVICETYPE_ ASSOCIATION`(4)<br />-   `DM_SERVICETYPE_ DENSITY_ESTIMATE`(8)<br />-   `DM_SERVICETYPE_SEQUENCE`(16)|  
|`SERVICE_NAME`|`DBTYPE_WSTR`||O nome específico do provedor para o algoritmo de mineração de dados usado pelo modelo.|  
|`CREATION_STATEMENT`|`DBTYPE_WSTR`||A instrução usada na criação do modelo de mineração.|  
|`PREDICTION_ENTITY`|`DBTYPE_WSTR`||Uma lista delimitada por vírgulas que indica quais colunas de mineração poderão ser previstas.|  
|`IS_POPULATED`|`DBTYPE_BOOL`||Um sinalizador Booliano que indica se o modelo está preenchido.<br /><br /> `TRUE` Se o modelo estiver preenchido; Caso contrário, `FALSE`.|  
|`MINING_PARAMETERS`|`DBTYPE_WSTR`||Uma lista separada por vírgulas dos parâmetros usados quando o modelo foi criado.|  
|`MINING_STRUCTURE`|`DBTYPE_WSTR`||A ID da estrutura de mineração em que o modelo se baseia.|  
|`LAST_PROCESSED`|`DBTYPE_DBTIMESTAMP`||A data em que o modelo foi processado pela última vez.|  
|`MSOLAP_IS_DRILLTHROUGH_ENABLED`|`DBTYPE_BOOL`||Um sinalizador Booliano que indica se o modelo oferece suporte a detalhamento.|  
|`FILTER`|`DBTYPE_WSTR`||A expressão de filtro associada ao modelo de mineração.<br /><br /> NULL ou uma cadeia de caracteres vazia indica que nenhum filtro foi aplicado.|  
|`TRAINING_SET_SIZE`|`DBTYPE_UIS`||O número de casos contidos no conjunto de treinamento do modelo de mineração após o processamento da estrutura e da aplicação de qualquer filtro ao modelo.|  
  
## <a name="restriction-columns"></a>Colunas de restrição  
 O conjunto de linhas `DMSCHEMA_MINING_MODELS` pode ser restringido nas colunas da tabela a seguir.  
  
|Nome da coluna|Indicador de tipo|Estado de restrição|  
|-----------------|--------------------|-----------------------|  
|`MODEL_CATALOG`|`DBTYPE_WSTR`|Opcional.|  
|`MODEL_SCHEMA`|`DBTYPE_WSTR`|Opcional.|  
|`MODEL_NAME`|`DBTYPE_WSTR`|Opcional.|  
|`MODEL_TYPE`|`DBTYPE_WSTR`|Opcional.|  
|`SERVICE_NAME`|`DBTYPE_WSTR`|Opcional.|  
|`SERVICE_TYPE_ID`|`DBTYPE_UI4`|Opcional.|  
|`MINING_STRUCTURE`|`DBTYPE_WSTR`|Opcional.|  
  
 Para obter exemplos de como consultar esse conjunto de linhas, consulte [consultar os parâmetros usados para criar um modelo de mineração](../../data-mining/query-the-parameters-used-to-create-a-mining-model.md).  
  
## <a name="see-also"></a>Consulte também  
 [Conjuntos de linhas de esquema de mineração de dados](../../schema-rowsets/data-mining/data-mining-schema-rowsets.md) 
  
  
