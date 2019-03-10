---
title: 如何：定义停靠的 ToolStrip 控件的 Z 顺序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], specifying z-order
- z-order
ms.assetid: 8b595429-ba9f-46af-9c55-3d5cc53f7fff
ms.openlocfilehash: 1ae7e6f63488d2dbb6b408cdf255f111f929298f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722653"
---
# <a name="how-to-define-z-ordering-of-docked-toolstrip-controls"></a><span data-ttu-id="107f7-102">如何：定义停靠的 ToolStrip 控件的 Z 顺序</span><span class="sxs-lookup"><span data-stu-id="107f7-102">How to: Define Z-Ordering of Docked ToolStrip Controls</span></span>
<span data-ttu-id="107f7-103">若要通过停靠正确定位 <xref:System.Windows.Forms.ToolStrip> 控件，则必须在窗体的 z 顺序中正确定位该控件。</span><span class="sxs-lookup"><span data-stu-id="107f7-103">To position a <xref:System.Windows.Forms.ToolStrip> control correctly with docking, you must position the control correctly in the form's z-order.</span></span>  
  
## <a name="example"></a><span data-ttu-id="107f7-104">示例</span><span class="sxs-lookup"><span data-stu-id="107f7-104">Example</span></span>  
 <span data-ttu-id="107f7-105">下面的代码示例演示如何通过指定 z 顺序排列 <xref:System.Windows.Forms.ToolStrip> 控件和停靠的 <xref:System.Windows.Forms.MenuStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="107f7-105">The following code example demonstrates how to arrange a <xref:System.Windows.Forms.ToolStrip> control and a docked <xref:System.Windows.Forms.MenuStrip> control by specifying the z-order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#21)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#21)]  
  
 <span data-ttu-id="107f7-106">z 顺序由 <xref:System.Windows.Forms.ToolStrip> 和 <xref:System.Windows.Forms.MenuStrip></span><span class="sxs-lookup"><span data-stu-id="107f7-106">The z-order is determined by the order in which the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip></span></span>  
  
 <span data-ttu-id="107f7-107">控件添加到窗体的 <xref:System.Windows.Forms.Control.Controls%2A> 集合的顺序决定。</span><span class="sxs-lookup"><span data-stu-id="107f7-107">controls are added to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#23)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#23)]  
  
 <span data-ttu-id="107f7-108">颠倒 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> 方法的调用顺序，查看对布局产生的影响。</span><span class="sxs-lookup"><span data-stu-id="107f7-108">Reverse the order of these calls to the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method and view the effect on the layout.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="107f7-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="107f7-109">Compiling the Code</span></span>  
 <span data-ttu-id="107f7-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="107f7-110">This example requires:</span></span>  
  
-   <span data-ttu-id="107f7-111">对 System.Design、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="107f7-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="107f7-112">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="107f7-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="107f7-113">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="107f7-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="107f7-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="107f7-114">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>
- <xref:System.Windows.Forms.Control.Controls%2A>
- <xref:System.Windows.Forms.Control.Dock%2A>
- [<span data-ttu-id="107f7-115">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="107f7-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
