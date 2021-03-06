---
title: Desenvolvendo com XMLA no Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- XML for Analysis, data mining
- commands [XML for Analysis]
- data mining [XML for Analysis]
- XMLA, data mining
- XML for Analysis, Analysis Services tasks
- XMLA, Analysis Services tasks
ms.assetid: 54445ee7-720c-4683-99a6-e75b3dcca904
caps.latest.revision: 31
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: f4eef38459df5d2d872646a7bc64973028d25ac4
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37265652"
---
# <a name="developing-with-xmla-in-analysis-services"></a>Desenvolvendo com XMLA no Analysis Services
  O XMLA (XML for Analysis) é um protocolo XML baseado em SOAP, criado especificamente para acesso a dados universal para qualquer fonte de dados multidimensional padrão que pode ser acessado por meio de uma conexão HTTP. O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usa o XMLA como seu único protocolo para se comunicar com aplicativos cliente. Basicamente, todas as bibliotecas de cliente com suporte do Analysis Services formulam solicitações e respostas em XMLA.  
  
 Como desenvolvedor, você pode usar o XMLA para integrar um aplicativo cliente ao [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], sem qualquer dependência das interfaces do .NET Framework ou COM. Os requisitos de aplicativo que incluem a hospedagem em uma ampla variedade de plataformas podem ser atendidos com o uso do XMLA e de uma conexão HTTP com o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
 O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] é totalmente compatível com a especificação 1.1 do XMLA, mas também a estende para habilitar o suporte para definição, manipulação e controle de dados. As extensões do Analysis Services são referidas como ASSL (Analysis Services Scripting Language). Usar XMLA e ASSL juntos habilita uma variedade maior de funcionalidades do que o XMLA fornece sozinho. Para obter mais informações sobre ASSL, consulte [desenvolver com o Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).  
  
## <a name="in-this-section"></a>Nesta seção  
  
|Tópico|Description|  
|-----------|-----------------|  
|[Gerenciando conexões e sessões &#40;XMLA&#41;](managing-connections-and-sessions-xmla.md)|Descreve como se conectar a uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e como gerenciar sessões e a capacidade de manutenção de status do processo no XMLA.|  
|[Tratamento de erros e avisos &#40;XMLA&#41;](handling-errors-and-warnings-xmla.md)|Descreve como o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retorna informações de erro e de aviso para métodos e comandos no XMLA.|  
|[Definindo e identificando objetos &#40;XMLA&#41;](../xmla/xml-elements-objects.md)|Descreve identificadores de objetos e referências de objeto, e como usar identificadores e referências em comandos XMLA.|  
|[Gerenciando transações &#40;XMLA&#41;](managing-transactions-xmla.md)|Fornece detalhes sobre como usar o [BeginTransaction](../xmla/xml-elements-commands/begintransaction-element-xmla.md), [CommitTransaction](../xmla/xml-elements-commands/committransaction-element-xmla.md), e [RollbackTransaction](../xmla/xml-elements-commands/rollbacktransaction-element-xmla.md) comandos explicitamente definir e gerenciar uma transação em XMLA atual sessão.|  
|[Cancelando comandos &#40;XMLA&#41;](../multidimensional-models-scripting-language-assl-xmla/canceling-commands-xmla.md)|Descreve como usar o [Cancelar](../xmla/xml-elements-commands/cancel-element-xmla.md)comando para cancelar comandos, sessões e conexões no XMLA.|  
|[Executando operações em lote &#40;XMLA&#41;](performing-batch-operations-xmla.md)|Descreve como usar o [lote](../xmla/xml-elements-commands/batch-element-xmla.md) comando para executar XMLA vários comandos, em série ou paralelamente, dentro da mesma transação ou como transações separadas, usando um único XMLA [Execute](../xmla/xml-elements-methods-execute.md) método.|  
|[Criando e alterando objetos &#40;XMLA&#41;](creating-and-altering-objects-xmla.md)|Descreve como usar o [Create](../xmla/xml-elements-commands/create-element-xmla.md), [Alter](../xmla/xml-elements-commands/alter-element-xmla.md), e [excluir](../xmla/xml-elements-commands/delete-element-xmla.md) comandos, junto com elementos do Analysis Services Scripting Language (ASSL), para definir, alterar ou remover objetos de um [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instância.|  
|[Bloqueando e desbloqueando bancos de dados &#40;XMLA&#41;](locking-and-unlocking-databases-xmla.md)|Fornece detalhes sobre como usar o [bloqueio](../xmla/xml-elements-commands/lock-element-xmla.md) e [Unlock](../xmla/xml-elements-commands/unlock-element-xmla.md) comandos para bloquear e desbloquear um [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] banco de dados.|  
|[Processamento de objetos &#40;XMLA&#41;](processing-objects-xmla.md)|Descreve como usar o [processo](../xmla/xml-elements-commands/process-element-xmla.md) comando ao processo um [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objeto.|  
|[Mesclando partições &#40;XMLA&#41;](merging-partitions-xmla.md)|Descreve como usar o [MergePartitions](../xmla/xml-elements-commands/mergepartitions-element-xmla.md) comando para mesclar partições em um [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instância.|  
|[Projetando agregações &#40;XMLA&#41;](designing-aggregations-xmla.md)|Descreve como usar o [DesignAggregations](../xmla/xml-elements-commands/designaggregations-element-xmla.md) comando, em iterativo ou modo de lote para criar agregações para um design de agregação em [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].|  
|[Fazendo backup, restaurando e sincronizando bancos de dados &#40;XMLA&#41;](backing-up-restoring-and-synchronizing-databases-xmla.md)|Descreve como usar o [Backup](../xmla/xml-elements-commands/backup-element-xmla.md) e [restaurar](../xmla/xml-elements-commands/restore-element-xmla.md) comandos para fazer backup e restaurar um [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] banco de dados de um arquivo de backup.<br /><br /> Também descreve como usar o [Synchronize](../xmla/xml-elements-commands/synchronize-element-xmla.md) comando para sincronizar um [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] banco de dados com um banco de dados existente na mesma instância ou em uma instância diferente.|  
|[Inserindo, atualizando e descartando membros &#40;XMLA&#41;](inserting-updating-and-dropping-members-xmla.md)|Descreve como usar o [inserir](../xmla/xml-elements-commands/insert-element-xmla.md), [atualização](../xmla/xml-elements-commands/update-element-xmla.md), e [Drop](../xmla/xml-elements-commands/drop-element-xmla.md) comandos para adicionar, alterar ou excluir membros de uma dimensão habilitada para gravação.|  
|[Atualizando células &#40;XMLA&#41;](updating-cells-xmla.md)|Descreve como usar o [UpdateCells](../xmla/xml-elements-commands/updatecells-element-xmla.md) comando para alterar os valores de células em uma partição habilitada para gravação.|  
|[Gerenciando Caches &#40;XMLA&#41;](managing-caches-xmla.md)|Fornece detalhes sobre como usar o [ClearCache](../xmla/xml-elements-commands/clearcache-element-xmla.md) comando para limpar os caches de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objetos.|  
|[Monitorando rastreamentos &#40;XMLA&#41;](monitoring-traces-xmla.md)|Descreve como usar o [Subscribe](../xmla/xml-elements-commands/subscribe-element-xmla.md) comando para assinar e monitorar um rastreamento existente em um [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instância.|  
  
## <a name="data-mining-with-xmla"></a>Mineração de dados com o XMLA  
 O XML for Analysis dá suporte completo a conjuntos de linhas do esquema de mineração de dados. Esses conjuntos de linhas fornecem informações para consultar os modelos de mineração de dados usando o [Discover](../xmla/xml-elements-methods-discover.md) método. Para obter mais informações sobre linhas do esquema de mineração de dados, consulte [Data Mining Schema Rowsets](../schema-rowsets/data-mining/data-mining-schema-rowsets.md) 
  
 Para obter mais informações sobre DMX, consulte [extensões de mineração de dados &#40;DMX&#41; referência](/sql/dmx/data-mining-extensions-dmx-reference).  
  
## <a name="namespace-and-schema"></a>Namespace e esquema  
  
### <a name="namespace"></a>Namespace  
 O esquema definido nesta especificação usa o namespace XML http://schemas.microsoft.com/AnalysisServices/2003/Engine e a abreviação padrão "DDL".  
  
### <a name="schema"></a>esquema  
 A definição de um esquema da linguagem XSD para a linguagem de definição do objeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] baseia-se na definição dos elementos de esquema e na hierarquia desta seção.  
  
## <a name="extensibility"></a>Extensibilidade  
 A extensibilidade do esquema da linguagem de definição do objeto é fornecida por meio de um elemento do `Annotation` incluído em todos os objetos. Este elemento pode conter qualquer XML válido de qualquer namespace XML (diferente do namespace de destino que define o DDL), e está sujeito às seguintes regras:  
  
-   O XML pode conter somente elementos.  
  
-   Cada elemento deve ter um nome exclusivo. É recomendado que o valor de `Name` faça referência ao namespace de destino.  
  
 Estas regras são impostas para que o conteúdo da marca `Annotation` seja exposto como um conjunto de pares Nome/Valor por meio do DSO 9.0 (Decision Support Objects).  
  
 Os comentários e o espaço em branco na marca `Annotation` que não forem incluídos com um elemento filho podem não ser preservados. Além disso, todos os elementos devem ser leitura / gravação; elementos somente leitura são ignorados.  
  
 O esquema de linguagem de definição do objeto é fechado, sendo que o servidor não permite a substituição de tipos derivados para elementos definidos no esquema. Dessa forma, o servidor só aceitará o conjunto de elementos definido aqui e nenhum outro elemento ou atributo. Elementos desconhecidos farão com que o mecanismo do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] gere um erro.  
  
## <a name="see-also"></a>Consulte também  
 [Desenvolvimento com o Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)   
 [Noções básicas sobre a arquitetura do Microsoft OLAP](../multidimensional-models/olap-physical/understanding-microsoft-olap-architecture.md)  
  
  
