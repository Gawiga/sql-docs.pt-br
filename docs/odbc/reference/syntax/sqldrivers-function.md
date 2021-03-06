---
title: Função SQLDrivers | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
apiname:
- SQLDrivers
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLDrivers
helpviewer_keywords:
- SQLDrivers function [ODBC]
ms.assetid: 6b5b7514-e9cb-4cfd-8b7a-ab51dfab9efa
caps.latest.revision: 23
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: ce9fa521b4084ce61dec795ac7462504178b6b37
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32920711"
---
# <a name="sqldrivers-function"></a>Função SQLDrivers
**Conformidade**  
 Versão introduzidas: Conformidade de padrões 2.0 ODBC: ODBC  
  
 **Resumo**  
 **SQLDrivers** lista palavras-chave de atributo de driver e descrições de driver. Essa função é implementada somente pelo Gerenciador de Driver.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
SQLRETURN SQLDrivers(  
     SQLHENV         EnvironmentHandle,  
     SQLUSMALLINT    Direction,  
     SQLCHAR *       DriverDescription,  
     SQLSMALLINT     BufferLength1,  
     SQLSMALLINT *   DescriptionLengthPtr,  
     SQLCHAR *       DriverAttributes,  
     SQLSMALLINT     BufferLength2,  
     SQLSMALLINT *   AttributesLengthPtr);  
```  
  
## <a name="arguments"></a>Argumentos  
 *EnvironmentHandle*  
 [Entrada] Identificador de ambiente.  
  
 *Direção*  
 [Entrada] Determina se o Gerenciador de Driver busca a descrição do driver Avançar na lista (SQL_FETCH_NEXT) ou se a pesquisa começa desde o início da lista (SQL_FETCH_FIRST).  
  
 *DriverDescription*  
 [Saída] Ponteiro para um buffer no qual retornar a descrição do driver.  
  
 Se *DriverDescription* for NULL, *DescriptionLengthPtr* ainda retornará o número total de caracteres (excluindo o caractere null de terminação para dados de caractere) disponíveis para retornar o buffer apontado pelo *DriverDescription*.  
  
 *BufferLength1*  
 [Entrada] Comprimento do **DriverDescription* buffer, em caracteres.  
  
 *DescriptionLengthPtr*  
 [Saída] Ponteiro para um buffer no qual retornar o número total de caracteres (excluindo o caractere null de terminação) disponíveis para retornar em \* *DriverDescription*. Se o número de caracteres disponíveis para retornar for maior que ou igual a *BufferLength1*, a descrição do driver em \* *DriverDescription* será truncado para  *BufferLength1* menos o comprimento de um caractere null de terminação.  
  
 *DriverAttributes*  
 [Saída] Ponteiro para um buffer no qual retornar a lista de pares de valor de atributo de driver (consulte "Comentários").  
  
 Se *DriverAttributes* for NULL, *AttributesLengthPtr* ainda retornará o número total de bytes (excluindo o caractere null de terminação para dados de caractere) disponível no buffer de retorno apontada pelo *DriverAttributes*.  
  
 *BufferLength2*  
 [Entrada] Comprimento do \* *DriverAttributes* buffer, em caracteres. Se o  *\*DriverDescription* valor é uma cadeia de caracteres Unicode (ao chamar **SQLDriversW**), o *BufferLength* argumento deve ser um número par.  
  
 *AttributesLengthPtr*  
 [Saída] Ponteiro para um buffer no qual retornar o número total de bytes (excluindo o byte nulo de terminação) disponíveis para retornar em \* *DriverAttributes*. Se o número de bytes disponíveis para retornar é maior que ou igual a *BufferLength2*, a lista de pares de valor de atributo no \* *DriverAttributes* será truncado para  *BufferLength2* menos o comprimento do caractere null de terminação.  
  
## <a name="returns"></a>Retorna  
 SQL_SUCCESS, SQL_SUCCESS_WITH_INFO, SQL_NO_DATA, SQL_ERROR ou SQL_INVALID_HANDLE.  
  
## <a name="diagnostics"></a>diagnóstico  
 Quando **SQLDrivers** retorna SQL_ERROR ou SQL_SUCCESS_WITH_INFO, um valor SQLSTATE associado pode ser obtido chamando **SQLGetDiagRec** com um *HandleType* de SQL_HANDLE_ENV e um *tratar* de *EnvironmentHandle*. A tabela a seguir lista os valores SQLSTATE normalmente retornados por **SQLDrivers** e explica cada uma no contexto dessa função; a notação "(DM)" precede as descrições de SQLSTATEs retornados pelo Gerenciador de Driver. O código de retorno associado a cada valor SQLSTATE é SQL_ERROR, a menos que indicado em contrário.  
  
|SQLSTATE|Erro|Description|  
|--------------|-----------|-----------------|  
|01000|Aviso geral|(DM) mensagem informativa do Gerenciador de Driver específico. (A função retornará SQL_SUCCESS_WITH_INFO.)|  
|01004|Dados de cadeia de caracteres truncados à direita|(DM) o buffer \* *DriverDescription* não era grande o suficiente para retornar a descrição completa do driver. Portanto, a descrição foi truncada. O comprimento da descrição do driver concluído é retornado no \* *DescriptionLengthPtr*. (A função retornará SQL_SUCCESS_WITH_INFO.)<br /><br /> (DM) o buffer \* *DriverAttributes* não era grande o suficiente para retornar a lista completa de pares de valor de atributo. Portanto, a lista foi truncada. O comprimento da lista completo de pares de valor de atributo é retornado em **AttributesLengthPtr*. (A função retornará SQL_SUCCESS_WITH_INFO.)|  
|HY000|Erro geral|Ocorreu um erro para o qual não houve nenhuma SQLSTATE específico e para o qual nenhuma SQLSTATE específicos de implementação foi definida. A mensagem de erro retornada pelo **SQLGetDiagRec** no  *\*MessageText* buffer descreve o erro e sua causa.|  
|HY001|Erro de alocação de memória|O Gerenciador de Driver (DM) não pôde alocar a memória necessária para dar suporte a execução ou a conclusão da função.|  
|HY010|Erro de sequência de função|(DM) **SQLExecute**, **SQLExecDirect**, ou **SQLMoreResults** foi chamado para o *StatementHandle* e retornado SQL_PARAM_DATA_ DISPONÍVEL. Essa função foi chamada antes de recuperação para todos os parâmetros de fluxo de dados.|  
|HY013|Erro de gerenciamento de memória|Não foi possível processar a chamada de função porque os objetos de memória subjacente não podem ser acessados, possivelmente devido a condições de memória insuficiente.|  
|HY090|Comprimento de buffer ou cadeia de caracteres inválido|(DM) o valor especificado para o argumento *BufferLength1* era menor do que 0.<br /><br /> (DM) o valor especificado para o argumento *BufferLength2* foi menor que 0 ou igual a 1.|  
|HY103|Código de recuperação inválido|(DM) o valor especificado para o argumento *direção* não era igual a SQL_FETCH_FIRST ou SQL_FETCH_NEXT.|  
|HY117|Conexão está suspenso devido ao estado de transação desconhecido. Somente Desconecte e funções de somente leitura são permitidas.|(DM) para obter mais informações sobre o estado suspenso, consulte [função SQLEndTran](../../../odbc/reference/syntax/sqlendtran-function.md).|  
  
## <a name="comments"></a>Comentários  
 **SQLDrivers** retorna a descrição do driver no \* *DriverDescription* buffer. Retorna informações adicionais sobre o driver no \* *DriverAttributes* buffer como uma lista de pares de valor de palavra-chave. Todas as palavras-chave listadas nas informações do sistema para drivers serão retornados para todos os drivers, exceto para **CreateDSN**, que é usado para solicitar a criação de fontes de dados e, portanto, é opcional. Cada par é encerrada com um byte nulo e a lista completa é encerrada com um byte nulo (ou seja, dois bytes nulos marcar o fim da lista). Por exemplo, um driver de arquivo usando a sintaxe de C pode retornar a lista de atributos ("\0" representa um caractere nulo) a seguir:  
  
```  
FileUsage=1\0FileExtns=*.dbf\0\0  
```  
  
 Se \* *DriverAttributes* é não grande o suficiente para manter toda a lista, a lista será truncada, **SQLDrivers** retorna SQLSTATE 01004 (dados truncados) e o comprimento da lista (excluindo o byte final de terminação nula) é retornado em **AttributesLengthPtr*.  
  
 Palavras-chave de atributo de driver são adicionadas das informações do sistema quando o driver está instalado. Para obter mais informações, consulte [instalar componentes de ODBC](../../../odbc/reference/install/installing-odbc-components.md).  
  
 Um aplicativo pode chamar **SQLDrivers** várias vezes para recuperar todas as descrições de driver. O Gerenciador de Driver recupera informações das informações do sistema. Quando não houver nenhuma mais descrições de driver, **SQLDrivers** retorna SQL_NO_DATA. Se **SQLDrivers** é chamado com SQL_FETCH_NEXT imediatamente após ele retornar SQL_NO_DATA, ele retorna a descrição do driver primeiro. Para obter informações sobre como um aplicativo usa as informações retornadas por **SQLDrivers**, consulte [escolhendo uma fonte de dados ou Driver](../../../odbc/reference/develop-app/choosing-a-data-source-or-driver.md).  
  
 Se SQL_FETCH_NEXT for passado para **SQLDrivers** a primeira vez que ele é chamado, **SQLDrivers** retorna o primeiro nome de fonte de dados.  
  
 Porque **SQLDrivers** é implementado no Gerenciador de Driver, há suporte para todos os drivers, independentemente de conformidade com padrões de um driver específico.  
  
## <a name="related-functions"></a>Funções relacionadas  
  
|Para obter informações sobre|Consulte|  
|---------------------------|---------|  
|Descobrindo e listar os valores necessários para se conectar a uma fonte de dados|[Função SQLBrowseConnect](../../../odbc/reference/syntax/sqlbrowseconnect-function.md)|  
|Conectando-se a uma fonte de dados|[Função SQLConnect](../../../odbc/reference/syntax/sqlconnect-function.md)|  
|Retornando nomes de fonte de dados|[Função SQLDataSources](../../../odbc/reference/syntax/sqldatasources-function.md)|  
|Conectando a uma fonte de dados usando uma caixa de diálogo ou cadeia de caracteres de conexão|[Função SQLDriverConnect](../../../odbc/reference/syntax/sqldriverconnect-function.md)|  
  
## <a name="see-also"></a>Consulte também  
 [Referência de API de ODBC](../../../odbc/reference/syntax/odbc-api-reference.md)   
 [Arquivos de cabeçalho ODBC](../../../odbc/reference/install/odbc-header-files.md)
