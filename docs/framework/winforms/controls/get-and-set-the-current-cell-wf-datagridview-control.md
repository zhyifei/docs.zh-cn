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
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a>如何：获取和设置 Windows 窗体 DataGridView 控件中的当前单元格
与 <xref:System.Windows.Forms.DataGridView> 的交互通常要求您以编程方式发现哪个单元格当前处于活动状态。 您可能还需要更改当前单元格。 可以通过 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 属性执行这些任务。  
  
> [!NOTE]
> 不能将 <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> 属性设置为 `false`的行或列中的当前单元格设置为 ""。  
  
 根据 <xref:System.Windows.Forms.DataGridView> 控件的选择模式，更改当前单元格可以更改所选内容。 有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的选择模式](selection-modes-in-the-windows-forms-datagridview-control.md)。  
  
### <a name="to-get-the-current-cell-programmatically"></a>以编程方式获取当前单元格  
  
- 使用 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 属性。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a>以编程方式设置当前单元格  
  
- 设置 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 属性。 在下面的代码示例中，当前单元格设置为第0行，第1列。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- <xref:System.Windows.Forms.Button> 名为 `getCurrentCellButton` 和 `setCurrentCellButton`的控件。 在视觉C#对象中，你必须将每个按钮的 <xref:System.Windows.Forms.Control.Click> 事件附加到示例代码中的关联事件处理程序。  
  
- `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
- <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 선택 모드](selection-modes-in-the-windows-forms-datagridview-control.md)
