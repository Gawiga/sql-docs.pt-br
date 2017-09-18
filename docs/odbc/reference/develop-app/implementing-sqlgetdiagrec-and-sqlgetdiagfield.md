---
title: Implementando SQLGetDiagRec e SQLGetDiagField | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- diagnostic information [ODBC], SqlGetDiagField
- SQLGetDiagField function [ODBC], and SQLGetDiagRec
- SQLGetDiagRec function [ODBC], and SQLGetDiagField
- diagnostic information [ODBC], SqlGetDiagRec
- retrieving diagnostic information [ODBC]
ms.assetid: 11ba1857-b533-4517-8131-a2a8a0154a0a
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 463ddfe552c94a9e90ceb2a24f8061674955979d
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="implementing-sqlgetdiagrec-and-sqlgetdiagfield"></a>Implementando SQLGetDiagRec e SQLGetDiagField
**SQLGetDiagRec** e **SQLGetDiagField** são implementados pelo Gerenciador de Driver e cada driver. O Gerenciador de Driver e cada driver mantenham registros de diagnóstico para cada ambiente, a conexão, a instrução e o identificador do descritor e liberará esses registros somente quando outra função seja chamada com que o identificador ou o identificador é liberado.  
  
 Embora o Gerenciador de Driver e cada driver devem determinar primeiro registro status de acordo com as classificações no [sequência de registros de Status](../../../odbc/reference/develop-app/sequence-of-status-records.md), o Gerenciador de Driver determina a sequência de final de registros.  
  
 **SQLGetDiagRec** e **SQLGetDiagField** não publique os registros de diagnóstico sobre eles.  
  
 Esta seção contém os tópicos a seguir.  
  
-   [Regras de tratamento de diagnóstico](../../../odbc/reference/develop-app/diagnostic-handling-rules.md)  
  
-   [Função do Gerenciador do Driver](../../../odbc/reference/develop-app/role-of-the-driver-manager.md)  
  
-   [Função do driver](../../../odbc/reference/develop-app/role-of-the-driver.md)