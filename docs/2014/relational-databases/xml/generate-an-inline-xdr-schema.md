---
title: Gerar um esquema XDR embutido | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-xml
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- XDR schemas [SQL Server]
- inline XDR schema generation [SQL Server]
- XMLDATA option
- FOR XML clause, inline XDR schema generation
ms.assetid: 2a40d617-9724-4f7d-80a4-a85c702f14d0
caps.latest.revision: 31
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 136eb4624680d6a372d36313216ad54ee17beb07
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37212556"
---
# <a name="generate-an-inline-xdr-schema"></a>Gerar um esquema XDR embutido
  A diretiva **XMLDATA** no FOR XML retorna um esquema XDR embutido junto com o resultado da consulta. No entanto, o esquema XDR não oferece suporte a todos os novos tipos de dados e outras melhorias apresentadas no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões anteriores. Em vez disso, é possível solicitar um esquema XSD embutido usando [a diretiva XMLSCHEMA](generate-an-inline-xsd-schema.md).  
  
> [!IMPORTANT]  
>  A diretiva XMLDATA para a opção FOR XML foi preterida. Use geração de XSD no caso dos modos RAW e AUTO. Não há substituição para a diretiva XMLDATA no modo EXPLICIT. [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 Também observe o seguinte sobre o suporte ao esquema XDR:  
  
-   Se o resultado da consulta FOR XML incluir colunas de tipo **xml** e você solicitar um esquema XDR embutido, será retornado um erro. O XDR embutido não oferece suporte a esses tipos.  
  
-   Os tipos **(n)varchar(max)** e **(n)varbinary(max)** serão mapeados para **(n)varchar(n)** e **varbinary(n)**, respectivamente.  
  
-   Quando o modo de compatibilidade é definido como 90 ou superior, os valores **timestamp** são considerados como dados **varbinary(8)** , são tratados como dados binários e retornados no resultado da seguinte maneira:  
  
    -   A codificação de Base 64 é usada quando **binary base64** é especificado.  
  
    -   A codificação de URL é usada no modo AUTO quando **binary base64** não é especificado.  
  
  
