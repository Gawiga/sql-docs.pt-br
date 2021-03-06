---
title: Importar um projeto de mineração de dados usando o Assistente de importação do Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 62bc9fc5-c6ff-4517-b598-d92df76743a2
caps.latest.revision: 5
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: eb48edb7b991a92e17e3c1c8d7b70cce54d1c938
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37319336"
---
# <a name="import-a-data-mining-project-using-the-analysis-services-import-wizard"></a>Importar um projeto de mineração de dados usando o Assistente de Importação do Analysis Services
  Este tópico descreve como criar um novo projeto de mineração de dados importando os metadados de projetos existentes de mineração de dados em outro servidor, usando o modelo **Projeto Importar do Servidor (Multidimensional ou Mineração de dados)**, no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].  
  
## <a name="import-data-sources-mining-structures-and-mining-models-from-an-existing-data-mining-project"></a>Importar fontes de dados, estruturas de mineração de dados e modelos de mineração de projetos existentes de mineração de dados.  
 Quando você usa o modelo **Projeto Importar do Servidor (Multidimensional ou Mineração de dados)**, o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] cria um novo projeto de mineração de dados e copiar os metadados do projeto de mineração de dados especificado. O novo projeto contém as mesmas fontes de dados, exibições de fontes de dados, estruturas de mineração e modelos de mineração que o banco de dados do ssASnoversion do qual você importou. Porém, o projeto não pode ser usado até que você tenha atualizado determinadas propriedades e processado os objetos como descrito:  
  
-   Os próprios dados não são copiados do servidor de origem para o novo projeto de mineração de dados — somente as definições da fonte de dados e as exibições da fonte de dados são importadas. Portanto, depois de concluído o processo de importação e da criação dos objetos, você deve popular os objetos com os dados treinando as estruturas de mineração e os modelos dependentes. Você pode usar o comando **Processar Tudo** no Designer de Mineração de Dados para treinar os modelos e as estruturas.  
  
-   Se você estiver importando um projeto que foi criado em uma versão anterior do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], a fonte de dados pode usar provedores que não estão instalados no servidor para o qual você está importando o projeto. Se você encontrar erros ao processar as estruturas de mineração importadas, clique com o botão direito do mouse em cada fonte de dados e selecione **Abrir Designer** para editar a cadeia de conexão e examinar as propriedades do provedor.  
  
     Neste momento, você também pode precisar verificar se a conta que está usando para processar os objetos de mineração de dados ou consultar modelos de mineração de dados tem as permissões necessárias na fonte de dados.  
  
-   Por padrão, quando você importa um projeto, o banco de dados de espaço de trabalho é definido como localhost ou qualquer instância padrão é configurada como o **Servidor de Destino Padrão** no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]. Para definir esta propriedade, no menu **Opções** , selecione **Designers de Business intelligence**, **Analysis Services**e **Geral**.  
  
     Observe que, no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], há outra opção separada que você pode definir para configurar o servidor de implantação padrão para projetos de modelo de tabela do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] . A configuração **Servidor de Implantação Padrão**determina o banco de dados de espaço de trabalho padrão para projetos de modelo de tabela. Você não pode usar instâncias que dão suporte a modelos de tabela para projetos de mineração de dados  
  
     Se você não puder alterar o banco de dados de implantação padrão para usar uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que é executada em modo multidimensional ou de mineração de dados, sempre poderá especificar o banco de dados de implantação usando a caixa de diálogo **Propriedades do Projeto** .  
  
#### <a name="to-create-a-new-data-mining-project-by-importing-an-existing-data-mining-project"></a>Para criar um novo projeto de mineração de dados importando um projeto existente de mineração de dados  
  
1.  No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], no menu **Arquivo** , clique em **Novo**e, em seguida, em **Projeto**.  
  
2.  Na caixa de diálogo **Novo Projeto** , em **Modelos Instalados**, clique em **Business Intelligence**, **Analysis Services**e em **Importar do Servidor (Multidimensional/Mineração de Dados)**.  
  
3.  Para **Nome**, digite um nome para o projeto e especifique um local e um nome para a solução e clique em **OK**.  
  
     O **Assistente para Importação de Bancos de Dados do Analysis Services** é iniciado. Clique em OK na página inicial para continuar.  
  
4.  Na página **Selecionar Banco de Dados de Origem**, para **Servidor**, especifique a instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contém a solução que você quer importar.  
  
     Para **Banco de Dados**, escolha o banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contém os objetos de mineração de dados que você quer importar.  
  
    > [!WARNING]  
    >  Você não pode especificar os objetos você quer importar; quando você escolhe um banco de dados existente do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , todos os objetos multidimensionais e de mineração de dados são importados.  
  
     Clique em **Avançar**.  
  
5.  A página **Concluindo o Assistente**exibe o andamento da operação de importação. Você não pode cancelar a operação ou alterar os objetos que estão sendo importados. Clique em **Concluir** quando tiver terminado.  
  
     O novo projeto é automaticamente aberto usando o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades do projeto &#40;Tabular do SSAS&#41;](../tabular-models/properties-ssas-tabular.md)  
  
  
