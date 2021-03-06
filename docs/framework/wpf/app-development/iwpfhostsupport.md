---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 51964358d27a16d9840e29be06c11f57de2fad23
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548188"
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
Aplicativos que hospedam conteúdo [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] via PresentationHost.exe implementam essa interface para fornecer um ponto de integração entre o host e PresentationHost.exe.  
  
## <a name="remarks"></a>Comentários  
 Aplicativos [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], como navegadores da Web podem hospedar conteúdo [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)], incluindo [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] e XAML avulsos. Para hospedar conteúdo [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)], os aplicativos [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] criam uma instância do [controle WebBrowser](http://go.microsoft.com/fwlink/?LinkId=97911). Para ser hospedado, o [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] cria uma instância de PresentationHost.exe, que fornece o conteúdo [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] hospedado para o host para exibição no [controle WebBrowser](http://go.microsoft.com/fwlink/?LinkId=97911).  
  
 A integração habilitada por `IWpfHostSupport` permite ao PresentationHost.exe:  
  
-   Descobrir e registrar os dispositivos de dados brutos (dispositivos de interface humana) no qual o aplicativo host está interessado.  
  
-   Receber mensagens de entrada de dispositivos de dados brutos registrados e encaminhar as mensagens apropriadas ao aplicativo host.  
  
-   Consultar o aplicativo host para interfaces do usuário de andamento e de erro personalizadas.  
  
> [!NOTE]
>  Esta API é destinada e tem suporte somente para uso no computador cliente local  
  
## <a name="members"></a>Membros  
  
|Membro|Descrição|  
|------------|-----------------|  
|[GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)|Permite ao PresentationHost.exe descobrir e registrar os dispositivos de dados brutos (dispositivos de interface humana) no qual o aplicativo host está interessado.|  
|[FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)|Chamado pelo PresentationHost.exe sempre que uma mensagem é recebida, a menos que E_NOTIMPL seja retornado.|  
|[GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)|Por padrão, o PresentationHost.exe fornece suas próprias interfaces do usuário de andamento da implantação e de erro da implantação que são exibidas quando o conteúdo WPF é implantado.|
