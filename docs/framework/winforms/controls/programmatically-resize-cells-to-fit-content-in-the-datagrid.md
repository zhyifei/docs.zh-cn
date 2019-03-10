---
title: 如何：以编程方式调整大小以适应 Windows 窗体 DataGridView 控件中内容的单元格
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells to fit content
- cells [Windows Forms], resizing to fit contents
- DataGridView control [Windows Forms], resizing cells
- grids [Windows Forms], resizing cells to fit content
ms.assetid: 63d770dc-b3f5-462b-901a-3125b2753792
ms.openlocfilehash: 09ac5e43653a3389737777258db3bb5e0ed4c0a1
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722914"
---
# <a name="how-to-programmatically-resize-cells-to-fit-content-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="7b4ce-102">如何：以编程方式调整大小以适应 Windows 窗体 DataGridView 控件中内容的单元格</span><span class="sxs-lookup"><span data-stu-id="7b4ce-102">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="7b4ce-103">可使用 <xref:System.Windows.Forms.DataGridView> 控件方法调整行、列和标头大小，以便它们显示其完整值而无截断。</span><span class="sxs-lookup"><span data-stu-id="7b4ce-103">You can use the <xref:System.Windows.Forms.DataGridView> control methods to resize rows, columns, and headers so that they display their entire values without truncation.</span></span> <span data-ttu-id="7b4ce-104">可在选择时使用这些方法调整 <xref:System.Windows.Forms.DataGridView> 元素的大小。</span><span class="sxs-lookup"><span data-stu-id="7b4ce-104">You can use these methods to resize <xref:System.Windows.Forms.DataGridView> elements at times of your choosing.</span></span> <span data-ttu-id="7b4ce-105">或者，可配置控件以在内容更改时自动调整这些元素的大小。</span><span class="sxs-lookup"><span data-stu-id="7b4ce-105">Alternately, you can configure the control to resize these elements automatically whenever content changes.</span></span> <span data-ttu-id="7b4ce-106">但是，在处理大型数据集或数据频繁更改时，这可能效率很低。</span><span class="sxs-lookup"><span data-stu-id="7b4ce-106">This can be inefficient, however, when you are working with large data sets or when your data changes frequently.</span></span> <span data-ttu-id="7b4ce-107">有关详细信息，请参阅[Windows 窗体 DataGridView 控件中调整大小选项](sizing-options-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="7b4ce-107">For more information, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="7b4ce-108">通常，只有在从数据源加载新数据或用户已编辑值时，才以编程方式调整 <xref:System.Windows.Forms.DataGridView> 元素以适合它的内容。</span><span class="sxs-lookup"><span data-stu-id="7b4ce-108">Typically, you will programmatically adjust <xref:System.Windows.Forms.DataGridView> elements to fit their content only when you load new data from a data source or when the user has edited a value.</span></span> <span data-ttu-id="7b4ce-109">此操作可用于优化性能，但当想要用户使用鼠标手动调整行和列的大小时，它也非常有用。</span><span class="sxs-lookup"><span data-stu-id="7b4ce-109">This is useful to optimize performance, but it is also useful when you want to enable your users to manually resize rows and columns with the mouse.</span></span>  
  
 <span data-ttu-id="7b4ce-110">以下代码示例演示可用于以编程方式调整大小的选项。</span><span class="sxs-lookup"><span data-stu-id="7b4ce-110">The following code example demonstrates the options available to you for programmatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b4ce-111">示例</span><span class="sxs-lookup"><span data-stu-id="7b4ce-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CPP/programmaticsizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CS/programmaticsizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/VB/programmaticsizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7b4ce-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="7b4ce-112">Compiling the Code</span></span>  
 <span data-ttu-id="7b4ce-113">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="7b4ce-113">This example requires:</span></span>  
  
-   <span data-ttu-id="7b4ce-114">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="7b4ce-114">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="7b4ce-115">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="7b4ce-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="7b4ce-116">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="7b4ce-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b4ce-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b4ce-117">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [<span data-ttu-id="7b4ce-118">调整 Windows 窗体 DataGridView 控件中列和行的大小</span><span class="sxs-lookup"><span data-stu-id="7b4ce-118">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="7b4ce-119">Windows 窗体 DataGridView 控件中的重设大小选项</span><span class="sxs-lookup"><span data-stu-id="7b4ce-119">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="7b4ce-120">如何：在 Windows 窗体 DataGridView 控件中的内容更改时自动调整大小的单元格</span><span class="sxs-lookup"><span data-stu-id="7b4ce-120">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)
