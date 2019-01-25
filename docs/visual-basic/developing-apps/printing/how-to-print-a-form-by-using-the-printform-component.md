---
title: 如何：打印窗体使用 PrintForm 组件 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Form [Visual Basic], printing
ms.assetid: df963bf6-3ee1-49f4-8b2e-1d95d1beb0be
ms.openlocfilehash: 0a1a62627390c8839625862b9d43d61fc07ebf12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521564"
---
# <a name="how-to-print-a-form-by-using-the-printform-component-visual-basic"></a><span data-ttu-id="aa514-102">如何：打印窗体使用 PrintForm 组件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa514-102">How to: Print a Form by Using the PrintForm Component (Visual Basic)</span></span>
<span data-ttu-id="aa514-103">通过 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件，可以在不使用 <xref:System.Drawing.Printing.PrintDocument> 组件的情况下如实快速打印窗体的图像。</span><span class="sxs-lookup"><span data-stu-id="aa514-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form exactly as it appears on screen without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="aa514-104">以下过程介绍如何将窗体打印到打印机、打印预览窗口和封装的 PostScript 文件。</span><span class="sxs-lookup"><span data-stu-id="aa514-104">The following procedures show how to print a form to a printer, to a print preview window, and to an Encapsulated PostScript file.</span></span>  
  
 <span data-ttu-id="aa514-105">Visual Studio 中不再包含 PowerPack 控件，但你可以从 [下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=25169)下载它们。</span><span class="sxs-lookup"><span data-stu-id="aa514-105">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-a-form-to-the-default-printer"></a><span data-ttu-id="aa514-106">将窗体打印到默认打印机</span><span class="sxs-lookup"><span data-stu-id="aa514-106">To print a form to the default printer</span></span>  
  
1.  <span data-ttu-id="aa514-107">在“工具箱” 中，单击“Visual Basic PowerPacks”  选项卡，然后将 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件拖动到窗体上。</span><span class="sxs-lookup"><span data-stu-id="aa514-107">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="aa514-108"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件被添加到组件栏。</span><span class="sxs-lookup"><span data-stu-id="aa514-108">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="aa514-109">在“属性”  窗口中，将 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> 属性设置为 <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>。</span><span class="sxs-lookup"><span data-stu-id="aa514-109">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="aa514-110">在相应的事件处理程序中（例如在“打印” `Click`**的**`Button`事件处理程序中）添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="aa514-110">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-display-a-form-in-a-print-preview-window"></a><span data-ttu-id="aa514-111">在打印预览窗口中显示窗体</span><span class="sxs-lookup"><span data-stu-id="aa514-111">To display a form in a print preview window</span></span>  
  
1.  <span data-ttu-id="aa514-112">在“工具箱” 中，单击“Visual Basic PowerPacks”  选项卡，然后将 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件拖动到窗体上。</span><span class="sxs-lookup"><span data-stu-id="aa514-112">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="aa514-113"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件被添加到组件栏。</span><span class="sxs-lookup"><span data-stu-id="aa514-113">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="aa514-114">在“属性”  窗口中，将 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> 属性设置为 <xref:System.Drawing.Printing.PrintAction.PrintToPreview>。</span><span class="sxs-lookup"><span data-stu-id="aa514-114">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPreview>.</span></span>  
  
3.  <span data-ttu-id="aa514-115">在相应的事件处理程序中（例如在“打印” `Click`**的**`Button`事件处理程序中）添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="aa514-115">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-print-a-form-to-a-file"></a><span data-ttu-id="aa514-116">将窗体打印到文件</span><span class="sxs-lookup"><span data-stu-id="aa514-116">To print a form to a file</span></span>  
  
1.  <span data-ttu-id="aa514-117">在“工具箱” 中，单击“Visual Basic PowerPacks”  选项卡，然后将 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件拖动到窗体上。</span><span class="sxs-lookup"><span data-stu-id="aa514-117">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="aa514-118"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件被添加到组件栏。</span><span class="sxs-lookup"><span data-stu-id="aa514-118">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="aa514-119">在“属性”  窗口中，将 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> 属性设置为 <xref:System.Drawing.Printing.PrintAction.PrintToFile>。</span><span class="sxs-lookup"><span data-stu-id="aa514-119">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToFile>.</span></span>  
  
3.  <span data-ttu-id="aa514-120">（可选）选择 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> 属性，并键入目标文件的完整路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="aa514-120">Optionally, select the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> property and type the full path and file name for the destination file.</span></span>  
  
     <span data-ttu-id="aa514-121">如果跳过此步骤，将在运行时提示用户输入文件名。</span><span class="sxs-lookup"><span data-stu-id="aa514-121">If you skip this step, the user will be prompted for a file name at run time.</span></span>  
  
4.  <span data-ttu-id="aa514-122">在相应的事件处理程序中（例如在“打印” `Click`**的**`Button`事件处理程序中）添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="aa514-122">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print()  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="aa514-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa514-123">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>
- [<span data-ttu-id="aa514-124">如何：打印窗体的工作区</span><span class="sxs-lookup"><span data-stu-id="aa514-124">How to: Print the Client Area of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)
- [<span data-ttu-id="aa514-125">如何：打印窗体的工作区和非工作区</span><span class="sxs-lookup"><span data-stu-id="aa514-125">How to: Print Client and Non-Client Areas of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)
- [<span data-ttu-id="aa514-126">如何：打印可滚动的窗体</span><span class="sxs-lookup"><span data-stu-id="aa514-126">How to: Print a Scrollable Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
- [<span data-ttu-id="aa514-127">PrintForm 组件</span><span class="sxs-lookup"><span data-stu-id="aa514-127">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)
