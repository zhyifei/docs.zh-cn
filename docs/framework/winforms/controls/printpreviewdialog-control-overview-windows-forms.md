---
title: "PrintPreviewDialog 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewDialog
helpviewer_keywords: PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3c898dc24c9a4418e3af45fce507e6befcf905a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="3e27b-102">PrintPreviewDialog 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="3e27b-102">PrintPreviewDialog Control Overview (Windows Forms)</span></span>
<span data-ttu-id="3e27b-103">Windows 窗体<xref:System.Windows.Forms.PrintPreviewDialog>控件是一个预配置的对话框，用于显示如何[PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)打印时将显示。</span><span class="sxs-lookup"><span data-stu-id="3e27b-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="3e27b-104">中基于 Windows 的应用程序而不是配置自己对话框的简单解决方案，使用它。</span><span class="sxs-lookup"><span data-stu-id="3e27b-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="3e27b-105">该控件包含用于打印、放大、显示一页或多页以及关闭对话框的按钮。</span><span class="sxs-lookup"><span data-stu-id="3e27b-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="3e27b-106">键属性和方法</span><span class="sxs-lookup"><span data-stu-id="3e27b-106">Key Properties and Methods</span></span>  
 <span data-ttu-id="3e27b-107">控件的键属性是<xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>，这会设置要预览的文档。</span><span class="sxs-lookup"><span data-stu-id="3e27b-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="3e27b-108">文档必须是<xref:System.Drawing.Printing.PrintDocument>对象。</span><span class="sxs-lookup"><span data-stu-id="3e27b-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="3e27b-109">若要显示对话框中，您必须调用其<xref:System.Windows.Forms.Form.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="3e27b-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="3e27b-110">抗锯齿可以使文本显示生成更平滑的但它还可显示更慢;若要使用它，将设置<xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="3e27b-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="3e27b-111">某些属性均可通过<xref:System.Windows.Forms.PrintPreviewControl>，<xref:System.Windows.Forms.PrintPreviewDialog>包含。</span><span class="sxs-lookup"><span data-stu-id="3e27b-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="3e27b-112">(无需添加此<xref:System.Windows.Forms.PrintPreviewControl>到窗体; 它会自动包含在<xref:System.Windows.Forms.PrintPreviewDialog>向窗体添加对话框时。)可通过属性的示例<xref:System.Windows.Forms.PrintPreviewControl>是<xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>和<xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>属性，这些扩展名决定了水平和垂直显示在控件上的页面数。</span><span class="sxs-lookup"><span data-stu-id="3e27b-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="3e27b-113">你可以访问<xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>属性作为`PrintPreviewDialog1.PrintPreviewControl.Columns`中[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]，`printPreviewDialog1.PrintPreviewControl.Columns`中[!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]，或`printPreviewDialog1->PrintPreviewControl->Columns`中[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3e27b-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], or `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e27b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e27b-114">See Also</span></span>  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [<span data-ttu-id="3e27b-115">PrintPreviewControl 控件概述</span><span class="sxs-lookup"><span data-stu-id="3e27b-115">PrintPreviewControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="3e27b-116">PrintPreviewDialog 控件</span><span class="sxs-lookup"><span data-stu-id="3e27b-116">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [<span data-ttu-id="3e27b-117">对话框控件和组件</span><span class="sxs-lookup"><span data-stu-id="3e27b-117">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
