---
title: Definir uma relação de fato e propriedades de relação de fato | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: data-mining
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- fact dimensions [Analysis Services]
ms.assetid: d8e41724-da77-4ac1-bc42-956b5d91ea5d
caps.latest.revision: 10
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: c9ac99949cbac77b8a4edd806523acfc073c3dc2
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2018
---
# <a name="define-a-fact-relationship-and-fact-relationship-properties"></a>Definir uma relação de fato e propriedades de relação de fato
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]Quando você define uma nova dimensão de cubo ou um novo grupo de medidas, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] tentará detectar se uma relação de dimensão de fatos existe e, em seguida, defina a configuração de uso de dimensão como **fatos**. É possível exibir ou editar uma relação de dimensão de fatos na guia **Uso da Dimensão** do Designer de Cubo. A relação de dimensão de fatos entre uma dimensão e um grupo de medidas apresenta as seguintes restrições:  
  
-   Uma dimensão de cubo pode ter apenas uma relação de fatos com um determinado grupo de medidas.  
  
-   Uma dimensão de cubo pode ter relações de fatos separadas com vários grupos de medidas.  
  
-   O atributo de granularidade da relação deve ser o atributo de chave (como Número da Transação) da dimensão. Isso cria uma relação de um para um entre a dimensão e os fatos da tabela de fatos.  
  
  
