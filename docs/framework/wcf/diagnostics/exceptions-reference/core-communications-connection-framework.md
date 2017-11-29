---
title: "Comunicações principais: estrutura de conexão"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61ee00e1-896d-47c8-942f-1db28ac89cdc
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c485c05c1c54a19a102a8378dc79c908a29aa658
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="core-communications-connection-framework"></a>Comunicações principais: estrutura de conexão
Este tópico lista todas as exceções geradas pelo [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Framework de Conexão.  
  
## <a name="exception-list"></a>Lista de exceções  
  
|Código do recurso|Cadeia de caracteres de recurso|  
|-------------------|---------------------|  
|CloseTimedOut|O método Close atingiu o tempo limite após o período especificado. Aumente o valor de tempo limite que é passado para a chamada para fechar ou aumente o valor de CloseTimeout na associação. O tempo determinado para essa operação pode ter sido uma parte de um tempo limite maior.|  
|ContentTypeMismatch|O tipo de conteúdo especificado foi enviado a um serviço que estava esperando especificado. As associações de cliente e serviço talvez não sejam compatíveis.|  
|DuplexChannelAbortedDuringOpen|O canal duplex para especificado foi finalizado durante o processo de abertura.|  
|FramingValueNotAvailable|O valor não pode ser acessado porque ele não é totalmente decodificado.|  
|OperationAbortedDuringConnectionEstablishment|A operação foi encerrada ao estabelecer uma conexão especificado.|  
|ReceiveTimedOut2|A operação de recebimento expirou após o período especificado. O tempo determinado para essa operação pode ter sido uma parte de um tempo limite maior.|  
|SendCannotBeCalledAfterCloseOutputSession|Você não pode enviar mensagens em um canal após CloseOutputSession ter sido chamado.|