---
title: Configurações de informações de dispositivo ATOM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: fe4a56a4-5552-423c-85c1-895e2e212fee
caps.latest.revision: 7
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: c4d0f85da3c3762d32b8a59a34e073e9f14736a9
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37321869"
---
# <a name="atom-device-information-settings"></a>Configurações de informações do dispositivo ATOM
  As configurações das informações de dispositivo para a extensão de renderização Atom dão suporte ao envio do nome de um feed Atom e de uma codificação de caracteres a ser usada.  
  
 A tabela a seguir lista as configurações de informações de dispositivo para renderização para um documento de serviço de dados.  
  
|Configuração|Valor|  
|-------------|-----------|  
|`DataFeed`|Se for especificado, renderiza o feed Atom que corresponde ao nome do feed fornecido nessa configuração. Se não, renderiza o documento do serviço Atom para o relatório. O identificador exclusivo gerado automaticamente do feed de dados. Este valor é usado internamente e você não deve alterar isto.|  
|**Codificação**|O nome da IANA (Internet Assigned Numbers Authority) de uma codificação de caracteres com suporte do .NET Framework. O valor padrão é `UTF-8`. Exemplos de outros valores incluem ASCII, UTF-7 e UTF-16.|  
  
## <a name="see-also"></a>Consulte também  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 [Passando configurações de informações do dispositivo para extensões de renderização](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md)   
 [Personalizar parâmetros de extensão de renderização em RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md)   
 [Referência técnica &#40;SSRS&#41;](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
