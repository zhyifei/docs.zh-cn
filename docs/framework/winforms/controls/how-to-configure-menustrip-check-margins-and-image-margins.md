---
title: 如何：配置 MenuStrip 选中边距和图像边距
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins [Windows Forms], setting in MenuStrip controls
- menus [Windows Forms], setting margins
- MenuStrip control [Windows Forms], configuring check and image margins
ms.assetid: 45a9075d-4bea-4ce2-9b2c-7619aa39f8ce
ms.openlocfilehash: 5db4b3546b6c15af916d53b1a53c347174f1f30b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64643125"
---
# <a name="how-to-configure-menustrip-check-margins-and-image-margins"></a><span data-ttu-id="58333-102">如何：配置 MenuStrip 选中边距和图像边距</span><span class="sxs-lookup"><span data-stu-id="58333-102">How to: Configure MenuStrip Check Margins and Image Margins</span></span>
<span data-ttu-id="58333-103">可以通过设置各种组合中的 <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> 和 <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> 属性来自定义 <xref:System.Windows.Forms.MenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="58333-103">You can customize a <xref:System.Windows.Forms.MenuStrip> by setting the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> properties in various combinations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58333-104">示例</span><span class="sxs-lookup"><span data-stu-id="58333-104">Example</span></span>  
 <span data-ttu-id="58333-105">下面的代码示例演示如何设置和自定义 <xref:System.Windows.Forms.ContextMenuStrip> 选中边距和图像边距。</span><span class="sxs-lookup"><span data-stu-id="58333-105">The following code example demonstrates how to set and customize the <xref:System.Windows.Forms.ContextMenuStrip> check margins and image margins.</span></span> <span data-ttu-id="58333-106">该过程在 <xref:System.Windows.Forms.ContextMenuStrip> 或 <xref:System.Windows.Forms.MenuStrip>是相同的。</span><span class="sxs-lookup"><span data-stu-id="58333-106">The procedure is the same for a <xref:System.Windows.Forms.ContextMenuStrip> or a <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="58333-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="58333-107">Compiling the Code</span></span>  
 <span data-ttu-id="58333-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="58333-108">This example requires:</span></span>  
  
- <span data-ttu-id="58333-109">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="58333-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="58333-110">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="58333-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="58333-111">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="58333-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58333-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="58333-112">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="58333-113">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="58333-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="58333-114">如何：启用选中边距和 ContextMenuStrip 控件中的图像边距</span><span class="sxs-lookup"><span data-stu-id="58333-114">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>](how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)
