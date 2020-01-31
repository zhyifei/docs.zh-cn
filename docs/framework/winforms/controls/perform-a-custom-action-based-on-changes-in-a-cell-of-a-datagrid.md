---
title: 基于 DataGridView 控件中的更改执行自定义操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: a809134b0a79bc9685c5b84acce58b4c61b5c526
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744279"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a><span data-ttu-id="c8f12-102">如何：根据 Windows 窗体 DataGridView 控件的单元格中的更改执行自定义操作</span><span class="sxs-lookup"><span data-stu-id="c8f12-102">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c8f12-103"><xref:System.Windows.Forms.DataGridView> 控件有多个事件可用于检测 <xref:System.Windows.Forms.DataGridView> 单元格状态的更改。</span><span class="sxs-lookup"><span data-stu-id="c8f12-103">The <xref:System.Windows.Forms.DataGridView> control has a number of events you can use to detect changes in the state of <xref:System.Windows.Forms.DataGridView> cells.</span></span> <span data-ttu-id="c8f12-104">最常使用的两种情况是 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 和 <xref:System.Windows.Forms.DataGridView.CellStateChanged> 事件。</span><span class="sxs-lookup"><span data-stu-id="c8f12-104">Two of the most commonly used are the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a><span data-ttu-id="c8f12-105">检测 DataGridView 单元值的更改</span><span class="sxs-lookup"><span data-stu-id="c8f12-105">To detect changes in the values of DataGridView cells</span></span>  
  
- <span data-ttu-id="c8f12-106">为 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 事件编写处理程序。</span><span class="sxs-lookup"><span data-stu-id="c8f12-106">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellValueChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a><span data-ttu-id="c8f12-107">检测 DataGridView 单元格状态的更改</span><span class="sxs-lookup"><span data-stu-id="c8f12-107">To detect changes in the states of DataGridView cells</span></span>  
  
- <span data-ttu-id="c8f12-108">为 <xref:System.Windows.Forms.DataGridView.CellStateChanged> 事件编写处理程序。</span><span class="sxs-lookup"><span data-stu-id="c8f12-108">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellStateChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c8f12-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="c8f12-109">Compiling the Code</span></span>  
 <span data-ttu-id="c8f12-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="c8f12-110">This example requires:</span></span>  
  
- <span data-ttu-id="c8f12-111">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="c8f12-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span> <span data-ttu-id="c8f12-112">对于C#，事件处理程序必须连接到相应的事件。</span><span class="sxs-lookup"><span data-stu-id="c8f12-112">For C#, the event handlers must be connected to the corresponding events.</span></span>  
  
- <span data-ttu-id="c8f12-113">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="c8f12-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f12-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8f12-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [<span data-ttu-id="c8f12-115">使用 Windows 窗体 DataGridView 控件中的单元格、行和列编程</span><span class="sxs-lookup"><span data-stu-id="c8f12-115">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [<span data-ttu-id="c8f12-116">演练：在 Windows 窗体 DataGridView 控件中验证数据</span><span class="sxs-lookup"><span data-stu-id="c8f12-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
