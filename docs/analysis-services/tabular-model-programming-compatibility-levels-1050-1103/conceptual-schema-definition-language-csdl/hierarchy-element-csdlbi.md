---
title: Elemento Hierarchy (CSDLBI) | Microsoft Docs
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
ms.assetid: 9debb638-1b28-401b-9499-8f63943863e9
caps.latest.revision: 13
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: f3ff3c0bd93b75384b53e1f386a14196bcc803c3
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="hierarchy-element-csdlbi"></a>Elemento Hierarchy (CSDLBI)
  O elemento Hierarchy é um contêiner lógico para os campos em uma tabela que podem ser vinculados entre si para formar uma hierarquia. O elemento Hierarchy é derivado do elemento CSDL Member e foi estendido para oferecer suporte às hierarquias criadas em modelos de dados de business intelligence.  
  
## <a name="elements-and-attributes"></a>Elementos e atributos  
 A tabela a seguir lista os elementos e atributos que definem o elemento Hierarchy.  
  
|Nome|É obrigatório|Descrição|  
|----------|-----------------|-----------------|  
|Documentação|Não|Uma descrição da hierarquia.|  
|Nível|Sim|Um ou mais elementos Level que definem as colunas usadas na hierarquia.<br /><br /> Consulte [Elemento Level &#40;CSDLBI&#41;](../../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/conceptual-schema-definition-language-csdl/level-element-csdlbi.md).|  
  
## <a name="remarks"></a>Comentários  
 Em modelos tabulares, as hierarquias são criadas por meio da especificação de relações pai-filho entre colunas na mesma tabela. Para obter mais informações, consulte [Hierarquias &#40;SSAS Tabular&#41;](../../../analysis-services/tabular-models/hierarchies-ssas-tabular.md).  
  
## <a name="example"></a>Exemplo  
 **Tabular**  
  
 O exemplo a seguir, na versão 1.0 da CSDLBI, mostra uma hierarquia no modelo de exemplo da AdventureWorks que foi adicionado à tabela Products.  
  
```  
  
<bi:Hierarchy Name="Categoryy">  
    <bi:Level Name="CategoryName">  
       <bi:Source>  
       <bi:PropertyRef Name="CategoryName" />  
       </bi:Source>  
    </bi:Level>  
    <bi:Level Name="ProductName">  
       <bi:Source>  
       <bi:PropertyRef Name="ProductName" />  
       </bi:Source>  
    </bi:Level>  
</bi:Hierarchy>  
  
```  
  
## <a name="example"></a>Exemplo  
 **Multidimensional**  
  
 O exemplo a seguir, na versão 1.1 da CSDLBI, mostra uma hierarquia do cubo Operações de Varejo da Contoso.  
  
```  
  
<bi:Hierarchy Name="Product_Hierarchy" Caption="Product Hierarchy" ReferenceName="Product Hierarchy">  
   <bi:Documentation>  
      <bi:Summary>DESCRIPTION_ProductModelCateg_Hierarchies</bi:Summary>  
   </bi:Documentation>  
  
   <bi:Level Name="ProductLine">  
      <bi:Source>  
      <bi:PropertyRef Name="ProductLine" />  
      </bi:Source>  
   </bi:Level>  
  
   <bi:Level Name="ModelName">  
         <bi:Source>  
      <bi:PropertyRef Name="ModelName" />  
      </bi:Source>  
   </bi:Level>  
</bi:Hierarchy>  
  
```  
  
## <a name="see-also"></a>Consulte também  
 [Noções básicas sobre o modelo de objeto de tabela em compatibilidade 1050 1103 por meio de níveis](../../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)   
 [Compreendendo funções para hierarquias pai-filho em DAX](http://msdn.microsoft.com/en-us/b11f0cff-cee4-4ae7-a5b3-ebe288fc42d3)   
 [Configurar o &#40; Todos os &#41; Nível para hierarquias de atributo](../../../analysis-services/multidimensional-models/database-dimensions-configure-the-all-level-for-attribute-hierarchies.md)  
  
  

