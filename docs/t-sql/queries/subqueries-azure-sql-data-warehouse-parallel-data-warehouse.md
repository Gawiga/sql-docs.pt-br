---
title: Subconsultas (Azure SQL Data Warehouse, Parallel Data Warehouse) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e8ebd60-1936-48c9-b2b9-e099c8269fcf
caps.latest.revision: 7
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 351d559bde6300d9f746d68a802ae0a61202f8b8
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="subqueries-azure-sql-data-warehouse-parallel-data-warehouse"></a>Subconsultas (Azure SQL Data Warehouse, Parallel Data Warehouse)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw_md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  Este tópico fornece exemplos de uso de subconsultas em [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] ou [!INCLUDE[ssPDW](../../includes/sspdw-md.md)].  
  
 Para a instrução SELECT, consulte [SELECT &#40; Transact-SQL &#41;](../../t-sql/queries/select-transact-sql.md)  
  
## <a name="contents"></a>Sumário  
  
-   [Noções básicas](#Basics)  
  
-   [Exemplos: SQL Data Warehouse e o Parallel Data Warehouse](#Examples)  
  
##  <a name="Basics"></a>Noções básicas  
 Subconsulta  
 Uma subconsulta é uma consulta aninhada em uma instrução SELECT, INSERT, UPDATE ou DELETE, ou em subconsulta. Isso também é chamado uma consulta interna ou seleção interna.  
  
 Consulta externa  
 A instrução que contém a subconsulta. Isso também é chamado uma seleção externa.  
  
 Subconsulta correlacionada  
 Uma subconsulta que faz referência a uma tabela na consulta externa.  
  
##  <a name="Examples"></a>Exemplos: [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] e[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 Esta seção fornece exemplos de subconsultas com suporte no [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] ou [!INCLUDE[ssPDW](../../includes/sspdw-md.md)].  
  
### <a name="a-top-and-order-by-in-a-subquery"></a>A. TOP e ORDER BY em uma subconsulta  
  
```  
SELECT * FROM tblA  
WHERE col1 IN  
    (SELECT TOP 100 col1 FROM tblB ORDER BY col1);  
  
```  
  
### <a name="b-having-clause-with-a-correlated-subquery"></a>B. COM a cláusula com uma subconsulta correlacionada  
  
```  
SELECT dm.EmployeeKey, dm.FirstName, dm.LastName   
FROM DimEmployee AS dm   
GROUP BY dm.EmployeeKey, dm.FirstName, dm.LastName  
HAVING 5000 <=   
(SELECT sum(OrderQuantity)  
FROM FactResellerSales AS frs  
WHERE dm.EmployeeKey = frs.EmployeeKey)  
ORDER BY EmployeeKey;  
  
```  
  
### <a name="c-correlated-subqueries-with-analytics"></a>C. Subconsultas correlacionadas com a análise  
  
```  
SELECT * FROM ReplA AS A   
WHERE A.ID IN   
    (SELECT sum(B.ID2) OVER() FROM ReplB AS B WHERE A.ID2 = B.ID);  
```  
  
### <a name="d-correlated-union-statements-in-a-subquery"></a>D. Instruções de união correlacionadas em uma subconsulta  
  
```  
SELECT * FROM RA   
WHERE EXISTS   
    (SELECT 1 FROM RB WHERE RB.b1 = RA.a1   
     UNION ALL SELECT 1 FROM RC);  
```  
  
### <a name="e-join-predicates-in-a-subquery"></a>E. Unir predicados em uma subconsulta  
  
```  
SELECT * FROM RA INNER JOIN RB   
    ON RA.a1 = (SELECT COUNT(*) FROM RC);  
```  
  
### <a name="f-correlated-join-predicates-in-a-subquery"></a>F. Predicados de junção correlacionados em uma subconsulta  
  
```  
SELECT * FROM RA   
    WHERE RA.a2 IN   
    (SELECT 1 FROM RB INNER JOIN RC ON RA.a1=RB.b1+RC.c1);  
```  
  
### <a name="g-correlated-subselects-as-data-sources"></a>G. Subseleções correlacionadas como fontes de dados  
  
```  
SELECT * FROM RA   
    WHERE 3 = (SELECT COUNT(*)   
        FROM (SELECT b1 FROM RB WHERE RB.b1 = RA.a1) X);  
```  
  
### <a name="h-correlated-subqueries-in-the-data-values--used-with-aggregates"></a>H. Subconsultas correlacionadas nos valores de dados usadas com agregações  
  
```  
SELECT Rb.b1, (SELECT RA.a1 FROM RA WHERE RB.b1 = RA.a1) FROM RB GROUP BY RB.b1;  
```  
  
### <a name="i-using-in-with-a-correlated-subquery"></a>I. Usando com uma subconsulta correlacionada  
 O exemplo a seguir usa `IN` em uma subconsulta correlata ou repetitiva. Trata-se de uma consulta que depende da consulta externa para obter seus valores. A consulta interna é executada repetidamente, uma vez para cada linha que pode ser selecionada pela consulta externa. Essa consulta recupera uma instância do `EmployeeKey` além do nome e sobrenome de cada funcionário para o qual o `OrderQuantity` no `FactResellerSales` tabela é `5` e para que os números de identificação de funcionário correspondem no `DimEmployee` e `FactResellerSales` tabelas.  
  
```  
SELECT DISTINCT dm.EmployeeKey, dm.FirstName, dm.LastName   
FROM DimEmployee AS dm   
WHERE 5 IN   
    (SELECT OrderQuantity  
    FROM FactResellerSales AS frs  
    WHERE dm.EmployeeKey = frs.EmployeeKey)  
ORDER BY EmployeeKey;  
```  
  
### <a name="j-using-exists-versus-in-with-a-subquery"></a>J. Usando EXISTS versus com uma subconsulta  
 O exemplo a seguir mostra consultas semanticamente equivalentes para ilustrar a diferença entre usar o `EXISTS` palavra-chave e o `IN` palavra-chave. Ambos são exemplos de uma subconsulta que recupera uma instância de cada nome de produto para o qual a subcategoria de produto é `Road Bikes`. `ProductSubcategoryKey`faz a correspondência entre o `DimProduct` e `DimProductSubcategory` tabelas.  
  
```  
SELECT DISTINCT EnglishProductName  
FROM DimProduct AS dp   
WHERE EXISTS  
    (SELECT *  
     FROM DimProductSubcategory AS dps   
     WHERE dp.ProductSubcategoryKey = dps.ProductSubcategoryKey  
           AND dps.EnglishProductSubcategoryName = 'Road Bikes')  
ORDER BY EnglishProductName;  
```  
  
 Ou  
  
```  
SELECT DISTINCT EnglishProductName  
FROM DimProduct AS dp   
WHERE dp.ProductSubcategoryKey IN  
    (SELECT ProductSubcategoryKey  
     FROM DimProductSubcategory   
     WHERE EnglishProductSubcategoryName = 'Road Bikes')  
ORDER BY EnglishProductName;  
```  
  
### <a name="k-using-multiple-correlated-subqueries"></a>K. Usando várias subconsultas correlacionadas  
 Este exemplo usa duas subconsultas correlatas para localizar os nomes de funcionários que venderam um produto específico.  
  
```  
SELECT DISTINCT LastName, FirstName, e.EmployeeKey  
FROM DimEmployee e JOIN FactResellerSales s ON e.EmployeeKey = s.EmployeeKey  
WHERE ProductKey IN  
(SELECT ProductKey FROM DimProduct WHERE ProductSubcategoryKey IN  
(SELECT ProductSubcategoryKey FROM DimProductSubcategory   
 WHERE EnglishProductSubcategoryName LIKE '%Bikes'))  
ORDER BY LastName  
;  
  
```  
  
  