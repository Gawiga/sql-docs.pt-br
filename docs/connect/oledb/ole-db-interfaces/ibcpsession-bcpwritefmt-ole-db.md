---
title: 'Ibcpsession:: Bcpwritefmt (OLE DB) | Microsoft Docs'
description: 'Usando ibcpsession:: Bcpwritefmt para salvar os arquivos de formato em formato de texto ou xml (OLE DB)'
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: oledb|ole-db-interfaces
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IBCPSession::BCPWriteFmt (OLE DB)
apitype: COM
helpviewer_keywords:
- BCPWriteFmt method
author: pmasl
ms.author: pelopes
manager: craigg
ms.openlocfilehash: 2a74157f1c90fbf0ef2c9e1c3e0efe837796b01e
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43030984"
---
# <a name="ibcpsessionbcpwritefmt-ole-db"></a>IBCPSession::BCPWriteFmt (OLE DB)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  Grava informações de formato relativas a cada coluna no arquivo de formato.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
HRESULT BCPWriteFmt(   
      const wchar_t *pwszFormatFile);  
```  
  
## <a name="remarks"></a>Remarks  
 O arquivo de formato especifica o formato de dados de um arquivo de dados criado por cópia em massa. As chamadas aos métodos [IBCPSession::BCPColumns](../../oledb/ole-db-interfaces/ibcpsession-bcpcolumns-ole-db.md) e [IBCPSession::BCPColFmt](../../oledb/ole-db-interfaces/ibcpsession-bcpcolfmt-ole-db.md) definem o formato do arquivo de dados. O método **BCPWriteFmt** salva essa definição no arquivo referenciado pelo argumento pwszFormatFile.  
  
 O método **BCPWriteFmt** pode salvar os arquivos de formato em xml ou formato de texto. Isso precisa ser indicado usando a opção de controle BCP_OPTION_XML com o método [IBCPSession::BCPControl](../../oledb/ole-db-interfaces/ibcpsession-bcpcontrol-ole-db.md).  
  
 Para carregar um arquivo de formato salvo, use o método [IBCPSession::BCPReadFmt](../../oledb/ole-db-interfaces/ibcpsession-bcpreadfmt-ole-db.md).  
  
## <a name="arguments"></a>Argumentos  
 *pwszFormatFile*[in]  
 O caminho e o nome do arquivo que contém os valores de formato do arquivo de dados.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 S_OK  
 O método foi bem-sucedido.  
  
 E_FAIL  
 Um erro específico do provedor ocorreu. Para obter informações detalhadas, use a interface [ISQLServerErrorInfo](http://msdn.microsoft.com/library/a8323b5c-686a-4235-a8d2-bda43617b3a1).  
  
 E_OUTOFMEMORY  
 Erro de memória insuficiente.  
  
 E_UNEXPECTED  
 A chamada para o método era inesperada. Por exemplo, o método [IBCPSession::BCPInit](../../oledb/ole-db-interfaces/ibcpsession-bcpinit-ole-db.md) não foi chamado antes desse método.  
  
## <a name="see-also"></a>Consulte Também  
 [IBCPSession &#40;OLE DB&#41;](../../oledb/ole-db-interfaces/ibcpsession-ole-db.md)   
 [Executando operações de cópia em massa](../../oledb/features/performing-bulk-copy-operations.md) 
  
  
