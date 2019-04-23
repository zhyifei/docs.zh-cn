---
title: 如何：设置应用程序的 ToolStrip 呈现器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Renderer property [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], customizing
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
ms.openlocfilehash: 857d5ea3771b098d4edcbd7b24f1e6feaf3ec2cb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083071"
---
# <a name="how-to-set-the-toolstrip-renderer-for-an-application"></a><span data-ttu-id="b74d5-102">如何：设置应用程序的 ToolStrip 呈现器</span><span class="sxs-lookup"><span data-stu-id="b74d5-102">How to: Set the ToolStrip Renderer for an Application</span></span>
<span data-ttu-id="b74d5-103">可以单独自定义 <xref:System.Windows.Forms.ToolStrip> 控件的外观，或应用程序中所有 <xref:System.Windows.Forms.ToolStrip> 控件的外观。</span><span class="sxs-lookup"><span data-stu-id="b74d5-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> controls individually or for all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b74d5-104">示例</span><span class="sxs-lookup"><span data-stu-id="b74d5-104">Example</span></span>  
 <span data-ttu-id="b74d5-105">下面的代码示例演示如何有选择地应用自定义呈现器到 <xref:System.Windows.Forms.ToolStrip> 控件和 <xref:System.Windows.Forms.MenuStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="b74d5-105">The following code example demonstrates how to selectively apply a custom renderer to a <xref:System.Windows.Forms.ToolStrip> control and a <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="b74d5-106">若要使用此代码示例，请编译并运行该应用程序，然后从 <xref:System.Windows.Forms.ComboBox> 控件中选择自定义呈现的作用域。</span><span class="sxs-lookup"><span data-stu-id="b74d5-106">To use this code example, compile and run the application, and then select the scope of the custom rending from the <xref:System.Windows.Forms.ComboBox> control.</span></span> <span data-ttu-id="b74d5-107">单击“应用”设置呈现器。</span><span class="sxs-lookup"><span data-stu-id="b74d5-107">Click **Apply** to set the renderer.</span></span>  
  
 <span data-ttu-id="b74d5-108">若要查看自定义菜单项呈现，请选择<xref:System.Windows.Forms.MenuStrip>选项从<xref:System.Windows.Forms.ComboBox>控件中，单击**应用**，然后打开**文件**菜单项。</span><span class="sxs-lookup"><span data-stu-id="b74d5-108">To see custom menu item rendering, select the <xref:System.Windows.Forms.MenuStrip> option from the <xref:System.Windows.Forms.ComboBox> control, click **Apply**, and then open the **File** menu item.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 <span data-ttu-id="b74d5-109">设置 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 属性，将自定义呈现器应用到你的应用程序中所有的 <xref:System.Windows.Forms.ToolStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="b74d5-109">Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
 <span data-ttu-id="b74d5-110">设置 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 属性，将自定义呈现器应用到单个 <xref:System.Windows.Forms.ToolStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="b74d5-110">Set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to an individual <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b74d5-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="b74d5-111">Compiling the Code</span></span>  
 <span data-ttu-id="b74d5-112">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="b74d5-112">This example requires:</span></span>  
  
-   <span data-ttu-id="b74d5-113">对 System.Design、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="b74d5-113">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="b74d5-114">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="b74d5-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b74d5-115">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="b74d5-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b74d5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b74d5-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [<span data-ttu-id="b74d5-117">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="b74d5-117">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
