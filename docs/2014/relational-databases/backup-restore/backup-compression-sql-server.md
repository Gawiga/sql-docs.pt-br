---
title: Compactação de backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: backup-restore
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], backup compression
- backup compression [SQL Server], about backup compression
- compression [SQL Server], backup compression
- backups [SQL Server], compression
- backing up [SQL Server], backup compression
- backup compression [SQL Server]
ms.assetid: 05bc9c4f-3947-4dd4-b823-db77519bd4d2
caps.latest.revision: 48
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: fe90321363497500a46e81faee7b40bf3bf8a4d2
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37168997"
---
# <a name="backup-compression-sql-server"></a>Compactação de backup (SQL Server)
  Este tópico descreve a compactação dos backups do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , incluindo restrições, compensação de desempenho de backups compactados, a configuração da compactação de backup e a taxa de compactação.  
  
> [!NOTE]  
>  Para informações sobre quais edições do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oferecem suporte à compactação de backup, consulte [recursos compatíveis com as edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md). Todas as edições do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ou posterior podem restaurar um backup compactado.  
  
  
##  <a name="Benefits"></a> Benefícios  
  
-   Como um backup compactado é menor do que um backup não compactado dos mesmos dados, a compactação de um backup normalmente requer menos operações de E/S do dispositivo e, portanto, normalmente aumenta significativamente a velocidade do backup.  
  
     Para obter mais informações, consulte [Impacto de desempenho dos backups compactados](#PerfImpact), posteriormente neste tópico.  
  
  
##  <a name="Restrictions"></a> Restrições  
 As restrições a seguir aplicam-se aos backups compactados:  
  
-   Backups compactados e não compactados não podem coexistir em um conjunto de mídias.  
  
-   Porém, as versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não podem ler os backups compactados.  
  
-   Backups NT não podem compartilhar uma fita com backups compactados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
  
##  <a name="PerfImpact"></a> Impacto de desempenho dos backups compactados  
 Por padrão, a compactação aumenta consideravelmente o uso da CPU, e o consumo adicional da CPU por parte do processo de compactação pode afetar negativamente as operações simultâneas. Portanto, convém criar backups compactados de baixa prioridade em uma sessão cujo uso da CPU é limitado pelo[Resource Governor](../resource-governor/resource-governor.md). Para obter mais informações, consulte [Usar o Resource Governor para limitar o uso de CPU por meio de compactação de backup &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).  
  
 Para obter uma boa visão do desempenho de E/S do seu backup, é possível isolar o E/S do backup para ou dos dispositivos avaliando as seguintes classificações dos contadores de desempenho:  
  
-   Contadores de desempenho de E/S do Windows, como os contadores de disco físico  
  
-   O contador de **Taxa de Transferência do Dispositivo em Bytes/s** do objeto [SQLServer:Backup Device](../performance-monitor/sql-server-backup-device-object.md)  
  
-   O contador **Taxa de Transferência de Backup/Restauração/s** do objeto [SQLServer:Databases](../performance-monitor/sql-server-databases-object.md)  
  
 Para obter informações sobre contadores do Windows, consulte a ajuda do Windows. Para obter informações sobre como trabalhar com contadores SQL Server, consulte [Usar objetos do SQL Server](../performance-monitor/use-sql-server-objects.md).  
  
  
##  <a name="CompressionRatio"></a> Calcular a taxa de compactação de um backup compactado  
 Para calcular a taxa de compactação de um backup, use os valores para o backup nas colunas **backup_size** e **compressed_backup_size** da tabela de histórico [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) da seguinte maneira:  
  
 **backup_size**:**compressed_backup_size**  
  
 Por exemplo, uma taxa de compactação de 3:1 indica que você está economizando aproximadamente 66% de espaço em disco. Para consultar essas colunas, você pode usar a seguinte instrução Transact-SQL:  
  
```  
SELECT backup_size/compressed_backup_size FROM msdb..backupset;  
```  
  
 A taxa de compactação de um backup compactado depende dos dados que foram compactados. Uma variedade de fatores pode impactar na taxa de compactação obtida. Os principais fatores incluem:  
  
-   O tipo de dados.  
  
     Os dados de caractere compactam mais do que outros tipos de dados.  
  
-   A consistência dos dados entre as linhas em uma página.  
  
     Normalmente, se uma página contém várias linhas com um campo contendo o mesmo valor, poderá ocorrer uma compactação significativa para esse valor. Por outro lado, para um banco de dados que contém dados aleatórios ou contém somente uma grande linha por página, um backup compactado pode ser tão grande quanto um backup não compactado.  
  
-   Se os dados são criptografados.  
  
     A compactação de dados criptografados é significativamente menor do que a compactação de dados equivalentes não criptografados. Se criptografia transparente de dados for usada para criptografar um banco de dados inteiro, a compactação de backup talvez não reduza muito o tamanho, se reduzir.  
  
-   Se o banco de dados é compactado.  
  
     Se o banco de dados for compactado, a compactação de backups poderá não reduzir muito o seu tamanho.  
  
  
##  <a name="Allocation"></a> Alocação de espaço para o arquivo de backup  
 Para backups compactados, o tamanho do arquivo de backup final depende de como os dados são compactáveis e isto é desconhecido antes da conclusão da operação de backup.  Portanto, por padrão, ao fazer backup de um banco de dados usando compactação, o Mecanismo de Banco de Dados usa um algoritmo de pré-alocação para o arquivo de backup. Este algoritmo pré-aloca um percentual predefinido do tamanho do banco de dados para o arquivo de backup. Se for necessário mais espaço durante a operação de backup, o Mecanismo de Banco de Dados crescerá o arquivo. Se o tamanho final for menor que o espaço alocado, no final da operação de backup, o Mecanismo de Banco de Dados reduzirá o arquivo para o tamanho final real do backup.  
  
 Para permitir que o arquivo de backup somente cresça conforme o necessário para alcançar seu tamanho final, use o sinalizador de rastreamento 3042. O sinalizador de rastreamento 3042 faz a operação de backup ignorar o algoritmo padrão de pré-alocação da compactação de backup. Este sinalizador de rastreamento será útil se você precisar salvar em espaço alocando somente o tamanho real necessário para o backup compactado. Porém, usar este sinalizador de rastreamento pode causar uma pequena penalidade de desempenho (um possível aumento na duração da operação de backup).  
  
##  <a name="RelatedTasks"></a> Tarefas relacionadas  
  
-   [Configurar compactação de backup &#40;SQL Server&#41;](backup-compression-sql-server.md)  
  
-   [Exibir ou configurar a opção de configuração de servidor backup compression default](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
-   [Usar o Resource Governor para limitar o uso de CPU por meio de compactação de backup &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)  
  
-   [DBCC TRACEON &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-transact-sql)  
  
-   [DBCC TRACEOFF &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceoff-transact-sql)  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral do backup &#40;SQL Server&#41;](backup-overview-sql-server.md)   
 [Sinalizadores de rastreamento &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql)  
  
  
