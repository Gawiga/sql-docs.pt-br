---
title: catalog.set_worker_agent_property (banco de dados SSISDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/02/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: ddd2a534-6925-4d66-90e7-541c14f41de7
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 88abded1fe0cd2cdb0e86be54f5a94843282c45c
ms.sourcegitcommit: de5e726db2f287bb32b7910831a0c4649ccf3c4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2018
ms.locfileid: "35333980"
---
# <a name="catalogsetworkeragentproperty-ssisdb-database"></a>catalog.set_worker_agent_property (banco de dados SSISDB)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

Define a propriedade de um Trabalho do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Scale Out.

## <a name="syntax"></a>Sintaxe

```sql
catalog.set_worker_agent_property [@WorkerAgentId =] WorkerAgentId, [@PropertyName =] PropertyName, [@PropertyValue =] PropertyValue 
```

## <a name="arguments"></a>Argumentos
[@WorkerAgentId =] *WorkerAgentId*  
A ID do agente de trabalho do Trabalhador do Scale Out. O *WorkerAgentId* é **uniqueidentifier**.

[@PropertyName =] *PropertyName*  
O nome da propriedade. O *PropertyName* é **nvarchar(256)**.

[@PropertyValue =] *PropertyValue*  
O valor da propriedade. O *PropertyValue* é **nvarchar(max)**.

## <a name="remarks"></a>Remarks
Os nomes de propriedade válidos são **DisplayName**, **Description** e **Tags**.

## <a name="return-code-value"></a>Valor do código de retorno  
 0 (êxito)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
 Nenhum  

## <a name="permissions"></a>Permissões  
 Este procedimento armazenado exige uma das seguintes permissões:  
  
-   Associação à função de banco de dados **ssis_admin**  
  
-   Associação à função de servidor **sysadmin**

## <a name="errors-and-warnings"></a>Erros e avisos
  A lista a seguir descreve algumas condições que podem gerar um erro ou um aviso:  
  
-   O usuário não tem as permissões apropriadas 

-   A ID do agente de trabalho não é válida.

-   O nome da propriedade não é válido.

-   O valor da propriedade não é válido.  
