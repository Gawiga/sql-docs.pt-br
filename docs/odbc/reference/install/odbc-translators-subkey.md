---
title: ODBC tradutores subchave | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: reference
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- translator subkey [ODBC]
- subkeys [ODBC], translator subkey
- registry entries for components [ODBC], translator subkey
ms.assetid: 6b170f1f-e263-4aac-9d49-8d0ca0470ca2
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 547790398258ef250cca0331e468b8834218890e
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2017
---
# <a name="odbc-translators-subkey"></a>ODBC tradutores subchave
Os valores na subchave conversor ODBC listam os tradutores instalados. O formato desses valores é mostrado na tabela a seguir.  
  
|Nome|Tipo de dados|data|  
|----------|---------------|----------|  
|*desc conversor*|REG_SZ|**Instalado**|  
  
 O *conversor desc* nome é definido pelo desenvolvedor do conversor.  
  
 Por exemplo, suponha que um usuário tiver instalado o conversor de página de código do Microsoft® e um ASCII personalizado para o conversor de EBCDIC. Os valores na subchave conversor ODBC podem ser como segue:  
  
```  
MS Code Page Translator: REG_SZ : Installed  
ASCII to EBCDIC: REG_SZ : Installed.  
```
