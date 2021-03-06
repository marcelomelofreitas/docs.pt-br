---
title: '&lt;legacyCorruptedStateExceptionsPolicy&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6228aaf4c7da70337d9d1a99adcb78f71a0039b2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744610"
---
# <a name="ltlegacycorruptedstateexceptionspolicygt-element"></a>&lt;legacyCorruptedStateExceptionsPolicy&gt; elemento
Especifica se o common language runtime permite que o código gerenciado detectar violações de acesso e outras exceções de estado corrompido.  
  
 \<configuration>  
\<runtime>  
\<legacyCorruptedStateExceptionsPolicy >  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|`enabled`|Atributo obrigatório.<br /><br /> Especifica que o aplicativo irá detectar a corrupção de falhas de exceção de estado, como violações de acesso.|  
  
## <a name="enabled-attribute"></a>Atributo habilitado  
  
|Valor|Descrição|  
|-----------|-----------------|  
|`false`|O aplicativo não capturará corrupção de falhas de exceção de estado, como violações de acesso. Esse é o padrão.|  
|`true`|O aplicativo irá detectar a corrupção de falhas de exceção de estado, como violações de acesso.|  
  
### <a name="child-elements"></a>Elementos filho  
 nenhuma.  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|`configuration`|O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.|  
|`runtime`|Contém informações sobre associação do assembly e coleta de lixo.|  
  
## <a name="remarks"></a>Comentários  
 No .NET Framework versão 3.5 e anteriores, o common language runtime permitido código gerenciado para capturar exceções que foram geradas pelo processo corrompido estados. Uma violação de acesso é um exemplo desse tipo de exceção.  
  
 Começando com o [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]gerenciado código não captura esses tipos de exceções em `catch` blocos. No entanto, você pode substituir essa alteração e manter o tratamento de exceções de estado corrompido de duas maneiras:  
  
-   Definir o `<legacyCorruptedStateExceptionsPolicy>` do elemento `enabled` atributo `true`. Esta configuração é aplicada processwide e afeta todos os métodos.  
  
 -ou-  
  
-   Aplicar o <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> de atributo para o método que contém as exceções `catch` bloco.  
  
 Este elemento de configuração está disponível apenas no [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] e posterior.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir mostra como especificar que o aplicativo deve ser revertida para o comportamento antes do [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]e catch corrompido todas as falhas de exceção de estado.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>  
 [Esquema de configurações do tempo de execução](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de arquivos de configuração](../../../../../docs/framework/configure-apps/file-schema/index.md)
