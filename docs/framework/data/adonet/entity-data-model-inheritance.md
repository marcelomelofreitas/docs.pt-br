---
title: 'Modelo de Dados de Entidade: Herança'
ms.date: 03/30/2017
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
ms.openlocfilehash: c5c1b385ea72e48fd70ed5ec0cf8d1c42c1284e4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765263"
---
# <a name="entity-data-model-inheritance"></a>Modelo de Dados de Entidade: Herança
O modelo de dados de entidade (EDM) oferece suporte a herança para [tipos de entidade](../../../../docs/framework/data/adonet/entity-type.md). Herança em EDM é semelhante à herança para classes em idiomas de programação orientada a objeto. Como com classes linguagens orientadas a objeto, em um modelo conceitual você pode definir um tipo de entidade (uma *tipo derivado*) que é herdada de outro tipo de entidade (o *tipo base*). No entanto, ao contrário das classes em programação orientada a objeto, em um modelo conceitual tipo derivado sempre herda todas as [propriedades](../../../../docs/framework/data/adonet/property.md) e [propriedades de navegação](../../../../docs/framework/data/adonet/navigation-property.md) do tipo base. Você não pode substituir propriedades herdadas em um tipo derivado.  
  
 Em um modelo conceitual você pode criar hierarquias de herança em que um tipo derivado herda de outro tipo derivado. O tipo na parte superior da hierarquia (um tipo na hierarquia que não é um tipo derivado) é chamado de *tipo raiz*. Em uma hierarquia de herança, o [chave da entidade](../../../../docs/framework/data/adonet/entity-key.md) devem ser definidos no tipo de raiz.  
  
 Você não pode criar hierarquias de herança em que um tipo derivado herda de mais de um tipo. Por exemplo, em um modelo conceitual com um tipo de entidade de `Book` , você pode definir tipos derivados `FictionBook` e `NonFictionBook` que cada herda de `Book`. No entanto, você não pode então definir um tipo que herdasse dos tipos de `FictionBook` e de `NonFictionBook` .  
  
## <a name="example"></a>Exemplo  
 O diagrama a seguir mostra um modelo conceitual com quatro tipos de entidade: `Book`, `FictionBook`, `Publisher`, e `Author`. O tipo de entidade de `FictionBook` é um tipo derivado, herdando do tipo de entidade de `Book` . O tipo de `FictionBook` herda `ISBN (Key)`, `Title`, e propriedades de `Revision` , e define uma propriedade chamada adicional `Genre`.  
  
 ![Herança](../../../../docs/framework/data/adonet/media/inheritanceexample.gif "InheritanceExample")  
  
 O [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa uma linguagem específica de domínio (DSL) chamada linguagem de definição de esquema conceitual ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir modelos conceituais. CSDL seguir define um tipo de entidade, `FictionBook`, que herda do tipo de `Book` (como no diagrama anterior):  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## <a name="see-also"></a>Consulte também  
 [Principais conceitos do Modelo de Dados de Entidade](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Modelo de Dados de Entidade](../../../../docs/framework/data/adonet/entity-data-model.md)
