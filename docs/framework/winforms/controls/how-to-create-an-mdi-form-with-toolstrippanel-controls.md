---
title: 如何：创建带有 ToolStripPanel 控件的 MDI 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms [Windows Forms]
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
ms.assetid: d198ef8e-f7c4-4b3f-a7f5-ce858cb90cec
ms.openlocfilehash: f2d4b92ffd37a5d9ce1552fa590357ec55cc6df5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43406334"
---
# <a name="how-to-create-an-mdi-form-with-toolstrippanel-controls"></a><span data-ttu-id="c0b03-102">如何：创建带有 ToolStripPanel 控件的 MDI 窗体</span><span class="sxs-lookup"><span data-stu-id="c0b03-102">How to: Create an MDI Form with ToolStripPanel Controls</span></span>
<span data-ttu-id="c0b03-103">可以创建四面均框有 <xref:System.Windows.Forms.ToolStrip> 控件的多文档界面 (MDI) 窗体。</span><span class="sxs-lookup"><span data-stu-id="c0b03-103">You can create a multiple document interface (MDI) form that has <xref:System.Windows.Forms.ToolStrip> controls framing it on all four sides.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0b03-104">示例</span><span class="sxs-lookup"><span data-stu-id="c0b03-104">Example</span></span>  
 <span data-ttu-id="c0b03-105">下面的代码示例演示如何使用停靠 <xref:System.Windows.Forms.ToolStripPanel> 控件来构造具有四个 <xref:System.Windows.Forms.ToolStrip> 控件的 MDI 窗口。</span><span class="sxs-lookup"><span data-stu-id="c0b03-105">The following code example demonstrates how to use docked <xref:System.Windows.Forms.ToolStripPanel> controls to frame an MDI window with four <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="c0b03-106">在该示例中，<xref:System.Windows.Forms.ToolStripPanel.Join%2A> 方法将 <xref:System.Windows.Forms.ToolStrip> 控件附加到相应的 <xref:System.Windows.Forms.ToolStripPanel> 控件上。</span><span class="sxs-lookup"><span data-stu-id="c0b03-106">In the example, the <xref:System.Windows.Forms.ToolStripPanel.Join%2A> method attaches the <xref:System.Windows.Forms.ToolStrip> controls to the corresponding <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c0b03-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="c0b03-107">Compiling the Code</span></span>  
 <span data-ttu-id="c0b03-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="c0b03-108">This example requires:</span></span>  
  
-   <span data-ttu-id="c0b03-109">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="c0b03-109">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="c0b03-110">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="c0b03-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c0b03-111">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="c0b03-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="c0b03-112">另请参阅[如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="c0b03-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0b03-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0b03-113">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripPanel>  
 <xref:System.Windows.Forms.ToolStripPanel.Join%2A>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="c0b03-114">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="c0b03-114">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
