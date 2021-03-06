---
title: Adicionando uma referência de serviço em uma solução de fluxo de trabalho
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 01bf4b0040d545ce42a9a7c803767aa4925de75e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488319"
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a>Adicionando uma referência de serviço em uma solução de fluxo de trabalho
Adicionar uma referência de serviço em um aplicativo de fluxo de trabalho funciona um pouco diferente de um aplicativo WCF regular. Quando você seleciona Adicionar referência de serviço e especifique a URL para o serviço de metadados é baixado e atividades personalizadas são geradas que permitem que você chamar o serviço WCF ou serviço de fluxo de trabalho WCF que você adicionou uma referência para. Depois de adicionar uma referência de serviço, recompile a solução para que as atividades geradas são criadas. Em seguida, eles serão exibidos na caixa de ferramentas de designer da fluxo de trabalho. No entanto, observe que isso só funcionará se você estiver adicionando uma referência de serviço dentro de uma solução de fluxo de trabalho. A conversão de web a seguir mostra como adicionar uma referência de serviço em outros tipos de projetos: [chamando um serviço WCF de um fluxo de trabalho em um projeto Web](http://go.microsoft.com/fwlink/?LinkId=207725).  
  
 Adicionando referências de serviço de dois ou mais serviços que contêm o mesmo nome de operação fará com que um problema. As atividades geradas chamará somente a primeira operação de serviço. Para contornar esse problema renomear as operações de serviço para que eles são diferentes, ou alterar o nome da configuração de ponto de extremidade dentro de cada atividade gerado.  
  
## <a name="see-also"></a>Consulte também  
 [Serviços de fluxo de trabalho](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Como criar um serviço de fluxo de trabalho que chama outro serviço de fluxo de trabalho](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-that-calls-another-workflow-service.md)  
 [Chamando um serviço WCF de um fluxo de trabalho em um projeto Web](http://go.microsoft.com/fwlink/?LinkId=207725)
