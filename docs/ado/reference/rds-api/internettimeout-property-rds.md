---
title: Propriedade InternetTimeout (RDS) | Microsoft Docs
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
helpviewer_keywords:
- InternetTimeout property [ADO]
ms.assetid: 4d1c8892-4bbc-4e71-bf4b-ba52c0ea9549
caps.latest.revision: 15
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 2320ba200cf8343a32e2a0d00589a80014517260
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="internettimeout-property-rds"></a>Propriedade InternetTimeout (RDS)
Indica o número de milissegundos de espera antes que uma solicitação expire.  
  
> [!IMPORTANT]
>  Começando com o Windows 8 e Windows Server 2012, os componentes de servidor RDS não estão mais incluídos no sistema operacional Windows (veja o Windows 8 e [manual de compatibilidade do Windows Server 2012](https://www.microsoft.com/en-us/download/details.aspx?id=27416) para obter mais detalhes). Componentes de cliente RDS serão removidos em uma versão futura do Windows. Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam. Aplicativos que usam o RDS devem migrar para [WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="settings-and-return-values"></a>Configurações e valores de retorno  
 Define ou retorna um **longo** valor que representa o número de milissegundos antes de uma solicitação expire.  
  
## <a name="remarks"></a>Comentários  
 Essa propriedade se aplica apenas às solicitações enviadas com os protocolos HTTP ou HTTPS.  
  
 Solicitações em um ambiente de três camadas podem levar vários minutos para ser executada. Use essa propriedade para especificar o tempo adicional para solicitações de longa execução.  
  
## <a name="applies-to"></a>Aplica-se a  
  
|||  
|-|-|  
|[Objeto DataControl (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)|[Objeto DataSpace (RDS)](../../../ado/reference/rds-api/dataspace-object-rds.md)|  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo de propriedade InternetTimeout (VB)](../../../ado/reference/rds-api/internettimeout-property-example-vb.md)   
 [Exemplo da propriedade InternetTimeout (VC++)](../../../ado/reference/rds-api/internettimeout-property-example-vc.md)   
 

