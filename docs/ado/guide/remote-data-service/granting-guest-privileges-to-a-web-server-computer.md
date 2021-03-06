---
title: Conceder privilégios de convidado para um computador do servidor Web | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- guest privileges in RDS [ADO]
ms.assetid: e851a22d-01bc-4eb0-bc42-92b8f65d1c63
caps.latest.revision: 14
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 326a68def125fbc9e5f3b3d19ba1a0eb66cb5932
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35274035"
---
# <a name="granting-guest-privileges-to-a-web-server-computer"></a>Conceder privilégios de convidado para um computador do servidor Web
A conta do servidor Web anônima (IUSR _*ComputerName*) deve ser adicionado ao local grupo convidados no computador do servidor Web para usar o RDS.  
  
> [!IMPORTANT]
>  Começando com o Windows 8 e Windows Server 2012, os componentes de servidor RDS não estão mais incluídos no sistema operacional Windows (veja o Windows 8 e [manual de compatibilidade do Windows Server 2012](https://www.microsoft.com/en-us/download/details.aspx?id=27416) para obter mais detalhes). Componentes de cliente RDS serão removidos em uma versão futura do Windows. Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam. Aplicativos que usam o RDS devem migrar para [WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
### <a name="to-grant-guest-privileges-to-a-web-server-computer"></a>Para conceder privilégios de convidado em um computador do servidor Web  
  
1.  No computador do Microsoft Windows 2000 Server, clique em **iniciar**, aponte para **programas**, aponte para **ferramentas administrativas**e, em seguida, clique em **computador Gerenciamento**.  
  
2.  Na árvore de console, em **usuários e grupos locais**, clique em **grupos**.  
  
3.  Selecione o **convidados** grupo local. Do **ação** menu, escolha **propriedades**.  
  
4.  No **propriedades convidados** caixa de diálogo, clique em **adicionar**.  
  
5.  Se a conta do servidor Web anônima não aparecerá na lista de **selecionar usuários ou grupos** caixa de diálogo, digite seu nome (IUSR _*ComputerName*) na caixa em branco inferior e clique **adicionar** .  
  
6.  Clique em **OK**.


