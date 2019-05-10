---
title: 如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 9b07c139689a9776f6f901c0f9fbe9d2d0303d56
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648150"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="0d7c6-102">如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观</span><span class="sxs-lookup"><span data-stu-id="0d7c6-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0d7c6-103">您可以通过处理自定义的任意单元格的外观<xref:System.Windows.Forms.DataGridView>控件的<xref:System.Windows.Forms.DataGridView.CellPainting>事件。</span><span class="sxs-lookup"><span data-stu-id="0d7c6-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="0d7c6-104">你可以提取<xref:System.Windows.Forms.DataGridView>控件的<xref:System.Drawing.Graphics>从<xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A>属性的<xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>。</span><span class="sxs-lookup"><span data-stu-id="0d7c6-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="0d7c6-105">与此<xref:System.Drawing.Graphics>，可能会影响整个外观<xref:System.Windows.Forms.DataGridView>控件，但你通常会想要产生效果仅为当前正在绘制的单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="0d7c6-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="0d7c6-106"><xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A>属性的<xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>使您能够限制您对当前正在绘制的单元格的绘制操作。</span><span class="sxs-lookup"><span data-stu-id="0d7c6-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="0d7c6-107">在下面的代码示例中，将绘制中的所有单元格`ContactName`列使用<xref:System.Windows.Forms.DataGridView>控件的配色方案。</span><span class="sxs-lookup"><span data-stu-id="0d7c6-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="0d7c6-108">在绘制每个单元格的文本内容<xref:System.Drawing.Color.Crimson%2A>，并与相同的颜色绘制一个内嵌的矩形<xref:System.Windows.Forms.DataGridView>控件的<xref:System.Windows.Forms.DataGridView.GridColor%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0d7c6-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d7c6-109">示例</span><span class="sxs-lookup"><span data-stu-id="0d7c6-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0d7c6-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="0d7c6-110">Compiling the Code</span></span>  
 <span data-ttu-id="0d7c6-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="0d7c6-111">This example requires:</span></span>  
  
- <span data-ttu-id="0d7c6-112">一个<xref:System.Windows.Forms.DataGridView>名为控件`dataGridView1`与`ContactName`如 Northwind 示例数据库中的 Customers 表中的列。</span><span class="sxs-lookup"><span data-stu-id="0d7c6-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
- <span data-ttu-id="0d7c6-113">对 System、System.Windows.Forms 和 System.Drawing 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="0d7c6-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d7c6-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="0d7c6-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="0d7c6-115">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="0d7c6-115">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
