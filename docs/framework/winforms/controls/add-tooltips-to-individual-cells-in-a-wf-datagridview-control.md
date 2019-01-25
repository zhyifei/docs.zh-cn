---
title: 如何：Windows 窗体 DataGridView 控件中的单个单元格添加工具提示
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: baa6f79f2e0d454412992d9c951734a3437a96cf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517638"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a><span data-ttu-id="cb85f-102">如何：Windows 窗体 DataGridView 控件中的单个单元格添加工具提示</span><span class="sxs-lookup"><span data-stu-id="cb85f-102">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="cb85f-103">默认情况下，使用工具提示显示的值<xref:System.Windows.Forms.DataGridView>太小而无法显示其完整内容的单元格。</span><span class="sxs-lookup"><span data-stu-id="cb85f-103">By default, ToolTips are used to display the values of <xref:System.Windows.Forms.DataGridView> cells that are too small to show their entire contents.</span></span> <span data-ttu-id="cb85f-104">您可以重写此行为，但是，若要设置的各个单元格工具提示文本值。</span><span class="sxs-lookup"><span data-stu-id="cb85f-104">You can override this behavior, however, to set ToolTip-text values for individual cells.</span></span> <span data-ttu-id="cb85f-105">这是要显示给用户的单元的相关的其他信息，或向用户提供的单元格内容的其他说明。</span><span class="sxs-lookup"><span data-stu-id="cb85f-105">This is useful to display to users additional information about a cell or to provide to users an alternate description of the cell contents.</span></span> <span data-ttu-id="cb85f-106">例如，如果有行显示状态图标，你可能想要提供了使用工具提示的文本说明。</span><span class="sxs-lookup"><span data-stu-id="cb85f-106">For example, if you have a row that displays status icons, you may want to provide text explanations using ToolTips.</span></span>  
  
 <span data-ttu-id="cb85f-107">此外可以通过设置禁用的单元格级别工具提示显示<xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="cb85f-107">You can also disable the display of cell-level ToolTips by setting the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
### <a name="to-add-a-tooltip-to-a-cell"></a><span data-ttu-id="cb85f-108">若要向单元格添加工具提示</span><span class="sxs-lookup"><span data-stu-id="cb85f-108">To add a ToolTip to a cell</span></span>  
  
-   <span data-ttu-id="cb85f-109">设置 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="cb85f-109">Set the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cb85f-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="cb85f-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="cb85f-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="cb85f-111">This example requires:</span></span>  
  
-   <span data-ttu-id="cb85f-112">一个<xref:System.Windows.Forms.DataGridView>名为控件`dataGridView1`，其中包含一个名为列`Rating`显示字符串值的一到四个星号 ("\*") 符号。</span><span class="sxs-lookup"><span data-stu-id="cb85f-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Rating` for displaying string values of one through four asterisk ("\*") symbols.</span></span> <span data-ttu-id="cb85f-113"><xref:System.Windows.Forms.DataGridView.CellFormatting>控件的事件必须与在示例中所示的事件处理程序方法关联。</span><span class="sxs-lookup"><span data-stu-id="cb85f-113">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event of the control must be associated with the event handler method shown in the example.</span></span>  
  
-   <span data-ttu-id="cb85f-114">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="cb85f-114">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="cb85f-115">可靠编程</span><span class="sxs-lookup"><span data-stu-id="cb85f-115">Robust Programming</span></span>  
 <span data-ttu-id="cb85f-116">当绑定<xref:System.Windows.Forms.DataGridView>到外部数据源控件或通过实现虚拟模式下提供您自己的数据源，可能会遇到性能问题。</span><span class="sxs-lookup"><span data-stu-id="cb85f-116">When you bind the <xref:System.Windows.Forms.DataGridView> control to an external data source or provide your own data source by implementing virtual mode, you might encounter performance issues.</span></span> <span data-ttu-id="cb85f-117">若要使用的大量数据时，请避免对性能产生负面影响，请处理<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>事件而不是设置<xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A>的多个单元格的属性。</span><span class="sxs-lookup"><span data-stu-id="cb85f-117">To avoid a performance penalty when working with large amounts of data, handle the <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> event rather than setting the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property of multiple cells.</span></span> <span data-ttu-id="cb85f-118">当处理此情况下，获取单元格的值<xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A>属性引发事件，并返回的值<xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType>属性设置为指定在事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cb85f-118">When you handle this event, getting the value of a cell <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property raises the event and returns the value of the <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> property as specified in the event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb85f-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb85f-119">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [<span data-ttu-id="cb85f-120">使用 Windows 窗体 DataGridView 控件中的单元格、行和列编程</span><span class="sxs-lookup"><span data-stu-id="cb85f-120">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
