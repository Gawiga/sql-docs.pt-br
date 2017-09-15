---
title: "Compatibilidade com versões anteriores de tipos de dados C | Microsoft Docs"
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
- backward compatibility [ODBC], C data types
- compatibility [ODBC], C data types
- data types [ODBC], backward compatibility
- C data types [ODBC], backward compatibility
ms.assetid: b1453a65-ae03-4061-b0cf-a8434d8bc40b
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 24d0c05a7410a3db37718ebaa667abbb01072796
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="backward-compatibility-of-c-data-types"></a>Compatibilidade com versões anteriores de tipos de dados C
SQL_C_SHORT, SQL_C_LONG e SQL_C_TINYINT foram substituídos no ODBC por tipos assinados e não assinados: SQL_C_SSHORT e SQL_C_USHORT, SQL_C_SLONG e SQL_C_ULONG e SQL_C_STINYINT e SQL_C_UTINYINT. Um ODBC 3*. x* driver deve funcionar com ODBC 2.* x* aplicativos devem oferecer suporte a SQL_C_SHORT, SQL_C_LONG e SQL_C_TINYINT, porque quando eles são chamados, o Gerenciador de Driver passa-los por meio do driver.
