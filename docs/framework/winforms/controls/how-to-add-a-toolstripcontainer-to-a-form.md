---
title: 如何：向窗体添加 ToolStripContainer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
ms.openlocfilehash: d70c5b8f548cf325083782d6ea185c18fd2fa003
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011133"
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a><span data-ttu-id="01835-102">如何：向窗体添加 ToolStripContainer</span><span class="sxs-lookup"><span data-stu-id="01835-102">How to: Add a ToolStripContainer to a Form</span></span>
<span data-ttu-id="01835-103">可以通过编程方式向 Windows 窗体添加 <xref:System.Windows.Forms.ToolStripContainer> 并用控件填充该窗体。</span><span class="sxs-lookup"><span data-stu-id="01835-103">You can programmatically add a <xref:System.Windows.Forms.ToolStripContainer> to a Windows Form and populate it with controls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01835-104">示例</span><span class="sxs-lookup"><span data-stu-id="01835-104">Example</span></span>  
 <span data-ttu-id="01835-105">下面的代码示例演示如何向 Windows 窗体添加 <xref:System.Windows.Forms.ToolStripContainer> 和 <xref:System.Windows.Forms.ToolStrip>，如何向 <xref:System.Windows.Forms.ToolStrip> 添加项，以及如何向 <xref:System.Windows.Forms.ToolStripContainer> 的 <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> 添加 <xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="01835-105">The following code example demonstrates how to add a <xref:System.Windows.Forms.ToolStripContainer> and a <xref:System.Windows.Forms.ToolStrip> to a Windows Forms, how to add items to the <xref:System.Windows.Forms.ToolStrip>, and how to add the <xref:System.Windows.Forms.ToolStrip> to the <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="01835-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="01835-106">Compiling the Code</span></span>  
 <span data-ttu-id="01835-107">此代码示例需要：</span><span class="sxs-lookup"><span data-stu-id="01835-107">This code example requires:</span></span>  
  
- <span data-ttu-id="01835-108">引用 System.Drawing、System.Text 和 System.Windows.Forms 程序集。</span><span class="sxs-lookup"><span data-stu-id="01835-108">References to the System.Drawing, System.Text, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="01835-109">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="01835-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="01835-110">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="01835-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="01835-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="01835-111">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="01835-112">ToolStripContainer 控件</span><span class="sxs-lookup"><span data-stu-id="01835-112">ToolStripContainer Control</span></span>](toolstripcontainer-control.md)
- [<span data-ttu-id="01835-113">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="01835-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
