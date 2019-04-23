---
title: 如何：在 ToolStrip 应用程序中自定义颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], customizing colors
- colors [Windows Forms], customizing in ToolStrip controls [Windows Forms]
- ToolStrip control [Windows Forms], custom colors
ms.assetid: e2752fe2-1afb-489e-ab96-b7805acd96bc
ms.openlocfilehash: 4d051085bdba41b9784d3dd7f921189c1300daf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "59980546"
---
# <a name="how-to-customize-colors-in-toolstrip-applications"></a><span data-ttu-id="b4a4b-102">如何：在 ToolStrip 应用程序中自定义颜色</span><span class="sxs-lookup"><span data-stu-id="b4a4b-102">How to: Customize Colors in ToolStrip Applications</span></span>
<span data-ttu-id="b4a4b-103">可借助 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 类使用自定义颜色来自定义 <xref:System.Windows.Forms.ToolStrip> 的外观。</span><span class="sxs-lookup"><span data-stu-id="b4a4b-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> by using the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class to use customized colors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4a4b-104">示例</span><span class="sxs-lookup"><span data-stu-id="b4a4b-104">Example</span></span>  
 <span data-ttu-id="b4a4b-105">下面的代码示例演示如何使用 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 在运行时定义自定义颜色。</span><span class="sxs-lookup"><span data-stu-id="b4a4b-105">The following code example demonstrates how to use a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> to define custom colors at run time.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b4a4b-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="b4a4b-106">Compiling the Code</span></span>  
 <span data-ttu-id="b4a4b-107">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="b4a4b-107">This example requires:</span></span>  
  
-   <span data-ttu-id="b4a4b-108">对 System.Design、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="b4a4b-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="b4a4b-109">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="b4a4b-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b4a4b-110">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="b4a4b-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4a4b-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4a4b-111">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
