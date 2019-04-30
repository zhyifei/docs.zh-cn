---
title: PrintPreviewControl 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: e9f1c2ae912b6beeba70c318b94a3052e2f99acb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012590"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a><span data-ttu-id="bb33d-102">PrintPreviewControl 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="bb33d-102">PrintPreviewControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="bb33d-103">Windows 窗体<xref:System.Windows.Forms.PrintPreviewControl>用来显示[PrintDocument](printdocument-component-windows-forms.md)打印时将显示。</span><span class="sxs-lookup"><span data-stu-id="bb33d-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> is used to display a [PrintDocument](printdocument-component-windows-forms.md) as it will appear when printed.</span></span> <span data-ttu-id="bb33d-104">此控件具有没有按钮或其他用户界面元素，因此通常仅在你想要编写自己的打印预览用户界面时才使用 <xref:System.Windows.Forms.PrintPreviewControl>。</span><span class="sxs-lookup"><span data-stu-id="bb33d-104">This control has no buttons or other user interface elements, so typically you use the <xref:System.Windows.Forms.PrintPreviewControl> only if you wish to write your own print-preview user interface.</span></span> <span data-ttu-id="bb33d-105">如果您希望的标准用户界面，使用<xref:System.Windows.Forms.PrintPreviewDialog>控制; 请参阅[PrintPreviewDialog 控件概述](printpreviewdialog-control-overview-windows-forms.md)概述。</span><span class="sxs-lookup"><span data-stu-id="bb33d-105">If you want the standard user interface, use a <xref:System.Windows.Forms.PrintPreviewDialog> control; see [PrintPreviewDialog Control Overview](printpreviewdialog-control-overview-windows-forms.md) for an overview.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="bb33d-106">键属性</span><span class="sxs-lookup"><span data-stu-id="bb33d-106">Key Properties</span></span>  
 <span data-ttu-id="bb33d-107">控件的关键属性是<xref:System.Windows.Forms.PrintPreviewControl.Document%2A>，用于设置要预览的文档。</span><span class="sxs-lookup"><span data-stu-id="bb33d-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="bb33d-108">文档必须是<xref:System.Drawing.Printing.PrintDocument>对象。</span><span class="sxs-lookup"><span data-stu-id="bb33d-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="bb33d-109">创建进行打印的文档的概述，请参阅[PrintDocument 组件概述](printdocument-component-overview-windows-forms.md)并[Windows 窗体打印支持](../advanced/windows-forms-print-support.md)。</span><span class="sxs-lookup"><span data-stu-id="bb33d-109">For an overview of creating documents for printing, see [PrintDocument Component Overview](printdocument-component-overview-windows-forms.md) and [Windows Forms Print Support](../advanced/windows-forms-print-support.md).</span></span> <span data-ttu-id="bb33d-110"><xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>和<xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>属性确定的水平和垂直显示在控件上的页数。</span><span class="sxs-lookup"><span data-stu-id="bb33d-110">The <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="bb33d-111">抗锯齿功能可以使文本显示更加顺利，但它还可以显示更慢;若要使用它，将设置<xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="bb33d-111">Antialiasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb33d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb33d-112">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewControl>
- [<span data-ttu-id="bb33d-113">PrintPreviewDialog 控件概述</span><span class="sxs-lookup"><span data-stu-id="bb33d-113">PrintPreviewDialog Control Overview</span></span>](printpreviewdialog-control-overview-windows-forms.md)
- [<span data-ttu-id="bb33d-114">PrintPreviewControl 控件</span><span class="sxs-lookup"><span data-stu-id="bb33d-114">PrintPreviewControl Control</span></span>](printpreviewcontrol-control-windows-forms.md)
- [<span data-ttu-id="bb33d-115">对话框控件和组件</span><span class="sxs-lookup"><span data-stu-id="bb33d-115">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
