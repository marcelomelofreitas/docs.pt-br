---
title: Indexadores (Guia de Programação em C#)
ms.date: 03/10/2017
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
ms.openlocfilehash: acc82ca370a71a0469fc543d042da9c279d69fb2
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/21/2018
ms.locfileid: "42907742"
---
# <a name="indexers-c-programming-guide"></a>Indexadores (Guia de Programação em C#)

Os indexadores permitem que instâncias de uma classe ou struct sejam indexados como matrizes. O valor indexado pode ser definido ou recuperado sem especificar explicitamente um membro de instância ou tipo. Os indexadores parecem com [propriedades](../../../csharp/programming-guide/classes-and-structs/properties.md), a diferença é que seus acessadores usam parâmetros.  
 
 O exemplo a seguir define uma classe genérica com métodos de acesso [get](../../../csharp/language-reference/keywords/get.md) e [set](../../../csharp/language-reference/keywords/set.md) simples para atribuir e recuperar valores. A classe `Program` cria uma instância dessa classe para armazenar cadeias de caracteres.  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
>  Para mais exemplos, consulte as [seções relacionadas](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).  
  
## <a name="expression-body-definitions"></a>Definições de corpo de expressão  
 
É comum para um acessador get ou set de um indexador ser constituído de uma única instrução que retorna ou define um valor. Os membros de expressão fornecem uma sintaxe simplificada para dar suporte a esse cenário. Começando do C# 6, um indexador somente leitura pode ser implementado como um membro de expressão, como mostra o exemplo a seguir.

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

Observe que `=>` apresenta o corpo da expressão e que a palavra-chave `get` não é usada. 

Começando do C# 7.0, os acessadores get e set podem ser implementados como membros aptos para expressão. Nesse caso, as palavras-chave `get` e `set` devem ser usadas. Por exemplo:

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a>Visão Geral dos Indexadores  
  
-   Os indexadores permitem que objetos sejam indexados de maneira semelhante às matrizes.  
  
-   Um acessador `get` retorna um valor. Um acessador `set` atribui um valor.  
  
-   A palavra-chave [this](../../../csharp/language-reference/keywords/this.md) é usada para definir o indexador.  
  
-   A palavra-chave [value](../../../csharp/language-reference/keywords/value.md) é usada para definir o valor que está sendo atribuído pelo indexador `set`.  
  
-   Os indexadores não precisam ser indexados por um valor inteiro. Você deve definir o mecanismo de pesquisa específico.  
  
-   Os indexadores podem ser sobrecarregados.  
  
-   Os indexadores podem ter mais de um parâmetro formal, por exemplo, ao acessar uma matriz bidimensional.  
  
##  <a name="BKMK_RelatedSections"></a> Seções relacionadas  
  
-   [Usando indexadores](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [Indexadores em interfaces](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [Comparação entre propriedades e indexadores](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [Restringindo a acessibilidade ao acessador](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a>Especificação da Linguagem C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Guia de Programação em C#](../../../csharp/programming-guide/index.md)  
 [Propriedades](../../../csharp/programming-guide/classes-and-structs/properties.md)
