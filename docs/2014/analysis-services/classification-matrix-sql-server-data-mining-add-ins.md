---
title: Matriz de classificação (SQL Server Data Mining Add-ins) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- mining models, validating
- classification matrix
- confusion table
- mining models, testing
ms.assetid: d6f620f4-39af-4714-9628-28ce3c361fca
caps.latest.revision: 14
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 3d87c2d37ed69e2cc3f3e224ddf1a489b34425b8
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37249636"
---
# <a name="classification-matrix-sql-server-data-mining-add-ins"></a>Matriz de classificação (Suplementos de Mineração de Dados do SQL Server)
  ![Botão matriz de classificação, faixa de opções mineração de dados](media/dmc-cmatrix.gif "botão matriz de classificação, faixa de opções mineração de dados")  
  
 Você pode usar a matriz de classificação para avaliar a precisão de um modelo para previsão. Para gerar uma matriz de classificação, você executar um conjunto de dados de teste através do modelo, e a ferramenta da matriz de classificação compara os valores reais do conjunto de teste com as previsões feitas pelo modelo. Ao examinar a matriz, você pode identificar rapidamente com que frequência o modelo está correto, e a frequência de previsões erradas.  
  
 Esses suplementos, use o **matriz de classificação** Assistente para selecionar um modelo, especifique os dados de teste e, em seguida, gerar uma matriz de resultados.  
  
## <a name="how-to-read-a-classification-matrix"></a>Como ler uma matriz de classificação  
 Digamos que seu objetivo seja criar um programa de lealdade de cliente e atribuir clientes a categorias apropriadas, de forma que você possa fornecer a eles o nível apropriado de incentivos. Você implementou três níveis para o programa de recompensa -- bronze, prata e ouro – e forneceu isso aos clientes em uma fase de avaliação. Você também criou um modelo que analisa clientes e prevê as categorias corretas. Agora você usará a matriz de classificação nos dados de avaliação para determinar quão bom era o modelo em prever a oferta correta para todos os clientes.  
  
 A tabela da matriz de classificação mostra quantos clientes seriam atribuídos a cada categoria com base no modelo, e compara esse resultado ao número de clientes que de fato se inscreveram em cada nível de recompensa.  
  
||Bronze (real)|Ouro (real)|Prata (real)|  
|-|-----------------------|---------------------|-----------------------|  
|Bronze|**% 94.45**|% 15.18|% 1,70|  
|Ouro|% 2.72|**% 84.82**|0.00%|  
|Prata|% 1.84|0.00%|**% 93.80**|  
|*Corrigir*|*% 95.45*|*% 84.82*|*% 98.30*|  
|*Classificado incorretamente*|*% 4.55*|*% 15.18*|*% 1,70*|  
  
-   Cada coluna mostra os valores reais no conjunto de dados de teste.  
  
-   Cada linha exibe os valores previstos.  
  
-   Os valores em negrito, executados diagonalmente do canto superior esquerdo para o canto inferior direito da matriz, mostram até que ponto o modelo deu certo.  
  
-   Todos os demais valores fora da diagonal representam erros. Alguns erros são falsos positivos; isso significa que o modelo previu que o cliente se associaria ao programa de ouro, mas ele estava errado.  Dependendo de seu domínio, os falsos positivos podem ser muito dispendiosos.  
  
     Outros são falsos negativos; isso significa que o modelo previu que o cliente não estaria interessado, embora não tivesse se associado ao programa. Novamente, dependendo do domínio do problema, o custo dessa oportunidade perdida pode ser significativo.  
  
## <a name="using-the-classification-matrix-wizard"></a>Usando o Assistente da Matriz de Classificação  
  
1.  Selecione o modelo de mineração no qual basear as previsões.  
  
2.  Selecione uma fonte de novos dados de teste, ou use os dados de teste que foram salvos com a estrutura.  
  
3.  Selecione a coluna cuja precisão você deseja avaliar. Você pode escolher apenas uma coluna ao criar uma matriz, mas a coluna pode ter vários valores.  
  
     Dica: talvez seja difícil interpretar uma matriz de classificação se a coluna previsível tiver muitas colunas a serem comparadas.  
  
     No **selecionar colunas para prever** página, você também pode especificar se deseja exibir a contagem de valores corretos e incorretos ou exibir uma porcentagem.  
  
4.  Na página Selecionar Dados de Origem, indique se você está usando dados de teste externos, ou os dados de teste salvos com o modelo.  
  
5.  Se você usar dados externos de teste, você precisará mapear o modelo para as colunas de entrada sobre o **especifique a relação** página do assistente.  
  
     Se você usar o conjunto de dados de teste inserido, o mapeamento será realizado para você  
  
6.  Clique em **concluir** para executar previsões no modelo e gerar a matriz de classificação.  
  
     O assistente cria um relatório que contém a matriz de classificação e outros detalhes sobre a análise. Este relatório é salvo como uma tabela no Excel, com um resumo acima do relatório que indica quantos casos foram previstos corretamente e quantas previsões foram incorretas.  
  
### <a name="requirements"></a>Requisitos  
  
-   Para criar uma matriz de classificação, você deve ter acesso a um modelo de mineração existente que dá suporte à medida de precisão. Modelos de previsão e modelos de associação não podem ser medidos usando essa ferramenta.  
  
-   O modelo que você está medindo precisa prever um valor que seja discreto ou que já tenha sido discretizado.  
  
-   Se você não tiver usado a opção para salvar um conjunto de teste junto com sua estrutura ou modelo, precisará obter um conjunto de dados de entrada que tenha essencialmente o mesmo número de colunas, com tipos de dados compatíveis, como aqueles usados no modelo.  
  
-   O modelo de mineração de dados e os novos dados que você estiver usando para teste deverão conter pelo menos uma coluna que possa ser prevista, e as colunas devem conter o mesmo tipo de dados.  
  
### <a name="known-issues"></a>Problemas conhecidos  
 No SQL Server 2012 e SQL Server 2014, a capacidade de mapear o conjunto de dados de teste interno para o modelo não está funcionando na **matriz de classificação** ferramenta. No entanto, você pode especificar um conjunto de dados externo, e selecionar o treinamento definido como a entrada para determinar o erro no conjunto de dados original.  
  
## <a name="see-also"></a>Consulte também  
 [Validando modelos e usando modelos para previsão &#40;Data Mining Add-ins para Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md)   
 [Explorar dados &#40;suplementos de mineração de dados do SQL Server&#41;](explore-data-sql-server-data-mining-add-ins.md)   
 [Detectar categorias &#40;ferramentas de análise de tabela para Excel&#41;](detect-categories-table-analysis-tools-for-excel.md)  
  
  
