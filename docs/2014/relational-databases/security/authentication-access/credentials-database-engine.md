---
title: Credenciais (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: security
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- principals [SQL Server], credentials
- schemas [SQL Server], credentials
- permissions [SQL Server], credentials
- groups [SQL Server], credentials
- ALTER ANY CREDENTIAL permission
- security [SQL Server], credentials
- authentication [SQL Server], credentials
- users [SQL Server], credentials
- credentials [SQL Server], about credentials
- credentials [SQL Server]
ms.assetid: c8df6022-e0b4-46b8-9670-3f86938d3177
author: VanMSFT
ms.author: vanto
manager: craigg
ms.openlocfilehash: d1a5247e5a6260b77ca3ea5349d6620fec9698dc
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43032761"
---
# <a name="credentials-database-engine"></a>Credenciais (Mecanismo de Banco de Dados)
  Uma credencial é um registro que contém as informações de autenticação(credenciais) necessárias para conectar-se a um recurso fora do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Essas informações são usadas internamente pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. A maioria das credenciais contém um nome e uma senha de usuário do Windows.  
  
 As informações armazenadas em uma credencial permite que um usuário quem se conectou com o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] por meio da Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] acesse os recursos fora da instância do servidor. Quando o recurso externo for o Windows, o usuário é autenticado como o usuário de Windows especificado na credencial. Uma única credencial pode ser mapeada para vários logons do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . No entanto, um logon do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] só pode ser mapeado para uma credencial.  
  
 Credenciais de sistema são criadas automaticamente e associadas a pontos de extremidade específicos. Nomes para credenciais de sistema iniciam com dois sinais de hash (##).  
  
 Para obter mais informações sobre credenciais, consulte o [sys. Credentials](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) exibição do catálogo.  
  
## <a name="related-content"></a>Conteúdo relacionado  
 [Criar uma credencial](../authentication-access/create-a-credential.md) [criar CREDENCIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql)  
  
 [Protegendo o SQL Server](../securing-sql-server.md)  
  
  
