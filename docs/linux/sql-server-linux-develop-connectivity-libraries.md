---
title: Estruturas e bibliotecas de conectividade | Microsoft Docs
description: Lista os drivers de conectividade que aplicativos cliente podem usar vários idiomas para se conectar ao Microsoft SQL Server em execução localmente ou na nuvem, no Linux, Windows ou Docker e também para o banco de dados SQL e Azure SQL Data Warehouse.
author: rothja
ms.author: jroth
manager: craigg
ms.date: 03/17/2017
ms.topic: conceptual
ms.prod: sql
ms.component: ''
ms.suite: sql
ms.custom: sql-linux
ms.technology: linux
ms.assetid: 80efe5ff-09ba-48a0-ac93-a91d62cff47c
ms.openlocfilehash: 37b6714a11adc9a64b796830183ecc02101a4823
ms.sourcegitcommit: 79d4dc820767f7836720ce26a61097ba5a5f23f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2018
ms.locfileid: "40392706"
---
# <a name="connectivity-libraries-and-frameworks-for-microsoft-sql-server"></a>Estruturas e bibliotecas de conectividade para Microsoft SQL Server

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-linuxonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-linuxonly.md)]

Confira a [tutoriais de Introdução](http://aka.ms/sqldev) para rapidamente começar com linguagens de programação como c#, Java, Node. js, PHP e Python e criar um aplicativo usando o SQL Server no Linux ou Windows ou Docker no macOS.

A tabela a seguir lista as bibliotecas de conectividade ou *drivers* que aplicativos cliente podem usar de uma variedade de idiomas para conectar e usar o Microsoft SQL Server em execução localmente ou na nuvem, no Linux, Windows ou Docker e também ao Azure SQL Database e Azure SQL Data Warehouse. 

| Linguagem | Plataforma | Recursos adicionais | Download | Introdução |
| :-- | :-- | :-- | :-- | :-- |
| C# | Windows, Linux, macOS | [Microsoft ADO.NET for SQL Server](http://msdn.microsoft.com/library/mt657768.aspx) | [Download](https://msdn.microsoft.com/vstudio/aa496123.aspx) | [Introdução](https://www.microsoft.com/en-us/sql-server/developer-get-started/csharp/ubuntu)
| Java | Windows, Linux, macOS | [Microsoft JDBC Driver para SQL Server](http://msdn.microsoft.com/library/mt484311.aspx) | [Download](http://go.microsoft.com/fwlink/?LinkId=245496) |  [Introdução](https://www.microsoft.com/en-us/sql-server/developer-get-started/java/ubuntu)
| PHP | Windows, Linux, macOS| [Driver SQL de PHP para SQL Server](../connect/php/microsoft-php-driver-for-sql-server.md) | Sistema Operacional: <br/> \* [Windows](https://www.microsoft.com/download/details.aspx?id=20098) <br/> \* [Linux](https://github.com/Microsoft/msphpsql/tree/dev#install-unix) <br/> \* [macOS](https://github.com/Microsoft/msphpsql/tree/dev#install-unix) |  [Introdução](https://www.microsoft.com/en-us/sql-server/developer-get-started/php/ubuntu)
| Node.js | Windows, Linux, macOS | [Driver Node.js para SQL Server](../connect/node-js/node-js-driver-for-sql-server.md) |  [Introdução](https://www.microsoft.com/en-us/sql-server/developer-get-started/node/ubuntu)
| Python | Windows, Linux, macOS | [Driver SQL Python](../connect/python/python-driver-for-sql-server.md) <br/> \* [pyodbc](http://msdn.microsoft.com/library/mt763257.aspx) |  [Introdução](https://www.microsoft.com/en-us/sql-server/developer-get-started/python/ubuntu)
| Ruby | Windows, Linux, macOS | [Ruby Driver para SQL Server](../connect/ruby/ruby-driver-for-sql-server.md) | [Introdução](https://www.microsoft.com/en-us/sql-server/developer-get-started/ruby/ubuntu)
| C++ | Windows, Linux, macOS | [Microsoft ODBC Driver for SQL Server](https://msdn.microsoft.com/library/mt654048(v=sql.1).aspx) | [Download](https://msdn.microsoft.com/library/mt654048(v=sql.1).aspx) |  

A tabela a seguir lista alguns exemplos de estruturas de objeto ORM (mapeamento relacional) e frameworks da web que aplicativos cliente podem usar com o Microsoft SQL Server em execução localmente ou na nuvem, no Linux, Windows ou Docker e também para o banco de dados SQL e Azure SQL Data Warehouse. 

| Linguagem | Plataforma | ORM(s) |
| :-- | :-- | :-- |
| C# | Windows, Linux, macOS | [Entity Framework](https://docs.microsoft.com/ef)<br>[O Entity Framework Core](https://docs.microsoft.com/ef/core/index) |
| Java | Windows, Linux, macOS |[Hibernar ORM](http://hibernate.org/orm)|
| PHP | Windows, Linux | [Laravel (eloquente)](https://laravel.com/docs/5.0/eloquent) |
| Node.js | Windows, Linux, macOS | [Sequelize ORM](http://docs.sequelizejs.com) |
| Python | Windows, Linux, macOS |[Django](https://www.djangoproject.com/) |
| Ruby | Windows, Linux, macOS | [Ruby on Rails](http://rubyonrails.org/) |

## <a name="related-links"></a>Links relacionados
- [Drivers do SQL Server](http://msdn.microsoft.com/library/mt654049.aspx) para conectar-se de aplicativos cliente
