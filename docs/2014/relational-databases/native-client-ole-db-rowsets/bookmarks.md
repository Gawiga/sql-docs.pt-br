---
title: Indicadores | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- bookmarks [OLE DB]
- SQL Server Native Client OLE DB provider, bookmarks
- rowsets [OLE DB], bookmarks
- OLE DB rowsets, bookmarks
ms.assetid: 7d9076f2-bf9c-452e-b816-70371a0c1644
caps.latest.revision: 30
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d09cd5421d34f1f84d0b61423ed898e7249cffa9
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37417135"
---
# <a name="bookmarks"></a>Indicadores
  Os indicadores permitem que os consumidores voltem rapidamente para uma linha. Com os indicadores, os consumidores podem acessar linhas aleatoriamente com base no valor do indicador. A coluna do indicador é a coluna 0 no conjunto de linhas. O consumidor define o valor de campo dwFrag da estrutura associada como DBCOLUMNSINFO_ISBOOKMARK para indicar que a coluna é usada como um indicador. O consumidor também define a propriedade DBPROP_BOOKMARKS do conjunto de linhas como VARIANT_TRUE. Isso permite que a coluna 0 esteja presente no conjunto de linhas. O **irowsetlocate:: Getrowsat** método é usado para buscar linhas, iniciando com a linha especificada como um deslocamento de um indicador.  
  
## <a name="see-also"></a>Consulte também  
 [Conjuntos de linhas](rowsets.md)  
  
  
