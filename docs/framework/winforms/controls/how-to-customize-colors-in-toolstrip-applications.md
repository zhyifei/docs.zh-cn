---
title: 如何：自定义 ToolStrip 应用程序中的颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], customizing colors
- colors [Windows Forms], customizing in ToolStrip controls [Windows Forms]
- ToolStrip control [Windows Forms], custom colors
ms.assetid: e2752fe2-1afb-489e-ab96-b7805acd96bc
ms.openlocfilehash: 9a3f712a4d729452ac0d2d4755a5fba59ca102ed
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858728"
---
# <a name="how-to-customize-colors-in-toolstrip-applications"></a><span data-ttu-id="b9262-102">如何：自定义 ToolStrip 应用程序中的颜色</span><span class="sxs-lookup"><span data-stu-id="b9262-102">How to: Customize Colors in ToolStrip Applications</span></span>
<span data-ttu-id="b9262-103">可借助 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 类使用自定义颜色来自定义 <xref:System.Windows.Forms.ToolStrip> 的外观。</span><span class="sxs-lookup"><span data-stu-id="b9262-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> by using the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class to use customized colors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9262-104">示例</span><span class="sxs-lookup"><span data-stu-id="b9262-104">Example</span></span>  
 <span data-ttu-id="b9262-105">下面的代码示例演示如何使用 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 在运行时定义自定义颜色。</span><span class="sxs-lookup"><span data-stu-id="b9262-105">The following code example demonstrates how to use a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> to define custom colors at run time.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b9262-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="b9262-106">Compiling the Code</span></span>  
 <span data-ttu-id="b9262-107">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="b9262-107">This example requires:</span></span>  
  
-   <span data-ttu-id="b9262-108">对 System.Design、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="b9262-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="b9262-109">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="b9262-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b9262-110">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="b9262-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="b9262-111">另请参阅[如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="b9262-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9262-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9262-112">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.ProfessionalColorTable>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
