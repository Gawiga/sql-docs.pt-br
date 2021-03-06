---
title: Nova página do relatório vinculado (Gerenciador de relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- SQL Server 2014
ms.assetid: fefb46e8-6901-4d50-a3f8-7c49ad72e7b1
caps.latest.revision: 22
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 63c244c74ac6039867834b7c289fd02de2e03b17
ms.sourcegitcommit: c8f7e9f05043ac10af8a742153e81ab81aa6a3c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39083618"
---
# <a name="new-linked-report-page-report-manager"></a>Página Novo Relatório Vinculado (Gerenciador de Relatórios)
  Use a página Novo Relatório Vinculado para criar um relatório vinculado. Um relatório vinculado é um relatório com configurações e propriedades próprias, mas vincula à definição de relatório de outro relatório. Relatórios vinculados são úteis quando você tem um relatório padrão que deseja variar para grupos ou usuários específicos; por exemplo, um relatório regional que retorna dados diferentes com base em um código regional especificado como parâmetro. Geralmente, um relatório vinculado é criado a partir um relatório com parâmetros quando você deseja variar e salvar valores de parâmetro diferentes com cada instância de relatório. Porém, você pode criar um relatório vinculado de qualquer relatório ao qual tenha acesso.  
  
 Um relatório vinculado pode ter seu próprio nome, descrição, local, propriedades de parâmetro, propriedades de histórico de execução de relatório, permissões e assinaturas. No entanto, um relatório vinculado deve usar as propriedades de fonte de dados e o layout do relatório padrão que fornece a definição do relatório.  
  
## <a name="navigation"></a>Navegação  
 Use os procedimentos a seguir para navegar para este local na interface do usuário.  
  
###### <a name="to-open-the-new-linked-report-page-from-the-contents-page"></a>Para abrir a página Novo Relatório Vinculado na página Conteúdo  
  
1.  Abra o Gerenciador de Relatórios e localize um relatório para o qual você deseja criar um relatório vinculado.  
  
2.  Focalize o relatório e clique na seta do menu suspenso.  
  
3.  No menu suspenso, clique em **Criar Relatório Vinculado**.  
  
###### <a name="to-open-the-new-linked-report-page-from-the-general-properties-page-of-a-report"></a>Para abrir a página Novo Relatório Vinculado na página de Propriedades gerais de um relatório.  
  
1.  Abra o Gerenciador de Relatórios e localize um relatório para o qual você deseja criar um relatório vinculado.  
  
2.  Focalize o relatório e clique na seta do menu suspenso.  
  
3.  No menu suspenso, clique em **Gerenciar**. Esse procedimento abre a página de propriedades Geral do relatório.  
  
4.  Na barra de ferramentas de item, clique em **Criar Relatório Vinculado**.  
  
## <a name="options"></a>Opções  
 **Nome**  
 Especifique o nome do relatório vinculado. Um nome deve conter pelo menos um caractere alfanumérico. Também pode conter espaços e certos símbolos. Porém, você não deve usar os caracteres; ? : \@ & = +, $ / * \< > | "ou / ao especificar um nome.  
  
 **Descrição**  
 Digite uma descrição do conteúdo do relatório. Essa descrição aparece na página Conteúdo para usuários com permissão para acessar o relatório.  
  
 **Local**  
 Especifique o caminho de pasta que contém o relatório. Por padrão, relatórios vinculados são criados como irmãos para o relatório padrão. Clique em **Alterar Local** para colocar o relatório vinculado em uma pasta diferente.  
  
 **OK**  
 Clique em **OK** para salvar suas alterações e voltar à página de propriedades Geral do relatório padrão.  
  
## <a name="see-also"></a>Consulte também  
 [Criar um relatório vinculado](reports/create-a-linked-report.md)   
 [Página Propriedades Gerais, Relatórios &#40;Gerenciador de Relatórios&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md)   
 [Ajuda F1 do Gerenciador de Relatórios](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
