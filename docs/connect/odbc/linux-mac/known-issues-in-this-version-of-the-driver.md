---
title: "Problemas conhecidos de nesta versão do Driver | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- known issues
caps.latest.revision: 30
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: f4202004a556479779d4884fc42d04ae540ed56d
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="known-issues-in-this-version-of-the-driver"></a>Problemas conhecidos nesta versão do driver
[!INCLUDE[Driver_ODBC_Download](../../../includes/driver_odbc_download.md)]Este tópico contém uma lista dos problemas conhecidos com o Microsoft ODBC Driver 13 for SQL Server no Linux e macOS.

Problemas adicionais serão postados no [blog da equipe do driver ODBC da Microsoft](http://blogs.msdn.com/b/sqlnativeclient/).  

- Windows, Linux e macOS converter caracteres da área de uso particular (PUA) ou caracteres definidos pelo usuário (EUDC) diferente. Conversões executadas no servidor no [!INCLUDE[tsql](../../../includes/tsql_md.md)] usar a biblioteca de conversão do Windows. Conversões no driver usam as bibliotecas de conversão do Windows, Linux ou macOS. Cada biblioteca pode produzir resultados diferentes ao executar essas conversões. Para obter mais informações, consulte [End-User-Defined and Private Use Area Characters](http://msdn.microsoft.com/library/dd317802.aspx).

- Se o cliente a codificação UTF-8, o Gerenciador de driver não sempre converter corretamente de UTF-8 em UTF-16. Atualmente, os dados são corrompidos quando 1 ou mais caracteres na cadeia de caracteres não são caracteres UTF-8 válidos. Caracteres ASCII são mapeados corretamente. O gerenciador de driver tentará fazer essa conversão ao chamar as versões SQLCHAR da API do ODBC (por exemplo, SQLDriverConnectA). O gerenciador de driver não tentará fazer essa conversão ao chamar as versões SQLWCHAR da API do ODBC (por exemplo, SQLDriverConnectW).  

- O *ColumnSize* parâmetro **SQLBindParameter** refere-se ao número de caracteres do tipo SQL, enquanto *BufferLength* é o número de bytes do aplicativo buffer. No entanto, se o tipo de dados SQL é `varchar(n)` ou `char(n)`, o aplicativo associa o parâmetro como SQL_C_CHAR ou SQL_C_VARCHAR e a codificação de caracteres do cliente é UTF-8, você pode receber um erro de "dados de cadeia de caracteres, truncamento à direita" do se até mesmo driver a valor de *ColumnSize* está alinhado com o tamanho do tipo de dados no servidor. Esse erro ocorre porque as conversões entre codificações de caractere podem alterar o comprimento dos dados. Por exemplo, um apóstrofo reto caractere (U + 2019) é codificado em CP-1252 como o único byte 0x92, mas em UTF-8 como a sequência de bytes de 3 0xe2 0x80 0x99.

Por exemplo, se a codificação é UTF-8 e você especificar 1 para ambos *BufferLength* e *ColumnSize* na **SQLBindParameter** por um parâmetro de saída e, em seguida, tentar recuperar o caractere acima armazenado em um `char(1)` coluna no servidor (usando CP-1252), o driver tenta convertê-lo para a codificação de 3 bytes UTF-8, mas não é possível ajustar o resultado em um buffer de 1 byte. Na outra direção, ele compara *ColumnSize* com o *BufferLength* na **SQLBindParameter** antes de fazer a conversão entre as páginas de código diferentes no cliente e servidor. Como um *ColumnSize* de valor 1 é menor que um *BufferLength* de valor 3 (por exemplo), o driver gerará um erro. Para evitar esse erro, verifique se o comprimento dos dados após a conversão se adapta a coluna ou o buffer especificado. Observe que *ColumnSize* não pode ser maior que 8000 para o `varchar(n)` tipo.

## <a name="see-also"></a>Consulte também  
[Diretrizes de programação](../../../connect/odbc/linux-mac/programming-guidelines.md)  
[Notas de versão](../../../connect/odbc/linux-mac/release-notes.md)  

