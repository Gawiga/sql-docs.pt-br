---
title: Requisitos do sistema para o Driver JDBC | Microsoft Docs
ms.custom: ''
ms.date: 07/19/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 447792bb-f39b-49b4-9fd0-1ef4154c74ab
caps.latest.revision: 73
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 377afbebe029add867a2d02cb02a38421dc8d1f2
ms.sourcegitcommit: 603d2e588ac7b36060fa0cc9c8621ff2a6c0fcc7
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42785033"
---
# <a name="system-requirements-for-the-jdbc-driver"></a>Requisitos de sistema para o JDBC Driver
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  Para acessar dados de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou de um [!INCLUDE[ssAzure](../../includes/ssazure_md.md)] usando o [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)], você deve ter os seguintes componentes instalados no computador:

- [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] ([baixar](download-microsoft-jdbc-driver-for-sql-server.md))
- Java Runtime Environment

## <a name="java-runtime-environment-requirements"></a>Requisitos do Java Runtime Environment  
 Começando com o Microsoft JDBC Driver 7.0 para o SQL Server, há suporte para Sun Java SE Development Kit (JDK) 10.0 e Java Runtime Environment (JRE) 10.0.

 Começando com o Microsoft JDBC Driver 6.4 para o SQL Server, há suporte para Sun Java SE Development Kit (JDK) 9.0 e Java Runtime Environment (JRE) 9.0.

 Começando com o 4.2 do Microsoft JDBC Driver para SQL Server, Sun Java SE Development Kit (JDK) 8.0 e Java Runtime Environment (JRE) 8.0 que têm suporte. Suporte para a API de especificação do Java Database Connectivity (JDBC) foi estendido para incluir a API do JDBC 4.1 e 4.2.  
  
 A partir do Microsoft JDBC Driver 4.1 para o SQL Server, o Sun Java SE Development Kit (JDK) 7.0 e Java Runtime Environment (JRE) 7.0 têm suporte.  
  
 Começando com o [!INCLUDE[jdbc_40](../../includes/jdbc_40_md.md)], o suporte para o JDBC driver para a API da Especificação do JDBC (Java Database Connectivity) foi estendido para incluir a API do JDBC 4.0. A API do JDBC 4.0 foi introduzida como parte do Sun Java SE Development Kit (JDK) 6.0 e do JRE (Java Runtime Environment) 6.0. O JDBC 4.0 é um superconjunto da API do JDBC 3.0.  
  
 Quando você implanta o [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] nos sistemas operacionais Windows e UNIX, deve usar os pacotes de instalação *sqljdbc_\<version>_enu.exe* e *sqljdbc_\<version>_enu.tar.gz*, respectivamente. Para obter mais informações sobre como implantar o Driver JDBC, consulte [Implantando o Driver JDBC](../../connect/jdbc/deploying-the-jdbc-driver.md) tópico.  
  
**Microsoft JDBC Driver 7.0 para SQL Server:**  

  O JDBC Driver 7.0 inclui duas bibliotecas de classes JAR em cada pacote de instalação: **mssql-jdbc-7.0.0.jre8.jar** e **mssql-jdbc-7.0.0.jre10.jar**.

  O JDBC Driver 7.0 foi desenvolvido para funcionar e ser compatível com todas as principais máquinas virtuais Java equivalentes às da Sun, mas foi testado somente com Sun JRE 8.0 e 10.0.
  
  A seguir, um resumo do suporte fornecido pelos dois arquivos JAR incluídos com o Microsoft JDBC Drivers 7.0 for SQL Server:  
  
  |JAR|Conformidade de versão do JDBC|Java versão recomendada|Descrição|  
|---------|-----------------------------|----------------------|-----------------|   
|mssql-jdbc-7.0.0.jre8.jar|4.2|8|Requer um Java Runtime Environment (JRE) 8.0. Usando o JRE 7.0 ou inferior lança uma exceção.<br /><br /> Os novos recursos no 7.0 incluem: suporte de 10 de JDK, o nível de compatibilidade padrão atualizado especificações JDBC 4.2, suporte a tipos de dados espaciais, cancelQueryTimeout propriedade de conexão, métodos de limite de solicitação, propriedade de conexão useBulkCopyForBatchInsert, dados Informações de descoberta e classificação, recurso de extensão de UTF-8 e suporte de CityHash. |    
|mssql-jdbc-7.0.0.jre10.jar|4.3|10|Requer um JRE (Java Runtime Environment) 10.0. Usando o JRE 9.0 ou inferior lança uma exceção.<br /><br /> Os novos recursos no 7.0 incluem: suporte de 10 de JDK, o nível de compatibilidade padrão atualizado especificações JDBC 4.2, suporte a tipos de dados espaciais, cancelQueryTimeout propriedade de conexão, métodos de limite de solicitação, propriedade de conexão useBulkCopyForBatchInsert, dados Informações de descoberta e classificação, recurso de extensão de UTF-8 e suporte de CityHash. |    


  O JDBC Driver 7.0 também está disponível no repositório Maven Central e podem ser adicionados a um projeto Maven adicionando o código a seguir no POM. XML:  
  
 ```xml
<dependency>
    <groupId>com.microsoft.sqlserver</groupId>
    <artifactId>mssql-jdbc</artifactId>
    <version>7.0.0.jre10</version>
</dependency>
```      
  
**Microsoft JDBC Driver 6.4 for SQL Server:**  

  O JDBC Driver 6.4 inclui duas bibliotecas de classes JAR em cada pacote de instalação: **mssql-jdbc-6.4.0.jre7.jar** e **mssql-jdbc-6.4.0.jre8.jar**.

  OJDBC Driver 6.4 foi desenvolvido para funcionar e ser compatível com todas as principais máquinas virtuais Java equivalentes às da Sun, mas foi testado somente com Sun JRE 7.0, 8.0 e 9.0.
  
  A seguir, um resumo do suporte fornecido pelos três arquivos JAR incluídos com o Microsoft JDBC Drivers 6.4 for SQL Server:  
  
  |JAR|Conformidade de versão do JDBC|Java versão recomendada|Descrição|  
|---------|-----------------------------|----------------------|-----------------|   
|mssql-jdbc-6.4.0.jre7.jar|4.1|7|Requer um Java Runtime Environment (JRE) 7.0. Usando o JRE 6.0 ou inferior lança uma exceção.<br /><br /> Novos recursos no 6.4 incluem: autenticação do Azure AD para o Linux, o método de entidade de segurança/senha para o Kerberos, a detecção automática de REALM no SPN para a autenticação de domínio cruzado, delegação restrita de Kerberos, o tempo limite da consulta, o tempo limite de soquete e preparada instrução lidar com a reutilização. |  
|mssql-jdbc-6.4.0.jre8.jar|4.2|8|Requer um Java Runtime Environment (JRE) 8.0. Usando o JRE 7.0 ou inferior lança uma exceção.<br /><br /> Novos recursos no 6.4 incluem: autenticação do Azure AD para o Linux, o método de entidade de segurança/senha para o Kerberos, a detecção automática de REALM no SPN para a autenticação de domínio cruzado, delegação restrita de Kerberos, o tempo limite da consulta, o tempo limite de soquete e preparada instrução lidar com a reutilização. |    
|mssql-jdbc-6.4.0.jre9.jar|4.3|9|Requer um JRE (Java Runtime Environment) 9.0. Usando o JRE 8.0 ou inferior lança uma exceção.<br /><br /> Novos recursos no 6.4 incluem: autenticação do Azure AD para o Linux, o método de entidade de segurança/senha para o Kerberos, a detecção automática de REALM no SPN para a autenticação de domínio cruzado, delegação restrita de Kerberos, o tempo limite da consulta, o tempo limite de soquete e preparada instrução lidar com a reutilização. |

O JDBC Driver 6.4 também está disponível no repositório Maven Central e podem ser adicionados a um projeto Maven adicionando o código a seguir no POM. XML 

 ```xml
<dependency>
    <groupId>com.microsoft.sqlserver</groupId>
    <artifactId>mssql-jdbc</artifactId>
    <version>6.4.0.jre9</version>
</dependency>
```

**Microsoft JDBC Driver 6.2 for SQL Server:**  
  
  O JDBC Driver 6.2 inclui duas bibliotecas de classes JAR em cada pacote de instalação: **mssql-jdbc-6.2.2.jre7.jar** e **mssql-jdbc-6.2.2.jre8.jar**. 
  
 OJDBC Driver 6.2 foi desenvolvido para funcionar e ser compatível com todas as principais máquinas virtuais Java equivalentes às da Sun, mas foi testado somente com Sun JRE 5.0, 6.0, 7.0 e 8.0.
  
 A seguir, um resumo do suporte fornecido pelos dois arquivos JAR incluídos com os Microsoft JDBC Drivers 6.0 e 4.2 para o SQL Server:  
  
|JAR|Conformidade de versão do JDBC|Java versão recomendada|Descrição|  
|---------|-----------------------------|----------------------|-----------------|
|MSSQL-jdbc-6.2.2.jre7.jar|4.1|7|Requer um Java Runtime Environment (JRE) 7.0. Usando o JRE 6.0 ou inferior lança uma exceção.<br /><br /> Os novos recursos no 6.2 incluem: autenticação do Azure AD para o Linux, o método de entidade de segurança/senha para o Kerberos, a detecção automática de REALM no SPN para a autenticação de domínio cruzado, delegação restrita de Kerberos, o tempo limite da consulta, o tempo limite de soquete e preparada instrução lidar com a reutilização. |  
|MSSQL-jdbc-6.2.3.jre8.jar|4.2|8|Requer um Java Runtime Environment (JRE) 8.0. Usando o JRE 7.0 ou inferior lança uma exceção.<br /><br /> Os novos recursos no 6.2 incluem: autenticação do Azure AD para o Linux, o método de entidade de segurança/senha para o Kerberos, a detecção automática de REALM no SPN para a autenticação de domínio cruzado, delegação restrita de Kerberos, o tempo limite da consulta, o tempo limite de soquete e preparada reutilização do identificador de instrução|    

  O JDBC Driver 6.2 também está disponível no repositório Maven Central e podem ser adicionados a um projeto Maven adicionando o código a seguir no POM. XML 
  
 ```xml
<dependency>
    <groupId>com.microsoft.sqlserver</groupId>
    <artifactId>mssql-jdbc</artifactId>
    <version>6.2.2.jre8</version>
</dependency>
```    

 **Microsoft JDBC Driver 6.0 e 4.2 for SQL Server:**  
  
  Os Drivers JDBC 6.0 e 4.2 incluem duas bibliotecas de classes JAR em cada pacote de instalação: **sqljdbc41.jar**, e **sqljdbc42.jar**. 
  
 Os JDBC Drivers 6.0 e 4.2 foram desenvolvidos para funcionar e ser compatíveis com todas as principais máquinas virtuais Java equivalentes às da Sun, somente foram testados somente com Sun JRE 5.0, 6.0, 7.0 e 8.0. 
  
 A seguir, um resumo do suporte fornecido pelos dois arquivos JAR incluídos com os Microsoft JDBC Drivers 6.0 e 4.2 para o SQL Server:  
  
|JAR|Conformidade de versão do JDBC|Java versão recomendada|Descrição|  
|---------|-----------------------------|----------------------|-----------------|   
|sqljdbc41.jar|4.1|7|Requer um Java Runtime Environment (JRE) 7.0. Usando o JRE 6.0 ou inferior lança uma exceção.<br /><br /> Os novos recursos em pacotes 4.2 & 6.0 incluem: conformidade JDBC 4.1 e cópia em massa<br /><br /> Além disso, os novos recursos no pacote 6.0 incluem: preparado do Always Encrypted, parâmetros com valor de tabela, autenticação do Azure Active Directory, as conexões transparentes para grupos de disponibilidade AlwaysOn, melhoria na recuperação de metadados de parâmetro para consultas e o nome de domínio internacionalizado (IDN)|  
|sqljdbc42.jar|4.2|8|Requer um Java Runtime Environment (JRE) 8.0. Usando o JRE 7.0 ou inferior lança uma exceção.<br /><br /> Os novos recursos em pacotes 4.2 & 6.0 incluem: conformidade JDBC 4.1, conformidade JDBC 4.2 e cópia em massa<br /><br /> Além disso, os novos recursos no pacote 6.0 incluem: preparado do Always Encrypted, parâmetros com valor de tabela, autenticação do Azure Active Directory, as conexões transparentes para grupos de disponibilidade AlwaysOn, melhoria na recuperação de metadados de parâmetro para consultas e o nome de domínio internacionalizado (IDN)|  
  
 **Microsoft JDBC Driver 4.1 for SQL Server:**  
  
 O JDBC Driver 4.1 inclui uma biblioteca de classes JAR em cada pacote de instalação: **sqljdbc41.jar**.  
    
|JAR|Descrição|  
|---------|-----------------|  
|sqljdbc41.jar|A biblioteca de classes **sqljdbc41.jar** dá suporte à API do JDBC 4.0. Ele inclui todos os recursos do driver JDBC 4.0, bem como métodos de API do JDBC 4.0. Não há suporte para o JDBC 4.1 (lança uma exceção "SQLFeatureNotSupportedException").<br /><br /> A biblioteca de classes **sqljdbc41.jar** requer um JRE (Java Runtime Environment) 7.0. Usando o **sqljdbc41.jar** JRE 6.0 e 5.0 lançará uma exceção.<br /><br /> 
  
 O driver JDBC foi desenvolvido para funcionar e ser compatível com todas as principais máquinas virtuais Java equivalentes às da Sun, mas foi testado somente com Sun JRE 5.0, 6.0 e 7.0.  
  
 A seguir, um resumo do suporte fornecido pelo arquivo JAR incluído com o Microsoft JDBC Driver 4.1 para o SQL Server.  
  
|JAR|Versão JDBC|JRE (pode ser executado)|JDK (pode ser compilado)|  
|---------|------------------|---------------------|-------------------------|   
|sqljdbc41.jar|4|7|7 6 5|  
  
## <a name="sql-server-requirements"></a>Requisitos do SQL Server  
 O driver JDBC dá suporte a conexões ao Banco de Dados SQL do Azure e ao SQL Server. Para o Microsoft JDBC Driver 4.2 e 4.1 para SQL Server, o suporte começa com o SQL Server 2008.
  
## <a name="operating-system-requirements"></a>Requisitos do sistema operacional  
 O driver JDBC foi desenvolvido para funcionar em qualquer sistema operacional que ofereça suporte ao uso de uma JVM (Máquina Virtual Java). Porém, só os sistemas operacionais Sun Solaris, SUSE Linux e Windows foram testados oficialmente.  
  
## <a name="supported-languages"></a>Idiomas com suporte  
 O driver JDBC dá suporte a todos os agrupamentos de coluna do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Para obter mais informações sobre os agrupamentos com suporte pelo driver JDBC, consulte [recursos internacionais do JDBC Driver](../../connect/jdbc/international-features-of-the-jdbc-driver.md).  
  
 Para obter mais informações sobre agrupamentos, consulte "Trabalhando com agrupamentos" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="see-also"></a>Consulte Também  
 [Visão geral do JDBC Driver](../../connect/jdbc/overview-of-the-jdbc-driver.md)  
  
  
