---
title: Elemento LastSchemaUpdate (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- LastSchemaUpdate Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#LastSchemaUpdate
- urn:schemas-microsoft-com:xml-analysis#LastSchemaUpdate
- microsoft.xml.analysis.lastschemaupdate
helpviewer_keywords:
- LastSchemaUpdate element
ms.assetid: 2109955c-2817-413e-93aa-95d9910e8b24
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 7dbf2a1d11f799263b0b74671a16106d63c3d4d0
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48226397"
---
# <a name="lastschemaupdate-element-xmla"></a>Elemento LastSchemaUpdate (XMLA)
  Contém a data e a hora em que os metadados do cubo representados pelo elemento pai [Cube](cube-element-olapinfo-xmla.md) foram atualizados pela última vez.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Cube>  
   ...  
   <LastSchemaUpdate>...</LastSchemaUpdate>  
   ...  
</Cube>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|dateTime|  
|Valor padrão|None|  
|Cardinalidade|0-1: elemento opcional que pode ocorrer apenas uma única vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Cube](cube-element-olapinfo-xmla.md)|  
|Elementos filho|None|  
  
## <a name="remarks"></a>Comentários  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades &#40;XMLA&#41;](xml-elements-properties.md)  
  
  
