---
title: Banco de dados do Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.suite: sql
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- database [Master Data Services], about the database
- database [Master Data Services]
ms.assetid: 5f590cc1-6ec2-4b8c-a598-03de0f6051a0
caps.latest.revision: 6
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 2dd57db792a9a46480c186a627e5377b28c5949e
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "37998188"
---
# <a name="master-data-services-database"></a>Banco de dados do Master Data Services

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  O banco de dados contém todas as informações do sistema [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] . Ele é fundamental para uma implantação do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] . O banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] :  
  
-   Armazena as configurações, os objetos de banco de dados e os dados necessários ao sistema [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .  
  
-   Contém tabelas de preparo que são usadas para processar dados de sistemas de origem.  
  
-   Fornece um esquema e objetos de banco de dados para armazenar dados mestre de sistemas de origem.  
  
-   Oferece suporte à funcionalidade de controle de versão, inclusive validação de regra de negócio e notificações por email.  
  
-   Fornece exibições para sistemas de assinatura que precisam recuperar dados do banco de dados.  
  
## <a name="in-this-section"></a>Nesta seção  
  
-   [Tabela de preparo de membros folha &#40;Master Data Services&#41;](../master-data-services/leaf-member-staging-table-master-data-services.md)  
  
-   [Tabela de preparo de membros consolidados &#40;Master Data Services&#41;](../master-data-services/consolidated-member-staging-table-master-data-services.md)  
  
-   [Tabela de preparo de relações &#40;Master Data Services&#41;](../master-data-services/relationship-staging-table-master-data-services.md)  
  
-   [Erros de processo de preparo &#40;Master Data Services&#41;](../master-data-services/staging-process-errors-master-data-services.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Criar um banco de dados do Master Data Services](../master-data-services/install-windows/create-a-master-data-services-database.md)   
 [Segurança de objeto de banco de dados &#40;Master Data Services&#41;](../master-data-services/database-object-security-master-data-services.md)   
 [Logons, usuários e funções de banco de dados &#40;Master Data Services&#41;](../master-data-services/database-logins-users-and-roles-master-data-services.md)  
  
  
