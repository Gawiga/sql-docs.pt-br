---
title: Adicionar inteligência de dimensão a uma dimensão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Business Intelligence enhancements [Analysis Services], dimension intelligence
- dimensions [Analysis Services], Business Intelligence enhancements
- dimension intelligence [Analysis Services]
- Type property
ms.assetid: b64fa386-eac2-4286-a320-0631a1887aac
caps.latest.revision: 32
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: fcd7ea323857e0db796b6e4a17bf8c2dde21e199
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37208126"
---
# <a name="add-dimension-intelligence-to-a-dimension"></a>Adicionar inteligência de dimensão a uma dimensão
  Adicione o aprimoramento de inteligência de dimensão a um cubo ou uma dimensão para especificar um tipo de negócios padrão para uma dimensão. Esse aprimoramento também especifica os tipos correspondentes para atributos de dimensão. Aplicativos cliente podem usar essas especificações de tipo ao analisar dados.  
  
 Para adicionar inteligência de dimensão, use o Assistente de Business Intelligence e selecione a opção **Definir inteligência de dimensão** na página **Escolher Aprimoramento** . Esse assistente orientará você durante as etapas para selecionar a dimensão à qual você deseja aplicar a inteligência de dimensão e identificar os atributos para a dimensão selecionada.  
  
## <a name="selecting-a-dimension"></a>Selecionando uma dimensão  
 Na primeira página **Definir Opções de Inteligência de Dimensão** do assistente, especifique a dimensão à qual você deseja aplicar a inteligência de dimensão. O aprimoramento de inteligência de dimensão adicionado à dimensão selecionada provocará alterações na dimensão. Essas alterações serão herdadas por todos os cubos que tiverem a dimensão selecionada.  
  
> [!NOTE]  
>  Se você selecionar **Conta** como dimensão, especificará a inteligência de conta para a dimensão. Para obter mais informações, consulte [Adicionar inteligência de conta a uma dimensão](bi-wizard-add-account-intelligence-to-a-dimension.md).  
  
## <a name="specifying-dimension-attributes"></a>Especificando atributos de dimensão  
 Sobre o **definir inteligência de dimensão** página, na **tipo de dimensão** lista, a seleção feita define a dimensão `Type` propriedade. O `Type` configuração da propriedade fornece informações ao cliente e servidores de aplicativos sobre o conteúdo de uma dimensão. Algumas configurações fornecem apenas orientação para aplicativos cliente; essas configurações são opcionais. Outras configurações, como para Contas ou Tempo, determinam comportamentos específicos e podem ser necessárias para implementar determinados aprimoramentos de business intelligence. Por exemplo, o SQL Server Management Studio usa o tipo de dimensão para identificar uma dimensão Moeda e definir as regras para conversão de moeda apropriadas. A configuração padrão de **Tipo de Dimensão** é **Regular**, o que não faz nenhuma suposição sobre o conteúdo da dimensão.  
  
 Depois de selecionar o tipo de dimensão, em **Atributos da dimensão**, na coluna **Incluir** , marque a caixa de seleção ao lado de cada tipo de atributo padrão para o qual existe um atributo correspondente na dimensão. Por fim, na coluna **Atributo de Dimensão** , expanda a lista suspensa e selecione o atributo da dimensão correspondente ao tipo de atributo selecionado. Selecionar o atributo na lista configura a propriedade `Type` dos atributos.  
  
 Por exemplo, convém adicionar inteligência de dimensão a uma dimensão Contas. Em **Tipo de Dimensão**, selecione **Contas**. Em seguida, se a dimensão tiver os atributos **Tipo de Conta** e **Descrição da Conta** , na coluna **Incluir** , marque as caixas de seleção dos tipos de conta **Nome da Conta** e **Tipo de Conta** . Na coluna **Atributo de Dimensão** , associe esses tipos de conta aos atributos **Descrição da Conta** e **Tipo de Conta** , respectivamente, na dimensão.  
  
## <a name="see-also"></a>Consulte também  
 [Definir cálculos de inteligência de tempo usando o Assistente de Business Intelligence](define-time-intelligence-calculations-using-the-business-intelligence-wizard.md)  
  
  
