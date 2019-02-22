---
title: 如何：启用 Windows 窗体 DataGridView 控件中的列重新排序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], reordering columns
- columns [Windows Forms], reordering
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
ms.openlocfilehash: 3aff0b0262441fb6c9d24240b1fe1c24707f94b8
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584247"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e0e83-102">如何：启用 Windows 窗体 DataGridView 控件中的列重新排序</span><span class="sxs-lookup"><span data-stu-id="e0e83-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e0e83-103">如果你启用了 <xref:System.Windows.Forms.DataGridView> 控件中的列重新排序，用户则可通过用鼠标拖动列标题来将列移动到新位置。</span><span class="sxs-lookup"><span data-stu-id="e0e83-103">When you enable column reordering in the <xref:System.Windows.Forms.DataGridView> control, users can move a column to a new position by dragging the column header with the mouse.</span></span> <span data-ttu-id="e0e83-104">在 <xref:System.Windows.Forms.DataGridView> 控件中，<xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> 属性值确定用户是否可以将列移动到不同的位置。</span><span class="sxs-lookup"><span data-stu-id="e0e83-104">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> property value determines whether users can move columns to different positions.</span></span>  
  
 <span data-ttu-id="e0e83-105">Visual Studio 中对此任务提供支持。</span><span class="sxs-lookup"><span data-stu-id="e0e83-105">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="e0e83-106">另请参阅[如何：启用列重新排序在 Windows 窗体 DataGridView 控件使用设计器](enable-column-reordering-in-the-datagrid-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="e0e83-106">Also see [How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer](enable-column-reordering-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-enable-column-reordering-programmatically"></a><span data-ttu-id="e0e83-107">以编程方式启用列重新排序</span><span class="sxs-lookup"><span data-stu-id="e0e83-107">To enable column reordering programmatically</span></span>  
  
-   <span data-ttu-id="e0e83-108">将 <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="e0e83-108">Set the <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e0e83-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="e0e83-109">Compiling the Code</span></span>  
 <span data-ttu-id="e0e83-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="e0e83-110">This example requires:</span></span>  
  
-   <span data-ttu-id="e0e83-111">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="e0e83-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="e0e83-112">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="e0e83-112">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e83-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0e83-113">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e0e83-114">Windows 窗体 DataGridView 控件中的列、行和单元格基本功能</span><span class="sxs-lookup"><span data-stu-id="e0e83-114">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="e0e83-115">如何：冻结 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="e0e83-115">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)
