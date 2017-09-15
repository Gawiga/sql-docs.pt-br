---
title: Arquitetura | Microsoft Docs
ms.custom: 
ms.date: 07/26/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- r-services
ms.tgt_pltfrm: 
ms.topic: article
author: jeannt
ms.author: jeannt
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 1328a346dd9852cba349e38204b49faf32573611
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="architecture-overview-for-machine-learning-services-with-python"></a>Visão geral da arquitetura de serviços de aprendizado de máquina com Python

Este tópico fornece uma visão geral de como o Python é integrado com o SQL Server, incluindo o modelo de segurança, os componentes no mecanismo de banco de dados que oferecem suporte à execução de scripts externos e novos componentes que permitem a interoperabilidade do Python com o SQL Server. Para obter detalhes, consulte os tópicos vinculados.

> [!IMPORTANT]
> Suporte para Python está disponível a partir do SQL Server de 2017 CTP 2.0. Esse recurso de pré-lançamento está sujeita a alterações.

## <a name="python-interoperability"></a>Interoperabilidade de Python

Serviços de aprendizado de máquina do SQL Server (no banco de dados) instala a distribuição Anaconda de Python e o tempo de execução do Python 3.5 e o interpretador. Isso assegura a compatibilidade de perto concluir com soluções de Python padrão. Python é executado em um processo separado do SQL Server, para garantir que as operações de banco de dados não sejam comprometidas.

Para obter mais informações sobre a interação do SQL Server com o Python, consulte [interoperabilidade Python](../../advanced-analytics/python/python-interoperability.md)

## <a name="components-that-support-python-integration"></a>Componentes que oferecem suporte à integração do Python

A estrutura de extensibilidade introduzida no SQL Server 2016 agora dá suporte à execução de script de Python, por meio da adição de novos componentes específicos do idioma. Esses componentes melhorar a velocidade de troca de dados e compactação, enquanto fornece uma plataforma segura, de alto desempenho para a execução de scripts externos.

Para uma descrição detalhada dos componentes que dão suporte a Python, como o [!INCLUDE[rsql_launchpad_md](../../includes/rsql-launchpad-md.md)] e PythonLauncher, consulte [novos componentes](../../advanced-analytics/python/new-components-in-sql-server-to-support-python-integration.md).

## <a name="security"></a>Segurança

Executarem tarefas de Python fora do processo do SQL Server, para fornecer maior capacidade de gerenciamento e de segurança.

Todas as tarefas são protegidas pela segurança do SQL Server ou objetos de trabalho do Windows. Dados são mantidos dentro do limite de conformidade com a imposição da segurança do SQL Server no nível de instância, banco de dados e tabela. O administrador de banco de dados pode controlar quem tem a capacidade de executar trabalhos de Python, monitorar o uso de scripts de Python por usuários e exibir os recursos consumidos.

Para obter detalhes, consulte [segurança para Python](../../advanced-analytics/python/security-overview-sql-server-python-services.md)

## <a name="resource-governance"></a>Governança de recursos

No SQL Server Enterprise Edition, você pode usar o administrador de recursos para gerenciar e monitorar o uso de recursos de operações de script externo, incluindo o script R e scripts de Python.

Para obter mais informações, consulte [governança de recursos para R](../../advanced-analytics/r/resource-governance-for-r-services.md).

## <a name="next-steps"></a>Próximas etapas

[Executar Python usando o T-SQL](../tutorials/run-python-using-t-sql.md)