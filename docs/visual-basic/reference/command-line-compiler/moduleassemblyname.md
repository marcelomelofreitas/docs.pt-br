---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 479f9f639548eb81351d1df3f8f08b29b393cba1
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43257243"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname
Especifica o nome do assembly do qual esse módulo fará parte.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Arguments  
  
|Termo|Definição|  
|---|---|  
|`assembly_name`|O nome do assembly que esse módulo fará parte.|  
  
## <a name="remarks"></a>Comentários  
 O compilador processa os `-moduleassemblyname` somente se de opção a `-target:module` opção foi especificada. Isso faz com que o compilador crie um módulo. O módulo criado pelo compilador é válido somente para o conjunto especificado com o `-moduleassemblyname` opção. Se você colocar o módulo em um assembly diferente, ocorrerão erros de tempo de execução.  
  
 O `-moduleassemblyname` opção é necessária somente quando as seguintes condições forem verdadeiras:  
  
-   Um tipo de dados no módulo precisa acessar um `Friend` tipo em um assembly referenciado.  
  
-   O assembly referenciado concedeu acesso de assembly amigável para o assembly no qual o módulo será compilado.  
  
 Para obter mais informações sobre como criar um módulo, consulte [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Para obter mais informações sobre assemblies amigáveis, consulte [Assemblies amigáveis](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).  
  
> [!NOTE]
>  O `-moduleassemblyname` opção não está disponível no ambiente de desenvolvimento do Visual Studio; ele está disponível apenas quando você compila em um prompt de comando.  
  
## <a name="see-also"></a>Consulte também  
 [Como Compilar um Assembly de Vários Arquivos](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [Compilador de linha de comando do Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [-main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [-referência (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [Assemblies e o Cache de Assembly Global](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Linhas de Comando de Compilação de Exemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Assemblies Amigáveis](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)
