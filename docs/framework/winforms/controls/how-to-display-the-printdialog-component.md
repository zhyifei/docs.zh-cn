---
title: 如何：显示 PrintDialog 组件
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: d8765187522f8becf24b519434b7c170c1c755b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532182"
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="f9824-102">如何：显示 PrintDialog 组件</span><span class="sxs-lookup"><span data-stu-id="f9824-102">How to: Display the PrintDialog Component</span></span>
<span data-ttu-id="f9824-103"><xref:System.Windows.Forms.PrintDialog>组件是很多用户都将熟悉的标准 Windows 打印对话框。</span><span class="sxs-lookup"><span data-stu-id="f9824-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="f9824-104">因为你的用户将立即熟悉它，它可能会对你要使用有用<xref:System.Windows.Forms.PrintDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="f9824-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
### <a name="to-display-the-printdialog-component"></a><span data-ttu-id="f9824-105">显示 PrintDialog 组件</span><span class="sxs-lookup"><span data-stu-id="f9824-105">To display the PrintDialog component</span></span>  
  
-   <span data-ttu-id="f9824-106">调用<xref:System.Windows.Forms.Form.ShowDialog%2A>从你的应用程序的代码中的方法。</span><span class="sxs-lookup"><span data-stu-id="f9824-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>  
  
     <span data-ttu-id="f9824-107">显示出该组件后，用户可以与之进行交互，设置打印作业的属性。</span><span class="sxs-lookup"><span data-stu-id="f9824-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="f9824-108">这些保存在<!--zz <xref:System.Drawing.Printing.PrinterSetting>-->`PrinterSetting`类 (与<xref:System.Drawing.Printing.PageSettings>类，如果用户访问[PageSetupDialog 组件](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)通过<xref:System.Windows.Forms.PrintDialog>组件) 与该打印作业关联。</span><span class="sxs-lookup"><span data-stu-id="f9824-108">These are saved in the <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="f9824-109">然后可以调用它们所设置的属性以确定打印作业的细节。</span><span class="sxs-lookup"><span data-stu-id="f9824-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9824-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9824-110">See Also</span></span>  
 [<span data-ttu-id="f9824-111">如何：创建标准的 Windows 窗体打印作业</span><span class="sxs-lookup"><span data-stu-id="f9824-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [<span data-ttu-id="f9824-112">如何：在运行时从 PrintDialog 中捕获用户输入</span><span class="sxs-lookup"><span data-stu-id="f9824-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 [<span data-ttu-id="f9824-113">PrintPreviewDialog 控件</span><span class="sxs-lookup"><span data-stu-id="f9824-113">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [<span data-ttu-id="f9824-114">PrintDialog 组件</span><span class="sxs-lookup"><span data-stu-id="f9824-114">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 [<span data-ttu-id="f9824-115">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="f9824-115">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [<span data-ttu-id="f9824-116">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="f9824-116">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)
