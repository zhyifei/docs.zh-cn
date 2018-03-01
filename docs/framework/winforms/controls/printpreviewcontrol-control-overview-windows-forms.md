---
title: "PrintPreviewControl 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d50e772cf870d47314a25347f4909367062ffb94
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a><span data-ttu-id="6c174-102">PrintPreviewControl 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="6c174-102">PrintPreviewControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="6c174-103">Windows 窗体<xref:System.Windows.Forms.PrintPreviewControl>用于显示[PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)打印时的样子。</span><span class="sxs-lookup"><span data-stu-id="6c174-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> is used to display a [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) as it will appear when printed.</span></span> <span data-ttu-id="6c174-104">此控件具有没有按钮或其他用户界面元素，因此通常仅在你想要编写自己的打印预览用户界面时才使用 <xref:System.Windows.Forms.PrintPreviewControl>。</span><span class="sxs-lookup"><span data-stu-id="6c174-104">This control has no buttons or other user interface elements, so typically you use the <xref:System.Windows.Forms.PrintPreviewControl> only if you wish to write your own print-preview user interface.</span></span> <span data-ttu-id="6c174-105">如果你想标准用户界面，使用<xref:System.Windows.Forms.PrintPreviewDialog>控制; 请参阅[PrintPreviewDialog 控件概述](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)的概述。</span><span class="sxs-lookup"><span data-stu-id="6c174-105">If you want the standard user interface, use a <xref:System.Windows.Forms.PrintPreviewDialog> control; see [PrintPreviewDialog Control Overview](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) for an overview.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="6c174-106">键属性</span><span class="sxs-lookup"><span data-stu-id="6c174-106">Key Properties</span></span>  
 <span data-ttu-id="6c174-107">控件的键属性是<xref:System.Windows.Forms.PrintPreviewControl.Document%2A>，这会设置要预览的文档。</span><span class="sxs-lookup"><span data-stu-id="6c174-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="6c174-108">文档必须是<xref:System.Drawing.Printing.PrintDocument>对象。</span><span class="sxs-lookup"><span data-stu-id="6c174-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="6c174-109">创建用于打印的文档的概述，请参阅[PrintDocument 组件概述](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md)和[Windows 窗体打印支持](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)。</span><span class="sxs-lookup"><span data-stu-id="6c174-109">For an overview of creating documents for printing, see [PrintDocument Component Overview](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) and [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md).</span></span> <span data-ttu-id="6c174-110"><xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>和<xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>属性确定显示在控件上的水平和垂直的页面数。</span><span class="sxs-lookup"><span data-stu-id="6c174-110">The <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="6c174-111">抗锯齿功能可以使文本显示生成更平滑的但它还可显示更慢;若要使用它，将设置<xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="6c174-111">Antialiasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c174-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c174-112">See Also</span></span>  
 <xref:System.Windows.Forms.PrintPreviewControl>  
 [<span data-ttu-id="6c174-113">PrintPreviewDialog 控件概述</span><span class="sxs-lookup"><span data-stu-id="6c174-113">PrintPreviewDialog Control Overview</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)  
 [<span data-ttu-id="6c174-114">PrintPreviewControl 控件</span><span class="sxs-lookup"><span data-stu-id="6c174-114">PrintPreviewControl Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)  
 [<span data-ttu-id="6c174-115">对话框控件和组件</span><span class="sxs-lookup"><span data-stu-id="6c174-115">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
