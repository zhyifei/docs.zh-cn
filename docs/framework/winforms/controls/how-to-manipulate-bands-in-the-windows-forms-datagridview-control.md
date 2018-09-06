---
title: 如何：操作 Windows 窗体 DataGridView 控件中的带区
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], manipulating bands
- bands [Windows Forms], manipulating in Windows Forms
- DataGridView control [Windows Forms], manipulating bands
ms.assetid: 1ea3470e-480f-4edc-bcbd-51373eca3856
ms.openlocfilehash: 93d06f0c6a19d37171eba1c4521ce55e1483ae2a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855395"
---
# <a name="how-to-manipulate-bands-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e9cb3-102">如何：操作 Windows 窗体 DataGridView 控件中的带区</span><span class="sxs-lookup"><span data-stu-id="e9cb3-102">How to: Manipulate Bands in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e9cb3-103">以下代码示例介绍了使用从 <xref:System.Windows.Forms.DataGridViewRow> 和 <xref:System.Windows.Forms.DataGridViewColumn> 类派生的 <xref:System.Windows.Forms.DataGridViewBand> 类的属性处理 <xref:System.Windows.Forms.DataGridView> 行和列的各种方法。</span><span class="sxs-lookup"><span data-stu-id="e9cb3-103">The following code example shows various ways to manipulate <xref:System.Windows.Forms.DataGridView> rows and columns using properties of the <xref:System.Windows.Forms.DataGridViewBand> class from which the <xref:System.Windows.Forms.DataGridViewRow> and <xref:System.Windows.Forms.DataGridViewColumn> classes derive.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9cb3-104">示例</span><span class="sxs-lookup"><span data-stu-id="e9cb3-104">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ButtonDemos#0](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CPP/DataGridViewBandDemo.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ButtonDemos#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CS/DataGridViewBandDemo.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ButtonDemos#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/VB/datagridviewbanddemo.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e9cb3-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="e9cb3-105">Compiling the Code</span></span>  
 <span data-ttu-id="e9cb3-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="e9cb3-106">This example requires:</span></span>  
  
-   <span data-ttu-id="e9cb3-107">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="e9cb3-107">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="e9cb3-108">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="e9cb3-108">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="e9cb3-109">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="e9cb3-109">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="e9cb3-110">另请参阅[如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="e9cb3-110">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9cb3-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9cb3-111">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewBand>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [<span data-ttu-id="e9cb3-112">使用 Windows 窗体 DataGridView 控件中的单元格、行和列编程</span><span class="sxs-lookup"><span data-stu-id="e9cb3-112">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
