---
title: Elemento AllMemberTranslations (ASSL) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- AllMemberTranslations Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- AllMemberTranslations
helpviewer_keywords:
- AllMemberTranslations element
ms.assetid: 982ee2bf-c88d-4da5-a679-7a6b08a48a0d
caps.latest.revision: 38
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: fe2ce64e1ec9b9af2e79ee29ca8aeb050da2d392
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="allmembertranslations-element-assl"></a>Elemento AllMemberTranslations (ASSL)
  Contém a coleção de [tradução](../../../analysis-services/scripting/objects/translation-element-assl.md) elementos para a legenda do membro All de um [hierarquia](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) elemento.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Hierarchy>  
   ...  
   <AllMemberTranslations>  
      <AllMemberTranslation xsi:type="Translation">...  
            </AllMemberTranslation>  
   </AllMemberTranslations>  
      ...  
</Hierarchy>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Nenhum (coleção)|  
|Valor padrão|Nenhum (coleção)|  
|Cardinalidade|0-1: elemento obrigatório que pode ocorrer apenas uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elemento pai|[Hierarchy](../../../analysis-services/scripting/objects/hierarchy-element-assl.md)|  
|Elementos filho|[AllMemberTranslation](../../../analysis-services/scripting/objects/allmembertranslation-element-assl.md)|  
  
## <a name="remarks"></a>Comentários  
 O elemento correspondente para o pai do **AllMemberTranslations** no objeto Analysis Management Objects (AMO) o modelo é <xref:Microsoft.AnalysisServices.Hierarchy>.  
  
## <a name="see-also"></a>Consulte também  
 [Elemento Translation &#40; ASSL &#41;](../../../analysis-services/scripting/objects/translation-element-assl.md)   
 [Coleções de &#40; ASSL &#41;](../../../analysis-services/scripting/collections/collections-assl.md)  
  
  