---
title: "extremidade do conjunto de associação"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 20810eddda98403d244f6104807504489dde71cc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="association-set-end"></a><span data-ttu-id="f71d8-102">extremidade do conjunto de associação</span><span class="sxs-lookup"><span data-stu-id="f71d8-102">association set end</span></span>
<span data-ttu-id="f71d8-103">Um *final do conjunto de associação* identifica o [tipo de entidade](../../../../docs/framework/data/adonet/entity-type.md) e [conjunto de entidades](../../../../docs/framework/data/adonet/entity-set.md) no final de um [conjunto de associações](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="f71d8-103">An *association set end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) and the [entity set](../../../../docs/framework/data/adonet/entity-set.md) at the end of an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span> <span data-ttu-id="f71d8-104">Termina do conjunto de associações são definidas como parte de um conjunto de associações; um conjunto de associações deve ter exatamente duas termina do conjunto de associações.</span><span class="sxs-lookup"><span data-stu-id="f71d8-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="f71d8-105">Uma definição de final do conjunto de associações contém as informações a seguir:</span><span class="sxs-lookup"><span data-stu-id="f71d8-105">An association set end definition contains the following information:</span></span>  
  
-   <span data-ttu-id="f71d8-106">Um dos tipos de entidade envolvidos no conjunto de associações.</span><span class="sxs-lookup"><span data-stu-id="f71d8-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="f71d8-107">(Necessário)</span><span class="sxs-lookup"><span data-stu-id="f71d8-107">(Required)</span></span>  
  
-   <span data-ttu-id="f71d8-108">O conjunto de entidades para o tipo de entidade envolvido no conjunto de associações.</span><span class="sxs-lookup"><span data-stu-id="f71d8-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="f71d8-109">(Necessário)</span><span class="sxs-lookup"><span data-stu-id="f71d8-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="f71d8-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f71d8-110">Example</span></span>  
 <span data-ttu-id="f71d8-111">O diagrama a seguir mostra um modelo conceitual com duas associações: `WrittenBy` e `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="f71d8-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 <span data-ttu-id="f71d8-112">![Modelo de exemplo](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="f71d8-112">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="f71d8-113">O diagrama a seguir mostra um conjunto de associações (`PublishedBy`) e dois conjuntos de entidades (`Books` e `Publishers`) com base no modelo conceitual mostrado acima.</span><span class="sxs-lookup"><span data-stu-id="f71d8-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="f71d8-114">Termina do conjunto de associações são conjuntos de entidades de `Books` e de `Publishers` .</span><span class="sxs-lookup"><span data-stu-id="f71d8-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="f71d8-115">BI no `Books` conjunto de entidade representa uma ocorrência da `Book` tipo de entidade em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="f71d8-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="f71d8-116">Da mesma forma, Pj representa um `Publisher` de instância de `Publishers` conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="f71d8-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="f71d8-117">BiPj representa uma ocorrência da `PublishedBy` associação no `PublishedBy` conjunto de associações.</span><span class="sxs-lookup"><span data-stu-id="f71d8-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 <span data-ttu-id="f71d8-118">![Exemplo](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span><span class="sxs-lookup"><span data-stu-id="f71d8-118">![Sets Example](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span></span>  
  
 <span data-ttu-id="f71d8-119">O [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa uma DSL chamada linguagem de definição de esquema conceitual ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir modelos conceituais.</span><span class="sxs-lookup"><span data-stu-id="f71d8-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="f71d8-120">CSDL seguir define um contêiner de entidade com um conjunto de associações para cada associação no diagrama anterior.</span><span class="sxs-lookup"><span data-stu-id="f71d8-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="f71d8-121">Observe que termina do conjunto de associações são definidas como parte de cada definição do conjunto de associações.</span><span class="sxs-lookup"><span data-stu-id="f71d8-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="f71d8-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f71d8-122">See Also</span></span>  
 [<span data-ttu-id="f71d8-123">Conceitos chave do modelo de dados de entidade</span><span class="sxs-lookup"><span data-stu-id="f71d8-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="f71d8-124">Modelo de dados de entidade</span><span class="sxs-lookup"><span data-stu-id="f71d8-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)