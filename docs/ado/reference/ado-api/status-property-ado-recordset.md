---
title: A propriedade de status (conjunto de registros ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset15::GetStatus
- Recordset15::Status
helpviewer_keywords:
- Status property [ADO Recordset]
ms.assetid: 41d70d89-880f-4850-9d17-19d9790cc8eb
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 819b8e0d1c1716fd630aefc1622d7c08dcc4da73
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35282075"
---
# <a name="status-property-ado-recordset"></a>Propriedade de status (conjunto de registros ADO)
Indica o status de registro atual em relação a atualizações em lotes ou outras operações em massa.  
  
## <a name="return-value"></a>Valor retornado  
 Retorna a soma de uma ou mais [RecordStatusEnum](../../../ado/reference/ado-api/recordstatusenum.md) valores.  
  
## <a name="remarks"></a>Remarks  
 Use o **Status** propriedade para ver as alterações que estão pendentes para os registros modificados durante a atualização em lotes. Você também pode usar o **Status** propriedades para exibir o status dos registros que falham durante as operações em massa, como quando você chama o [Resync](../../../ado/reference/ado-api/resync-method.md), [UpdateBatch](../../../ado/reference/ado-api/updatebatch-method.md), ou [CancelBatch](../../../ado/reference/ado-api/cancelbatch-method-ado.md) métodos em um [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) de objeto, ou definir o [filtro](../../../ado/reference/ado-api/filter-property.md) propriedade em uma **Recordset** objeto para uma matriz de indicadores. Com essa propriedade, você pode determinar como um determinado registro falha e resolvê-lo adequadamente.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo da propriedade status (conjunto de registros) (VB)](../../../ado/reference/ado-api/status-property-example-recordset-vb.md)   
 [Exemplo da propriedade Status (VC++)](../../../ado/reference/ado-api/status-property-example-vc.md)   
