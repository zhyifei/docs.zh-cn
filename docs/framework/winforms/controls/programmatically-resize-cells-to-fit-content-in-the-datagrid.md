---
title: 以编程方式调整单元格大小以适应 DataGridView 控件中的内容
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
ms.openlocfilehash: df3b378a8ba358fa0bfe549a7901b3d59d53f556
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742450"
---
# <a name="how-to-programmatically-resize-cells-to-fit-content-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="b8e59-102">如何：以编程方式调整单元格的大小来适应 Windows 窗体 DataGridView 控件中的内容</span><span class="sxs-lookup"><span data-stu-id="b8e59-102">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b8e59-103">可使用 <xref:System.Windows.Forms.DataGridView> 控件方法调整行、列和标头大小，以便它们显示其完整值而无截断。</span><span class="sxs-lookup"><span data-stu-id="b8e59-103">You can use the <xref:System.Windows.Forms.DataGridView> control methods to resize rows, columns, and headers so that they display their entire values without truncation.</span></span> <span data-ttu-id="b8e59-104">可在选择时使用这些方法调整 <xref:System.Windows.Forms.DataGridView> 元素的大小。</span><span class="sxs-lookup"><span data-stu-id="b8e59-104">You can use these methods to resize <xref:System.Windows.Forms.DataGridView> elements at times of your choosing.</span></span> <span data-ttu-id="b8e59-105">或者，可配置控件以在内容更改时自动调整这些元素的大小。</span><span class="sxs-lookup"><span data-stu-id="b8e59-105">Alternately, you can configure the control to resize these elements automatically whenever content changes.</span></span> <span data-ttu-id="b8e59-106">但是，在处理大型数据集或数据频繁更改时，这可能效率很低。</span><span class="sxs-lookup"><span data-stu-id="b8e59-106">This can be inefficient, however, when you are working with large data sets or when your data changes frequently.</span></span> <span data-ttu-id="b8e59-107">有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的调整大小选项](sizing-options-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="b8e59-107">For more information, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="b8e59-108">通常，只有在从数据源加载新数据或用户已编辑值时，才以编程方式调整 <xref:System.Windows.Forms.DataGridView> 元素以适合它的内容。</span><span class="sxs-lookup"><span data-stu-id="b8e59-108">Typically, you will programmatically adjust <xref:System.Windows.Forms.DataGridView> elements to fit their content only when you load new data from a data source or when the user has edited a value.</span></span> <span data-ttu-id="b8e59-109">此操作可用于优化性能，但当想要用户使用鼠标手动调整行和列的大小时，它也非常有用。</span><span class="sxs-lookup"><span data-stu-id="b8e59-109">This is useful to optimize performance, but it is also useful when you want to enable your users to manually resize rows and columns with the mouse.</span></span>  
  
 <span data-ttu-id="b8e59-110">以下代码示例演示可用于以编程方式调整大小的选项。</span><span class="sxs-lookup"><span data-stu-id="b8e59-110">The following code example demonstrates the options available to you for programmatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8e59-111">示例</span><span class="sxs-lookup"><span data-stu-id="b8e59-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CPP/programmaticsizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CS/programmaticsizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/VB/programmaticsizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b8e59-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="b8e59-112">Compiling the Code</span></span>  
 <span data-ttu-id="b8e59-113">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="b8e59-113">This example requires:</span></span>  
  
- <span data-ttu-id="b8e59-114">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="b8e59-114">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8e59-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8e59-115">See also</span></span>

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
- [<span data-ttu-id="b8e59-116">调整 Windows 窗体 DataGridView 控件中列和行的大小</span><span class="sxs-lookup"><span data-stu-id="b8e59-116">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="b8e59-117">Windows 窗体 DataGridView 控件中的重设大小选项</span><span class="sxs-lookup"><span data-stu-id="b8e59-117">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="b8e59-118">如何：在 Windows 窗体 DataGridView 控件中的内容发生变化时自动重设单元格大小</span><span class="sxs-lookup"><span data-stu-id="b8e59-118">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)
