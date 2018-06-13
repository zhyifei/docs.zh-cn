---
title: Windows 窗体打印支持
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: 4ea04d0b6bb8ffa7182d5166ebd66b809adeed34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528549"
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="8a20b-102">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="8a20b-102">Windows Forms Print Support</span></span>
<span data-ttu-id="8a20b-103">在 Windows 窗体中的打印主要由使用[PrintDocument 组件](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)组件，使用户能够打印，和[PrintPreviewDialog 控件](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)控件， [PrintDialog组件](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)和[PageSetupDialog 组件](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)组件以向熟悉 Windows 操作系统的用户提供熟悉的图形界面。</span><span class="sxs-lookup"><span data-stu-id="8a20b-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="8a20b-104">通常，你创建的新实例<xref:System.Drawing.Printing.PrintDocument>组件，设置描述打印使用内容的属性<xref:System.Drawing.Printing.PrinterSettings>和<xref:System.Drawing.Printing.PageSettings>类，并调用<xref:System.Drawing.Printing.PrintDocument.Print%2A>方法来实际打印文档。</span><span class="sxs-lookup"><span data-stu-id="8a20b-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="8a20b-105">从基于 Windows 的应用程序，打印过程<xref:System.Drawing.Printing.PrintDocument>组件将向警报用户事实指出正在进行打印并允许打印作业要取消显示中止打印对话框。</span><span class="sxs-lookup"><span data-stu-id="8a20b-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a20b-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="8a20b-106">In This Section</span></span>  
 [<span data-ttu-id="8a20b-107">如何：创建标准的 Windows 窗体打印作业</span><span class="sxs-lookup"><span data-stu-id="8a20b-107">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="8a20b-108">说明如何使用<xref:System.Drawing.Printing.PrintDocument>组件从 Windows 窗体进行打印。</span><span class="sxs-lookup"><span data-stu-id="8a20b-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="8a20b-109">如何：在运行时从 PrintDialog 中捕获用户输入</span><span class="sxs-lookup"><span data-stu-id="8a20b-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="8a20b-110">说明如何修改所选的打印选项，以编程方式使用<xref:System.Windows.Forms.PrintDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="8a20b-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="8a20b-111">如何：在 Windows 窗体中选择用户计算机连接的打印机</span><span class="sxs-lookup"><span data-stu-id="8a20b-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="8a20b-112">介绍更改打印机来打印到使用<xref:System.Windows.Forms.PrintDialog>在运行时组件。</span><span class="sxs-lookup"><span data-stu-id="8a20b-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="8a20b-113">如何：在 Windows 窗体中打印图形</span><span class="sxs-lookup"><span data-stu-id="8a20b-113">How to: Print Graphics in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="8a20b-114">描述发送到打印机的图形。</span><span class="sxs-lookup"><span data-stu-id="8a20b-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="8a20b-115">如何：打印 Windows 窗体中的多页文本文件</span><span class="sxs-lookup"><span data-stu-id="8a20b-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="8a20b-116">描述发送到打印机的文本。</span><span class="sxs-lookup"><span data-stu-id="8a20b-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="8a20b-117">如何：完成 Windows 窗体打印作业</span><span class="sxs-lookup"><span data-stu-id="8a20b-117">How to: Complete Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="8a20b-118">说明如何通知用户打印作业的完成。</span><span class="sxs-lookup"><span data-stu-id="8a20b-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="8a20b-119">如何：打印 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="8a20b-119">How to: Print a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 <span data-ttu-id="8a20b-120">演示如何打印一份当前窗体。</span><span class="sxs-lookup"><span data-stu-id="8a20b-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="8a20b-121">如何：使用打印预览在 Windows 窗体中进行打印</span><span class="sxs-lookup"><span data-stu-id="8a20b-121">How to: Print in Windows Forms Using Print Preview</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="8a20b-122">演示如何使用<xref:System.Windows.Forms.PrintPreviewDialog>打印文档。</span><span class="sxs-lookup"><span data-stu-id="8a20b-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8a20b-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="8a20b-123">Related Sections</span></span>  
 [<span data-ttu-id="8a20b-124">PrintDocument 组件</span><span class="sxs-lookup"><span data-stu-id="8a20b-124">PrintDocument Component</span></span>](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="8a20b-125">说明使用<xref:System.Drawing.Printing.PrintDocument>组件。</span><span class="sxs-lookup"><span data-stu-id="8a20b-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="8a20b-126">PrintDialog 组件</span><span class="sxs-lookup"><span data-stu-id="8a20b-126">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="8a20b-127">说明使用<xref:System.Windows.Forms.PrintDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="8a20b-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="8a20b-128">PrintPreviewDialog 控件</span><span class="sxs-lookup"><span data-stu-id="8a20b-128">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="8a20b-129">说明使用<xref:System.Windows.Forms.PrintPreviewDialog>控件。</span><span class="sxs-lookup"><span data-stu-id="8a20b-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="8a20b-130">PageSetupDialog 组件</span><span class="sxs-lookup"><span data-stu-id="8a20b-130">PageSetupDialog Component</span></span>](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="8a20b-131">说明使用<xref:System.Windows.Forms.PageSetupDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="8a20b-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="8a20b-132">描述中的类<xref:System.Drawing.Printing>命名空间。</span><span class="sxs-lookup"><span data-stu-id="8a20b-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
