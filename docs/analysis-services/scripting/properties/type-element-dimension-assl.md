---
title: Tipo de elemento (dimensão) (ASSL) | Microsoft Docs
ms.date: 5/8/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 3af3168c39f685702154bb7c76435bd1d241a642
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "37990308"
---
# <a name="type-element-dimension-assl"></a>Elemento Type (Dimension) (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Fornece informações sobre o conteúdo da dimensão.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Dimension>  
      ...  
   <Type>...</Type>  
   ...  
</Dimension>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Cadeia de caracteres (enumeração)|  
|Valor padrão|*Regular*|  
|Cardinalidade|0-1: elemento opcional que pode ocorrer apenas uma única vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elemento pai|[Dimension](../../../analysis-services/scripting/objects/dimension-element-assl.md)|  
|Elementos filho|Nenhum|  
  
## <a name="remarks"></a>Remarks  
 Alguns valores para **Type**, por exemplo *Accounts*, determinam um comportamento específico.  
  
 O valor desse elemento é limitado a uma das cadeias de caracteres listadas na tabela a seguir.  
  
|Valor|Description|  
|-----------|-----------------|  
|*Regular*|A dimensão é uma dimensão regular.|  
|*Hora*|A dimensão é uma dimensão de tempo.<br /><br /> Observação: Esse valor indica que a dimensão oferece suporte a funcionalidades específicas para dimensões de tempo.|  
|*Geografia*|A dimensão contém atributos geográficos.|  
|*Organização*|A dimensão contém atributos organizacionais.|  
|*BillOfMaterials*|A dimensão contém uma conta de atributos de materiais.|  
|*Contas*|A dimensão contém atributos relacionados à conta.<br /><br /> Observação: Esse valor indica que a dimensão oferece suporte a funcionalidades específicas para dimensões de conta.|  
|*Clientes*|A dimensão contém atributos relacionados ao cliente.|  
|*Produtos*|A dimensão contém atributos relacionados ao produto.|  
|*Cenário*|A dimensão contém atributos relacionados ao cenário.|  
|*Quantitativa*|A dimensão contém atributos quantitativos.|  
|*Utilitário*|A dimensão contém atributos de utilitário.|  
|*Moeda*|A dimensão contém atributos de moeda.|  
|*Taxas*|A dimensão contém atributos de taxa de câmbio.|  
|*Canal*|A dimensão contém atributos de canal.|  
|*Promoção*|A dimensão contém atributos relacionados à promoção.|  
  
 A enumeração que corresponde aos valores permitidos para **tipo** no objeto Analysis Management Objects (AMO) o modelo é <xref:Microsoft.AnalysisServices.DimensionType>.  
  
 O elemento que corresponde ao pai de **tipo** no objeto Analysis Management Objects (AMO) o modelo é <xref:Microsoft.AnalysisServices.Dimension>.  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades &#40;ASSL&#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
