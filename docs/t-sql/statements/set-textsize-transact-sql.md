---
title: SET TEXTSIZE (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 04/12/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- TEXTSIZE_TSQL
- TEXTSIZE
- SET_TEXTSIZE_TSQL
- SET TEXTSIZE
dev_langs:
- TSQL
helpviewer_keywords:
- SET TEXTSIZE statement
- SELECT statement [SQL Server], text size returned
- size [SQL Server], text and image data
- TEXTSIZE option
- text size returned [SQL Server]
ms.assetid: 787154a6-39a6-4dd6-a6d0-67b4364f95d5
caps.latest.revision: 38
author: CarlRabeler
ms.author: carlrab
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 2473c8b56725ce1298d44912b129acea4d15e2ab
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43093794"
---
# <a name="set-textsize-transact-sql"></a>SET TEXTSIZE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Especifica o tamanho dos dados **varchar(max)**, **nvarchar(max)**, **varbinary(max)**, **text**, **ntext** e **image** retornados por uma instrução SELECT.  
  
> [!IMPORTANT]  
>  Os tipos de dados **ntext**, **text** e **image** serão removidos em uma versão futura do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Evite usar esses tipos de dados em novos trabalhos de desenvolvimento e planeje modificar os aplicativos que os utilizam atualmente. Em vez disso, use **nvarchar(max)**, **varchar(max)** e **varbinary(max)** .  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
SET TEXTSIZE { number }   
```  
  
## <a name="arguments"></a>Argumentos  
 *number*  
 É o tamanho dos dados **varchar(max)**, **nvarchar(max)**, **varbinary(max)**, **text**, **ntext** ou **image** em bytes. *number* é um inteiro com um valor máximo de 2147483647 (2 GB).  Um valor -1 indica um tamanho ilimitado. Um valor 0 redefine o tamanho para o valor padrão de 4 KB.  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client (10.0 e superior) e o Driver ODBC para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] especificam automaticamente `-1` (ilimitado) durante a conexão.  
  
 **Drivers anteriores ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2008:** o driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client e o Provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client (versão 9) para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] definem TEXTSIZE automaticamente como 2147483647 durante a conexão.  
  
## <a name="remarks"></a>Remarks  
 A definição de SET TEXTSIZE afeta a função @@TEXTSIZE.  
  
 A configuração de TEXTSIZE é definida na execução ou em tempo de execução, e não no momento de análise.  
  
## <a name="permissions"></a>Permissões  
 Requer associação à função **pública** .  
  
## <a name="see-also"></a>Consulte Também  
 [@@TEXTSIZE &#40;Transact-SQL&#41;](../../t-sql/functions/textsize-transact-sql.md)   
 [Tipos de dados &#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)   
 [Instruções SET &#40;Transact-SQL&#41;](../../t-sql/statements/set-statements-transact-sql.md)  
  
  
