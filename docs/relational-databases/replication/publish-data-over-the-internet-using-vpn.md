---
title: Publicar dados pela Internet usando a VPN | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: replication
ms.reviewer: ''
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- VPNs [SQL Server replication]
- Web publishing [SQL Server replication], VPNs
- Internet [SQL Server replication], VPNs
ms.assetid: 9ffb6546-9973-4574-aaa0-8fe0017e3601
caps.latest.revision: 33
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 5b26f84367d85a1f9e2a3d210b35d6c94b1aa15d
ms.sourcegitcommit: 022d67cfbc4fdadaa65b499aa7a6a8a942bc502d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37351048"
---
# <a name="publish-data-over-the-internet-using-vpn"></a>Publicar dados pela Internet usando VPN
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  A tecnologia VPN (rede virtual privada) permite que usuários que trabalham em casa, filiais, clientes remotos e outras empresas se conectem a uma rede corporativa pela Internet, mantendo comunicações seguras. Os usuários podem usar a Autenticação do Windows como se estivessem em uma LAN (rede local). Todos os tipos de replicação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem replicar dados por uma VPN, no entanto, considere usar a sincronização da Web quando a replicação de mesclagem for utilizada, porque a sincronização da Web elimina a necessidade de uma VPN. Para obter mais informações, consulte [Web Synchronization for Merge Replication](../../relational-databases/replication/web-synchronization-for-merge-replication.md).  
  
 A VPN inclui um software cliente de modo que os computadores são conectados pela Internet (ou, em casos especiais, até mesmo por uma intranet) a um software em um computador ou um servidor dedicado. Opcionalmente, se utiliza criptografia nas duas extremidades, assim como métodos de autenticação de usuário. A conexão VPN pela Internet opera logicamente como um link WAN (Rede de Longa Distância) entre os sites.  
  
 Uma VPN conecta os componentes de uma rede usando outra rede. Para conectar, o usuário trafega pela Internet ou outra rede pública usando um protocolo como o [!INCLUDE[msCoName](../../includes/msconame-md.md)] PPTP (protocolo de encapsulamento ponto a ponto) ou L2TP (protocolo de encapsulamento de camada 2). Este processo provê a mesma segurança e os recursos previamente apenas disponíveis em uma rede privada. O PPTP é disponível com os sistemas operacionais Microsoft Windows NT versão 4.0 e o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2000( e versões posteriores); o L2TP é disponível com o Windows 2000 e versões posteriores.  
  
 Para o usuário, a infraestrutura de roteamento intermediário da Internet não é visível e parece que os dados estão sendo enviados por um link privado dedicado. Para os usuários, a VPN é uma conexão ponto a ponto entre o computador do usuário e um servidor corporativo.  
  
 Depois de você ter configurado o seu cliente remoto para conectar usando uma VPN e o cliente tenha acesso à Internet e se registre à LAN corporativa, você pode configurar a replicação como se o cliente remoto estivesse conectado diretamente na LAN. Por motivos de segurança, é possível ter diferentes recursos de rede disponíveis aos usuários conectados pela VPN e àqueles conectados diretamente pela LAN.  
  
 Para obter mais informações sobre a configuração de uma VPN, consulte a documentação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.  
  
## <a name="see-also"></a>Consulte Também  
 [Replicação na Internet](../../relational-databases/replication/replication-over-the-internet.md)  
  
  
