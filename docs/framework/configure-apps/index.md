---
title: "Configurando aplicativos usando arquivos de configuração "
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AutoGeneratedOrientationPage
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- security configuration files
- end tags
- configuration files [.NET Framework], application
- machine configuration files
- .NET Framework application configuration, configuration files
- applications [.NET Framework], configuration files
- application configuration files, security
- application configuration files, format
- configuration files [.NET Framework]
- hosts, application
- application configuration files, machine
- ASP.NET, configuring
- configuration files [.NET Framework], security
- application configuration files, about
- application configuration files
- <runtime> element
- start tags
- configuration files [.NET Framework], machine
- configuration files [.NET Framework], format
ms.assetid: 86bd26d3-737e-4484-9782-19b17f34cd1f
caps.latest.revision: 28
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4c4fcd4fbd70e41664cf0f5624a404f83baa6a48
ms.contentlocale: pt-br
ms.lasthandoff: 09/05/2017

---
# <a name="configuring-apps-by-using-configuration-files"></a>Configurando aplicativos usando arquivos de configuração 
O .NET Framework, por meio de arquivos de configuração, fornece aos desenvolvedores e administradores controle e flexibilidade sobre a maneira de executar aplicativos. Os arquivos de configuração são arquivos XML que podem ser alterados quando necessário. Um administrador pode controlar quais recursos protegidos um aplicativo pode acessar, quais versões de assemblies um aplicativo usará e onde os aplicativos e objetos remotos são localizados. Os desenvolvedores podem colocar definições em arquivos de configuração, eliminando a necessidade de recompilar um aplicativo sempre que uma configuração é alterada. Esta seção descreve o que pode ser configurado e por que a configuração de um aplicativo pode ser útil.  
  
> [!NOTE]
>  O código gerenciado pode usar as classes no namespace <xref:System.Configuration> para ler configurações dos arquivos de configuração, mas não para gravar configurações nesses arquivos.  
  
 Este tópico descreve a sintaxe dos arquivos de configuração e fornece informações sobre os três tipos de arquivos de configuração: computador, aplicativo e segurança.  
  
## <a name="configuration-file-format"></a>Formato do arquivo de configuração  
 Os arquivos de configuração contêm elementos que são estruturas de dados lógicas que definem informações de configuração. Em um arquivo de configuração, você usa marcas para marcar o início e o fim de um elemento. Por exemplo, o elemento `<runtime>` consiste em `<runtime>`*elementos filho*`</runtime>`. Um elemento vazio seria escrito como `<runtime/>` ou `<runtime>``</runtime>`.  
  
 Como com todos os arquivos XML, a sintaxe em arquivos de configuração diferencia maiúsculas de minúsculas.  
  
 Você especifica configurações usando atributos predefinidos que são pares de nome/valor na marca inicial de um elemento. O exemplo a seguir especifica dois atributos (`version` e `href`) para o elemento `<codeBase>` que especifica onde o tempo de execução pode localizar um assembly (para obter mais informações, consulte [Especificando o local de um assembly](../../../docs/framework/configure-apps/specify-assembly-location.md)).  
  
```xml  
<codeBase version="2.0.0.0"  
          href="http://www.litwareinc.com/myAssembly.dll"/>  
```  
  
## <a name="machine-configuration-files"></a>Arquivos de configuração de computador  
 O arquivo de configuração do computador, Machine.config, contém configurações que se aplicam a um computador inteiro. Esse arquivo está localizado no diretório %*runtime install path*%\Config. Machine.config contém as definições de configuração para associação de assembly em todo o computador, [canais remotos](http://msdn.microsoft.com/en-us/6e9b60e0-9bc0-47b4-a8ef-3b78585f9a18) internos e ASP.NET.  
  
 O sistema de configuração primeiro procura o [elemento **\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/index.md) no arquivo de configuração do computador e outras seções de configuração que um desenvolvedor pode definir. Em seguida, ele examina o arquivo de configuração de aplicativo. Para manter o arquivo de configuração do computador gerenciável, é melhor colocar essas configurações no arquivo de configuração de aplicativo. No entanto, colocar as configurações no arquivo de configuração do computador pode tornar seu sistema mais sustentável. Por exemplo, se você tiver um componente de terceiros que seu aplicativo para cliente e servidor use, será mais fácil colocar as configurações para esse componente em um local. Nesse caso, o arquivo de configuração do computador será o local apropriado para as configurações de forma que você não terá as mesmas configurações em dois arquivos diferentes.  
  
> [!NOTE]
>  Implantar um aplicativo que use XCOPY não copiará as configurações no arquivo de configuração do computador.  
  
 Para obter mais informações de como o Common Language Runtime usa o arquivo de configuração do computador para a associação de assembly, consulte [Como o tempo de execução localiza assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
## <a name="application-configuration-files"></a>Arquivos de configuração de aplicativo  
 Um arquivo de configuração de aplicativo contém configurações específicas para um aplicativo. Esse arquivo inclui configurações que o Common Language Runtime lê (como política de associação de assembly, objetos remotos e assim por diante), além das configurações que o aplicativo pode ler.  
  
 O nome e o local do arquivo de configuração de aplicativo dependem do host do aplicativo que pode ser um dos seguintes:  
  
-   Aplicativo hospedado em executável.  
  
     Esses aplicativos têm dois arquivos de configuração: um arquivo de configuração de origem, que é modificado pelo desenvolvedor durante o desenvolvimento, e um arquivo de saída que é distribuído com o aplicativo.  
  
     Ao desenvolver no Visual Studio, coloque o arquivo de configuração de origem do aplicativo no diretório do projeto e defina sua propriedade **Copiar para Diretório de Saída** como **Copiar sempre** ou **Copiar se for mais novo**. O nome do arquivo de configuração é o nome do aplicativo com uma extensão .config. Por exemplo, um aplicativo chamado myApp.exe deve ter um arquivo de configuração de origem chamado myApp.exe.config.  
  
     O Visual Studio copia automaticamente o arquivo de configuração de origem para o diretório onde o assembly compilado é colocado para criar o arquivo de configuração de saída que é implantado com o aplicativo. Em alguns casos, o Visual Studio pode modificar o arquivo de configuração de saída. Para obter mais informações, consulte a seção [Redirecting assembly versions at the app level](../../../docs/framework/configure-apps/redirect-assembly-versions.md#BKMK_Redirectingassemblyversionsattheapplevel) (Redirecionando versões de assembly no nível do aplicativo) do artigo [Redirecting Assembly Versions](../../../docs/framework/configure-apps/redirect-assembly-versions.md) (Redirecionando versões de assembly).  
  
-   Aplicativo hospedado no ASP.NET.  
  
     Para obter mais informações sobre arquivos de configuração do ASP.NET, consulte [Definições de configuração do ASP.NET](http://msdn.microsoft.com/en-us/116608f3-c03d-4413-9fc7-978703e18b0f)  
  
-   Aplicativo hospedado no Internet Explorer.  
  
     Se um aplicativo hospedado no Internet Explorer possuir um arquivo de configuração, o local desse arquivo será especificado em uma marca `<link>` com a seguinte sintaxe:  
  
     \<link rel="*ConfigurationFileName*" href="*location*">  
  
     Nessa marca, `location` é uma URL para o arquivo de configuração. Isso define a base do aplicativo. O arquivo de configuração deve estar localizado no mesmo site que o aplicativo.  
  
## <a name="security-configuration-files"></a>Arquivos de configuração de segurança  
 Os arquivos de configuração de segurança contêm informações sobre a hierarquia e os conjuntos de permissões do grupo de códigos associados a um nível de política. É altamente recomendável que você use a [ferramenta Política de Segurança de Acesso a Códigos (Caspol.exe)](../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md) para modificar a política de segurança a fim de garantir que as alterações de política não corrompam os arquivos de configuração de segurança.  
  
> [!NOTE]
>  A partir do [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], os arquivos de configuração de segurança estarão presentes somente se a política de segurança tiver sido alterada.  
  
 Os arquivos de configuração de segurança estão nos seguintes locais:  
  
-   Arquivo de configuração de política empresarial: %*runtime-install-path*%\Config\Enterprisesec.config  
  
-   Arquivo de configuração de política de computador: %*runtime-install-path*%\Config\Security.config  
  
-   Arquivo de configuração de política de usuário: %USERPROFILE%\Application data\Microsoft\CLR security config\v*xx.xx*\Security.config  
  
## <a name="in-this-section"></a>Nesta seção  
 [Como localizar assemblies usando DEVPATH](../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)  
 Descreve como direcionar o tempo de execução para usar a variável de ambiente DEVPATH ao procurar por assemblies.  
  
 [Redirecionando versões de assembly](../../../docs/framework/configure-apps/redirect-assembly-versions.md)  
 Descreve como especificar o local de um assembly e qual versão de um assembly será usada.  
  
 [Especificando o local de um assembly](../../../docs/framework/configure-apps/specify-assembly-location.md)  
 Descreve como especificar onde o tempo de execução deve pesquisar um assembly.  
  
 [Configurando classes de criptografia](../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 Descreve como mapear um nome de algoritmo para uma classe de criptografia e um identificador de objeto para um algoritmo de criptografia.  
  
 [Como criar uma política de editor](../../../docs/framework/configure-apps/how-to-create-a-publisher-policy.md)  
 Descreve quando e como você deve adicionar um arquivo de política de editor para especificar as configurações de base de redirecionamento e código de assembly.  
  
 [Esquema de arquivos de configuração](../../../docs/framework/configure-apps/file-schema/index.md)  
 Descreve a hierarquia de esquema de inicialização, tempo de execução, rede e outros tipos de parâmetros de configuração.  
  
## <a name="see-also"></a>Consulte também  
 [Esquema de arquivo de configuração](../../../docs/framework/configure-apps/file-schema/index.md)   
 [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md)  (Especificando o local de um assembly)  
 [Redirecting Assembly Versions](../../../docs/framework/configure-apps/redirect-assembly-versions.md)  (Redirecionando versões de assembly)  
 [Registering Remote Objects Using Configuration Files](http://msdn.microsoft.com/en-us/bc503ee1-c811-4f82-9525-470343326adc)  (Registrando objetos remotos usando arquivos de configuração)  
 [Administração de site ASP.NET](http://msdn.microsoft.com/library/1298034b-5f7d-464d-abd1-ad9e6b3eeb7e)   
 [NIB: gerenciamento de política de segurança](http://msdn.microsoft.com/en-us/d754e05d-29dc-4d3a-a2c2-95eaaf1b82b9)   
 [Caspol.exe (Ferramenta de Política de Segurança de Acesso de Código)](../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md)   
 [Assemblies no Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)   
 [Objetos remotos](http://msdn.microsoft.com/en-us/515686e6-0a8d-42f7-8188-73abede57c58)
