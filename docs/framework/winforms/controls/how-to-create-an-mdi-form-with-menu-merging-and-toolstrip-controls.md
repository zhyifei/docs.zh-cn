---
title: 如何：创建合并了菜单并具有 ToolStrip 控件的 MDI 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
ms.openlocfilehash: badbf316c769f60001b2ca2a4cacbf268f600e8d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="a1638-102">如何：创建合并了菜单并具有 ToolStrip 控件的 MDI 窗体</span><span class="sxs-lookup"><span data-stu-id="a1638-102">How to: Create an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="a1638-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间支持多文档界面 (MDI) 应用程序，而 <xref:System.Windows.Forms.MenuStrip> 控件支持菜单合并。</span><span class="sxs-lookup"><span data-stu-id="a1638-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="a1638-104">MDI 窗体还可支持 <xref:System.Windows.Forms.ToolStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="a1638-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="a1638-105">没有对 Visual Studio 中的此功能提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="a1638-105">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="a1638-106">另请参阅[演练：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体](http://msdn.microsoft.com/library/ms233676\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="a1638-106">Also see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](http://msdn.microsoft.com/library/ms233676\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1638-107">示例</span><span class="sxs-lookup"><span data-stu-id="a1638-107">Example</span></span>  
 <span data-ttu-id="a1638-108">以下代码示例演示如何将 <xref:System.Windows.Forms.ToolStripPanel> 控件和 MDI 窗体配合使用。</span><span class="sxs-lookup"><span data-stu-id="a1638-108">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="a1638-109">此窗体还支持菜单与子菜单合并。</span><span class="sxs-lookup"><span data-stu-id="a1638-109">The form also supports menu merging with child menus.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a1638-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="a1638-110">Compiling the Code</span></span>  
 <span data-ttu-id="a1638-111">此代码示例需要：</span><span class="sxs-lookup"><span data-stu-id="a1638-111">This code example requires:</span></span>  
  
-   <span data-ttu-id="a1638-112">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="a1638-112">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="a1638-113">为 Visual Basic 或 Visual C# 中生成此示例从命令行有关的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="a1638-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="a1638-114">你也可以通过将代码粘贴到新项目中生成 Visual Studio 中的此示例。</span><span class="sxs-lookup"><span data-stu-id="a1638-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="a1638-115">另请参阅[如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="a1638-115">Also sssee [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1638-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1638-116">See Also</span></span>  
 [<span data-ttu-id="a1638-117">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="a1638-117">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
