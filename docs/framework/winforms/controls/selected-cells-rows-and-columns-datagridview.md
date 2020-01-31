---
title: 获取 DataGridView 控件中选定的单元格、行和列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 0079c590ee6e4732523fd50be157bd58ec1bfb1b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743082"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8f04a-102">방법: Windows Forms DataGridView 컨트롤에서 선택한 셀, 행 및 열 가져오기</span><span class="sxs-lookup"><span data-stu-id="8f04a-102">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8f04a-103">通过使用相应的属性，可以从 <xref:System.Windows.Forms.DataGridView> 控件获取选定的单元格、行或列： <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>、<xref:System.Windows.Forms.DataGridView.SelectedRows%2A>和 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>。</span><span class="sxs-lookup"><span data-stu-id="8f04a-103">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="8f04a-104">在下面的过程中，您将获取选定的单元格，并在 <xref:System.Windows.Forms.MessageBox>中显示其行和列索引。</span><span class="sxs-lookup"><span data-stu-id="8f04a-104">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="8f04a-105">获取 DataGridView 控件中选定的单元格</span><span class="sxs-lookup"><span data-stu-id="8f04a-105">To get the selected cells in a DataGridView control</span></span>  
  
- <span data-ttu-id="8f04a-106"><xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f04a-106">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8f04a-107">使用 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> 方法可避免显示可能大量的单元格。</span><span class="sxs-lookup"><span data-stu-id="8f04a-107">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="8f04a-108">获取 DataGridView 控件中的选定行</span><span class="sxs-lookup"><span data-stu-id="8f04a-108">To get the selected rows in a DataGridView control</span></span>  
  
- <span data-ttu-id="8f04a-109"><xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f04a-109">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="8f04a-110">若要使用户能够选择行，必须将 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 属性设置为 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 或 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>。</span><span class="sxs-lookup"><span data-stu-id="8f04a-110">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="8f04a-111">获取 DataGridView 控件中的选定列</span><span class="sxs-lookup"><span data-stu-id="8f04a-111">To get the selected columns in a DataGridView control</span></span>  
  
- <span data-ttu-id="8f04a-112"><xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f04a-112">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="8f04a-113">若要使用户能够选择列，必须将 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 属性设置为 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> 或 <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>。</span><span class="sxs-lookup"><span data-stu-id="8f04a-113">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8f04a-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8f04a-114">Compiling the Code</span></span>  
 <span data-ttu-id="8f04a-115">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8f04a-115">This example requires:</span></span>  
  
- <span data-ttu-id="8f04a-116"><xref:System.Windows.Forms.Button> 名为 `selectedCellsButton`、`selectedRowsButton`和 `selectedColumnsButton`的控件，每个控件都具有附加的 <xref:System.Windows.Forms.Control.Click> 事件的处理程序。</span><span class="sxs-lookup"><span data-stu-id="8f04a-116"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
- <span data-ttu-id="8f04a-117">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8f04a-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="8f04a-118"><xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> 및 <xref:System.Text?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="8f04a-118">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8f04a-119">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="8f04a-119">Robust Programming</span></span>  
 <span data-ttu-id="8f04a-120">如果选择了大量的单元格、行或列，本主题中所述的集合将无法有效地执行。</span><span class="sxs-lookup"><span data-stu-id="8f04a-120">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="8f04a-121">有关对大量数据使用这些集合的详细信息，请参阅[缩放 Windows 窗体 DataGridView 控件的最佳做法](best-practices-for-scaling-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="8f04a-121">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f04a-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f04a-122">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [<span data-ttu-id="8f04a-123">Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용</span><span class="sxs-lookup"><span data-stu-id="8f04a-123">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
