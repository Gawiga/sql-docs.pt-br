---
title: Saltar para um registro | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- record jumping [ADO]
- jumping to record [ADO]
ms.assetid: 6caf6299-2eea-4d34-9b0e-b75aab07b740
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 4da5573ef2f96947f9d8660d8d3461df879398e4
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35272025"
---
# <a name="jumping-to-a-record"></a>Saltar para um registro
O [mover](../../../ado/reference/ado-api/move-method-ado.md) método permite que você mova Avançar ou retroceder no **registros** um número especificado de registros usando a seguinte sintaxe:  
  
```  
oRs.Move NumRecords, Start  
```  
  
## <a name="remarks"></a>Remarks  
 O **mover** método tem suporte em todos os **registros** objetos.  
  
 Se o *NumRecords* argumento for maior que zero, a posição do registro atual avança (até o fim do **registros**). Se *NumRecords* é menor que zero, a posição atual do registro recua (no início do **registros**).  
  
 Se o **mover** chamada moverá a posição atual do registro para um ponto antes do primeiro registro, o ADO define o registro atual para a posição antes do primeiro registro no **registros** (**BOF** é **True**). Tentativa de mover para trás quando o **BOF** propriedade já está **True** gera um erro.  
  
 Se o **mover** chamada moverá a posição atual do registro para um ponto após o último registro, ADO define o registro atual para a posição após o último registro de **Recordset** (**EOF** é **True**). Tentativa de mover quando encaminhar o **EOF** propriedade já está **True** gera um erro.  
  
 Chamando o **mover** método de vazio **registros** objeto gera um erro.  
  
 Se você passar um indicador no *iniciar* argumento, a movimentação é relativo ao registro com esse indicador, supondo que o **registros** objeto dá suporte a indicadores. Um indicador é obtido usando o [indicador](../../../ado/reference/ado-api/bookmark-property-ado.md) propriedade. Se não for especificado, a movimentação é relativo ao registro atual.  
  
 Se você estiver usando o **CacheSize** propriedade em cache localmente registros do provedor, passando um *NumRecords* argumento que move a posição atual do registro fora do grupo atual de registros armazenado em cache força o ADO para recuperar um novo grupo de registros, a partir do registro de destino. O **CacheSize** propriedade determina o tamanho do grupo recuperado recentemente, e o registro de destino é o primeiro registro recuperado.
