---
title: "如何：根据 Windows 窗体 DataGridView 控件的单元格中的更改执行自定义操作"
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
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7f81cf7df0272a1b90de77332712b3b8a9e202de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a><span data-ttu-id="f0a35-102">如何：根据 Windows 窗体 DataGridView 控件的单元格中的更改执行自定义操作</span><span class="sxs-lookup"><span data-stu-id="f0a35-102">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f0a35-103"><xref:System.Windows.Forms.DataGridView>控件具有可用于检测的状态更改的事件数<xref:System.Windows.Forms.DataGridView>单元格。</span><span class="sxs-lookup"><span data-stu-id="f0a35-103">The <xref:System.Windows.Forms.DataGridView> control has a number of events you can use to detect changes in the state of <xref:System.Windows.Forms.DataGridView> cells.</span></span> <span data-ttu-id="f0a35-104">两个最常使用的是<xref:System.Windows.Forms.DataGridView.CellValueChanged>和<xref:System.Windows.Forms.DataGridView.CellStateChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="f0a35-104">Two of the most commonly used are the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a><span data-ttu-id="f0a35-105">若要检测 DataGridView 单元格的值中的更改</span><span class="sxs-lookup"><span data-stu-id="f0a35-105">To detect changes in the values of DataGridView cells</span></span>  
  
-   <span data-ttu-id="f0a35-106">编写处理程序<xref:System.Windows.Forms.DataGridView.CellValueChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="f0a35-106">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellValueChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a><span data-ttu-id="f0a35-107">若要检测的 DataGridView 单元格状态中的更改</span><span class="sxs-lookup"><span data-stu-id="f0a35-107">To detect changes in the states of DataGridView cells</span></span>  
  
-   <span data-ttu-id="f0a35-108">编写处理程序<xref:System.Windows.Forms.DataGridView.CellStateChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="f0a35-108">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellStateChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f0a35-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="f0a35-109">Compiling the Code</span></span>  
 <span data-ttu-id="f0a35-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="f0a35-110">This example requires:</span></span>  
  
-   <span data-ttu-id="f0a35-111">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="f0a35-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span> <span data-ttu-id="f0a35-112">对于 C# 中，事件处理程序必须连接到相应的事件。</span><span class="sxs-lookup"><span data-stu-id="f0a35-112">For C#, the event handlers must be connected to the corresponding events.</span></span>  
  
-   <span data-ttu-id="f0a35-113">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="f0a35-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a35-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0a35-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>  
 [<span data-ttu-id="f0a35-115">使用 Windows 窗体 DataGridView 控件中的单元格、行和列编程</span><span class="sxs-lookup"><span data-stu-id="f0a35-115">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 [<span data-ttu-id="f0a35-116">演练：在 Windows 窗体 DataGridView 控件中验证数据</span><span class="sxs-lookup"><span data-stu-id="f0a35-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
