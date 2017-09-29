---
title: "Documentação do desenvolvedor do Integration Services | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Integration Services, programming
- SSIS, programming
- SQL Server Integration Services, programming
- packages [Integration Services], programming
ms.assetid: 60fe148b-a7c4-4289-ae3e-2e949fc1886c
caps.latest.revision: 76
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: cf7d7afba8ada3f6027db3053914b1822597792c
ms.contentlocale: pt-br
ms.lasthandoff: 09/26/2017

---
# <a name="integration-services-developer-documentation"></a>Documentação do desenvolvedor do Integration Services
  O [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] inclui um modelo de objeto totalmente reescrito, que foi aprimorado com vários recursos que tornam a extensão e a programação mais fáceis, flexíveis e eficientes. Desenvolvedores podem estender e programar quase todos os aspectos de pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].  
  
 Como desenvolvedor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], há duas abordagens fundamentais que você pode adotar na programação do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:  
  
-   Você pode estender pacotes escrevendo componentes que são disponibilizados dentro do Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] para fornecer funcionalidade personalizada em um pacote.  
  
-   Você pode criar, configurar e executar pacotes programaticamente a partir de seus próprios aplicativos.  
  
 Se você achar que os componentes internos no [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] não atenderem às suas necessidades, você pode ampliar a capacidade de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] codificando suas próprias extensões. Nessa abordagem, você tem duas opções distintas:  
  
-   Para uso ad hoc em um único pacote, você pode criar uma tarefa personalizada, escrevendo código na tarefa Script, ou um componente de fluxo de dados personalizado, escrevendo código no componente Script, que pode ser configurado como uma origem, transformação ou destino. Esses wrappers avançados escrevem o código de infraestrutura para você e permitem focar exclusivamente o desenvolvimento da sua funcionalidade personalizada; entretanto, não é fácil reutilizá-los em outros locais.  
  
-   Para permitir o uso em vários pacotes, você pode criar extensões personalizadas do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tais como gerenciadores de conexões, tarefas, enumeradores, provedores de log e componentes de fluxo de dados. O modelo de objeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] gerenciado contém classes base que fornecem um ponto de partida e facilitam ainda mais o desenvolvimento de extensões personalizadas.  
  
 Se desejar criar pacotes dinamicamente, ou gerenciar e executar pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] fora do ambiente de desenvolvimento, você poderá manipular pacotes programaticamente. Você pode carregar, modificar e executar pacotes existentes, ou criar e executar pacotes inteiramente novos programaticamente. Nessa abordagem, você tem uma série de opções:  
  
-   Carregar e executar um pacote existente sem modificação.  
  
-   Carregue um pacote existente, reconfigure-o (por exemplo, especifique outra fonte de dados) e execute-o.  
  
-   Crie um pacote novo, adicione e configure componentes, fazendo alterações em cada objeto e em cada propriedade, salve-o e, depois, execute-o.  
  
 Essas abordagens da programação do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] são descritas nessa seção e demonstradas através de exemplos.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Visão geral da programação do Integration Services](../integration-services/integration-services-programming-overview.md)  
 Descreve as funções de fluxo de controle e fluxo de dados no desenvolvimento do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].  
  
 [Compreendendo as transformações síncronas e assíncronas](../integration-services/understanding-synchronous-and-asynchronous-transformations.md)  
 Descreve a diferença importante entre saídas síncronas e assíncronas e os componentes que usam essas saídas no fluxo de dados.  
  
 [Trabalhando programaticamente com gerenciadores de conexões](../integration-services/working-with-connection-managers-programmatically.md)  
 Lista os gerenciadores de conexão que você pode usar a partir do código gerenciado e os valores retornados os gerenciadores de conexão quando o código chama o **AcquireConnection** método.  
  
 [Estender pacotes com scripts](../integration-services/extending-packages-scripting/extending-packages-with-scripting.md)  
 Descreve como estender o fluxo de controle por meio da tarefa Script ou o fluxo de dados por meio do componente Script.  
  
 [Estendendo pacotes com objetos personalizados](../integration-services/extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
 Descreve como criar e programar tarefas personalizadas, componentes de fluxo de dados e outros objetos de pacote para uso em vários pacotes.  
  
 [Compilar Pacotes Programaticamente](../integration-services/building-packages-programmatically/building-packages-programmatically.md)  
 Descreve como criar, configurar e salvar pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programaticamente.  
  
 [Executar e gerenciar pacotes programaticamente](../integration-services/run-manage-packages-programmatically/running-and-managing-packages-programmatically.md)  
 Descreve como enumerar, executar e gerenciar pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programaticamente.  
  
## <a name="reference"></a>Referência  
 [Referência de mensagens e erros do Integration Services](../integration-services/integration-services-error-and-message-reference.md)  
 Lista os códigos de erro predefinidos do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] acompanhados de seus nomes simbólicos e descrições.  
  
## <a name="related-sections"></a>Seções relacionadas  
 [Ferramentas de solução de problemas para desenvolvimento de pacotes](../integration-services/troubleshooting/troubleshooting-tools-for-package-development.md)  
 Descreve os recursos e as ferramentas que o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] fornece para solucionar problemas de pacotes durante o desenvolvimento.  
  
## <a name="external-resources"></a>Recursos externos  
  
-   Exemplos do CodePlex, [Exemplos de Produtos do Integration Services](http://go.microsoft.com/fwlink/?LinkID=131204), em www.codeplex.com/MSFTISProdSamples  
  
## <a name="see-also"></a>Consulte também  
 [SQL Server Integration Services](../integration-services/sql-server-integration-services.md)  
  
  