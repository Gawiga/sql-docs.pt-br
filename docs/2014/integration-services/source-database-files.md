---
title: Arquivos de banco de dados de origem | Microsoft Docs
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
- sql12.dts.designer.transferdatabasetask.sourcedbfiles.f1
ms.assetid: 7dc6bfeb-37c1-45e8-a705-a87564922265
caps.latest.revision: 16
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 9bad26723ccb553144359e77154804cf2ab11982
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37160677"
---
# <a name="source-database-files"></a>Arquivos de banco de dados de origem
  Use a caixa de diálogo **Arquivos de Banco de Dados de Origem** para visualizar os nomes e locais do arquivo do banco de dados no servidor de origem ou especificar um local de compartilhamento de arquivos na rede para a tarefa Transferir Banco de Dados. Para obter mais informações sobre essa tarefa, consulte [Tarefa Transferir Banco de Dados](control-flow/transfer-database-task.md).  
  
 Para popular esta caixa de diálogo com os nomes e locais dos arquivos do banco de dados no servidor de origem, especifique primeiro **SourceConnection** e **SourceDatabaseName** na página **Banco de Dados** da caixa de diálogo **Editor da Tarefa Transferir Banco de Dados** .  
  
## <a name="options"></a>Opções  
 **Arquivo de Origem**  
 Nomes do arquivo de banco de dados no servidor de origem que serão transferidos. O**Arquivo de Origem** é somente leitura.  
  
 **Pasta de Origem**  
 Pasta no servidor de origem em que residem os arquivos de banco de dados a serem transferidos. A**Pasta de Origem** é somente leitura.  
  
 **Compartilhamento de Arquivos na Rede**  
 Pasta de compartilhamento de rede no servidor de origem da qual os arquivos de banco de dados serão transferidos. Use **Compartilhamento de Arquivo na Rede** ao transferir um banco de dados em modo offline, especificando **DatabaseOffline** em **Método** na página **Banco de Dados** da caixa de diálogo **Editor da Tarefa Transferir Banco de Dados** .  
  
 Insira o local de compartilhamento de arquivos na rede ou clique no botão Procurar **(...)** para localizá-lo.  
  
 Na transferência de um banco de dados em modo offline, os arquivos de banco de dados são copiados para o local **Compartilhamento de arquivo na rede** no servidor de origem, antes de serem transferidos ao servidor de destino.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor da tarefa de banco de dados transferir &#40;página geral&#41;](general-page-of-integration-services-designers-options.md)   
 [Editor da tarefa de banco de dados transferir &#40;página de bancos de dados&#41;](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
