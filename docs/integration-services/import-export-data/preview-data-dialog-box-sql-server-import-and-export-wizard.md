---
title: Caixa de diálogo Visualizar Dados (Assistente de Importação e Exportação do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 02/16/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.dts.impexpwizard.previewdata.f1
ms.assetid: 423ac26a-ba02-4fdf-88b4-07995fe4a97e
caps.latest.revision: 22
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: f90a8b24e68d225cb929d4139b8efc42642e1a22
ms.sourcegitcommit: cc46afa12e890edbc1733febeec87438d6051bf9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2018
ms.locfileid: "35411548"
---
# <a name="preview-data-dialog-box-sql-server-import-and-export-wizard"></a>Caixa de diálogo Visualizar Dados (Assistente de Importação e Exportação do SQL Server)
  Depois de especificar os dados que você quer copiar, opcionalmente, você pode clicar em **Visualizar** para abrir a caixa de diálogo **Visualizar Dados** . Nessa página, você pode visualizar até 200 linhas de dados de exemplo da sua fonte de dados. Isso confirma se o assistente vai copiar os dados que você deseja copiar.
  
## <a name="screen-shot-of-the-preview-data-page"></a>Captura de tela da página Visualizar Dados 
 A captura de tela a seguir mostra a caixa de diálogo **Visualizar Dados** do Assistente.  
 
![Página Visualizar dados do Assistente de Importação e Exportação](../../integration-services/import-export-data/media/preview-data.png "Página Visualizar dados do Assistente de Importação e Exportação")  
  
## <a name="preview-sample-data"></a>Visualizar dados de exemplo  
 **Origem**  
Exibe a consulta usada pelo assistente para carregar dados da fonte de dados.

Se você tiver selecionado uma tabela para cópia, o campo **Origem** exibirá uma consulta de `SELECT * FROM <table>` em vez do nome da tabela. 
  
 **Grade de dados de exemplo**  
 Exibe até 200 linhas de dados de exemplo retornados pela consulta da fonte de dados.  


## <a name="thats-not-right-i-want-to-change-something"></a>Isso não está correto, quero alterar algo
Depois de visualizar os dados, é recomendável alterar as opções selecionadas nas páginas anteriores do assistente. Para fazer essas alterações, clique em **OK** para retornar à página **Selecionar Tabelas e Exibições de Origem** e clique em **Voltar** para retornar às páginas anteriores, nas quais é possível alterar as seleções.

## <a name="whats-next"></a>O que vem a seguir?  
 Depois de visualizar os dados que você vai copiar e clicar em **OK**, a **caixa de diálogo Visualizar Dados** retornará para a página **Selecionar Tabelas e Exibições de Origem** ou **Configurar Destino Arquivo Simples** . Para obter mais informações, consulte [Selecionar tabelas e exibições de origem](../../integration-services/import-export-data/select-source-tables-and-views-sql-server-import-and-export-wizard.md) ou [Configurar destino do arquivo simples](../../integration-services/import-export-data/configure-flat-file-destination-sql-server-import-and-export-wizard.md).  
 
 ## <a name="see-also"></a>Confira também
[Começar com esse exemplo simples de Assistente de Importação e Exportação](../../integration-services/import-export-data/get-started-with-this-simple-example-of-the-import-and-export-wizard.md)
