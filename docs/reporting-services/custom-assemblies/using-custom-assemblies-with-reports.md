---
title: Usando assemblies personalizados com relatórios | Microsoft Docs
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: custom-assemblies
ms.suite: pro-bi
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- custom assemblies [Reporting Services]
- assemblies [Reporting Services], custom
- custom assemblies [Reporting Services], about custom assemblies
ms.assetid: 53d141d0-2185-466a-84dc-7b90d284da3d
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 9fe8eebd23d23d59264b95265a3f140255e3c0ef
ms.sourcegitcommit: d96b94c60d88340224371926f283200496a5ca64
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43266664"
---
# <a name="using-custom-assemblies-with-reports"></a>Usando assemblies personalizados com relatórios
  No [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], você pode escrever código personalizado para valores de item de relatório, estilos e formatação. Por exemplo, você pode usar código personalizado para formatar moedas com base na localidade, sinalizar certos valores com formatação especial ou aplicar outras regras comerciais que sejam praticadas por sua empresa. Uma forma de incluir esse código nos relatórios é criar um assembly de código personalizado usando o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], que pode ser referenciado nos arquivos de definição de relatório. O servidor chama as funções em seus assemblies personalizados quando um relatório é executado. Os assemblies personalizados podem ser usados para recuperar funções especializadas que você planeja usar em seus relatórios.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Fazer referência a assemblies em um arquivo RDL](../../reporting-services/custom-assemblies/referencing-assemblies-in-an-rdl-file.md)  
 Descreve como referenciar seus assemblies personalizados em um arquivo de linguagem de definição de relatório.  
  
 [Implantando um assembly personalizado](../../reporting-services/custom-assemblies/deploying-a-custom-assembly.md)  
 Descreve como implantar um assembly personalizado para o Designer de Relatórios e para o servidor de relatório.  
  
 [Usar assemblies de nome forte personalizados](../../reporting-services/custom-assemblies/using-strong-named-custom-assemblies.md)  
 Descreve como usar assemblies personalizados com nomes fortes.  
  
 [Declarar permissões em assemblies personalizados](../../reporting-services/custom-assemblies/asserting-permissions-in-custom-assemblies.md)  
 Descreve como implantar assemblies personalizados com permissões limitadas e específicas e como declarar essas permissões em código.  
  
 [Acessar assemblies personalizados por meio de expressões](../../reporting-services/custom-assemblies/accessing-custom-assemblies-through-expressions.md)  
 Descreve como chamar métodos de assembly personalizados como expressões de relatório em suas definições de relatório.  
  
 [Inicializar objetos assembly personalizados](../../reporting-services/custom-assemblies/initializing-custom-assembly-objects.md)  
 Descreve como inicializar valores para objetos de assembly personalizados chamados de um relatório.  
  
 [Como depurar assemblies personalizados](../../reporting-services/custom-assemblies/how-to-debug-custom-assemblies.md)  
 Descreve como depurar seu código de assembly personalizado.  
  
## <a name="see-also"></a>Consulte Também  
 [Linguagem RDL &#40;SSRS&#41;](../../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
