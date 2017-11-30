---
title: "Visão geral do controle PrintPreviewControl (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47bef441b01d8bdcf9a365c341005cff28c64f27
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a><span data-ttu-id="e05ab-102">Visão geral do controle PrintPreviewControl (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e05ab-102">PrintPreviewControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="e05ab-103">Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> é usado para exibir um [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) como ele aparecerá quando impresso.</span><span class="sxs-lookup"><span data-stu-id="e05ab-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> is used to display a [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) as it will appear when printed.</span></span> <span data-ttu-id="e05ab-104">Este controle tem botões não ou outros elementos de interface do usuário, normalmente você usar o <xref:System.Windows.Forms.PrintPreviewControl> apenas se você quiser escrever sua própria interface de usuário de visualização de impressão.</span><span class="sxs-lookup"><span data-stu-id="e05ab-104">This control has no buttons or other user interface elements, so typically you use the <xref:System.Windows.Forms.PrintPreviewControl> only if you wish to write your own print-preview user interface.</span></span> <span data-ttu-id="e05ab-105">Se quiser que a interface de usuário padrão, use um <xref:System.Windows.Forms.PrintPreviewDialog> controlar; consulte [visão geral do controle PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) para obter uma visão geral.</span><span class="sxs-lookup"><span data-stu-id="e05ab-105">If you want the standard user interface, use a <xref:System.Windows.Forms.PrintPreviewDialog> control; see [PrintPreviewDialog Control Overview](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) for an overview.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="e05ab-106">Propriedades da chave</span><span class="sxs-lookup"><span data-stu-id="e05ab-106">Key Properties</span></span>  
 <span data-ttu-id="e05ab-107">Propriedade de chave do controle é <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, que define o documento a ser visualizado.</span><span class="sxs-lookup"><span data-stu-id="e05ab-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="e05ab-108">O documento deve ser um <xref:System.Drawing.Printing.PrintDocument> objeto.</span><span class="sxs-lookup"><span data-stu-id="e05ab-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="e05ab-109">Para obter uma visão geral da criação de documentos para impressão, confira [Visão geral do componente PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) e [Suporte à impressão nos Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md).</span><span class="sxs-lookup"><span data-stu-id="e05ab-109">For an overview of creating documents for printing, see [PrintDocument Component Overview](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) and [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md).</span></span> <span data-ttu-id="e05ab-110">O <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> e <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> propriedades determinam o número de páginas exibidas horizontalmente e verticalmente no controle.</span><span class="sxs-lookup"><span data-stu-id="e05ab-110">The <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="e05ab-111">Suavização pode fazer o texto pareça mais suave, mas ele também pode tornar a exibição mais lenta; para usá-lo, defina o <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> propriedade `true`.</span><span class="sxs-lookup"><span data-stu-id="e05ab-111">Antialiasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e05ab-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e05ab-112">See Also</span></span>  
 <xref:System.Windows.Forms.PrintPreviewControl>  
 [<span data-ttu-id="e05ab-113">Visão geral do controle PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="e05ab-113">PrintPreviewDialog Control Overview</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)  
 [<span data-ttu-id="e05ab-114">Controle PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="e05ab-114">PrintPreviewControl Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)  
 [<span data-ttu-id="e05ab-115">Controles e componentes da caixa de diálogo</span><span class="sxs-lookup"><span data-stu-id="e05ab-115">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)