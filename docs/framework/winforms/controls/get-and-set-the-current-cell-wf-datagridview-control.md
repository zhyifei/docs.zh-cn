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
ms.openlocfilehash: 670708f342e1cd1ac495c215b7508093349ac2e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933704"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a>如何：获取和设置 Windows 窗体 DataGridView 控件中的当前单元格
与的<xref:System.Windows.Forms.DataGridView>交互通常要求您以编程方式发现哪个单元格当前处于活动状态。 您可能还需要更改当前单元格。 可以通过<xref:System.Windows.Forms.DataGridView.CurrentCell%2A>属性执行这些任务。  
  
> [!NOTE]
> 不能将<xref:System.Windows.Forms.DataGridViewBand.Visible%2A>属性设置为的行或列中的当前单元格设置为`false`。  
  
 更改当前单元格可能会更改选定内容, 具体取决于控件的选择模式。<xref:System.Windows.Forms.DataGridView> 有关详细信息, 请参阅[Windows 窗体 DataGridView 控件中的选择模式](selection-modes-in-the-windows-forms-datagridview-control.md)。  
  
### <a name="to-get-the-current-cell-programmatically"></a>以编程方式获取当前单元格  
  
- 使用控件的<xref:System.Windows.Forms.DataGridView.CurrentCell%2A>属性。 <xref:System.Windows.Forms.DataGridView>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a>以编程方式设置当前单元格  
  
- 设置控件<xref:System.Windows.Forms.DataGridView>的属性。 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 在下面的代码示例中, 当前单元格设置为第0行, 第1列。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- <xref:System.Windows.Forms.Button>名为`getCurrentCellButton`和`setCurrentCellButton`的控件。 在视觉C#对象中, 你必须<xref:System.Windows.Forms.Control.Click>将每个按钮的事件附加到示例代码中的关联事件处理程序。  
  
- 名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。  
  
- 对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [Windows 窗体 DataGridView 控件中的列、行和单元格基本功能](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的选择模式](selection-modes-in-the-windows-forms-datagridview-control.md)
