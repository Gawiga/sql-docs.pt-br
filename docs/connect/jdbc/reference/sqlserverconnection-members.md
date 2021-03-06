---
title: Membros de SQLServerConnection | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 3115a533-756b-4c78-aee9-4ba7253c85e0
caps.latest.revision: 25
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 5a0d90e2b6b6c0faaa1dd8d6376b11b95a2ad523
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32852831"
---
# <a name="sqlserverconnection-members"></a>Membros de SQLServerConnection
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  As tabelas a seguir listam os membros expostos pelo [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) classe.  
  
## <a name="constructors"></a>Construtores  
 Nenhuma.  
  
## <a name="fields"></a>Campos  
  
|Nome|Description|  
|----------|-----------------|  
|[TRANSACTION_SNAPSHOT](../../../connect/jdbc/reference/transaction-snapshot-field-sqlserverconnection.md)|Usado para especificar o nível de isolamento da transação de instantâneo.|  
  
## <a name="inherited-fields"></a>Campos herdados  
  
|Classe herdada de:|Description|  
|---------------------------|-----------------|  
|java.sql.Connection|TRANSACTION_NONE, TRANSACTION_READ_COMMITTED, TRANSACTION_READ_UNCOMMITTED, TRANSACTION_REPEATABLE_READ, TRANSACTION_SERIALIZABLE|  
  
## <a name="methods"></a>Métodos  
  
|Nome|Description|  
|----------|-----------------|  
|[clearWarnings](../../../connect/jdbc/reference/clearwarnings-method-sqlserverconnection.md)|Limpa todos os avisos relatados para esse [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto.|  
|[close](../../../connect/jdbc/reference/close-method-sqlserverconnection.md)|Libera o banco de dados para este [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto e recursos do JDBC imediatamente em vez de aguardar que eles sejam liberados automaticamente.|  
|[closeUnreferencedPreparedStatementHandles](../../../connect/jdbc/reference/closeunreferencedpreparedstatementhandles-method-sqlserverconnection.md)|Força a cancelar-preparar solicitações para qualquer instrução preparada com descartados pendentes a serem executados.| 
|[commit](../../../connect/jdbc/reference/commit-method-sqlserverconnection.md)|Faz com que todas as alterações feitas desde a confirmação ou reversão anterior permanentes e libera qualquer bloqueio de banco de dados que é mantido por este [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto.|  
|[createBlob](../../../connect/jdbc/reference/createblob-method-sqlserverconnection.md)|Cria um **Java.SQL** objeto sem dados.|  
|[createClob](../../../connect/jdbc/reference/createclob-method-sqlserverconnection.md)|Cria um **CLOB** objeto sem dados.|  
|[createNClob](../../../connect/jdbc/reference/createnclob-method-sqlserverconnection.md)|Cria um **Java.SQL. NCLOB** objeto sem dados.|  
|[createStatement](../../../connect/jdbc/reference/createstatement-method-sqlserverconnection.md)|Cria um objeto [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md) para enviar instruções SQL ao banco de dados.|  
|[createSQLXML](../../../connect/jdbc/reference/createsqlxml-method-sqlserverconnection.md)|Cria um **Java.SQL** objeto sem dados.|  
|[getAutoCommit](../../../connect/jdbc/reference/getautocommit-method-sqlserverconnection.md)|Recupera o modo de confirmação automática atual para este [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto.|  
|[getCatalog](../../../connect/jdbc/reference/getcatalog-method-sqlserverconnection.md)|Recupera o nome do catálogo atual para este [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto.|  
|[Método getClientConnectionID &#40;SQLServerConnection&#41;](../../../connect/jdbc/reference/getclientconnectionid-method-sqlserverconnection.md)|Obtém a ID de conexão da última tentativa de conexão, seja a tentativa bem-sucedida ou não.|  
|[getClientInfo](../../../connect/jdbc/reference/getclientinfo-method-sqlserverconnection.md)|Recupera informações relativas às propriedades de informações de cliente que têm o suporte do driver JDBC.|  
|[getDisableStatementPooling](../../../connect/jdbc/reference/getdisablestatementpooling-method-sqlserverconnection.md)|Retorna o valor de **disableStatementPooling** propriedade de conexão. Essa configuração controla se o pooling de instrução está habilitada ou não para essa conexão.|
|[getDiscardedServerPreparedStatementCount](../../../connect/jdbc/reference/getdiscardedserverpreparedstatementcount-method-sqlserverconnection.md)|Retorna o número de pendente no momento preparada instrução unprepare ações.|
|[getEnablePrepareOnFirstPreparedStatementCall](../../../connect/jdbc/reference/getenableprepareonfirstpreparedstatementcall-method-sqlserverconnection.md)|Retorna o valor de **enablePrepareOnFirstPreparedStatementCall** propriedade de conexão.|
|[getHoldability](../../../connect/jdbc/reference/getholdability-method-sqlserverconnection.md)|Recupera a suspensão atual de [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) objetos que são criados usando esse [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto.|  
|[getMetaData](../../../connect/jdbc/reference/getmetadata-method-sqlserverconnection.md)|Recupera um [SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md) que contém metadados sobre o banco de dados ao qual este objeto [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto representa uma conexão.|  
|[getServerPreparedStatementDiscardThreshold](../../../connect/jdbc/reference/getserverpreparedstatementdiscardthreshold-method-sqlserverconnection.md)|Retorna o valor de **serverPreparedStatementDiscardThreshold** propriedade de conexão.|  
|[getStatementHandleCacheEntryCount](../../../connect/jdbc/reference/getstatementhandlecacheentrycount-method-sqlserverconnection.md)|Retorna o número atual de identificadores de instrução preparada em pool.|  
|[getStatementPoolingCacheSize](../../../connect/jdbc/reference/getstatementpoolingcachesize-method-sqlserverconnection.md)|Retorna o tamanho do cache de instrução preparada para esta conexão.|  
|[getTransactionIsolation](../../../connect/jdbc/reference/gettransactionisolation-method-sqlserverconnection.md)|Recupera o nível de isolamento da transação atual para este [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto.|  
|[getTypeMap](../../../connect/jdbc/reference/gettypemap-method-sqlserverconnection.md)|Recupera o objeto de mapa que está associado a essa [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto.|  
|[getWarnings](../../../connect/jdbc/reference/getwarnings-method-sqlserverconnection.md)|Recupera o primeiro aviso relatado por chamadas nisso [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto.|  
|[isClosed](../../../connect/jdbc/reference/isclosed-method-sqlserverconnection.md)|Indica se este [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) o objeto foi fechado.|  
|[isReadOnly](../../../connect/jdbc/reference/isreadonly-method-sqlserverconnection.md)|Indica se este [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto está no modo somente leitura.|  
|[isStatementPoolingEnabled](../../../connect/jdbc/reference/isstatementpoolingenabled-method-sqlserverconnection.md)|Retorna se o pooling de instrução está habilitada ou não para essa conexão.|  
|[isValid](../../../connect/jdbc/reference/isvalid-method-sqlserverconnection.md)|Indica se este [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto não foi fechado e ainda é válido.|  
|[nativeSQL](../../../connect/jdbc/reference/nativesql-method-sqlserverconnection.md)|Converte a instrução SQL fornecida na gramática SQL nativa do servidor de banco de dados.|  
|[prepareCall](../../../connect/jdbc/reference/preparecall-method-sqlserverconnection.md)|Cria um [SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md) objeto para chamar procedimentos armazenado do banco de dados.|  
|[prepareStatement](../../../connect/jdbc/reference/preparestatement-method-sqlserverconnection.md)|Cria um [SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) parametrizadas de objeto para enviar instruções SQL para o banco de dados.|  
|[releaseSavepoint](../../../connect/jdbc/reference/releasesavepoint-method-sqlserverconnection.md)|Remove o [SQLServerSavepoint](../../../connect/jdbc/reference/sqlserversavepoint-class.md) objeto da transação atual.|  
|[Reversão](../../../connect/jdbc/reference/rollback-method-sqlserverconnection.md)|Desfaz todas as alterações feitas na transação atual e libera todos os bloqueios de banco de dados atualmente mantidos por este [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto.|  
|[setAutoCommit](../../../connect/jdbc/reference/setautocommit-method-sqlserverconnection.md)|Define o modo de confirmação automática para este [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto para o estado especificado.|  
|[setCatalog](../../../connect/jdbc/reference/setcatalog-method-sqlserverconnection.md)|Define o nome de catálogo especificado para selecionar um subespaço deste [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) banco de dados do objeto no qual trabalhar.|  
|[setClientInfo](../../../connect/jdbc/reference/setclientinfo-method-sqlserverconnection.md)|Define o valor das propriedades de informações de cliente.|  
|[setDisableStatementPooling](../../../connect/jdbc/reference/setdisablestatementpooling-method-sqlserverconnection.md)|Define o pooling de instrução como true ou false.|  
|[setEnablePrepareOnFirstPreparedStatementCall](../../../connect/jdbc/reference/setenableprepareonfirstpreparedstatementcall-method-sqlserverconnection.md)|Especifica o novo valor da **enablePrepareOnFirstPreparedStatementCall** propriedade de conexão.|  
|[setHoldability](../../../connect/jdbc/reference/setholdability-method-sqlserverconnection.md)|Altera a colocação em espera de [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) objetos que são criados usando esse [SQLServerSavepoint](../../../connect/jdbc/reference/sqlserversavepoint-class.md) objeto para a colocação em espera fornecida.|  
|[setReadOnly](../../../connect/jdbc/reference/setreadonly-method-sqlserverconnection.md)|Coloca este [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto no modo somente leitura como uma dica para o driver JDBC para habilitar otimizações de banco de dados.|  
|[setSavepoint](../../../connect/jdbc/reference/setsavepoint-method-sqlserverconnection.md)|Cria um ponto de salvamento sem nome na transação atual e retorna o novo [SQLServerSavepoint](../../../connect/jdbc/reference/sqlserversavepoint-class.md) objeto que o representa.|  
|[setServerPreparedStatementDiscardThreshold](../../../connect/jdbc/reference/setserverpreparedstatementdiscardthreshold-method-sqlserverconnection.md)|Define o novo valor da **serverPreparedStatementDiscardThreshold** propriedade de conexão.|  
|[setStatementPoolingCacheSize](../../../connect/jdbc/reference/setstatementpoolingcachesize-method-sqlserverconnection.md)|Define o tamanho do cache de instrução preparada para esta conexão.|  
|[setTransactionIsolation](../../../connect/jdbc/reference/settransactionisolation-method-sqlserverconnection.md)|Tenta alterar o nível de isolamento da transação para esse [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto para um dado.|  
|[setTypeMap](../../../connect/jdbc/reference/settypemap-method-sqlserverconnection.md)|Instala o objeto TypeMap fornecido como o mapa de tipo para este [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) objeto.|  
  
## <a name="inherited-methods"></a>Métodos herdados  
  
|Classe herdada de:|Métodos|  
|---------------------------|-------------|  
|java.lang.Object|clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait|  
|java.lang.Wrapper|isWrapperFor, unwrap|  
  
## <a name="see-also"></a>Consulte também  
 [Classe SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
