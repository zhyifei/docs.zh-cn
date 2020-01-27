---
title: 使用设计器为 DataGridView 控件设置交替行样式
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: 74f65d03a359136de943f8a2937ed5e5f1e62519
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743046"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정

表格数据通常以类似帐目的格式显示，其中交替行具有不同的背景色。 이 형식을 사용하면 특히 많은 열을 포함하는 넓은 테이블에서 사용자가 각 행에 있는 셀을 쉽게 구분할 수 있습니다.

<xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하여 교대로 반복되는 행에 대한 전체 스타일 정보를 지정할 수 있습니다. 除了背景色以外，还可以使用样式特征（如前景颜色和字体）来区分交替行。 有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。

下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.DataGridView> 控件的窗体。 有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

### <a name="define-styles-for-alternating-rows"></a>定义交替行的样式

1. 在设计器中选择 "<xref:System.Windows.Forms.DataGridView>" 控件。

2. 在 "**属性**" 窗口中，单击 "<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>" 属性旁边的省略号按钮（![](./media/visual-studio-ellipsis-button.png)）属性窗口中的省略号按钮（...）。

3. 在 " **CellStyle 生成器**" 对话框中，通过设置属性来定义样式，并使用**预览**窗格来确认所做的选择。 指定的样式将用于在控件中显示的每个其他行，从第二行开始。

4. 若要为其余行定义样式，请使用 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 属性重复步骤2和3。

    > [!NOTE]
    > 使用从多个属性继承的样式显示单元。 有关样式继承的详细信息，请参阅[Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- [Windows Forms DataGridView 컨트롤의 셀 스타일](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤에 디자이너 사용](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)
