---
title: 如何：获取和设置 Windows 窗体 DataGridView 控件中的当前单元格
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 2508551cd4bcb056d1e746b2dc962c4500093ea5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495599"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="0b4cb-102">如何：获取和设置 Windows 窗体 DataGridView 控件中的当前单元格</span><span class="sxs-lookup"><span data-stu-id="0b4cb-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0b4cb-103">与交互<xref:System.Windows.Forms.DataGridView>通常要求您以编程方式发现哪个单元格是当前处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="0b4cb-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="0b4cb-104">您可能还需要更改当前单元格。</span><span class="sxs-lookup"><span data-stu-id="0b4cb-104">You may also need to change the current cell.</span></span> <span data-ttu-id="0b4cb-105">你可以执行这些任务与<xref:System.Windows.Forms.DataGridView.CurrentCell%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0b4cb-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b4cb-106">不能设置当前单元格的行或列中其<xref:System.Windows.Forms.DataGridViewBand.Visible%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="0b4cb-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="0b4cb-107">具体取决于<xref:System.Windows.Forms.DataGridView>控件的选择模式下，更改当前单元格可以更改所选内容。</span><span class="sxs-lookup"><span data-stu-id="0b4cb-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="0b4cb-108">有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的选择模式](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0b4cb-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="0b4cb-109">若要以编程方式获取当前单元格</span><span class="sxs-lookup"><span data-stu-id="0b4cb-109">To get the current cell programmatically</span></span>  
  
-   <span data-ttu-id="0b4cb-110">使用<xref:System.Windows.Forms.DataGridView>控件的<xref:System.Windows.Forms.DataGridView.CurrentCell%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0b4cb-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="0b4cb-111">若要以编程方式设置的当前单元格</span><span class="sxs-lookup"><span data-stu-id="0b4cb-111">To set the current cell programmatically</span></span>  
  
-   <span data-ttu-id="0b4cb-112">设置<xref:System.Windows.Forms.DataGridView.CurrentCell%2A>属性的<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="0b4cb-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0b4cb-113">在下面的代码示例中，当前单元格设置为 0，第 1 列行。</span><span class="sxs-lookup"><span data-stu-id="0b4cb-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0b4cb-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="0b4cb-114">Compiling the Code</span></span>  
 <span data-ttu-id="0b4cb-115">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="0b4cb-115">This example requires:</span></span>  
  
-   <span data-ttu-id="0b4cb-116"><xref:System.Windows.Forms.Button> 控件分别命名为`getCurrentCellButton`和`setCurrentCellButton`。</span><span class="sxs-lookup"><span data-stu-id="0b4cb-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="0b4cb-117">视觉对象中C#，必须将附加<xref:System.Windows.Forms.Control.Click>到关联的事件处理程序的代码示例中的每个按钮的事件。</span><span class="sxs-lookup"><span data-stu-id="0b4cb-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
-   <span data-ttu-id="0b4cb-118">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="0b4cb-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="0b4cb-119">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="0b4cb-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b4cb-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b4cb-120">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0b4cb-121">Windows 窗体 DataGridView 控件中的列、行和单元格基本功能</span><span class="sxs-lookup"><span data-stu-id="0b4cb-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="0b4cb-122">Windows 窗体 DataGridView 控件中的选择模式</span><span class="sxs-lookup"><span data-stu-id="0b4cb-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)
