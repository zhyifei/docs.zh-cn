---
title: 如何：联接 ToolStripPanel
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], joining together
- ToolStripPanel control [Windows Forms], joining together
ms.assetid: 4eadda6d-e3b8-4151-aaf2-a8d564fbe6b3
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 80a3194b4c300bf72306abd3f080fbff9eca6e52
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-join-toolstrippanels"></a><span data-ttu-id="fc3cc-102">如何：联接 ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="fc3cc-102">How to: Join ToolStripPanels</span></span>
<span data-ttu-id="fc3cc-103">您可以在运行时将 <xref:System.Windows.Forms.ToolStrip> 控件联接到 <xref:System.Windows.Forms.ToolStripPanel>，它提供了多文档界面 (MDI) 应用程序的灵活性。</span><span class="sxs-lookup"><span data-stu-id="fc3cc-103">You can join <xref:System.Windows.Forms.ToolStrip> controls to a <xref:System.Windows.Forms.ToolStripPanel> at run time, which provides the flexibility of multiple-document interface (MDI) applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc3cc-104">示例</span><span class="sxs-lookup"><span data-stu-id="fc3cc-104">Example</span></span>  
 <span data-ttu-id="fc3cc-105">下列代码示例演示如何将 <xref:System.Windows.Forms.ToolStrip> 控件联接到 <xref:System.Windows.Forms.ToolStripPanel>。</span><span class="sxs-lookup"><span data-stu-id="fc3cc-105">The following code example demonstrates how to join <xref:System.Windows.Forms.ToolStrip> controls to a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#11)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fc3cc-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="fc3cc-106">Compiling the Code</span></span>  
 <span data-ttu-id="fc3cc-107">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="fc3cc-107">This example requires:</span></span>  
  
-   <span data-ttu-id="fc3cc-108">对 System.Design、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="fc3cc-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="fc3cc-109">有关生成此示例从 visual Basic 或 Visual C# 的命令行的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="fc3cc-109">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fc3cc-110">你也可以通过将代码粘贴到新项目中生成 Visual Studio 中的此示例。</span><span class="sxs-lookup"><span data-stu-id="fc3cc-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="fc3cc-111">另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="fc3cc-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc3cc-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc3cc-112">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripPanel>  
 [<span data-ttu-id="fc3cc-113">如何：在 MDI 中使用 ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="fc3cc-113">How to: Use ToolStripPanels for MDI</span></span>](../../../../docs/framework/winforms/controls/how-to-use-toolstrippanels-for-mdi.md)
