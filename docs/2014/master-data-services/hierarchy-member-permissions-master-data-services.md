---
title: Permissões de membro de hierarquia (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- members [Master Data Services], permissions
- permissions [Master Data Services], members
ms.assetid: b3880eed-1bf6-4f65-ab23-b08c194cc858
caps.latest.revision: 7
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 762006e2e5e6292fc17519894d74e6ca8f250472
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37239096"
---
# <a name="hierarchy-member-permissions-master-data-services"></a>Permissões de membro de hierarquia (Master Data Services)
  As permissões de membro de hierarquia são opcionais e devem ser usadas somente quando você desejar que um usuário tenha acesso limitado a membros específicos. Se você não atribuir permissões na guia **Membros da Hierarquia** , as permissões do usuário serão baseadas somente nas permissões atribuídas na guia **Modelos** .  
  
 As permissões de membros de hierarquia são atribuídas na interface do usuário do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , na área funcional **Usuário e Permissões de Grupo** da guia **Membros da Hierarquia** . Estas permissões determinam quais membros um usuário pode acessar na área funcional do **Gerenciador** da interface do usuário.  
  
 Na guia **Membros da Hierarquia** , cada hierarquia é representada como uma estrutura de árvore. Quando você atribuir permissão para um nó na árvore, todos os filhos herdam essa permissão a menos que ela seja atribuída explicitamente a um nível inferior.  
  
> [!NOTE]  
>  Quando você atribuir permissão para um nó em uma hierarquia, todos os membros de todos os outros nós no mesmo nível ou superior serão recusados implicitamente.  
  
 No **Gerenciador**, as permissões de membro são aplicadas em todos lugares em que o membro é exibido. Por exemplo, um membro com **somente leitura** permissão é somente leitura em quaisquer entidades, hierarquias e coleções à qual ele pertence.  
  
 As permissões de membro de hierarquia aplicam-se à versão do modelo que recebe as permissões, e a qualquer cópia futura da versão. Elas não se aplicam a versões anteriores a que você está atribuindo.  
  
|Permissão|Description|  
|----------------|-----------------|  
|**Somente leitura**|Os membros são exibidos, mas o usuário não pode alterá-los. O usuário também não pode mover os membros em qualquer hierarquia explícita ou coleções a que os membros pertencem.<br /><br /> Observação: Se você atribuir **somente leitura** permissão para **raiz**, os membros sob **raiz** são somente leitura; no entanto, em hierarquias explícitas e coleções, o usuário pode mover membros a serem **raiz** e pode adicionar novos membros **raiz**.|  
|**Update (atualizar)**|Os membros são exibidos e o usuário pode alterá-los. O usuário também pode mover os membros em qualquer hierarquia explícita ou coleções a que os membros pertencem.|  
|**Deny**|Os membros não são exibidos.|  
  
 Na guia **Membros da Hierarquia** , as permissões que você atribui não entram em vigor imediatamente. A frequência com que as permissões são aplicadas depende da **Configuração de intervalo de processamento da segurança de membro** na tabela de Configurações do Sistema no banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] . É possível aplicar permissões de membros imediatamente seguindo as etapas em [Immediately Apply Member Permissions &#40;Master Data Services&#41;](immediately-apply-member-permissions-master-data-services.md).  
  
> [!NOTE]  
>  Não é possível atribuir permissões de membro de hierarquia a hierarquias recursivas, hierarquias derivadas com delimitações explícitas e a hierarquias derivadas com níveis ocultos.  
  
## <a name="possible-overlapping-permissions"></a>Permissões sobrepostas possíveis  
 Ao atribuir permissão para membros, pode ser necessário resolver permissões sobrepostas.  
  
### <a name="when-a-member-belongs-to-multiple-hierarchies"></a>Quando um membro pertence a várias hierarquias  
 Duas ou mais hierarquias podem conter o mesmo membro.  
  
-   Se for atribuído a um nó de hierarquia **atualização** permissão e outra receber **somente leitura**, então os membros no nó serão **somente leitura**.  
  
-   Se for atribuído a um nó de hierarquia **atualização** ou **somente leitura** permissão e o outro nó receber **Deny**, em seguida, os membros no nó não são exibidos.  
  
## <a name="see-also"></a>Consulte também  
 [Atribuir permissões de membro de hierarquia &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)   
 [Como as permissões são determinadas &#40;Master Data Services&#41;](../../2014/master-data-services/how-permissions-are-determined-master-data-services.md)   
 [Membros &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md)   
 [Hierarquias &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchies-master-data-services.md)   
 [Aplicação imediata de permissões de membro &#40;Master Data Services&#41;](immediately-apply-member-permissions-master-data-services.md)  
  
  
