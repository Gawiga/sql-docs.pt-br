---
title: "Método (Java, booleano) updateBoolean | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname: SQLServerResultSet.updateBoolean (java.lang.String, boolean)
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 5fed9ebb-d9a3-4d1a-9212-1057a603c4e5
caps.latest.revision: "8"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 823182c05831c710f98714a7d0fd58c90c81fa01
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2017
---
# <a name="updateboolean-method-javalangstring-boolean"></a>Método updateBoolean (java.lang.String, boolean)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Atualiza a coluna designada com um **booliano** valor, considerando o nome da coluna.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public void updateBoolean(java.lang.String columnName,  
                          boolean x)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *columnName*  
  
 Um **cadeia de caracteres** que contém o nome da coluna.  
  
 *x*  
  
 Um **booliano** valor.  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentários  
 Esse método updateBoolean é especificado pelo método updateBoolean na interface Java.SQL. resultset.  
  
## <a name="see-also"></a>Consulte também  
 [Método updateBoolean &#40; SQLServerResultSet &#41;](../../../connect/jdbc/reference/updateboolean-method-sqlserverresultset.md)   
 [Membros de SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Classe SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
