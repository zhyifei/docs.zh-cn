---
title: "如何：获取 Windows 窗体 DataGridView 控件中选定的单元格、行和列"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 22b44668b403b5a991c03de661b6e680ccde0a44
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="93a26-102">如何：获取 Windows 窗体 DataGridView 控件中选定的单元格、行和列</span><span class="sxs-lookup"><span data-stu-id="93a26-102">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="93a26-103">你可以获取选定的单元格、 行或列从<xref:System.Windows.Forms.DataGridView>通过使用相应的属性的控件： <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>， <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>，和<xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>。</span><span class="sxs-lookup"><span data-stu-id="93a26-103">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="93a26-104">在下面的过程中，你将获取选定的单元格，并显示在其行和列索引<xref:System.Windows.Forms.MessageBox>。</span><span class="sxs-lookup"><span data-stu-id="93a26-104">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="93a26-105">若要获取 DataGridView 控件中选定的单元格</span><span class="sxs-lookup"><span data-stu-id="93a26-105">To get the selected cells in a DataGridView control</span></span>  
  
-   <span data-ttu-id="93a26-106">使用 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="93a26-106">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="93a26-107">使用<xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>方法，以避免只显示可能会极大量的单元格。</span><span class="sxs-lookup"><span data-stu-id="93a26-107">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="93a26-108">在 DataGridView 控件中获取所选的行</span><span class="sxs-lookup"><span data-stu-id="93a26-108">To get the selected rows in a DataGridView control</span></span>  
  
-   <span data-ttu-id="93a26-109">使用 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="93a26-109">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="93a26-110">若要使用户能够选择行，必须设置<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>属性<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>或<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>。</span><span class="sxs-lookup"><span data-stu-id="93a26-110">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="93a26-111">在 DataGridView 控件中获取所选的列</span><span class="sxs-lookup"><span data-stu-id="93a26-111">To get the selected columns in a DataGridView control</span></span>  
  
-   <span data-ttu-id="93a26-112">使用 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="93a26-112">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="93a26-113">若要使用户能够选择列，必须设置<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>属性<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>或<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>。</span><span class="sxs-lookup"><span data-stu-id="93a26-113">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="93a26-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="93a26-114">Compiling the Code</span></span>  
 <span data-ttu-id="93a26-115">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="93a26-115">This example requires:</span></span>  
  
-   <span data-ttu-id="93a26-116"><xref:System.Windows.Forms.Button>控件名为`selectedCellsButton`， `selectedRowsButton`，和`selectedColumnsButton`，每个处理程序<xref:System.Windows.Forms.Control.Click>附加事件。</span><span class="sxs-lookup"><span data-stu-id="93a26-116"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
-   <span data-ttu-id="93a26-117">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="93a26-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="93a26-118">对 <xref:System?displayProperty=nameWithType><xref:System.Windows.Forms?displayProperty=nameWithType> 和 <xref:System.Text?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="93a26-118">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="93a26-119">可靠编程</span><span class="sxs-lookup"><span data-stu-id="93a26-119">Robust Programming</span></span>  
 <span data-ttu-id="93a26-120">本主题中所述的集合时选择的单元格、 行或列的较大数字不高效地执行。</span><span class="sxs-lookup"><span data-stu-id="93a26-120">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="93a26-121">有关使用这些集合的大量数据的详细信息，请参阅[缩放 Windows 窗体 DataGridView 控件的最佳做法](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="93a26-121">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93a26-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="93a26-122">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>  
 [<span data-ttu-id="93a26-123">将选择模式和剪贴板与 Windows 窗体 DataGridView 控件结合使用</span><span class="sxs-lookup"><span data-stu-id="93a26-123">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
