---
title: RBS (Armazenamento de Blobs Remoto) (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Remote Blob Store (RBS) [SQL Server]
- RBS (Remote Blob Store) [SQL Server]
ms.assetid: 31c947cf-53e9-4ff4-939b-4c1d034ea5b1
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: fd459f9c8e1fa2a36a6eb8f3fadb3581cee87325
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37425235"
---
# <a name="remote-blob-store-rbs-sql-server"></a>RBS (Armazenamento de Blob Remoto) [SQL Server]
  O[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Remote BLOB Store (RBS) é um componente complementar opcional que permite aos administradores de bancos de dados armazenar objetos binários grandes em soluções de armazenamento de mercadorias, e não diretamente no servidor de banco de dados principal.  
  
 O RBS está incluído na mídia de instalação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , mas não é instalado pelo programa de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 Para mais informações sobre RBS, consulte [RBS Resources](#rbsresources) neste tópico.  
  
## <a name="benefits-of-rbs"></a>Benefícios do RBS  
 O RBS oferece os seguintes benefícios:  
  
### <a name="optimized-database-storage-and-performance"></a>Armazenamento e desempenho de banco de dados otimizados  
 O armazenamento de BLOBs no banco de dados pode consumir muito espaço em arquivo e envolver recursos caros de servidor. O RBS transfere os BLOBs com eficácia para uma solução de armazenamento dedicada de sua preferência e armazena as referências a eles no banco de dados. Isso libera armazenamento do servidor para dados estruturados e também libera recursos do servidor para operações de banco de dados.  
  
### <a name="efficient-management-of-blobs"></a>Gerenciamento eficaz de BLOBs  
 Vários recursos do RBS oferecem suporte ao gerenciamento conveniente de BLOBs armazenados:  
  
-   BLOBS são gerenciados com transações ACID (atomicidade, consistência, isolamento e durabilidade).  
  
-   BLOBs são organizados em coleções.  
  
-   São incluídas a coleta de lixo, a verificação de consistência e outras funções de manutenção.  
  
### <a name="standardized-api"></a>API padronizada  
 O RBS define um conjunto de APIs que fornecem um modelo de programação padronizado para que os aplicativos acessem e modifiquem qualquer repositório de BLOB. Cada repositório de BLOB pode especificar sua própria biblioteca de provedores, que se conecta à biblioteca cliente RBS e especifica como os BLOBs são armazenados e acessados.  
  
 Vários fornecedores de solução de armazenamento de terceiros desenvolveram provedores RBS que estão em conformidade com estas APIs padrão e oferecem suporte ao armazenamento de BLOB em várias plataformas de armazenamento.  
  
## <a name="rbs-requirements"></a>Requisitos de RBS  
 O RBS requer o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise para o servidor de banco de dados principal no qual os metadados de BLOB são armazenados. Porém, se você usar o provedor FILESTREAM fornecido, poderá armazenar os próprios BLOBs no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Standard.  
  
 O RBS inclui um provedor FILESTREAM que permite usar o RBS para armazenar BLOBs em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Caso deseje usar o RBS para armazenar BLOBs em uma solução de armazenamento diferente, utilize um provedor RBS de terceiros desenvolvido para essa solução de armazenamento ou desenvolva um provedor RBS personalizado usando a API do RBS. Um provedor de exemplo que armazena BLOBs no sistema de arquivos NTFS está disponível como um recurso de aprendizagem em [Codeplex](http://go.microsoft.com/fwlink/?LinkId=210190).  
  
## <a name="rbs-security"></a>Segurança do RBS  
 Quando você usar um provedor personalizado para armazenar BLOBs fora do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], talvez eles estejam disponíveis para outros processos que ignorem o sistema de segurança do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Proteja os BLOBs armazenados com permissões e opções de criptografia apropriadas para a mídia de armazenamento usada pelo provedor personalizado.  
  
##  <a name="rbsresources"></a> Recursos do RBS  
 **Documentação do RBS**  
 A documentação do RBS está incluída no pacote do Windows Installer. Se você desejar revisar a documentação do RBS sem instalar o RBS, poderá exibir a versão [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] da documentação [online na Biblioteca do MSDN](http://go.microsoft.com/fwlink/?LinkId=210192).  
  
 **White paper do RBS**  
 O white paper "[Remote BLOB Storage](http://go.microsoft.com/fwlink/?LinkId=210422)", que está disponível para download como um documento do Microsoft Word, fornece informações detalhadas sobre como instalar e configurar o RBS.  
  
 **Exemplos do RBS**  
 Os exemplos do RBS disponíveis em [Codeplex](http://go.microsoft.com/fwlink/?LinkId=210190) demonstram como desenvolver um aplicativo RBS, e como desenvolver e instalar um provedor RBS personalizado.  
  
 **Blog do RBS**  
 O [blog do RBS](http://go.microsoft.com/fwlink/?LinkId=210315) fornece informações adicionais para ajudá-lo a compreender, implantar e manter o RBS.  
  
  
