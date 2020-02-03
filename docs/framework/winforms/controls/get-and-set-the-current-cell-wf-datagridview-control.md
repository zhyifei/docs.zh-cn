---
title: 获取和设置 DataGridView 控件中的当前单元格
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 0fb01d5392e02b53e0e5bf905c872dbeeb22fad9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745661"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="c7ae9-102">如何：获取和设置 Windows 窗体 DataGridView 控件中的当前单元格</span><span class="sxs-lookup"><span data-stu-id="c7ae9-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c7ae9-103">与 <xref:System.Windows.Forms.DataGridView> 的交互通常要求您以编程方式发现哪个单元格当前处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="c7ae9-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="c7ae9-104">您可能还需要更改当前单元格。</span><span class="sxs-lookup"><span data-stu-id="c7ae9-104">You may also need to change the current cell.</span></span> <span data-ttu-id="c7ae9-105">可以通过 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 属性执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="c7ae9-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7ae9-106">不能将 <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> 属性设置为 `false`的行或列中的当前单元格设置为 ""。</span><span class="sxs-lookup"><span data-stu-id="c7ae9-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="c7ae9-107">根据 <xref:System.Windows.Forms.DataGridView> 控件的选择模式，更改当前单元格可以更改所选内容。</span><span class="sxs-lookup"><span data-stu-id="c7ae9-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="c7ae9-108">有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的选择模式](selection-modes-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="c7ae9-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="c7ae9-109">以编程方式获取当前单元格</span><span class="sxs-lookup"><span data-stu-id="c7ae9-109">To get the current cell programmatically</span></span>  
  
- <span data-ttu-id="c7ae9-110">使用 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="c7ae9-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="c7ae9-111">以编程方式设置当前单元格</span><span class="sxs-lookup"><span data-stu-id="c7ae9-111">To set the current cell programmatically</span></span>  
  
- <span data-ttu-id="c7ae9-112">设置 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="c7ae9-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c7ae9-113">在下面的代码示例中，当前单元格设置为第0行，第1列。</span><span class="sxs-lookup"><span data-stu-id="c7ae9-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c7ae9-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="c7ae9-114">Compiling the Code</span></span>  
 <span data-ttu-id="c7ae9-115">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="c7ae9-115">This example requires:</span></span>  
  
- <span data-ttu-id="c7ae9-116"><xref:System.Windows.Forms.Button> 名为 `getCurrentCellButton` 和 `setCurrentCellButton`的控件。</span><span class="sxs-lookup"><span data-stu-id="c7ae9-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="c7ae9-117">在视觉C#对象中，你必须将每个按钮的 <xref:System.Windows.Forms.Control.Click> 事件附加到示例代码中的关联事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="c7ae9-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
- <span data-ttu-id="c7ae9-118">名为 <xref:System.Windows.Forms.DataGridView> 的 `dataGridView1` 控件。</span><span class="sxs-lookup"><span data-stu-id="c7ae9-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="c7ae9-119">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="c7ae9-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7ae9-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7ae9-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c7ae9-121">Windows 窗体 DataGridView 控件中的列、行和单元格基本功能</span><span class="sxs-lookup"><span data-stu-id="c7ae9-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="c7ae9-122">Windows 窗体 DataGridView 控件中的选择模式</span><span class="sxs-lookup"><span data-stu-id="c7ae9-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
