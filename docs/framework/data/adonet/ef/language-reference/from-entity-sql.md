---
title: DE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff3e3048-0d5d-4502-ae5c-9187fcbd0514
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 51f65896cb54a65756558d846e1fc940de5b9470
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="from-entity-sql"></a>DE (Entity SQL)
Especifica a coleção usada em [selecione](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) instruções.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
FROM expression [ ,...n ] as C  
```  
  
## <a name="arguments"></a>Arguments  
 `expression`  
 Qualquer expressão de consulta válida que produzir uma coleção para usar como uma fonte em uma instrução de `SELECT` .  
  
## <a name="remarks"></a>Comentários  
 Uma cláusula de `FROM` é uma lista separada por vírgulas de um ou mais itens da cláusula de `FROM` . A cláusula de `FROM` pode ser usada para especificar uma ou mais fontes para uma declaração de `SELECT` . A forma mais simples de uma cláusula de `FROM` é uma única expressão de consulta que identifica uma coleção e um alias usadas como a origem em uma instrução de `SELECT` , conforme ilustrado no exemplo a seguir:  
  
 `FROM C as c`  
  
## <a name="from-clause-items"></a>Itens de cláusula  
 Cada item de cláusula de `FROM` refere-se a uma coleção de origem na consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . [!INCLUDE[esql](../../../../../../includes/esql-md.md)] suporta as seguintes classes de itens de cláusula de `FROM` : itens simples de cláusula de `FROM` , itens de cláusula de `JOIN FROM` , e itens da cláusula de `APPLY FROM` . Cada um desses itens de cláusula de `FROM` é descrito em detalhes nas seções seguintes.  
  
### <a name="simple-from-clause-item"></a>Simples de item da cláusula  
 O item mais simples de cláusula de `FROM` é uma única expressão que identifica uma coleção e um alias. A expressão pode ser simplesmente um conjunto de entidades, ou um subconsulta, ou qualquer outra expressão que é um tipo de coleção. A seguir está um exemplo:  
  
```  
LOB.Customers as c  
```  
  
 A especificação do alias é opcional. Uma especificação alternativa de acima do item da cláusula pode ser a seguinte:  
  
```  
LOB.Customers  
```  
  
 Se nenhum alias for especificada, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenta gerar um alias com base na expressão de coleção.  
  
### <a name="join-from-clause-item"></a>JUNTE-SE de item da cláusula  
 Um item da cláusula de `JOIN FROM` representa uma associação entre dois itens a cláusula de `FROM` . a cruz de suporte de[!INCLUDE[esql](../../../../../../includes/esql-md.md)] join, interno join, a esquerda e certeza externo join, e externo completo join. Todos esses se associam são semelhantes suporte à maneira que são suportados em [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]. Como em [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], os dois itens a cláusula de `FROM` envolvidos em `JOIN` devem ser independentes. Isto é, não podem ser correlacionados. `CROSS APPLY` ou `OUTER APPLY` podem ser usados para esses casos.  
  
#### <a name="cross-joins"></a>Cruzam A adição  
 Uma expressão de consulta de `CROSS JOIN` gerencia o produto cartesiano das duas coleções, como ilustrado no exemplo a seguir:  
  
 `FROM C AS c CROSS JOIN D as d`  
  
#### <a name="inner-joins"></a>Interno join  
 `INNER JOIN` gerencia um produto cartesiano restrito das duas coleções, como ilustrado no exemplo a seguir:  
  
 `FROM C AS c [INNER] JOIN D AS d ON e`  
  
 A expressão de consulta anterior processa uma combinação de cada elemento da coleção à esquerda emparelhado com cada elemento da coleção à direita, onde a condição de `ON` é verdadeira. Se nenhuma condição de `ON` for especificada, `INNER JOIN` degenerado a `CROSS JOIN`.  
  
#### <a name="left-outer-joins-and-right-outer-joins"></a>Left outer join e externo direito join  
 Uma expressão de consulta de `OUTER JOIN` gerencia um produto cartesiano restrito das duas coleções, como ilustrado no exemplo a seguir:  
  
 `FROM C AS c LEFT OUTER JOIN D AS d ON e`  
  
 A expressão de consulta anterior processa uma combinação de cada elemento da coleção à esquerda emparelhado com cada elemento da coleção à direita, onde a condição de `ON` é verdadeira. Se a condição de `ON` for falsa, a expressão ainda processa uma única instância do elemento à esquerda emparelhado contra o elemento à direita, com o valor de zero.  
  
 `RIGHT OUTER JOIN` pode ser expresso de maneira similar.  
  
#### <a name="full-outer-joins"></a>Externo completo join  
 `FULL OUTER JOIN` explícito gerencia um produto cartesiano restrito das duas coleções como ilustrado no exemplo a seguir:  
  
 `FROM C AS c FULL OUTER JOIN D AS d ON e`  
  
 A expressão de consulta anterior processa uma combinação de cada elemento da coleção à esquerda emparelhado com cada elemento da coleção à direita, onde a condição de `ON` é verdadeira. Se a condição de `ON` for falsa, a expressão ainda processa uma instância do elemento à esquerda emparelhado contra o elemento à direita, com o valor de zero. Também processa uma instância do elemento à direita emparelhado contra o elemento à esquerda, com o valor de zero.  
  
> [!NOTE]
>  Para preservar compatibilidade com SQL-92, em [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] a palavra-chave OUTER é opcional. Portanto, `LEFT JOIN`, `RIGHT JOIN`, e `FULL JOIN` são sinônimos para `LEFT OUTER JOIN`, `RIGHT OUTER JOIN`, e `FULL OUTER JOIN`.  
  
### <a name="apply-clause-item"></a>APPLY o item da cláusula  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] suporta dois tipos de `APPLY`: `CROSS APPLY` e `OUTER APPLY`.  
  
 `CROSS APPLY` gerencia um emparelhamento exclusivo de cada elemento da coleção à esquerda com um elemento da coleção gerada avaliando a expressão à direita. Com `CROSS APPLY`, a expressão à direita funcional é dependente no elemento à esquerda, conforme ilustrado no exemplo associado de coleção:  
  
 `SELECT c, f FROM C AS c CROSS APPLY c.Assoc AS f`  
  
 O comportamento de `CROSS APPLY` é semelhante à lista de associação. Se a expressão à direita é avaliada como uma coleção vazia, `CROSS APPLY` não gerencia nenhum pairings para essa instância do elemento à esquerda.  
  
 `OUTER APPLY` é semelhante a `CROSS APPLY`, a não ser que um emparelhamento ainda é gerado mesmo quando a expressão à direita é avaliada como uma coleção vazia. O código a seguir é um exemplo de `OUTER APPLY`:  
  
 `SELECT c, f FROM C AS c OUTER APPLY c.Assoc AS f`  
  
> [!NOTE]
>  Ao contrário em [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], não há necessidade de uma etapa para mais unnest explícita em [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
> [!NOTE]
>  `CROSS` e operadores de `OUTER APPLY` foram introduzidos em [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)]. Em alguns casos, o canal de consulta pode gerar Transact-SQL que contém `CROSS APPLY` e/ou operadores de `OUTER APPLY` . Porque alguns provedores backend, incluindo versões de [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] anteriores de [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)], não suportam esses operadores, essas consultas podem não ser executadas nesses provedores backend.  
>   
>  Alguns cenários típicos que podem resultar na presença de `CROSS APPLY` e/ou operadores de `OUTER APPLY` na saída consulte são os seguintes: um subconsulta correlacionado com paginação; AnyElement sobre um subconsulta correlacionado ou em uma coleção gerada por navegação; LINQ consulta que uso que agrupa os métodos que aceitam um seletor do elemento; uma consulta em que `CROSS APPLY` ou `OUTER APPLY` são especificados explicitamente; uma consulta que tenha uma compilação de `DEREF` sobre uma compilação de `REF` .  
  
## <a name="multiple-collections-in-the-from-clause"></a>Várias coleções na cláusula  
 A cláusula de `FROM` pode conter mais de uma coleção separados por vírgulas. Nesses casos, coleções são assumidas para ser agrupadas. Pense nesses CRUZ como uma maneira de n- JOIN.  
  
 No exemplo a seguir, `C` e `D` são coleções independentes, mas `c.Names` é dependente de `C`.  
  
```  
FROM C AS c, D AS d, c.Names AS e  
```  
  
 O exemplo anterior é logicamente equivalente ao exemplo a seguir:  
  
 `FROM (C AS c JOIN D AS d) CROSS APPLY c.Names AS e`  
  
## <a name="left-correlation"></a>Correlação esquerda  
 Os itens na cláusula `FROM` podem se referir aos itens especificados nas cláusulas anteriores. No exemplo a seguir, `C` e `D` coleções são independentes, mas `c.Names` é dependente em `C`:  
  
```  
from C as c, D as d, c.Names as e  
```  
  
 Isso é logicamente equivalente a:  
  
```  
from (C as c join D as d) cross apply c.Names as e  
```  
  
## <a name="semantics"></a>Semântica  
 Logicamente, coleções na cláusula `FROM` são assumidas para ser parte de `n`- a cruz de maneira joins a não ser que no caso de uma maneira 1 percorrer se junte). Alias na cláusula `FROM` são processadas esquerda para a direita, e adicionadas ao escopo atual para referência posterior. A cláusula de `FROM` é assumida para gerar um multiset de linhas. Haverá um campo para cada item na cláusula `FROM` que representa um único elemento do item da coleção.  
  
 A cláusula de `FROM` gerencia logicamente um multiset das linhas da linha de tipo (c, d, e) onde os campos c, d, e e são considerados para ser do tipo de elemento de `C`, de `D`, e de `c.Names`.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] apresenta um alias para cada item simples de cláusula de `FROM` no escopo. Por exemplo, o seguinte trecho da cláusula, os nomes são introduzidos no escopo c, d, e E.  
  
```  
from (C as c join D as d) cross apply c.Names as e  
```  
  
 Em [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (em vez de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]), a cláusula de `FROM` apresenta somente alias no escopo. Todas as referências às colunas (propriedades) dessas coleções devem ser qualificados com o alias.  
  
## <a name="pulling-up-keys-from-nested-queries"></a>Levantando chaves de consultas aninhadas  
 Determinados tipos de consultas que exigem gerar chaves de uma consulta aninhada não são suportados. Por exemplo, a seguinte consulta é válido:  
  
```  
select c.Orders from Customers as c   
```  
  
 No entanto, a consulta a seguir é inválido, porque a consulta aninhada não tem nenhuma chaves:  
  
```  
select {1} from {2, 3}  
```  
  
## <a name="see-also"></a>Consulte também  
 [Referência de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Expressões de Consulta](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
 [Tipos anuláveis estruturados](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)