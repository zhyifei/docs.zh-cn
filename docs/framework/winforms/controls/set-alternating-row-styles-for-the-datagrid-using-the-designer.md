---
title: 如何：使用设计器设置 Windows 窗体 DataGridView 控件的交替行样式
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: 1be746d4cce36344e034692a0e2e8e6a9e9320d5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040443"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a>如何：使用设计器设置 Windows 窗体 DataGridView 控件的交替行样式

表格数据通常以类似帐目的格式显示, 其中交替行具有不同的背景色。 这种格式使用户可以更轻松地分辨每一行的单元格，尤其是有多列的宽表。

借助 <xref:System.Windows.Forms.DataGridView> 控件，可为交替行指定完整的样式信息。 除了背景色以外, 还可以使用样式特征 (如前景颜色和字体) 来区分交替行。 有关详细信息, 请参阅[Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。

下面的过程需要一个**Windows 应用程序**项目, 该项目具有<xref:System.Windows.Forms.DataGridView>包含控件的窗体。 有关设置此类项目的信息, 请参阅[如何:创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)以及[如何:将控件添加到](how-to-add-controls-to-windows-forms.md)Windows 窗体。


### <a name="define-styles-for-alternating-rows"></a>定义交替行的样式

1. 在设计器中选择控件。<xref:System.Windows.Forms.DataGridView>

2. 在 "**属性**" 窗口中, 单击![ <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>属性旁边的省略号按钮 (Visual Studio](./media/visual-studio-ellipsis-button.png)的属性窗口中的省略号按钮 (...)。

3. 在 " **CellStyle 生成器**" 对话框中, 通过设置属性来定义样式, 并使用**预览**窗格来确认所做的选择。 指定的样式将用于在控件中显示的每个其他行, 从第二行开始。

4. 若要为其余行定义样式, 请使用<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>属性重复步骤2和3。

    > [!NOTE]
    > 使用从多个属性继承的样式显示单元。 有关样式继承的详细信息, 请参阅[Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.DataGridView>
- [Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的基本格式和样式设置](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [将设计器与 Windows 窗体 DataGridView 控件结合使用](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)
