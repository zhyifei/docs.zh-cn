---
title: 如何：创建采用专业样式的 ToolStrip 控件
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
ms.openlocfilehash: 6da6e113867efed79dfcd02f3b89ee1f9ae13c4e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104581"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="9977c-102">如何：创建采用专业样式的 ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="9977c-102">How to: Create a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="9977c-103">可以通过编写自己的派生自 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 类型的类，赋予应用程序的 <xref:System.Windows.Forms.ToolStrip> 控件一个专业的外观和行为（外观和感受）。</span><span class="sxs-lookup"><span data-stu-id="9977c-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior (look and feel) by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="9977c-104">没有对此功能在 Visual Studio 中的广泛支持。</span><span class="sxs-lookup"><span data-stu-id="9977c-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="9977c-105">请参阅[演练：创建具有专业样式的 ToolStrip 控件](walkthrough-creating-a-professionally-styled-toolstrip-control.md)。</span><span class="sxs-lookup"><span data-stu-id="9977c-105">See [Walkthrough: Creating a Professionally Styled ToolStrip Control](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9977c-106">示例</span><span class="sxs-lookup"><span data-stu-id="9977c-106">Example</span></span>  
 <span data-ttu-id="9977c-107">下面的代码示例演示如何使用<xref:System.Windows.Forms.ToolStrip>控件，创建复合控件，以模拟**导航窗格**Microsoft Outlook® 提供的。</span><span class="sxs-lookup"><span data-stu-id="9977c-107">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that mimics the **Navigation Pane** provided by Microsoft® Outlook®.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9977c-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="9977c-108">Compiling the Code</span></span>  
 <span data-ttu-id="9977c-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="9977c-109">This example requires:</span></span>  
  
-   <span data-ttu-id="9977c-110">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="9977c-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="9977c-111">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="9977c-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9977c-112">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="9977c-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="9977c-113">另请参阅[演练：创建具有专业样式的 ToolStrip 控件](walkthrough-creating-a-professionally-styled-toolstrip-control.md)。</span><span class="sxs-lookup"><span data-stu-id="9977c-113">Also see [Walkthrough: Creating a Professionally Styled ToolStrip Control](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9977c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9977c-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="9977c-115">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="9977c-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="9977c-116">如何：向窗体提供标准菜单项</span><span class="sxs-lookup"><span data-stu-id="9977c-116">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
