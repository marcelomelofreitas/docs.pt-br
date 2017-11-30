---
title: "Visão geral de gráficos vetoriais"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7bb3247f531a0dac83657e118fb53ebaf708ec9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="vector-graphics-overview"></a><span data-ttu-id="5ce71-102">Visão geral de gráficos vetoriais</span><span class="sxs-lookup"><span data-stu-id="5ce71-102">Vector Graphics Overview</span></span>
<span data-ttu-id="5ce71-103">O [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] desenha linhas, retângulos e outras formas em um sistema de coordenadas.</span><span class="sxs-lookup"><span data-stu-id="5ce71-103">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] draws lines, rectangles, and other shapes on a coordinate system.</span></span> <span data-ttu-id="5ce71-104">Você pode escolher entre uma variedade de sistemas de coordenadas, mas o sistema de coordenadas padrão tem origem no canto superior esquerdo, com o eixo x apontando para a direita e o eixo y apontando para baixo.</span><span class="sxs-lookup"><span data-stu-id="5ce71-104">You can choose from a variety of coordinate systems, but the default coordinate system has the origin in the upper-left corner with the x-axis pointing to the right and the y-axis pointing down.</span></span> <span data-ttu-id="5ce71-105">A unidade de medida no sistema de coordenadas padrão é o pixel.</span><span class="sxs-lookup"><span data-stu-id="5ce71-105">The unit of measure in the default coordinate system is the pixel.</span></span>  
  
## <a name="the-building-blocks-of-gdi"></a><span data-ttu-id="5ce71-106">Os blocos de construção da GDI+</span><span class="sxs-lookup"><span data-stu-id="5ce71-106">The Building Blocks of GDI+</span></span>  
 <span data-ttu-id="5ce71-107">![Gráfico vetorial](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span><span class="sxs-lookup"><span data-stu-id="5ce71-107">![Vector graphic](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span></span>  
  
 <span data-ttu-id="5ce71-108">Um monitor de computador cria sua exibição em uma matriz retangular de pontos chamados de elementos de imagem ou pixels.</span><span class="sxs-lookup"><span data-stu-id="5ce71-108">A computer monitor creates its display on a rectangular array of dots called picture elements or pixels.</span></span> <span data-ttu-id="5ce71-109">O número de pixels que aparecem na tela varia de um monitor para outro e o número de pixels que aparecem em um monitor individual normalmente pode ser configurado em alguma medida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="5ce71-109">The number of pixels that appear on the screen varies from one monitor to the next, and the number of pixels that appear on an individual monitor can usually be configured to some extent by the user.</span></span>  
  
 <span data-ttu-id="5ce71-110">![Gráfico vetorial](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span><span class="sxs-lookup"><span data-stu-id="5ce71-110">![Vector graphic](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span></span>  
  
 <span data-ttu-id="5ce71-111">Quando você usa [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] para desenhar uma linha, um retângulo ou uma curva, fornece determinadas informações importantes sobre o item a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="5ce71-111">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, rectangle, or curve, you provide certain key information about the item to be drawn.</span></span> <span data-ttu-id="5ce71-112">Por exemplo, você pode especificar uma linha fornecendo dois pontos e especificar um retângulo fornecendo um ponto, uma altura e uma largura.</span><span class="sxs-lookup"><span data-stu-id="5ce71-112">For example, you can specify a line by providing two points, and you can specify a rectangle by providing a point, a height, and a width.</span></span> <span data-ttu-id="5ce71-113">O [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funciona em conjunto com o software de driver de vídeo para determinar quais pixels devem ser ativados para mostrar a linha, o retângulo ou a curva.</span><span class="sxs-lookup"><span data-stu-id="5ce71-113">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] works in conjunction with the display driver software to determine which pixels must be turned on to show the line, rectangle, or curve.</span></span> <span data-ttu-id="5ce71-114">A ilustração a seguir mostra os pixels que são ativados para exibir uma linha do ponto (4, 2) ao ponto (12, 8).</span><span class="sxs-lookup"><span data-stu-id="5ce71-114">The following illustration shows the pixels that are turned on to display a line from the point (4, 2) to the point (12, 8).</span></span>  
  
 <span data-ttu-id="5ce71-115">![Gráfico vetorial](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span><span class="sxs-lookup"><span data-stu-id="5ce71-115">![Vector graphic](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span></span>  
  
 <span data-ttu-id="5ce71-116">Ao longo do tempo, determinados blocos de construção básicos mostraram ser mais úteis para criar imagens bidimensionais.</span><span class="sxs-lookup"><span data-stu-id="5ce71-116">Over time, certain basic building blocks have proven to be the most useful for creating two-dimensional pictures.</span></span> <span data-ttu-id="5ce71-117">Esses blocos de construção, que têm suporte no [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], são apresentados na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="5ce71-117">These building blocks, which are all supported by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], are given in the following list:</span></span>  
  
-   <span data-ttu-id="5ce71-118">Linhas</span><span class="sxs-lookup"><span data-stu-id="5ce71-118">Lines</span></span>  
  
-   <span data-ttu-id="5ce71-119">Retângulos</span><span class="sxs-lookup"><span data-stu-id="5ce71-119">Rectangles</span></span>  
  
-   <span data-ttu-id="5ce71-120">Elipses</span><span class="sxs-lookup"><span data-stu-id="5ce71-120">Ellipses</span></span>  
  
-   <span data-ttu-id="5ce71-121">Arcos</span><span class="sxs-lookup"><span data-stu-id="5ce71-121">Arcs</span></span>  
  
-   <span data-ttu-id="5ce71-122">Polígonos</span><span class="sxs-lookup"><span data-stu-id="5ce71-122">Polygons</span></span>  
  
-   <span data-ttu-id="5ce71-123">Splines cardinais</span><span class="sxs-lookup"><span data-stu-id="5ce71-123">Cardinal splines</span></span>  
  
-   <span data-ttu-id="5ce71-124">splines de Bézier</span><span class="sxs-lookup"><span data-stu-id="5ce71-124">Bezier splines</span></span>  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a><span data-ttu-id="5ce71-125">Métodos para desenhar com um objeto gráfico</span><span class="sxs-lookup"><span data-stu-id="5ce71-125">Methods For Drawing with a Graphics Object</span></span>  
 <span data-ttu-id="5ce71-126">O <xref:System.Drawing.Graphics> classe em [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornece os seguintes métodos para desenhar os itens na lista anterior: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (para splines cardinais), e <xref:System.Drawing.Graphics.DrawBezier%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ce71-126">The <xref:System.Drawing.Graphics> class in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] provides the following methods for drawing the items in the previous list: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (for cardinal splines), and <xref:System.Drawing.Graphics.DrawBezier%2A>.</span></span> <span data-ttu-id="5ce71-127">Cada um desses métodos está sobrecarregado; ou seja, cada método dá suporte a diferentes listas de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5ce71-127">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="5ce71-128">Por exemplo, uma variação do <xref:System.Drawing.Graphics.DrawLine%2A> método recebe um <xref:System.Drawing.Pen> objeto e quatro inteiros, enquanto outra variação o <xref:System.Drawing.Graphics.DrawLine%2A> método recebe um <xref:System.Drawing.Pen> objeto e dois <xref:System.Drawing.Point> objetos.</span><span class="sxs-lookup"><span data-stu-id="5ce71-128">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers, while another variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="5ce71-129">Os métodos para desenhar linhas, retângulos e splines de Bézier têm métodos plural complementar que se conectam a vários itens em uma única chamada: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, e <xref:System.Drawing.Graphics.DrawBeziers%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ce71-129">The methods for drawing lines, rectangles, and Bézier splines have plural companion methods that draw several items in a single call: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, and <xref:System.Drawing.Graphics.DrawBeziers%2A>.</span></span> <span data-ttu-id="5ce71-130">Além disso, o <xref:System.Drawing.Graphics.DrawCurve%2A> método tem um método complementar, <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, que fecha uma curva conectando o ponto final da curva a partir do ponto.</span><span class="sxs-lookup"><span data-stu-id="5ce71-130">Also, the <xref:System.Drawing.Graphics.DrawCurve%2A> method has a companion method, <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, that closes a curve by connecting the ending point of the curve to the starting point.</span></span>  
  
 <span data-ttu-id="5ce71-131">Todos os métodos de desenho de <xref:System.Drawing.Graphics> classe trabalham em conjunto com um <xref:System.Drawing.Pen> objeto.</span><span class="sxs-lookup"><span data-stu-id="5ce71-131">All of the drawing methods of the <xref:System.Drawing.Graphics> class work in conjunction with a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="5ce71-132">Para desenhar qualquer coisa, você deve criar pelo menos dois objetos: um <xref:System.Drawing.Graphics> objeto e um <xref:System.Drawing.Pen> objeto.</span><span class="sxs-lookup"><span data-stu-id="5ce71-132">To draw anything, you must create at least two objects: a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="5ce71-133">O <xref:System.Drawing.Pen> objeto armazena atributos, como largura da linha e a cor do item a ser desenhada.</span><span class="sxs-lookup"><span data-stu-id="5ce71-133">The <xref:System.Drawing.Pen> object stores attributes, such as line width and color, of the item to be drawn.</span></span> <span data-ttu-id="5ce71-134">O <xref:System.Drawing.Pen> objeto é passado como um dos argumentos para o método de desenho.</span><span class="sxs-lookup"><span data-stu-id="5ce71-134">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the drawing method.</span></span> <span data-ttu-id="5ce71-135">Por exemplo, uma variação do <xref:System.Drawing.Graphics.DrawLine%2A> método recebe um <xref:System.Drawing.Pen> objeto e quatro inteiros, conforme mostrado no exemplo a seguir, que desenha um retângulo com uma largura de 100, a altura de 50 e um canto superior esquerdo de (10, 20):</span><span class="sxs-lookup"><span data-stu-id="5ce71-135">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers as shown in the following example, which draws a rectangle with a width of 100, a height of 50 and an upper-left corner of (20, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="5ce71-136">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5ce71-136">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="5ce71-137">Linhas, Curvas e Formas</span><span class="sxs-lookup"><span data-stu-id="5ce71-137">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="5ce71-138">Como Criar Objetos Gráficos para Desenho</span><span class="sxs-lookup"><span data-stu-id="5ce71-138">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)