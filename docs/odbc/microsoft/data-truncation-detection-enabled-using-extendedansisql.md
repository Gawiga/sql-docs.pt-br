---
title: Detecção de truncamento de dados habilitada usando ExtendedAnsiSQL | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: odbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- truncating data [ODBC]
- extendedANSISQL [ODBC], data truncation detection
ms.assetid: cec2359b-917d-4e1d-9625-5cd678b62f10
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b8f50d96ea39ab5b9d2b23af2318f1dee724c04a
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="data-truncation-detection-enabled-using-extendedansisql"></a>Detecção de truncamento de dados habilitada usando ExtendedAnsiSQL
Quando o sinalizador ExtendedAnsiSQL está ativado e o aplicativo estiver inserindo dados em uma coluna binária ou de char e os dados são truncados, o truncamento será detectado. Quando o sinalizador ExtendedAnsiSQL estiver desativado, os dados são truncados sem aviso, como ele era em versões anteriores dos Drivers de banco de dados de área de trabalho do ODBC.
