---
title: "Propriedade de direção | Microsoft Docs"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- _Parameter::Direction
helpviewer_keywords:
- Direction property
ms.assetid: d5732578-3434-4dcd-a9f7-db1abd1b3b94
caps.latest.revision: 14
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 1a81c60a4505e1c5e420583c474109d0d08f4fb6
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="direction-property"></a>Propriedade de direção
Indica se o [parâmetro](../../../ado/reference/ado-api/parameter-object.md) representa um parâmetro de entrada, um parâmetro de saída, uma entrada e um parâmetro de saída, ou se o parâmetro é o valor de retorno de um procedimento armazenado.  
  
## <a name="settings-and-return-values"></a>Configurações e valores de retorno  
 Define ou retorna um [ParameterDirectionEnum](../../../ado/reference/ado-api/parameterdirectionenum.md) valor.  
  
## <a name="remarks"></a>Comentários  
 Use o **direção** propriedade para especificar como um parâmetro é passado para ou de um procedimento. O **direção** propriedade é somente leitura; Isso permite trabalhar com provedores que não retornam informações ou para definir essas informações quando você não deseja ADO para fazer uma chamada adicional para o provedor para recuperar informações de parâmetro.  
  
 Nem todos os provedores podem determinar a direção dos parâmetros em procedimentos armazenados. Nesses casos, você deve definir o **direção** propriedade antes de você executar a consulta.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Parameter](../../../ado/reference/ado-api/parameter-object.md)  
  
## <a name="see-also"></a>Consulte também  
 [ActiveConnection CommandText, CommandTimeout, CommandType, tamanho e exemplo de propriedades de direção (VB)](../../../ado/reference/ado-api/activeconnection-commandtext-commandtimeout-commandtype-size-example-vb.md)   
 [ActiveConnection CommandText, CommandTimeout, CommandType, tamanho e exemplo de propriedades de direção (VC + +)](../../../ado/reference/ado-api/activeconnection-commandtext-commandtimeout-commandtype-size-example-vc.md)   
 [ActiveConnection CommandText, CommandTimeout, CommandType, tamanho e exemplo de propriedades de direção (JScript)](../../../ado/reference/ado-api/activeconnection-commandtext-timeout-type-size-example-jscript.md)
