---
title: IRowsetFastLoad (OLE DB) | Microsoft Docs
description: IRowsetFastLoad (OLE DB)
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: oledb|ole-db-interfaces
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: reference
apitype: COM
helpviewer_keywords:
- IRowsetFastLoad interface
author: pmasl
ms.author: pelopes
manager: craigg
ms.openlocfilehash: cdae651fad5268ca03d863150482e0124c75aa0b
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43017578"
---
# <a name="irowsetfastload-ole-db"></a>IRowsetFastLoad (OLE DB)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  Uma interface **IRowsetFastLoad** expõe o suporte para operações de cópia em massa baseadas em memória do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Driver do OLE DB para consumidores do SQL Server, use a interface para rapidamente adicionar dados a um existente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tabela.  
  
 Se você definir SSPROP_ENABLEFASTLOAD como VARIANT_TRUE para uma sessão, não poderá ler dados de conjuntos de linhas subsequentemente passados como retorno dessa sessão. Quando SSPROP_ENABLEFASTLOAD for definido como VARIANT_TRUE, todos os conjuntos de linhas criados na sessão serão do tipo IRowsetFastLoad. Os conjuntos de linhas IRowsetFastLoad não dão suporte à funcionalidade de fetch de conjuntos de linhas; portanto, os dados desses conjuntos de linhas não podem ser lidos.  
  
## <a name="in-this-section"></a>Nesta seção  
  
|Método|Descrição|  
|------------|-----------------|  
|[IRowsetFastLoad:: Commit &#40;OLE DB&#41;](../../oledb/ole-db-interfaces/irowsetfastload-commit-ole-db.md)|Marca o término de um lote de linhas inseridas e escreve as linhas na tabela [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].|  
|[IRowsetFastLoad:: Insertrow &#40;OLE DB&#41;](../../oledb/ole-db-interfaces/irowsetfastload-insertrow-ole-db.md)|Adiciona uma linha ao conjunto de linhas de cópia em massa.|  
  
## <a name="see-also"></a>Consulte Também  
 [Interfaces &#40;OLE DB&#41;](../../oledb/ole-db-interfaces/oledb-driver-for-sql-server-ole-db-interfaces.md)   
 [Copiar dados em massa usando IRowsetFastLoad &#40;OLE DB&#41;](../../oledb/ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md)   
 [Enviar dados BLOB ao SQL SERVER usando IROWSETFASTLOAD e ISEQUENTIALSTREAM &#40;OLE DB&#41;](../../oledb/ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md)  
  
  
