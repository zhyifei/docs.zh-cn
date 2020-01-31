---
title: PrintPreviewControl 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: 8dfe5802a24d5ec85ed908fd04c5550e1fbec012
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741439"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a><span data-ttu-id="0d0bc-102">PrintPreviewControl 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="0d0bc-102">PrintPreviewControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="0d0bc-103">Windows 窗体 <xref:System.Windows.Forms.PrintPreviewControl> 用于显示[PrintDocument](printdocument-component-windows-forms.md) ，因为它会在打印时显示。</span><span class="sxs-lookup"><span data-stu-id="0d0bc-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> is used to display a [PrintDocument](printdocument-component-windows-forms.md) as it will appear when printed.</span></span> <span data-ttu-id="0d0bc-104">이 컨트롤에는 단추나 다른 사용자 인터페이스 요소가 없으므로, 일반적으로 고유한 인쇄 미리 보기 사용자 인터페이스를 작성하려는 경우에만 <xref:System.Windows.Forms.PrintPreviewControl>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d0bc-104">This control has no buttons or other user interface elements, so typically you use the <xref:System.Windows.Forms.PrintPreviewControl> only if you wish to write your own print-preview user interface.</span></span> <span data-ttu-id="0d0bc-105">如果需要标准用户界面，请使用 <xref:System.Windows.Forms.PrintPreviewDialog> 控件;有关概述，请参阅[PrintPreviewDialog 控件概述](printpreviewdialog-control-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="0d0bc-105">If you want the standard user interface, use a <xref:System.Windows.Forms.PrintPreviewDialog> control; see [PrintPreviewDialog Control Overview](printpreviewdialog-control-overview-windows-forms.md) for an overview.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="0d0bc-106">키 속성</span><span class="sxs-lookup"><span data-stu-id="0d0bc-106">Key Properties</span></span>  
 <span data-ttu-id="0d0bc-107">控件的键属性为 <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>，这将设置要预览的文档。</span><span class="sxs-lookup"><span data-stu-id="0d0bc-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="0d0bc-108">文档必须是 <xref:System.Drawing.Printing.PrintDocument> 的对象。</span><span class="sxs-lookup"><span data-stu-id="0d0bc-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="0d0bc-109">有关创建打印文档的概述，请参阅[PrintDocument 组件概述](printdocument-component-overview-windows-forms.md)和[Windows 窗体打印支持](../advanced/windows-forms-print-support.md)。</span><span class="sxs-lookup"><span data-stu-id="0d0bc-109">For an overview of creating documents for printing, see [PrintDocument Component Overview](printdocument-component-overview-windows-forms.md) and [Windows Forms Print Support](../advanced/windows-forms-print-support.md).</span></span> <span data-ttu-id="0d0bc-110"><xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 和 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 属性确定控件上水平和垂直显示的页数。</span><span class="sxs-lookup"><span data-stu-id="0d0bc-110">The <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="0d0bc-111">抗锯齿可以使文本显示得更平滑，但也可以使显示速度变慢;若要使用它，请将 <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="0d0bc-111">Antialiasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d0bc-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d0bc-112">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewControl>
- [<span data-ttu-id="0d0bc-113">PrintPreviewDialog 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="0d0bc-113">PrintPreviewDialog Control Overview</span></span>](printpreviewdialog-control-overview-windows-forms.md)
- [<span data-ttu-id="0d0bc-114">PrintPreviewControl 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0d0bc-114">PrintPreviewControl Control</span></span>](printpreviewcontrol-control-windows-forms.md)
- [<span data-ttu-id="0d0bc-115">대화 상자 컨트롤 및 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0d0bc-115">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
