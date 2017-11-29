---
title: "FUNÇÃO (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 40c8f218238492bbbc4af543aa6f9a635454b359
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="function-entity-sql"></a>FUNÇÃO (Entity SQL)
Define uma função no escopo de um comando de consulta Entity SQL.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
FUNCTION function-name  
( [ { parameter_name <type_definition>   
        [ ,...n ]  
  ]  
) AS ( function_expression )   
  
<type_definition>::=  
    { data_type | COLLECTION ( <type_definition> )   
                | REF ( data_type )   
                | ROW ( row_expression )   
        }   
```  
  
## <a name="arguments"></a>Arguments  
 `function-name`  
 Nome da função.  
  
 `parameter-name`  
 Nome de um parâmetro em função.  
  
 `function_expression`  
 Uma expressão válida de Entity SQL que é a função. O comando na função pode atuar nos parâmetros de `parameter_name` passados para a função.  
  
 `data_type`  
 Nome de um tipo suportado.  
  
 COLEÇÃO ( <type_definition`>` )  
 Uma expressão que retorna uma coleção de tipos suportados, de linhas, ou de referências.  
  
 REF **(**`data_type`**)**  
 Uma expressão que retorna uma referência a um tipo de objeto.  
  
 LINHA **(**`row_expression`**)**  
 Uma expressão que retorna registros anônimos, tipados estrutural de um ou mais valores. Para obter mais informações, consulte [linha](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).  
  
## <a name="remarks"></a>Comentários  
 Várias funções com o mesmo nome podem ser declarados embutidos, como as assinaturas de função são diferentes. Para obter mais informações, consulte [a resolução de sobrecarga de função](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
 Uma função in-line pode ser chamado em um comando de Entity SQL somente após foi definida no comando. No entanto, uma função in-line pode ser chamada dentro de outra função in-line tanto antes ou após a função chamada foi definido. No exemplo a seguir, funciona a função B de chamadas de antes que a função B é definida:  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 Para obter mais informações, consulte [como: chamar uma função definida pelo usuário](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02).  
  
 As funções podem também ser declaradas no próprio modelo. As funções declaradas no modelo são executadas da mesma forma como as funções está embutido no comando. Para obter mais informações, consulte [funções definidas pelo usuário](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).  
  
## <a name="example"></a>Exemplo  
 O seguinte comando de Entity SQL define uma função `Products` que recebe um valor inteiro para filtrar os produtos retornados.  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function1)]  
  
## <a name="example"></a>Exemplo  
 O seguinte comando de Entity SQL define uma função `StringReturnsCollection` que utiliza uma coleção de cadeias de caracteres para filtrar os contatos retornados.  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function2)]  
  
## <a name="see-also"></a>Consulte também  
 [Referência de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Entity SQL Language](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) (Linguagem SQL de entidade)