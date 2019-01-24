---
title: 如何：在 Windows 窗体 DataGridView 控件中的内容更改时自动调整大小的单元格
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells automatically
- cells [Windows Forms], resizing automatically
- DataGridView control [Windows Forms], resizing cells
ms.assetid: 1d68934d-a04c-4b12-9e66-c856c6828131
ms.openlocfilehash: c745af77b5608a7b80f96e4d4421745ea28405ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592297"
---
# <a name="how-to-automatically-resize-cells-when-content-changes-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="f52da-102">如何：在 Windows 窗体 DataGridView 控件中的内容更改时自动调整大小的单元格</span><span class="sxs-lookup"><span data-stu-id="f52da-102">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f52da-103">你可以配置 <xref:System.Windows.Forms.DataGridView> 控件，使其在内容发生更改时自动重新调整行、列和标题，以便单元格始终足以显示其值，而不出现剪切情况。</span><span class="sxs-lookup"><span data-stu-id="f52da-103">You can configure the <xref:System.Windows.Forms.DataGridView> control to resize its rows, columns, and headers automatically whenever content changes, so that cells are always large enough to display their values without clipping.</span></span>  
  
 <span data-ttu-id="f52da-104">你可以选择多种方法来限制用于确定新大小的单元格类型。</span><span class="sxs-lookup"><span data-stu-id="f52da-104">You have many options to restrict which cells are used to determine the new sizes.</span></span> <span data-ttu-id="f52da-105">例如，你可以将控件配置为根据当前限制的行中的值自动调整列宽。</span><span class="sxs-lookup"><span data-stu-id="f52da-105">For example, you can configure the control to automatically resize the width of its columns based only on the values in rows that are currently displayed.</span></span> <span data-ttu-id="f52da-106">使用此方法，你可以提高处理大量行时的工作效率，尽管在这种情况下，你可能想要使用调整方法（例如， <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> ）在选择时调整大小。</span><span class="sxs-lookup"><span data-stu-id="f52da-106">With this, you can avoid inefficiency when working with large numbers of rows, although in this case, you might want to use sizing methods such as <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> to adjust sizes at times of your choosing.</span></span>  
  
 <span data-ttu-id="f52da-107">有关自动调整大小的详细信息，请参阅 [Windows 窗体 DataGridView 控件中的大小调整选项](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="f52da-107">For more information about automatic resizing, see [Sizing Options in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="f52da-108">以下代码示例演示了可用于自动调整大小的选项。</span><span class="sxs-lookup"><span data-stu-id="f52da-108">The following code example demonstrates the options available for automatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f52da-109">示例</span><span class="sxs-lookup"><span data-stu-id="f52da-109">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.AutoSizing#0](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CPP/autosizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.AutoSizing#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CS/autosizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.AutoSizing#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/VB/autosizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f52da-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="f52da-110">Compiling the Code</span></span>  
 <span data-ttu-id="f52da-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="f52da-111">This example requires:</span></span>  
  
-   <span data-ttu-id="f52da-112">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="f52da-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="f52da-113">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="f52da-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="f52da-114">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="f52da-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="f52da-115">另请参阅[如何：编译和运行完整的 Windows 窗体代码示例使用 Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="f52da-115">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f52da-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f52da-116">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [<span data-ttu-id="f52da-117">调整 Windows 窗体 DataGridView 控件中列和行的大小</span><span class="sxs-lookup"><span data-stu-id="f52da-117">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f52da-118">Windows 窗体 DataGridView 控件中的重设大小选项</span><span class="sxs-lookup"><span data-stu-id="f52da-118">Sizing Options in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f52da-119">如何：以编程方式调整大小以适应 Windows 窗体 DataGridView 控件中内容的单元格</span><span class="sxs-lookup"><span data-stu-id="f52da-119">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programmatically-resize-cells-to-fit-content-in-the-datagrid.md)
