---
title: MSSQL_ENG021076 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021076 error
ms.assetid: 612e5c59-ba3e-49c3-a3df-56bac3d850a2
caps.latest.revision: 14
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 835233321589b9560b8933632dd82fdccf4206d3
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37190043"
---
# <a name="mssqleng021076"></a>MSSQL_ENG021076
    
## <a name="message-details"></a>Detalhes da mensagem  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|21076|  
|Origem do evento|MSSQLSERVER|  
|Componente|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nome simbólico||  
|Texto da mensagem|O instantâneo inicial do artigo '%s' ainda não está disponível.|  
  
## <a name="explanation"></a>Explicação  
 O erro MSSQL_ENG021076 pode ser gerado se o Distribution Agent for iniciado antes do Snapshot Agent terminar de gerar o instantâneo. Esse erro só será gerado se a publicação possuir um único artigo. Se a publicação possuir mais de um artigo, será gerado o erro MSSQL_ENG021075. Para obter mais informações, consulte [MSSQL_ENG021075](mssql-eng021075.md).  
  
## <a name="user-action"></a>Ação do usuário  
 Se o Snapshot Agent da publicação não for iniciado até que a assinatura seja criada, ou se não tiver sido iniciado desde que você optou por reiniciar a assinatura, inicie o Snapshot Agent e aguarde sua conclusão antes de iniciar o Distribution Agent. Para obter mais informações, consulte [Create and Apply the Snapshot](create-and-apply-the-snapshot.md) (Criar e aplicar o instantâneo).  
  
 Se o Agente de Instantâneo não for concluído, verifique o histórico do Agente de Instantâneo em relação a erros e faça o diagnóstico. Para obter informações sobre como exibir o status do agente e detalhes de erro no Replication Monitor, consulte [Exibir informações e executar tarefas para os agentes associados a uma publicação &#40;Replication Monitor&#41;](monitor/view-information-and-perform-tasks-for-publication-agents.md).  
  
 Se o erro continuar ocorrendo, aumente o log do agente e especifique um arquivo de saída para o log. Dependendo do contexto do erro, isso poderá fornecer as etapas que levaram ao erro e/ou as mensagens de erros adicionais.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md)  
  
  
