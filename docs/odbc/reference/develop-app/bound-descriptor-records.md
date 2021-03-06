---
title: Registros de descritor de associado | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- bound descriptor records [ODBC]
- descriptors [ODBC], bound descriptor records
ms.assetid: 55d09344-6682-40f6-b634-036b134ff650
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0ac161220673c32f13c08ab7588c269237b5aa6f
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32907562"
---
# <a name="bound-descriptor-records"></a>Registros de descritor associados
Quando o aplicativo define o campo SQL_DESC_DATA_PTR de um registro de descritor para que ele não contém um valor nulo, o registro será considerado *associado*.  
  
 Se o descritor é um APD, cada registro associado constitui um parâmetro associado. Para parâmetros de entrada, o aplicativo deve associar um parâmetro para cada marcador de parâmetro dinâmico na instrução SQL antes de executar a instrução. Parâmetros de saída, o aplicativo não precisa associar o parâmetro.  
  
 Se o descritor é um descartar, que descreve uma linha de dados do banco de dados, cada registro associado constitui uma coluna associada.
