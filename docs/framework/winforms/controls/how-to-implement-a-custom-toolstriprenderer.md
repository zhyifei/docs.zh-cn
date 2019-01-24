---
title: 如何：实现自定义 ToolStripRenderer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
ms.openlocfilehash: e99ffc45f3762ee816583a5294d56be30dfbff1a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577342"
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a><span data-ttu-id="eb20e-102">如何：实现自定义 ToolStripRenderer</span><span class="sxs-lookup"><span data-stu-id="eb20e-102">How to: Implement a Custom ToolStripRenderer</span></span>
<span data-ttu-id="eb20e-103">可以通过实现从 <xref:System.Windows.Forms.ToolStripRenderer> 中派生的类来自定义 <xref:System.Windows.Forms.ToolStrip> 控件的外观。</span><span class="sxs-lookup"><span data-stu-id="eb20e-103">You can customize the appearance of a <xref:System.Windows.Forms.ToolStrip> control by implementing a class that derives from <xref:System.Windows.Forms.ToolStripRenderer>.</span></span> <span data-ttu-id="eb20e-104">这使你可以灵活地创建一个不同于 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 类和 <xref:System.Windows.Forms.ToolStripSystemRenderer> 类提供的外观的外观。</span><span class="sxs-lookup"><span data-stu-id="eb20e-104">This gives you the flexibility to create an appearance that differs from the appearance provided the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> and <xref:System.Windows.Forms.ToolStripSystemRenderer> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb20e-105">示例</span><span class="sxs-lookup"><span data-stu-id="eb20e-105">Example</span></span>  
 <span data-ttu-id="eb20e-106">以下代码示例演示了如何实现一个自定义 <xref:System.Windows.Forms.ToolStripRenderer> 类。</span><span class="sxs-lookup"><span data-stu-id="eb20e-106">The following code example demonstrates how to implement a custom <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="eb20e-107">在此示例中，`GridStrip` 控件实现了一个滑动磁贴拼图，这样用户就可以在表布局中移动磁贴，以形成图像。</span><span class="sxs-lookup"><span data-stu-id="eb20e-107">In this example, the `GridStrip` control implements a sliding-tile puzzle, which allows the user to move tiles in a table layout to form an image.</span></span> <span data-ttu-id="eb20e-108">某个自定义 <xref:System.Windows.Forms.ToolStrip> 控件在网格布局中排列其 <xref:System.Windows.Forms.ToolStripButton> 控件。</span><span class="sxs-lookup"><span data-stu-id="eb20e-108">A custom <xref:System.Windows.Forms.ToolStrip> control arranges its <xref:System.Windows.Forms.ToolStripButton> controls in a grid layout.</span></span> <span data-ttu-id="eb20e-109">布局包含一个空单元格，用户可以通过拖放操作，将相邻的磁贴滑动到其中。</span><span class="sxs-lookup"><span data-stu-id="eb20e-109">The layout contains one empty cell, into which the user can slide an adjacent tile by using a drag-and-drop operation.</span></span> <span data-ttu-id="eb20e-110">用户可以移动的磁贴会突出显示。</span><span class="sxs-lookup"><span data-stu-id="eb20e-110">Tiles that the user can move are highlighted.</span></span>  
  
 <span data-ttu-id="eb20e-111">`GridStripRenderer` 类自定义了 `GridStrip` 控件外观的三个方面：</span><span class="sxs-lookup"><span data-stu-id="eb20e-111">The `GridStripRenderer` class customizes three aspects of the `GridStrip` control's appearance:</span></span>  
  
-   <span data-ttu-id="eb20e-112">`GridStrip` 边框</span><span class="sxs-lookup"><span data-stu-id="eb20e-112">`GridStrip` border</span></span>  
  
-   <span data-ttu-id="eb20e-113"><xref:System.Windows.Forms.ToolStripButton> 边框</span><span class="sxs-lookup"><span data-stu-id="eb20e-113"><xref:System.Windows.Forms.ToolStripButton> border</span></span>  
  
-   <span data-ttu-id="eb20e-114"><xref:System.Windows.Forms.ToolStripButton> 图像</span><span class="sxs-lookup"><span data-stu-id="eb20e-114"><xref:System.Windows.Forms.ToolStripButton> image</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eb20e-115">编译代码</span><span class="sxs-lookup"><span data-stu-id="eb20e-115">Compiling the Code</span></span>  
 <span data-ttu-id="eb20e-116">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="eb20e-116">This example requires:</span></span>  
  
-   <span data-ttu-id="eb20e-117">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="eb20e-117">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="eb20e-118">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="eb20e-118">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="eb20e-119">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="eb20e-119">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="eb20e-120">另请参阅[如何：编译和运行完整的 Windows 窗体代码示例使用 Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="eb20e-120">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb20e-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb20e-121">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="eb20e-122">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="eb20e-122">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
