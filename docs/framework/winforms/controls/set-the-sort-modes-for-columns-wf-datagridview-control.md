---
title: 如何：设置 Windows 窗体 DataGridView 控件中列的排序模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 4894de00a323f70ca244ea877101a5af1cbb37e0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096363"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="f42e1-102">如何：设置 Windows 窗体 DataGridView 控件中列的排序模式</span><span class="sxs-lookup"><span data-stu-id="f42e1-102">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f42e1-103">在<xref:System.Windows.Forms.DataGridView>控件中，文本框列使用自动排序默认情况下，而其他列类型不会自动排序。</span><span class="sxs-lookup"><span data-stu-id="f42e1-103">In the <xref:System.Windows.Forms.DataGridView> control, text box columns use automatic sorting by default, while other column types are not sorted automatically.</span></span> <span data-ttu-id="f42e1-104">有时想要重写这些默认值。</span><span class="sxs-lookup"><span data-stu-id="f42e1-104">Sometimes you will want to override these defaults.</span></span> <span data-ttu-id="f42e1-105">例如，可以显示图像以代替文本、 数字或枚举单元格的值。</span><span class="sxs-lookup"><span data-stu-id="f42e1-105">For example, you can display images in place of text, numbers, or enumeration cell values.</span></span> <span data-ttu-id="f42e1-106">映像不能进行排序，而它们所代表的基础值可以进行排序。</span><span class="sxs-lookup"><span data-stu-id="f42e1-106">While the images cannot be sorted, the underlying values that they represent can be sorted.</span></span>  
  
 <span data-ttu-id="f42e1-107">在中<xref:System.Windows.Forms.DataGridView>控件，<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>列的属性值确定其排序行为。</span><span class="sxs-lookup"><span data-stu-id="f42e1-107">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property value of a column determines its sorting behavior.</span></span>  
  
 <span data-ttu-id="f42e1-108">下面的过程演示`Priority`从列[如何：自定义 Windows 窗体 DataGridView 控件中的数据格式设置](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="f42e1-108">The following procedure shows the `Priority` column from [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="f42e1-109">此列是 image 列，不是默认情况下可排序。</span><span class="sxs-lookup"><span data-stu-id="f42e1-109">This column is an image column and is not sortable by default.</span></span> <span data-ttu-id="f42e1-110">它包含的都是字符串，但是，实际的单元值，因此可以自动进行排序。</span><span class="sxs-lookup"><span data-stu-id="f42e1-110">It contains actual cell values that are strings, however, so it can be sorted automatically.</span></span>  
  
### <a name="to-set-the-sort-mode-for-a-column"></a><span data-ttu-id="f42e1-111">若要设置某一列的排序模式</span><span class="sxs-lookup"><span data-stu-id="f42e1-111">To set the sort mode for a column</span></span>  
  
-   <span data-ttu-id="f42e1-112">设置 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="f42e1-112">Set the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f42e1-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="f42e1-113">Compiling the Code</span></span>  
 <span data-ttu-id="f42e1-114">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="f42e1-114">This example requires:</span></span>  
  
-   <span data-ttu-id="f42e1-115">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件，其包含一个名为 `Priority` 的列。</span><span class="sxs-lookup"><span data-stu-id="f42e1-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Priority`.</span></span>  
  
-   <span data-ttu-id="f42e1-116">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="f42e1-116">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f42e1-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="f42e1-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f42e1-118">在 Windows 窗体 DataGridView 控件中进行数据排序</span><span class="sxs-lookup"><span data-stu-id="f42e1-118">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f42e1-119">Windows 窗体 DataGridView 控件中的列排序模式</span><span class="sxs-lookup"><span data-stu-id="f42e1-119">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f42e1-120">如何：自定义 Windows 窗体 DataGridView 控件中的排序</span><span class="sxs-lookup"><span data-stu-id="f42e1-120">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
