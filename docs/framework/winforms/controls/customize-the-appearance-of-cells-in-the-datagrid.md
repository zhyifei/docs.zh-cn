---
title: 自定义 DataGridView 控件中单元格的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744053"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1b34a-102">如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观</span><span class="sxs-lookup"><span data-stu-id="1b34a-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1b34a-103">您可以通过处理 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.CellPainting> 事件来自定义任意单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="1b34a-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="1b34a-104">可以从 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>的 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> 属性中提取 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Drawing.Graphics>。</span><span class="sxs-lookup"><span data-stu-id="1b34a-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="1b34a-105">利用这 <xref:System.Drawing.Graphics>，你可以影响整个 <xref:System.Windows.Forms.DataGridView> 控件的外观，但你通常只想影响当前正在绘制的单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="1b34a-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="1b34a-106"><xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> 的 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> 属性使你能够将绘制操作限制为当前正在绘制的单元格。</span><span class="sxs-lookup"><span data-stu-id="1b34a-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="1b34a-107">在下面的代码示例中，你将使用 <xref:System.Windows.Forms.DataGridView> 控件的配色方案绘制 `ContactName` 列中的所有单元格。</span><span class="sxs-lookup"><span data-stu-id="1b34a-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="1b34a-108">每个单元格的文本内容都在 <xref:System.Drawing.Color.Crimson%2A>中进行绘制，并且嵌入矩形的颜色与 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.GridColor%2A> 属性相同。</span><span class="sxs-lookup"><span data-stu-id="1b34a-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b34a-109">示例</span><span class="sxs-lookup"><span data-stu-id="1b34a-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1b34a-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="1b34a-110">Compiling the Code</span></span>  
 <span data-ttu-id="1b34a-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="1b34a-111">This example requires:</span></span>  
  
- <span data-ttu-id="1b34a-112">一个名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件，该控件具有一个 `ContactName` 列，如 Northwind 示例数据库的 Customers 表中的列。</span><span class="sxs-lookup"><span data-stu-id="1b34a-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
- <span data-ttu-id="1b34a-113">对 System、System.Windows.Forms 和 System.Drawing 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="1b34a-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b34a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b34a-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="1b34a-115">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="1b34a-115">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
