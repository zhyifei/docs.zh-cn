---
title: 如何：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体
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
ms.openlocfilehash: 6cbab3c588aa74809a7aef80ae6ffc4c3772069f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646011"
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="bfea2-102">如何：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体</span><span class="sxs-lookup"><span data-stu-id="bfea2-102">How to: Create an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="bfea2-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间支持多文档界面 (MDI) 应用程序，而 <xref:System.Windows.Forms.MenuStrip> 控件支持菜单合并。</span><span class="sxs-lookup"><span data-stu-id="bfea2-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="bfea2-104">MDI 窗体还可支持 <xref:System.Windows.Forms.ToolStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="bfea2-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="bfea2-105">没有对此功能在 Visual Studio 中的广泛支持。</span><span class="sxs-lookup"><span data-stu-id="bfea2-105">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="bfea2-106">另请参阅[演练：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="bfea2-106">Also see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfea2-107">示例</span><span class="sxs-lookup"><span data-stu-id="bfea2-107">Example</span></span>  
 <span data-ttu-id="bfea2-108">以下代码示例演示如何将 <xref:System.Windows.Forms.ToolStripPanel> 控件和 MDI 窗体配合使用。</span><span class="sxs-lookup"><span data-stu-id="bfea2-108">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="bfea2-109">此窗体还支持菜单与子菜单合并。</span><span class="sxs-lookup"><span data-stu-id="bfea2-109">The form also supports menu merging with child menus.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bfea2-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="bfea2-110">Compiling the Code</span></span>  
 <span data-ttu-id="bfea2-111">此代码示例需要：</span><span class="sxs-lookup"><span data-stu-id="bfea2-111">This code example requires:</span></span>  
  
-   <span data-ttu-id="bfea2-112">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="bfea2-112">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="bfea2-113">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="bfea2-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="bfea2-114">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="bfea2-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="bfea2-115">另请参阅[如何：编译和运行完整的 Windows 窗体代码示例使用 Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="bfea2-115">Also sssee [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfea2-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfea2-116">See also</span></span>
- [<span data-ttu-id="bfea2-117">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="bfea2-117">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
