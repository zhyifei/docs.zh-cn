---
title: 如何：创建具有专业样式的 ToolStrip 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
ms.openlocfilehash: 3fe99fadc7ddccd5c4921c4694c5b546f4fd4749
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533180"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="d5958-102">如何：创建具有专业样式的 ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="d5958-102">How to: Create a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="d5958-103">可以通过编写自己的派生自 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 类型的类，赋予应用程序的 <xref:System.Windows.Forms.ToolStrip> 控件一个专业的外观和行为（外观和感受）。</span><span class="sxs-lookup"><span data-stu-id="d5958-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior (look and feel) by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="d5958-104">没有对 Visual Studio 中的此功能提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="d5958-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="d5958-105">请参阅[演练：创建具有专业样式的 ToolStrip 控件](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md)。</span><span class="sxs-lookup"><span data-stu-id="d5958-105">See [Walkthrough: Creating a Professionally Styled ToolStrip Control](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5958-106">示例</span><span class="sxs-lookup"><span data-stu-id="d5958-106">Example</span></span>  
 <span data-ttu-id="d5958-107">下面的代码示例演示如何使用<xref:System.Windows.Forms.ToolStrip>控件，创建复合控件，以模拟**导航窗格中**Microsoft Outlook® 提供的。</span><span class="sxs-lookup"><span data-stu-id="d5958-107">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that mimics the **Navigation Pane** provided by Microsoft® Outlook®.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d5958-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="d5958-108">Compiling the Code</span></span>  
 <span data-ttu-id="d5958-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="d5958-109">This example requires:</span></span>  
  
-   <span data-ttu-id="d5958-110">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d5958-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="d5958-111">为 Visual Basic 或 Visual C# 中生成此示例从命令行有关的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="d5958-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d5958-112">你也可以通过将代码粘贴到新项目中生成 Visual Studio 中的此示例。</span><span class="sxs-lookup"><span data-stu-id="d5958-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="d5958-113">另请参阅[演练：创建具有专业样式的 ToolStrip 控件](http://msdn.microsoft.com/library/ms233664\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="d5958-113">Also see [Walkthrough: Creating a Professionally Styled ToolStrip Control](http://msdn.microsoft.com/library/ms233664\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5958-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5958-114">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="d5958-115">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="d5958-115">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [<span data-ttu-id="d5958-116">如何：向窗体提供标准菜单项</span><span class="sxs-lookup"><span data-stu-id="d5958-116">How to: Provide Standard Menu Items to a Form</span></span>](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
