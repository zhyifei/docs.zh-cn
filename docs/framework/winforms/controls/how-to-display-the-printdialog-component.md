---
title: 如何显示 PrintDialog 组件
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: 198ae75d407bd1837033a1cc186d84ff972fdc2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941565"
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="c539e-102">如何显示 PrintDialog 组件</span><span class="sxs-lookup"><span data-stu-id="c539e-102">How to display the PrintDialog component</span></span>

<span data-ttu-id="c539e-103"><xref:System.Windows.Forms.PrintDialog>组件是许多用户都非常熟悉的标准 Windows 打印对话框。</span><span class="sxs-lookup"><span data-stu-id="c539e-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="c539e-104">由于你的用户将立即熟悉它，则将会有所帮助供你使用<xref:System.Windows.Forms.PrintDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="c539e-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>

## <a name="to-display-the-printdialog-component"></a><span data-ttu-id="c539e-105">显示 PrintDialog 组件</span><span class="sxs-lookup"><span data-stu-id="c539e-105">To display the PrintDialog component</span></span>

- <span data-ttu-id="c539e-106">调用<xref:System.Windows.Forms.Form.ShowDialog%2A>从你的应用程序的代码中的方法。</span><span class="sxs-lookup"><span data-stu-id="c539e-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>

     <span data-ttu-id="c539e-107">显示出该组件后，用户可以与之进行交互，设置打印作业的属性。</span><span class="sxs-lookup"><span data-stu-id="c539e-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="c539e-108">这些都保存在<xref:System.Drawing.Printing.PrinterSettings>类 (和<xref:System.Drawing.Printing.PageSettings>类，如果用户访问[PageSetupDialog 组件](pagesetupdialog-component-windows-forms.md)通过<xref:System.Windows.Forms.PrintDialog>组件) 与该打印作业相关联。</span><span class="sxs-lookup"><span data-stu-id="c539e-108">These are saved in the  <xref:System.Drawing.Printing.PrinterSettings> class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="c539e-109">然后可以调用它们所设置的属性以确定打印作业的细节。</span><span class="sxs-lookup"><span data-stu-id="c539e-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>

## <a name="see-also"></a><span data-ttu-id="c539e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="c539e-110">See also</span></span>

- [<span data-ttu-id="c539e-111">如何：创建标准 Windows 窗体打印作业</span><span class="sxs-lookup"><span data-stu-id="c539e-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [<span data-ttu-id="c539e-112">如何：在运行时捕获用户输入从 PrintDialog</span><span class="sxs-lookup"><span data-stu-id="c539e-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [<span data-ttu-id="c539e-113">PrintPreviewDialog 控件</span><span class="sxs-lookup"><span data-stu-id="c539e-113">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="c539e-114">PrintDialog 组件</span><span class="sxs-lookup"><span data-stu-id="c539e-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
- [<span data-ttu-id="c539e-115">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="c539e-115">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="c539e-116">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="c539e-116">Windows Forms Controls</span></span>](index.md)