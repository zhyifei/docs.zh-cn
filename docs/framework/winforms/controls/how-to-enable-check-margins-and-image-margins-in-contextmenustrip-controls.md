---
title: 如何：启用选中边距和 ContextMenuStrip 控件中的图像边距
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ShowCheckMargin property [Windows Forms]
- ShowImageMargin property [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: eb584e71-59da-4012-aaca-dbe1c7c7a156
ms.openlocfilehash: 881590f74805c0acdac80a1c2779cd978af39b90
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705319"
---
# <a name="how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls"></a><span data-ttu-id="9d7b2-102">如何：启用选中边距和 ContextMenuStrip 控件中的图像边距</span><span class="sxs-lookup"><span data-stu-id="9d7b2-102">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>
<span data-ttu-id="9d7b2-103">可在具有复选标记和自定义图像的 <xref:System.Windows.Forms.MenuStrip> 控件中自定义 <xref:System.Windows.Forms.ToolStripMenuItem> 对象。</span><span class="sxs-lookup"><span data-stu-id="9d7b2-103">You can customize the <xref:System.Windows.Forms.ToolStripMenuItem> objects in your <xref:System.Windows.Forms.MenuStrip> control with check marks and custom images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d7b2-104">示例</span><span class="sxs-lookup"><span data-stu-id="9d7b2-104">Example</span></span>  
 <span data-ttu-id="9d7b2-105">以下代码示例演示了如何创建具有复选标记和自定义图像的菜单项。</span><span class="sxs-lookup"><span data-stu-id="9d7b2-105">The following code example demonstrates how to create menu items that have check marks and custom images.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
 <span data-ttu-id="9d7b2-106">设置 <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A?displayProperty=nameWithType> 属性以指定复选标记和自定义图像何时在菜单项中显示。</span><span class="sxs-lookup"><span data-stu-id="9d7b2-106">Set the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A?displayProperty=nameWithType> properties to specify when check marks and custom images appear in your menu items.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9d7b2-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="9d7b2-107">Compiling the Code</span></span>  
 <span data-ttu-id="9d7b2-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="9d7b2-108">This example requires:</span></span>  
  
-   <span data-ttu-id="9d7b2-109">对 System.Design、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="9d7b2-109">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="9d7b2-110">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="9d7b2-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9d7b2-111">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="9d7b2-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d7b2-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d7b2-112">See also</span></span>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDownMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="9d7b2-113">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="9d7b2-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
