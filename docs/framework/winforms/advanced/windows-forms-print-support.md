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
ms.openlocfilehash: 8e008f2cb4b2f32cdba676e68d9fd790530e2b06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011842"
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="845ee-102">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="845ee-102">Windows Forms Print Support</span></span>
<span data-ttu-id="845ee-103">使用的主要包含在 Windows 窗体中的打印[PrintDocument 组件](../controls/printdocument-component-windows-forms.md)组件，使用户能够打印，并[PrintPreviewDialog 控件](../controls/printpreviewdialog-control-windows-forms.md)控件， [PrintDialog组件](../controls/printdialog-component-windows-forms.md)并[PageSetupDialog 组件](../controls/pagesetupdialog-component-windows-forms.md)要向用户习惯于 Windows 操作系统提供熟悉的图形界面的组件。</span><span class="sxs-lookup"><span data-stu-id="845ee-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="845ee-104">通常情况下，创建的新实例<xref:System.Drawing.Printing.PrintDocument>组件，将设置描述打印使用内容的属性<xref:System.Drawing.Printing.PrinterSettings>并<xref:System.Drawing.Printing.PageSettings>类，并调用<xref:System.Drawing.Printing.PrintDocument.Print%2A>方法来实际打印文档。</span><span class="sxs-lookup"><span data-stu-id="845ee-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="845ee-105">从基于 Windows 的应用程序，打印期间<xref:System.Drawing.Printing.PrintDocument>组件会警告用户正在进行打印的这一事实，并允许打印作业要取消显示中止打印对话框。</span><span class="sxs-lookup"><span data-stu-id="845ee-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="845ee-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="845ee-106">In This Section</span></span>  
 [<span data-ttu-id="845ee-107">如何：创建标准 Windows 窗体打印作业</span><span class="sxs-lookup"><span data-stu-id="845ee-107">How to: Create Standard Windows Forms Print Jobs</span></span>](how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="845ee-108">说明如何使用<xref:System.Drawing.Printing.PrintDocument>组件从 Windows 窗体中打印。</span><span class="sxs-lookup"><span data-stu-id="845ee-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="845ee-109">如何：在运行时捕获用户输入从 PrintDialog</span><span class="sxs-lookup"><span data-stu-id="845ee-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="845ee-110">说明如何修改所选的打印选项，以编程方式使用<xref:System.Windows.Forms.PrintDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="845ee-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="845ee-111">如何：选择连接到在 Windows 窗体中的用户的计算机的打印机</span><span class="sxs-lookup"><span data-stu-id="845ee-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="845ee-112">介绍更改打印机来打印到使用<xref:System.Windows.Forms.PrintDialog>在运行时组件。</span><span class="sxs-lookup"><span data-stu-id="845ee-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="845ee-113">如何：在 Windows 窗体中打印图形</span><span class="sxs-lookup"><span data-stu-id="845ee-113">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="845ee-114">介绍向打印机发送图形。</span><span class="sxs-lookup"><span data-stu-id="845ee-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="845ee-115">如何：打印 Windows 窗体中的多页文本文件</span><span class="sxs-lookup"><span data-stu-id="845ee-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="845ee-116">描述向打印机发送文本。</span><span class="sxs-lookup"><span data-stu-id="845ee-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="845ee-117">如何：完整的 Windows 窗体打印作业</span><span class="sxs-lookup"><span data-stu-id="845ee-117">How to: Complete Windows Forms Print Jobs</span></span>](how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="845ee-118">介绍如何向完成的打印作业的用户发出警报。</span><span class="sxs-lookup"><span data-stu-id="845ee-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="845ee-119">如何：打印 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="845ee-119">How to: Print a Windows Form</span></span>](how-to-print-a-windows-form.md)  
 <span data-ttu-id="845ee-120">演示如何打印一份当前窗体。</span><span class="sxs-lookup"><span data-stu-id="845ee-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="845ee-121">如何：使用打印预览的 Windows 窗体中打印</span><span class="sxs-lookup"><span data-stu-id="845ee-121">How to: Print in Windows Forms Using Print Preview</span></span>](how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="845ee-122">演示如何使用<xref:System.Windows.Forms.PrintPreviewDialog>用于打印文档。</span><span class="sxs-lookup"><span data-stu-id="845ee-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="845ee-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="845ee-123">Related Sections</span></span>  
 [<span data-ttu-id="845ee-124">PrintDocument 组件</span><span class="sxs-lookup"><span data-stu-id="845ee-124">PrintDocument Component</span></span>](../controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="845ee-125">说明使用方式的<xref:System.Drawing.Printing.PrintDocument>组件。</span><span class="sxs-lookup"><span data-stu-id="845ee-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="845ee-126">PrintDialog 组件</span><span class="sxs-lookup"><span data-stu-id="845ee-126">PrintDialog Component</span></span>](../controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="845ee-127">说明使用方式的<xref:System.Windows.Forms.PrintDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="845ee-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="845ee-128">PrintPreviewDialog 控件</span><span class="sxs-lookup"><span data-stu-id="845ee-128">PrintPreviewDialog Control</span></span>](../controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="845ee-129">说明使用方式的<xref:System.Windows.Forms.PrintPreviewDialog>控件。</span><span class="sxs-lookup"><span data-stu-id="845ee-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="845ee-130">PageSetupDialog 组件</span><span class="sxs-lookup"><span data-stu-id="845ee-130">PageSetupDialog Component</span></span>](../controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="845ee-131">说明使用方式的<xref:System.Windows.Forms.PageSetupDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="845ee-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="845ee-132">描述中的类<xref:System.Drawing.Printing>命名空间。</span><span class="sxs-lookup"><span data-stu-id="845ee-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
