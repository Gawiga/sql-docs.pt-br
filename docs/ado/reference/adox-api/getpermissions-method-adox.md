---
title: Método GetPermissions (ADOX) | Microsoft Docs
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
- _User25::GetPermissions
- _Group25::raw_GetPermissions
- _Group25::GetPermissions
- _User25::raw_GetPermissions
helpviewer_keywords:
- GetPermissions method [ADOX]
ms.assetid: df201c1f-c76a-465d-98f0-83b7fc36e6e3
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 55a5d4f9096d5a75855d4b612a202afd034b11da
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35286035"
---
# <a name="getpermissions-method-adox"></a>Método GetPermissions (ADOX)
Retorna as permissões para um [grupo](../../../ado/reference/adox-api/group-object-adox.md) ou [usuário](../../../ado/reference/adox-api/user-object-adox.md) em um objeto ou o contêiner do objeto.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
ReturnValue=GroupOrUser.GetPermissions(Name, ObjectType    [,ObjectTypeId])  
```  
  
## <a name="return-value"></a>Valor retornado  
 Retorna um **longo** valor que especifica uma máscara de bits que contém as permissões que o grupo ou usuário tem sobre o objeto. Esse valor pode ser um ou mais do [RightsEnum](../../../ado/reference/adox-api/rightsenum.md) constantes.  
  
#### <a name="parameters"></a>Parâmetros  
 *Nome*  
 Um **Variant** valor que especifica o nome do objeto para o qual definir permissões. Definir *nome* com um valor nulo se você deseja obter as permissões para o contêiner do objeto.  
  
 *ObjectType*  
 Um **longo** valor que pode ser um do [ObjectTypeEnum](../../../ado/reference/adox-api/objecttypeenum.md) constantes, que especifica o tipo de objeto para o qual obter as permissões.  
  
 *ObjectTypeId*  
 Opcional. Um **Variant** valor que especifica o GUID de um tipo de objeto de provedor não definido pela especificação do OLE DB. Esse parâmetro é necessário se *ObjectType* é definido como **adPermObjProviderSpecific**; caso contrário, ele não é usado.  
  
## <a name="applies-to"></a>Aplica-se a  
  
|||  
|-|-|  
|[Objeto Group (ADOX)](../../../ado/reference/adox-api/group-object-adox.md)|[Objeto User (ADOX)](../../../ado/reference/adox-api/user-object-adox.md)|  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo de métodos de SetPermissions (VB) e GetPermissions](../../../ado/reference/adox-api/getpermissions-and-setpermissions-methods-example-vb.md)   
 [Propriedade Name (ADOX)](../../../ado/reference/adox-api/name-property-adox.md)   
 [Método SetPermissions (ADOX)](../../../ado/reference/adox-api/setpermissions-method-adox.md)
