---
title: Instale o ADOMD.NET em servidores de front-end da Web executando a Administração Central | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: c2372180-e847-4cdb-b267-4befac3faf7e
caps.latest.revision: 8
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 5fd8c345a0f5b1cafdf675fa5ed57b857d9714b0
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37317536"
---
# <a name="install-adomdnet-on-web-front-end-servers-running-central-administration"></a>Instalar o ADOMD.NET em servidores Web front-end executando a Administração Central
  Se você instalar o PowerPivot para SharePoint em um farm que tenha a topologia de Administração Central, sem Serviços do Excel ou PowerPivot para SharePoint, baixe e instale a biblioteca cliente do Microsoft ADOMD.NET se quiser acesso completo aos relatórios internos no painel de gerenciamento PowerPivot. Alguns relatórios no painel usam ADOMD.NET para acessar dados internos que fornecem dados de relação sobre o processamento de consultas do PowerPivot e a integridade de servidor no farm.  
  
 **[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2010  
  
 Para o SharePoint 2013, o provedor é incluído no SQL Server feature pack. Para obter informações sobre como baixar o sppowerpivot. msi, consulte [Microsoft SQL Server 2014 Feature Pack](http://www.microsoft.com/download/details.aspx?id=35577)  
  
### <a name="download-and-install-the-client-library"></a>Baixar e instalar a biblioteca de cliente  
  
1.  Sobre o [página do Feature Pack do SQL Server 2014](http://go.microsoft.com/fwlink/?LinkID=296473), localize o Microsoft ADOMD.NET.  
  
2.  Baixe o Pacote x64 do programa de instalação `SQL_AS_ADOMD.msi`.  
  
3.  Execute o .msi para instalar a biblioteca.  
  
4.  Reinicie o IIS após a conclusão da instalação. Abra um prompt de comando administrativo e digite **IISRESET**.  
  
### <a name="verify-installation"></a>Verifique a instalação  
  
1.  Vá para Windows\Assembly.  
  
2.  Microsoft.AnalysisServices.AdomdClient com o botão direito e selecione **propriedades**.  
  
3.  Clique em **Versão**.  
  
4.  Verifique se a versão inclui 12.00. \<número da compilação > e que a descrição é analysisservice.  
  
## <a name="see-also"></a>Consulte também  
 [Painel de Gerenciamento PowerPivot e dados de uso](../../analysis-services/power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data.md)  
  
  
