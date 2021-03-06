---
title: Microsoft OLE DB Driver for SQL Server | Microsoft Docs
description: Instalar e desinstalar o Driver do OLE DB para SQL Server
ms.custom: ''
ms.date: 06/12/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: oledb|applications
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB Driver for SQL Server, uninstalling
- MSOLEDBSQL, installing
- MSOLEDBSQL, uninstalling
- Setup [OLE DB Driver for SQL Server]
- uninstalling OLE DB Driver for SQL Server
- data access [OLE DB Driver for SQL Server], uninstalling OLE DB Driver for SQL Server
- installing OLE DB Driver for SQL Server
- OLE DB Driver for SQL Server, installing
- data access [OLE DB Driver for SQL Server], installing OLE DB Driver for SQL Server
- removing OLE DB Driver for SQL Server
author: pmasl
ms.author: pelopes
manager: craigg
ms.openlocfilehash: 10bf2ce673543cbad21bccdac35ac863647e910a
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43019145"
---
# <a name="installing-ole-db-driver-for-sql-server"></a>Instalar o OLE DB Driver for SQL Server
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

Para instalar o Driver do OLE DB para SQL Server, você precisa msoledbsql.msi installer.
Execute o instalador e faça suas seleções preferenciais. O Driver do OLE DB para SQL Server pode ser instalada lado a lado com versões anteriores do provedor Microsoft OLE DB.

O Driver OLE DB para arquivos do SQL Server (msoledbsql.dll, msoledbsqlr.rll) são instalados em `%SYSTEMROOT%\system32\` . Além disso, o x64 msoledbsql.msi instala os binários de 32 bits em `%SYSTEMROOT%\SysWOW64\`.

> [!NOTE]  
> Todas as configurações de registro apropriados para o Driver do OLE DB para SQL Server são feitas como parte do processo de instalação.  

O Driver OLE DB para SQL Server cabeçalho e biblioteca de arquivos (msoledbsql.h e msoledbsql.lib) são instalados em `%PROGRAMFILES%\Microsoft SQL Server\Client SDK\OLEDB\181\SDK`. Além disso, o x64 msoledbsql.msi instala os mesmos arquivos no `%PROGRAMFILES(x86)%\Microsoft SQL Server\Client SDK\OLEDB\181\SDK`.  

Você pode distribuir o Driver do OLE DB para SQL Server por meio de msoledbsql.msi. Talvez você precise instalar o Driver do OLE DB para SQL Server quando você implanta um aplicativo. Uma maneira de instalar vários pacotes em um processo que, para o usuário, parece ser uma única instalação é usar a tecnologia de encadeador e bootstrapper. Para obter mais informações, confira [Criando um pacote de bootstrapper personalizado para o Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=115667) e [Adicionando pré-requisitos personalizados](http://go.microsoft.com/fwlink/?LinkId=115668).  
  
X64 msoledbsql.msi também instala a versão de 32 bits do Driver do OLE DB para SQL Server. Se seu aplicativo for destinado a uma plataforma diferente daquele que foi desenvolvido, você pode baixar versões do msoledbsql.msi para x64 e x86.

Quando você invoca msoledbsql.msi, só os componentes cliente são instalados por padrão. Os componentes cliente são arquivos que dão suporte à execução de um aplicativo que foi desenvolvido usando o OLE DB Driver for SQL Server. Para instalar também os componentes SDK, especifique `ADDLOCAL=All` na linha de comando. Por exemplo:  

`msiexec /i msoledbsql.msi ADDLOCAL=ALL`  

## <a name="silent-install"></a>Instalação silenciosa  
 Se você usar a opção /passive, /qn, /qb ou /qr com msiexec, também precisará especificar IACCEPTMSOLEDBSQLLICENSETERMS=YES, para indicar explicitamente que aceitou os termos da licença do usuário final. Essa opção deve ser especificada totalmente em letras maiúsculas.  

## <a name="installing-ole-db-driver-for-sql-server-as-a-dependency"></a>Instalar o Driver do OLE DB para SQL Server como uma dependência  
É importante não desinstalar o Driver do OLE DB para SQL Server até que todos os aplicativos dependentes são desinstalados. Para fornecer aos usuários um aviso de que seu aplicativo depende do Driver do OLE DB para SQL Server, use a opção de instalação APPGUID no MSI, da seguinte maneira:  

 `msiexec /i msoledbsql.msi APPGUID={0CC618CE-F36A-415E-84B4-FB1BFF6967E1}`  

O valor passado para APPGUID é o seu código de produto específico. É preciso criar um código de produto ao usar o Microsoft Installer para agrupar o programa de instalação do aplicativo.
A opção de APPGUID requer executar o instalador em um Prompt de comando elevado.

## <a name="see-also"></a>Consulte Também  
 [Criação de aplicativos com o Driver do OLE DB para SQL Server](../../oledb/applications/building-applications-with-oledb-driver-for-sql-server.md)   
