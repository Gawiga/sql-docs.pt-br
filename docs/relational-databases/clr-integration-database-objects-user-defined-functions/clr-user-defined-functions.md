---
title: "Funções CLR definidas pelo usuário | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: clr
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- building database objects [CLR integration], user-defined functions
- functions [CLR integration]
- common language runtime [SQL Server], user-defined functions
- database objects [CLR integration], user-defined functions
- user-defined functions [CLR integration]
ms.assetid: 6f7491f1-9a46-4146-ae09-056248634de2
caps.latest.revision: "46"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 6e719f6920cc67cc0b239981de33b22c87c96992
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="clr-user-defined-functions"></a>Funções CLR definidas pelo usuário
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]Funções definidas pelo usuário são rotinas que podem assumir parâmetros, executar cálculos ou outras ações e retornar um resultado. A partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], é possível escrever funções definidas pelo usuário em qualquer linguagem de programação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework, como o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET ou o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#.  
  
 Há dois tipos de funções: escalar, que retorna um único valor, e com valor de tabela, que retorna um conjunto de linhas.  
  
 A tabela a seguir lista os tópicos desta seção.  
  
 [Funções de valor escalar do CLR](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-scalar-valued-functions.md)  
 Abrange requisitos de implementação e exemplos de funções com valor escalar.  
  
 [Funções com valor de tabela do CLR](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-table-valued-functions.md)  
 Aborda como implementar e usar funções com valor de tabela (TVFs), além das diferenças entre TVFs CLR e [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
 [Agregações do CLR definidas pelo usuário](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md)  
 Descreve como implementar e usar agregações definidas pelo usuário.  
  
## <a name="see-also"></a>Consulte também  
 [Funções definidas pelo usuário](../../relational-databases/user-defined-functions/user-defined-functions.md)  
  
  