---
title: "Personalizando a aparência de um controle existente criando um ControlTemplate"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.assetid: 678dd116-43a2-4b8c-82b5-6b826f126e31
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c5455007e407bf4320355aebfd043bfc056d6d56
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2017
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>Personalizando a aparência de um controle existente criando um ControlTemplate
<a name="introduction"></a>Um <xref:System.Windows.Controls.ControlTemplate> Especifica a estrutura visual e o comportamento visual de um controle. Você pode personalizar a aparência de um controle, fornecendo it um novo <xref:System.Windows.Controls.ControlTemplate>. Quando você cria um <xref:System.Windows.Controls.ControlTemplate>, substitua a aparência de um controle existente sem alterar sua funcionalidade. Por exemplo, você pode fazer os botões no seu aplicativo arredondamento em vez de forma quadrada padrão, mas ainda gerará o botão de <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.  
  
 Este tópico explica as várias partes de um <xref:System.Windows.Controls.ControlTemplate>, demonstra como criar um simples <xref:System.Windows.Controls.ControlTemplate> para um <xref:System.Windows.Controls.Button>e explica como compreender o contrato de controle de um controle para que você possa personalizar sua aparência. Como criar um <xref:System.Windows.Controls.ControlTemplate> em [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], você pode alterar a aparência de um controle sem gravar qualquer código. Você também pode usar um designer, por exemplo, o Microsoft Expression Blend, para criar modelos de controle personalizado. Este tópico mostra exemplos de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que personalizar a aparência de um <xref:System.Windows.Controls.Button> e lista o exemplo completo no final do tópico. Para obter mais informações sobre como usar o Expression Blend, consulte [Definir o estilo de um controle que dá suporte a modelos](http://go.microsoft.com/fwlink/?LinkId=161153).  
  
 O ilustrações a seguir mostram um <xref:System.Windows.Controls.Button> que usa o <xref:System.Windows.Controls.ControlTemplate> que é criada neste tópico.  
  
 ![Um botão com um modelo de controle personalizado. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Um botão que usa um modelo de controle personalizado  
  
 ![Um botão com uma borda vermelha. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Um botão que usa um modelo de controle personalizado e tem o ponteiro do mouse sobre ele  
  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Pré-requisitos  
 Este tópico presume que você entenda como criar e usar controles e estilos, conforme discutido em [Controles](../../../../docs/framework/wpf/controls/index.md). Os conceitos abordados neste tópico se aplicam a elementos que herdam o <xref:System.Windows.Controls.Control> classe, exceto para o <xref:System.Windows.Controls.UserControl>. Não é possível aplicar uma <xref:System.Windows.Controls.ControlTemplate> para um <xref:System.Windows.Controls.UserControl>.  
  
<a name="when_you_should_create_a_controltemplate"></a>   
## <a name="when-you-should-create-a-controltemplate"></a>Quando você criar um ControlTemplate  
 Controles têm muitas propriedades, como <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, e <xref:System.Windows.Controls.Control.FontFamily%2A>, que você pode definir para especificar diferentes aspectos da aparência do controle, mas as alterações que você pode fazer ao definir essas propriedades são limitadas. Por exemplo, você pode definir o <xref:System.Windows.Controls.Control.Foreground%2A> propriedade para azul e <xref:System.Windows.Controls.Control.FontStyle%2A> em itálico em um <xref:System.Windows.Controls.CheckBox>.  
  
 Sem a capacidade de criar um novo <xref:System.Windows.Controls.ControlTemplate> para controles, todos os controles em cada [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-aplicativo com base terá a mesma aparência geral, o que limita a capacidade de criar um aplicativo com uma aparência personalizada. Por padrão, cada <xref:System.Windows.Controls.CheckBox> tem características semelhantes. Por exemplo, o conteúdo do <xref:System.Windows.Controls.CheckBox> é sempre à direita dos indicadores de seleção, e a marca de seleção é sempre usada para indicar que o <xref:System.Windows.Controls.CheckBox> está selecionado.  
  
 Você cria um <xref:System.Windows.Controls.ControlTemplate> quando você deseja personalizar a aparência do controle além do que as outras propriedades de configuração no controle será feito. No exemplo da <xref:System.Windows.Controls.CheckBox>, suponha que você deseja que o conteúdo da caixa de seleção acima o indicador de seleção e um X para indicar que você deseja o <xref:System.Windows.Controls.CheckBox> está selecionado. Especifique essas alterações no <xref:System.Windows.Controls.ControlTemplate> do <xref:System.Windows.Controls.CheckBox>.  
  
 A ilustração a seguir mostra um <xref:System.Windows.Controls.CheckBox> que usa um padrão <xref:System.Windows.Controls.ControlTemplate>.  
  
 ![Uma caixa de seleção com o modelo de controle padrão. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
Uma caixa de seleção que usa o modelo de controle padrão  
  
 A ilustração a seguir mostra um <xref:System.Windows.Controls.CheckBox> que usa um personalizado <xref:System.Windows.Controls.ControlTemplate> para colocar o conteúdo do <xref:System.Windows.Controls.CheckBox> acima o indicador de seleção e exibe um X quando o <xref:System.Windows.Controls.CheckBox> está selecionado.  
  
 ![Uma caixa de seleção com um modelo de controle personalizado. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
Uma caixa de seleção que usa um modelo de controle personalizado  
  
 O <xref:System.Windows.Controls.ControlTemplate> para o <xref:System.Windows.Controls.CheckBox> neste exemplo é relativamente complexa, assim, este tópico usa um exemplo simples de como criar um <xref:System.Windows.Controls.ControlTemplate> para um <xref:System.Windows.Controls.Button>.  
  
<a name="changing_the_visual_structure_of_a_control"></a>   
## <a name="changing-the-visual-structure-of-a-control"></a>Alterar a estrutura visual de um controle  
 Em [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], um controle geralmente é uma composição <xref:System.Windows.FrameworkElement> objetos. Quando você cria um <xref:System.Windows.Controls.ControlTemplate>, você combina <xref:System.Windows.FrameworkElement> objetos para criar um único controle. Um <xref:System.Windows.Controls.ControlTemplate> deve ter apenas um <xref:System.Windows.FrameworkElement> como seu elemento raiz. O elemento raiz normalmente contém outros <xref:System.Windows.FrameworkElement> objetos. A combinação de objetos compõe a estrutura visual do controle.  
  
 O exemplo a seguir cria um personalizado <xref:System.Windows.Controls.ControlTemplate> para o <xref:System.Windows.Controls.Button>. O <xref:System.Windows.Controls.ControlTemplate> cria a estrutura visual do <xref:System.Windows.Controls.Button>. Este exemplo não altera a aparência do botão quando você move o ponteiro do mouse sobre ele ou clica nele. A alteração da aparência do botão quando ele está em um estado diferente é discutida posteriormente neste tópico.  
  
 Neste exemplo, a estrutura visual consiste das seguintes partes:  
  
-   Um <xref:System.Windows.Controls.Border> chamado `RootElement` que serve como a raiz do modelo <xref:System.Windows.FrameworkElement>.  
  
-   Um <xref:System.Windows.Controls.Grid> que é um filho de `RootElement`.  
  
-   Um <xref:System.Windows.Controls.ContentPresenter> que exibe o conteúdo do botão. O <xref:System.Windows.Controls.ContentPresenter> permite qualquer tipo de objeto a ser exibido.  
  
 [!code-xaml[VSMButtonTemplate#BasicTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]  
  
### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>Preserva a funcionalidade das propriedades de um controle usando TemplateBinding  
 Quando você cria um novo <xref:System.Windows.Controls.ControlTemplate>, ainda deseja usar as propriedades públicas para alterar a aparência do controle. O [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) extensão de marcação associa uma propriedade de um elemento que está no <xref:System.Windows.Controls.ControlTemplate> para uma propriedade pública que é definida pelo controle. Quando você usa [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md), você habilita propriedades do controle para atuar como parâmetros para o modelo. Ou seja, quando uma propriedade em um controle é definida, esse valor é passado para o elemento que contém a [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md).  
  
 O exemplo a seguir repete a parte do exemplo anterior usa o [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) extensão de marcação para vincular as propriedades dos elementos que estão no <xref:System.Windows.Controls.ControlTemplate> para propriedades públicas que são definidas pelo botão.  
  
 [!code-xaml[VSMButtonTemplate#TemplateBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]  
  
 Neste exemplo, o <xref:System.Windows.Controls.Grid> tem seu <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> modelo de propriedade associado ao <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>. Porque <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> é o modelo associado, você pode criar vários botões que usam os mesmos <xref:System.Windows.Controls.ControlTemplate> e defina o <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> como valores diferentes em cada botão. Se <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> modelo não tiver sido associado a uma propriedade de um elemento no <xref:System.Windows.Controls.ControlTemplate>, a definição de <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> de um botão não haveria nenhum impacto sobre a aparência do botão.  
  
 Observe que os nomes das duas propriedades não precisam ser idênticos. No exemplo anterior, o <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> propriedade do <xref:System.Windows.Controls.Button> modelo associado ao <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType> propriedade o <xref:System.Windows.Controls.ContentPresenter>. Isso permite que o conteúdo do botão seja posicionado horizontalmente. <xref:System.Windows.Controls.ContentPresenter>não tem uma propriedade chamada `HorizontalContentAlignment`, mas <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> podem ser associados a <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>. Quando você associar o modelo de uma propriedade, certifique-se de que as propriedades de origem e destino sejam do mesmo tipo.  
  
 O <xref:System.Windows.Controls.Control> classe define várias propriedades que devem ser usadas pelo modelo de controle para ter um efeito sobre o controle quando eles são definidos. Como o <xref:System.Windows.Controls.ControlTemplate> usa a propriedade depende da propriedade. O <xref:System.Windows.Controls.ControlTemplate> deve usar a propriedade de uma das seguintes maneiras:  
  
-   Um elemento de <xref:System.Windows.Controls.ControlTemplate> modelo associa à propriedade.  
  
-   Um elemento de <xref:System.Windows.Controls.ControlTemplate> herda a propriedade de um pai <xref:System.Windows.FrameworkElement>.  
  
 A tabela a seguir lista as propriedades de visual herdadas por um controle do <xref:System.Windows.Controls.Control> classe. Ele também indica se o modelo de controle padrão de um controle usa o valor da propriedade herdada ou se ele deve teu seu modelo associado.  
  
|Propriedade|Método de uso|  
|--------------|------------------|  
|<xref:System.Windows.Controls.Control.Background%2A>|Associação de modelo|  
|<xref:System.Windows.Controls.Control.BorderThickness%2A>|Associação de modelo|  
|<xref:System.Windows.Controls.Control.BorderBrush%2A>|Associação de modelo|  
|<xref:System.Windows.Controls.Control.FontFamily%2A>|Herança de propriedade ou associação de modelo|  
|<xref:System.Windows.Controls.Control.FontSize%2A>|Herança de propriedade ou associação de modelo|  
|<xref:System.Windows.Controls.Control.FontStretch%2A>|Herança de propriedade ou associação de modelo|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|Herança de propriedade ou associação de modelo|  
|<xref:System.Windows.Controls.Control.Foreground%2A>|Herança de propriedade ou associação de modelo|  
|<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>|Associação de modelo|  
|<xref:System.Windows.Controls.Control.Padding%2A>|Associação de modelo|  
|<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>|Associação de modelo|  
  
 A tabela lista apenas as propriedades de visual herdadas da <xref:System.Windows.Controls.Control> classe. As propriedades listadas na tabela, além de um controle também pode herdar o <xref:System.Windows.FrameworkElement.DataContext%2A>, <xref:System.Windows.FrameworkElement.Language%2A>, e <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> propriedades do elemento pai do framework.  
  
 Além disso, se o <xref:System.Windows.Controls.ContentPresenter> está no <xref:System.Windows.Controls.ControlTemplate> de um <xref:System.Windows.Controls.ContentControl>, o <xref:System.Windows.Controls.ContentPresenter> associará automaticamente para o <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> e <xref:System.Windows.Controls.ContentControl.Content%2A> propriedades. Da mesma forma, um <xref:System.Windows.Controls.ItemsPresenter> no <xref:System.Windows.Controls.ControlTemplate> de um <xref:System.Windows.Controls.ItemsControl> associará automaticamente para o <xref:System.Windows.Controls.ItemsControl.Items%2A> e <xref:System.Windows.Controls.ItemsPresenter> propriedades.  
  
 O exemplo a seguir cria dois botões que usam o <xref:System.Windows.Controls.ControlTemplate> definida no exemplo anterior. O exemplo define o <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, e <xref:System.Windows.Controls.Control.FontSize%2A> propriedades em cada botão. Definindo o <xref:System.Windows.Controls.Control.Background%2A> propriedade tem um efeito porque ele é o modelo associado no <xref:System.Windows.Controls.ControlTemplate>. Embora o <xref:System.Windows.Controls.Control.Foreground%2A> e <xref:System.Windows.Controls.Control.FontSize%2A> propriedades não são associado de modelo, configurá-los tem um efeito como seus valores são herdados.  
  
 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]  
  
 O exemplo anterior produz um resultado semelhante ao mostrado na ilustração a seguir.  
  
 ![Dois botões, uma azul e um roxo. ] (../../../../docs/framework/wpf/controls/media/ndp-buttontwo.png "NDP_ButtonTwo")  
Dois botões com cores da tela de fundo diferentes  
  
<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>   
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>Alterar a aparência de um controle dependendo do seu estado  
 A diferença entre um botão com sua aparência padrão e o botão no exemplo anterior é que o botão padrão sofre uma alteração sutil quando ele está em estados diferentes. Por exemplo, a aparência do botão padrão muda quando o botão é pressionado, ou quando o ponteiro do mouse está sobre o botão. Embora o <xref:System.Windows.Controls.ControlTemplate> não altera a funcionalidade de um controle, ele altera o comportamento visual do controle. Um comportamento visual descreve a aparência do controle quando ele está em um determinado estado. Para entender a diferença entre a funcionalidade e o comportamento visual de um controle, considere o exemplo de botão. Funcionalidade do botão é gerar o <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento quando ele for clicado, mas comportamento visual do botão Alterar sua aparência quando ele é apontado ou pressionado.  
  
 Você usa <xref:System.Windows.VisualState> objetos para especificar a aparência de um controle quando ele está em um determinado estado. Um <xref:System.Windows.VisualState> contém um <xref:System.Windows.Media.Animation.Storyboard> que altera a aparência dos elementos que estão na <xref:System.Windows.Controls.ControlTemplate>. Você não precisa escrever nenhum código para que isso ocorra porque a lógica do controle muda de estado usando o <xref:System.Windows.VisualStateManager>. Quando o controle entra no estado especificado pelo <xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType> propriedade, o <xref:System.Windows.Media.Animation.Storyboard> começa. Quando o controle sai do estado, o <xref:System.Windows.Media.Animation.Storyboard> para.  
  
 A exemplo a seguir mostra o <xref:System.Windows.VisualState> que altera a aparência de um <xref:System.Windows.Controls.Button> quando o ponteiro do mouse está sobre ele. O <xref:System.Windows.Media.Animation.Storyboard> altera a cor da borda do botão alterando a cor do `BorderBrush`. Se você se referir a <xref:System.Windows.Controls.ControlTemplate> exemplo no início deste tópico, você deve se lembrar que `BorderBrush` é o nome do <xref:System.Windows.Media.SolidColorBrush> que é atribuído ao <xref:System.Windows.Controls.Border.Background%2A> do <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[VSMButtonTemplate#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]  
  
 O controle é responsável por definir os estados como parte de seu contrato de controle, que é abordado em detalhes em [Personalizar outros controles pela compreensão do contrato de controle](#customizing_other_controls_by_understanding_the_control_contract), mais adiante neste tópico. A tabela a seguir lista os estados que são especificados para o <xref:System.Windows.Controls.Button>.  
  
|Nome do VisualState|Nome do VisualStateGroup|Descrição|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|O estado padrão.|  
|MouseOver|CommonStates|O ponteiro do mouse é posicionado sobre o controle.|  
|Pressionado|CommonStates|O controle é pressionado.|  
|Disabled|CommonStates|O controle está desabilitado.|  
|Focalizado|FocusStates|O controle tem foco.|  
|Sem foco|FocusStates|O controle não tem foco.|  
  
 O <xref:System.Windows.Controls.Button> define dois grupos de estado: o `CommonStates` grupo contém o `Normal`, `MouseOver`, `Pressed`, e `Disabled` estados. O grupo `FocusStates` contém os estados `Focused` e `Unfocused`. Os estados no mesmo grupo de estados são mutuamente excludentes. O controle está sempre em exatamente um estado por grupo. Por exemplo, um <xref:System.Windows.Controls.Button> pode ter o foco, mesmo quando o ponteiro do mouse não está sobre ele, então um <xref:System.Windows.Controls.Button> no `Focused` estado pode estar no `MouseOver`, `Pressed`, ou `Normal` estado.  
  
 Adicionar <xref:System.Windows.VisualState> objetos <xref:System.Windows.VisualStateGroup> objetos. Adicionar <xref:System.Windows.VisualStateGroup> objetos para o <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> propriedade anexada. O exemplo a seguir define o <xref:System.Windows.VisualState> objetos para o `Normal`, `MouseOver`, e `Pressed` estados, que estão todos no `CommonStates` grupo. O <xref:System.Windows.VisualState.Name%2A> de cada <xref:System.Windows.VisualState> corresponde ao nome na tabela anterior. O estado `Disabled` e os estados no grupo `FocusStates` são omitidos para manter a brevidade do exemplo, mas eles estão incluídos no exemplo inteiro no final deste tópico.  
  
> [!NOTE]
>  Certifique-se de definir o <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> anexado a propriedade na raiz <xref:System.Windows.FrameworkElement> do <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[VSMButtonTemplate#VisualStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]  
  
 O exemplo anterior produz um resultado semelhante ao mostrado nas ilustrações a seguir.  
  
 ![Um botão com um modelo de controle personalizado. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Um botão que usa um modelo de controle personalizado no estado normal  
  
 ![Um botão com uma borda vermelha. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Um botão que usa um modelo de controle personalizado no estado de passar o mouse  
  
 ![A borda é transparente em um botão pressionado. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonpressed.png "NDP_ButtonPressed")  
Um botão que usa um modelo de controle personalizado no estado pressionado  
  
 Para localizar os estados visuais para controles incluídos no [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Estilos e modelos de controle](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>   
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>Especificar o comportamento de um controle quando ele faz a transição entre estados  
 No exemplo anterior, a aparência do botão também será alterada quando o usuário clicar nele; no entanto, se o usuário não pressionar o botão por um segundo completo, ele não verá o efeito. Por padrão, a animação dura um segundo. Como os usuários devem clicar e liberar um botão em muito menos tempo, os comentários visuais não será eficaz se você deixar o <xref:System.Windows.Controls.ControlTemplate> em seu estado padrão.  
  
 Você pode especificar a quantidade de tempo que leva uma animação para transição suave de um controle de um estado para outro adicionando <xref:System.Windows.VisualTransition> objetos para o <xref:System.Windows.Controls.ControlTemplate>. Quando você cria um <xref:System.Windows.VisualTransition>, você especificar um ou mais dos seguintes:  
  
-   O tempo que leva para que uma transição entre estados ocorra.  
  
-   Alterações adicionais na aparência do controle que ocorrem durante a transição.  
  
-   Quais estados de <xref:System.Windows.VisualTransition> é aplicado a.  
  
### <a name="specifying-the-duration-of-a-transition"></a>Especificar a duração de uma transição  
 Você pode especificar quanto tempo leva uma transição definindo o <xref:System.Windows.VisualTransition.GeneratedDuration%2A> propriedade. O exemplo anterior tem um <xref:System.Windows.VisualState> que especifica que a borda do botão fica transparente quando o botão for pressionado, mas a animação demora muito para ser observadas se o botão é pressionado e liberado rapidamente. Você pode usar um <xref:System.Windows.VisualTransition> para especificar a quantidade de tempo levará o controle para fazer a transição para o estado pressionado. O exemplo a seguir especifica que o controle utiliza um centésimo de segundo para ir para o estado pressionado.  
  
 [!code-xaml[VSMButtonTemplate#PressedTransition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]  
  
### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>Especificar alterações à aparência do controle durante uma transição  
 O <xref:System.Windows.VisualTransition> contém um <xref:System.Windows.Media.Animation.Storyboard> que começa quando o controle faz a transição entre estados. Por exemplo, você pode especificar que uma determinada animação ocorre quando o controle faz a transição do estado `MouseOver` para o estado `Normal`. O exemplo a seguir cria um <xref:System.Windows.VisualTransition> que especifica que quando o usuário move o ponteiro do mouse fora do botão, a borda do botão muda para azul, em seguida, amarelo e preto em 1,5 segundos.  
  
 [!code-xaml[VSMButtonTemplate#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]  
  
### <a name="specifying-when-a-visualtransition-is-applied"></a>Especificar quando uma VisualTransition é aplicada  
 Um <xref:System.Windows.VisualTransition> podem ser restringidas para aplicar a somente alguns estados, ou ele pode ser aplicado a qualquer momento as transições de controle entre estados. No exemplo anterior, o <xref:System.Windows.VisualTransition> é aplicado quando o controle sai do `MouseOver` estado para o `Normal` estado; no exemplo antes disso, o <xref:System.Windows.VisualTransition> é aplicado quando o controle entra no `Pressed` estado. Restringir quando um <xref:System.Windows.VisualTransition> é aplicado, definindo o <xref:System.Windows.VisualTransition.To%2A> e <xref:System.Windows.VisualTransition.From%2A> propriedades. A tabela a seguir descreve os níveis de restrição do mais restritivo para o menos restritivo.  
  
|Tipo de restrição|Valor de|Valor de|  
|-------------------------|-------------------|-----------------|  
|De um estado especificado para outro estado especificado|O nome de um<xref:System.Windows.VisualState>|O nome de um<xref:System.Windows.VisualState>|  
|De qualquer estado para um estado especificado|Não definido|O nome de um<xref:System.Windows.VisualState>|  
|De um estado especificado para qualquer estado|O nome de um<xref:System.Windows.VisualState>|Não definido|  
|De qualquer estado de qualquer outro estado|Não definido|Não definido|  
  
 Você pode ter várias <xref:System.Windows.VisualTransition> objetos em um <xref:System.Windows.VisualStateGroup> que se referem ao mesmo estado, mas eles serão usados na ordem em que especifica a tabela anterior. O exemplo a seguir, há dois <xref:System.Windows.VisualTransition> objetos. Quando o controle faz a transição do `Pressed` estado para o `MouseOver` estado, o <xref:System.Windows.VisualTransition> que tem ambos <xref:System.Windows.VisualTransition.From%2A> e <xref:System.Windows.VisualTransition.To%2A> conjunto é usado. Quando o controle faz a transição de um estado diferente de `Pressed` para o estado `MouseOver`, o outro estado é usado.  
  
 [!code-xaml[VSMButtonTemplate#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]  
  
 O <xref:System.Windows.VisualStateGroup> tem um <xref:System.Windows.VisualStateGroup.Transitions%2A> propriedade que contém o <xref:System.Windows.VisualTransition> objetos que se aplicam ao <xref:System.Windows.VisualState> objetos no <xref:System.Windows.VisualStateGroup>. Como o <xref:System.Windows.Controls.ControlTemplate> autor, você é livre para incluir quaisquer <xref:System.Windows.VisualTransition> desejado. No entanto, se o <xref:System.Windows.VisualTransition.To%2A> e <xref:System.Windows.VisualTransition.From%2A> propriedades são definidas como nomes de estado que não estão no <xref:System.Windows.VisualStateGroup>, o <xref:System.Windows.VisualTransition> será ignorado.  
  
 A exemplo a seguir mostra o <xref:System.Windows.VisualStateGroup> para o `CommonStates`. O exemplo define um <xref:System.Windows.VisualTransition> para cada uma das seguintes do botão fará a transição.  
  
-   Para o estado `Pressed`.  
  
-   Para o estado `MouseOver`.  
  
-   Do estado `Pressed` para o estado `MouseOver`.  
  
-   Do estado `MouseOver` para o estado `Normal`.  
  
 [!code-xaml[VSMButtonTemplate#VisualTransitions](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]  
  
<a name="customizing_other_controls_by_understanding_the_control_contract"></a>   
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>Personalizar de outros controles pela compreensão do contrato de controle  
 Um controle que usa um <xref:System.Windows.Controls.ControlTemplate> para especificar sua estrutura visual (usando <xref:System.Windows.FrameworkElement> objetos) e o comportamento visual (usando <xref:System.Windows.VisualState> objetos) usa o modelo de controle de partes. Muitos dos controles que estão incluídos no [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4 usam esse modelo. As partes que um <xref:System.Windows.Controls.ControlTemplate> autor precisa estar ciente das é comunicada por meio do contrato do controle. Quando você compreende as partes de um contrato de controle, você pode personalizar a aparência de qualquer controle que usa o modelo de controle de partes.  
  
 Um contrato de controle contém três elementos:  
  
-   Os elementos visuais usados pela lógica do controle.  
  
-   Os estados do controle e o grupo ao qual cada estado pertence.  
  
-   As propriedades públicas que afetam o controle visualmente.  
  
### <a name="visual-elements-in-the-control-contract"></a>Elementos visuais no contrato de controle  
 Às vezes, a lógica do controle interage com um <xref:System.Windows.FrameworkElement> no <xref:System.Windows.Controls.ControlTemplate>. Por exemplo, o controle pode manipular um evento de um de seus elementos. Quando um controle espera encontrar um determinado <xref:System.Windows.FrameworkElement> no <xref:System.Windows.Controls.ControlTemplate>, ele deve transmitir essas informações para o <xref:System.Windows.Controls.ControlTemplate> autor. O controle usa o <xref:System.Windows.TemplatePartAttribute> para transmitir o tipo de elemento que é esperado e o que deve ser o nome do elemento. O <xref:System.Windows.Controls.Button> não tem <xref:System.Windows.FrameworkElement> partes no seu contrato de controle, mas outros controles, como o <xref:System.Windows.Controls.ComboBox>, fazer.  
  
 A exemplo a seguir mostra o <xref:System.Windows.TemplatePartAttribute> objetos que são especificados no <xref:System.Windows.Controls.ComboBox> classe. A lógica de <xref:System.Windows.Controls.ComboBox> espera encontrar um <xref:System.Windows.Controls.TextBox> chamado `PART_EditableTextBox` e um <xref:System.Windows.Controls.Primitives.Popup> chamado `PART_Popup` em seu <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-csharp[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]  
  
 O exemplo a seguir mostra um simplificado <xref:System.Windows.Controls.ControlTemplate> para o <xref:System.Windows.Controls.ComboBox> que inclui os elementos que são especificados pelo <xref:System.Windows.TemplatePartAttribute> objetos a <xref:System.Windows.Controls.ComboBox> classe.  
  
 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]  
  
### <a name="states-in-the-control-contract"></a>Estados no contrato de controle  
 Os estados de um controle também são uma parte do contrato de controle. O exemplo de como criar um <xref:System.Windows.Controls.ControlTemplate> para um <xref:System.Windows.Controls.Button> mostra como especificar a aparência de um <xref:System.Windows.Controls.Button> dependendo de seus estados. Criar um <xref:System.Windows.VisualState> para cada estado de especificado e coloque todos os <xref:System.Windows.VisualState> objetos que compartilham uma <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> em uma <xref:System.Windows.VisualStateGroup>, conforme descrito em [alterando a aparência de um controle dependendo de seu estado](#changing_the_appearance_of_a_control_depending_on_its_state) anteriores neste tópico. Controles de terceiros devem especificar estados usando o <xref:System.Windows.TemplateVisualStateAttribute>, que permite que as ferramentas de designer, como o Expression Blend para expor os estados do controle para a criação de modelos de controle.  
  
 Para localizar o contrato de controle para controles incluídos no [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Estilos e modelos de controle](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
### <a name="properties-in-the-control-contract"></a>Propriedades no contrato de controle  
 As propriedades públicas que afetam visualmente o controle também estão incluídas no contrato de controle. Você pode definir essas propriedades para alterar a aparência do controle sem criar um novo <xref:System.Windows.Controls.ControlTemplate>. Você também pode usar o [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) extensão de marcação para vincular as propriedades dos elementos que estão no <xref:System.Windows.Controls.ControlTemplate> para propriedades públicas que são definidas pelo <xref:System.Windows.Controls.Button>.  
  
 O exemplo a seguir mostra o contrato de controle do botão.  
  
 [!code-csharp[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]  
  
 Ao criar um <xref:System.Windows.Controls.ControlTemplate>, geralmente é mais fácil começar com uma existente <xref:System.Windows.Controls.ControlTemplate> e fazer alterações nele. Você pode fazer um dos procedimentos a seguir para alterar uma já existente <xref:System.Windows.Controls.ControlTemplate>:  
  
-   Usar um designer como o Expression Blend, que fornece uma interface do usuário gráfica para criar modelos de controle. Para obter mais informações, consulte [Definir o estilo de um controle que dá suporte a modelos](http://go.microsoft.com/fwlink/?LinkId=161153).  
  
-   Obter o padrão <xref:System.Windows.Controls.ControlTemplate> e editá-lo. Para localizar os modelos de controle padrão que estão inclusos no [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Temas padrão do WPF](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>Exemplo completo  
 O exemplo a seguir mostra o completo <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.ControlTemplate> que é discutido neste tópico.  
  
 [!code-xaml[VSMButtonTemplate#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]  
  
## <a name="see-also"></a>Consulte também  
 [Estilo e modelagem](../../../../docs/framework/wpf/controls/styling-and-templating.md)