---
title: Conectar ao MySQL (MySQLToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.technology: ssma
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 94099d01-ab19-4d58-a172-340c86b4a0f3
caps.latest.revision: 9
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 3e4de2590221535410b5095494dd6f1801460f73
ms.sourcegitcommit: 8aa151e3280eb6372bf95fab63ecbab9dd3f2e5e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34775692"
---
# <a name="connect-to-mysql-mysqltosql"></a>Conectar ao MySQL (MySQLToSQL)
Use o **conectar ao MySQL** caixa de diálogo para se conectar ao banco de dados MySQL que você deseja migrar.  
  
Para acessar essa caixa de diálogo, no **arquivo** menu, selecione **conectar ao MySQL**. Se você se conectou anteriormente, o comando é **reconectar ao MySQL**.  
  
## <a name="options"></a>Opções  
**Provedor**  
  
Provedor de MySQL disponível é MySQL ODBC 5.1 Driver (confiável).  
  
**Modo**  
  
O modo padrão é o modo padrão. No modo padrão você inserir ou selecionar valores para o MySQL, o nome do servidor, a porta do servidor, o nome de usuário e a senha.  
  
**Nome do servidor**  
  
Insira o nome do servidor MySQL. Essa é uma opção de modo padrão.  
  
**Porta do servidor**  
  
Insira a porta do servidor. A porta do servidor padrão é 3306. Essa é uma opção de modo padrão.  
  
**Nome de usuário**  
  
Digite o nome de usuário SSMA usará para se conectar ao banco de dados MySQL.  
  
**Senha**  
  
Digite a senha para o nome de usuário.  
  
**SSL**  
  
Se você quiser se conectar com segurança ao MySQL, certifique-se de usar de Secure Socket Layer (SSL), verificando o **SSL** caixa de seleção.  
  
**Configurar**  
  
Ele fornece uma opção para configurar a conexão para MySQL por meio de Secure Socket Layer (SSL).  
  
> [!NOTE]  
> Para habilitar **configurar**, SSL deve ser definido como **True**.  
  
Em clicando no botão "Configurar", uma caixa de diálogo é exibida. Para usar a criptografia ao se conectar ao banco de dados MySQL, o caminho para os seguintes arquivos de três certificado presentes na caixa de diálogo deve ser definido [privacidade aprimorada Mail certificados (PEM)]:  
  
-   **Autoridade de certificação SSL:** Especifica o caminho para um arquivo com uma lista de relação de confiança de autoridades de certificação SSL.  
  
-   **Certificado SSL:** Especifica o nome do arquivo do certificado SSL a ser usado para estabelecer uma conexão segura.  
  
-   **CHAVE de SSL:** Especifica o nome do arquivo da chave SSL a ser usado para estabelecer uma conexão segura.  
  
> [!NOTE]  
> -   O **Okey** botão é habilitado quando as informações necessárias foi fornecidas. Se qualquer um dos caminhos de arquivo for inválido, o botão "Okey" permanecerá desabilitado.  
> -   O **Cancelar** botão fecha a caixa de diálogo e **desativa** a opção SSL do formulário de Conexão principal.  
  
