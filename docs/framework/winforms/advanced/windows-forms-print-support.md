---
title: 打印支持
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: d6e8f60db7afe2f1b04eaae6fe71aa93e5c22cae
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732488"
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="8d8f5-102">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="8d8f5-102">Windows Forms Print Support</span></span>
<span data-ttu-id="8d8f5-103">Windows 窗体中的打印主要包括使用[PrintDocument 组件](../controls/printdocument-component-windows-forms.md)组件来使用户能够打印， [PrintPreviewDialog 控件](../controls/printpreviewdialog-control-windows-forms.md)控制[PrintDialog 组件](../controls/printdialog-component-windows-forms.md)和[PageSetupDialog 组件](../controls/pagesetupdialog-component-windows-forms.md)组件，为习惯于 Windows 操作系统的用户提供熟悉的图形界面。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="8d8f5-104">通常，您创建 <xref:System.Drawing.Printing.PrintDocument> 组件的新实例，使用 <xref:System.Drawing.Printing.PrinterSettings> 和 <xref:System.Drawing.Printing.PageSettings> 类设置描述要打印内容的属性，然后调用 <xref:System.Drawing.Printing.PrintDocument.Print%2A> 方法来实际打印文档。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="8d8f5-105">在从基于 Windows 的应用程序中进行打印的过程中，<xref:System.Drawing.Printing.PrintDocument> 组件将显示 "中止打印" 对话框，以便向用户发出警报，提醒用户发生打印并允许取消打印作业。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8d8f5-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="8d8f5-106">In This Section</span></span>  
 [<span data-ttu-id="8d8f5-107">방법: 표준 Windows Forms 인쇄 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="8d8f5-107">How to: Create Standard Windows Forms Print Jobs</span></span>](how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="8d8f5-108">介绍如何使用 <xref:System.Drawing.Printing.PrintDocument> 组件从 Windows 窗体中进行打印。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="8d8f5-109">방법: 런타임에 PrintDialog에서 사용자 입력 캡처</span><span class="sxs-lookup"><span data-stu-id="8d8f5-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="8d8f5-110">说明如何使用 <xref:System.Windows.Forms.PrintDialog> 组件以编程方式修改选定的打印选项。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="8d8f5-111">방법: Windows Forms에서 사용자의 컴퓨터에 연결된 프린터 선택</span><span class="sxs-lookup"><span data-stu-id="8d8f5-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="8d8f5-112">描述如何在运行时使用 <xref:System.Windows.Forms.PrintDialog> 组件更改要打印到的打印机。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="8d8f5-113">방법: Windows Forms의 그래픽 인쇄</span><span class="sxs-lookup"><span data-stu-id="8d8f5-113">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="8d8f5-114">介绍如何将图形发送到打印机。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="8d8f5-115">방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄</span><span class="sxs-lookup"><span data-stu-id="8d8f5-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="8d8f5-116">介绍如何将文本发送到打印机。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="8d8f5-117">방법: Windows Forms 인쇄 작업 완료</span><span class="sxs-lookup"><span data-stu-id="8d8f5-117">How to: Complete Windows Forms Print Jobs</span></span>](how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="8d8f5-118">说明如何提醒用户完成打印作业。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="8d8f5-119">방법: Windows Form 인쇄</span><span class="sxs-lookup"><span data-stu-id="8d8f5-119">How to: Print a Windows Form</span></span>](how-to-print-a-windows-form.md)  
 <span data-ttu-id="8d8f5-120">说明如何打印当前窗体的副本。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="8d8f5-121">방법: Windows Forms에서 인쇄 미리 보기를 사용하여 인쇄</span><span class="sxs-lookup"><span data-stu-id="8d8f5-121">How to: Print in Windows Forms Using Print Preview</span></span>](how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="8d8f5-122">演示如何使用 <xref:System.Windows.Forms.PrintPreviewDialog> 打印文档。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8d8f5-123">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="8d8f5-123">Related Sections</span></span>  
 [<span data-ttu-id="8d8f5-124">PrintDocument 구성 요소</span><span class="sxs-lookup"><span data-stu-id="8d8f5-124">PrintDocument Component</span></span>](../controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="8d8f5-125">说明 <xref:System.Drawing.Printing.PrintDocument> 组件的用法。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="8d8f5-126">PrintDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="8d8f5-126">PrintDialog Component</span></span>](../controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="8d8f5-127">说明 <xref:System.Windows.Forms.PrintDialog> 组件的用法。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="8d8f5-128">PrintPreviewDialog 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8d8f5-128">PrintPreviewDialog Control</span></span>](../controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="8d8f5-129">说明 <xref:System.Windows.Forms.PrintPreviewDialog> 控件的用法。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="8d8f5-130">PageSetupDialog Component</span><span class="sxs-lookup"><span data-stu-id="8d8f5-130">PageSetupDialog Component</span></span>](../controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="8d8f5-131">说明 <xref:System.Windows.Forms.PageSetupDialog> 组件的用法。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="8d8f5-132">介绍 <xref:System.Drawing.Printing> 命名空间中的类。</span><span class="sxs-lookup"><span data-stu-id="8d8f5-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
