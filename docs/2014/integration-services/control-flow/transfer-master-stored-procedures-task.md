---
title: Tarefa Transferir Procedimentos Armazenados Mestres | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfermasterspstask.f1
helpviewer_keywords:
- Transfer Master Stored Procedures task [Integration Services]
ms.assetid: 81702560-48a3-46d1-a469-e41304c7af8e
caps.latest.revision: 25
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: b89788698662245d69cb8b209286e1e5dd2f93a8
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37235316"
---
# <a name="transfer-master-stored-procedures-task"></a>Tarefa Transferir Procedimentos Armazenados Mestres
  A tarefa Transferir Procedimentos Armazenados Mestres transfere um ou mais procedimentos armazenados definidos pelo usuário entre bancos de dados **mestre** em instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Para transferir um procedimento armazenado do banco de dados **mestre** , o proprietário do procedimento deve ser dbo.  
  
 A tarefa Transferir Procedimentos Armazenados Mestres pode ser configurada para transferir todos os procedimentos armazenados ou apenas procedimentos armazenados específicos. Essa tarefa não copia procedimentos armazenados do sistema.  
  
 Os procedimentos armazenados mestres a serem transferidos podem já existir no destino. A tarefa Transferir Procedimentos Armazenados Mestres pode ser configurada para lidar com procedimentos já existentes armazenados das seguintes maneiras:  
  
-   Substituir procedimentos armazenados existentes.  
  
-   Interromper a tarefa quando existirem procedimentos armazenados duplicados.  
  
-   Ignorar procedimentos armazenados duplicados.  
  
 Em tempo de execução, a tarefa Transferir Procedimentos Armazenados Mestres conecta-se aos servidores de origem e de destino usando dois gerenciadores de conexões SMO. Os gerenciadores de conexões SMO são configurados separadamente a partir da tarefa Transferir Procedimentos Armazenados Mestres e depois referenciados na tarefa Transferir Procedimentos Armazenados Mestres. Os gerenciadores de conexões SMO especificam o servidor e o modo de autenticação a serem usados ao acessar o servidor. Para obter mais informações, consulte [SMO Connection Manager](../connection-manager/smo-connection-manager.md).  
  
## <a name="transferring-stored-procedures-between-instances-of-sql-server"></a>Transferindo procedimentos armazenados entre instâncias do SQL Server  
 A tarefa Transferir Procedimentos Armazenados Mestres dá suporte a uma origem e a um destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
## <a name="events"></a>Eventos  
 A tarefa gera um evento de informações que informa o número de procedimentos armazenados transferidos e um evento de aviso quando um procedimento armazenado é substituído.  
  
 A tarefa Transferir Procedimentos Armazenados Mestres não informa o progresso incremental da transferência de logon; ela apenas informa 0% e 100% de conclusão.  
  
## <a name="execution-value"></a>Valor de execução  
 O valor de execução, definido no `ExecutionValue` propriedade da tarefa, retorna o número de procedimentos armazenados transferidos. Ao atribuir uma variável definida pelo usuário para o `ExecValueVariable` propriedade da tarefa transferir procedimentos armazenados mestres, informações sobre a transferência de procedimento armazenado pode se tornar disponível a outros objetos no pacote. Para obter mais informações, consulte [Variáveis do Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) e [Usar variáveis em pacotes](../use-variables-in-packages.md).  
  
## <a name="log-entries"></a>Entradas de log  
 A tarefa Transferir Procedimentos Armazenados Mestres inclui as seguintes entradas de log personalizadas:  
  
-   TransferStoredProceduresTaskStartTransferringObjects Essa entrada de log informa que a transferência foi iniciada. A entrada do log contém a hora de início.  
  
-   TransferSStoredProceduresTaskFinishedTransferringObjects Essa entrada de log informa que a transferência foi concluída. A entrada do log contém a hora de término.  
  
 Além disso, uma entrada de log para o `OnInformation` evento informa o número de procedimentos armazenados que foram transferidos e uma entrada de log para o `OnWarning` evento foi criado para cada procedimento armazenado no destino que é substituído.  
  
## <a name="security-and-permissions"></a>Segurança e permissões  
 O usuário deve ter permissão para exibir a lista do procedimento armazenado no banco de dados **mestre** na origem e deve ser um membro da função de servidor sysadmin ou ter permissão para procedimentos armazenados criados no banco de dados **mestre** no servidor de destino.  
  
## <a name="configuration-of-the-transfer-master-stored-procedures-task"></a>Configuração da tarefa Transferir Procedimentos Armazenados Mestres  
 Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.  
  
 Para obter informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos tópicos a seguir:  
  
-   [Editor da tarefa procedimentos armazenados mestres de transferência &#40;página geral&#41;](../general-page-of-integration-services-designers-options.md)  
  
-   [Editor da tarefa procedimentos armazenados mestres de transferência &#40;página de procedimentos armazenado&#41;](../transfer-master-stored-procedures-task-editor-stored-procedures-page.md)  
  
-   [Página Expressões](../expressions/expressions-page.md)  
  
 Para obter informações sobre como definir essas propriedades programaticamente, clique no tópico a seguir:  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferStoredProceduresTask.TransferStoredProceduresTask>  
  
### <a name="configuring-the-transfer-master-stored-procedures-task-programmatically"></a>Configurando a tarefa Transferir Procedimentos Armazenados Mestres programaticamente  
  
## <a name="related-tasks"></a>Related Tasks  
 Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique no tópico a seguir:  
  
-   [Definir as propriedades de uma tarefa ou contêiner](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a>Consulte também  
 [Transferir tarefa de objetos do SQL Server](transfer-sql-server-objects-task.md)   
 [Tarefas do Integration Services](integration-services-tasks.md)   
 [Fluxo de Controle](control-flow.md)  
  
  
