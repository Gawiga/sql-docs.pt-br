---
title: Perfis de agente (agente único) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.perfprofileagentname.f1
helpviewer_keywords:
- Agent Profile dialog box
ms.assetid: 22713555-c496-4ce1-8ec7-4ae75cfadca8
caps.latest.revision: 17
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 33d8a5564d6153a48da93da9b9a89ec3892a25a9
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37284952"
---
# <a name="agent-profiles-single-agent"></a>Perfis de Agente (agente único)
  Use a caixa de diálogo **Perfis de Agente** para gerenciar perfis para um agente. Perfis de agente fornecem um modo conveniente para gerenciar parâmetros em tempo de execução para cada agente. Cada agente tem um perfil padrão e alguns agentes têm perfis adicionais predefinidos. Por exemplo, o Merge Agent tem um perfil de "vínculo lento" projetado para baixas conexões de largura de banda. Perfis predefinidos são suficientes para a maioria dos aplicativos, mas você também pode criar perfis definidos pelo usuário, que permite personalizar o comportamento do agente.  
  
## <a name="options"></a>Opções  
 **Padrão para Novo**  
 Selecione o perfil que será usado quando são criados trabalhos para um agente de um determinado tipo. Por exemplo, se você criar um número de assinaturas para uma publicação de mesclagem, o trabalho do Merge Agent usará o perfil selecionado para cada assinatura. Se você quiser alterar o perfil dos trabalhos existentes, selecione um perfil e clique em **Alterar Agentes Existentes**.  
  
 **Nome**  
 O nome do perfil.  
  
 **Tipo**  
 O tipo de perfil: **Usuário** (definido pelo usuário) ou **Sistema** (predefinido).  
  
 **Propriedades (...)**  
 Clique para exibir os valores usados para cada parâmetro no perfil do agente.  
  
 **Nova**  
 Clique para criar um novo perfil.  
  
 **Delete (excluir)**  
 Selecione um perfil definido pelo usuário e então clique em **Excluir** para excluir aquele perfil. Perfis predefinidos não podem ser excluídos.  
  
 **Alterar Agentes Existentes**  
 Selecione um perfil e clique em **Alterar Agentes Existentes** para especificar que todos os trabalhos existentes, para um agente de um tipo específico, devem usar o perfil selecionado. Por exemplo, se você criou um número de assinaturas para uma publicação de mesclagem e quer alterar o perfil para especificar que um trabalho do Merge Agent para cada uma dessas assinaturas deve usar **Perfil do agente de vínculo lento**, selecione o perfil e clique em **Alterar Agentes Existentes**.  
  
## <a name="see-also"></a>Consulte também  
 [Trabalhar com perfis do Agente de Replicação](agents/work-with-replication-agent-profiles.md)   
 [Visão geral dos agentes de replicação](agents/replication-agents-overview.md)   
 [Perfis do agente de replicação](agents/replication-agent-profiles.md)  
  
  
