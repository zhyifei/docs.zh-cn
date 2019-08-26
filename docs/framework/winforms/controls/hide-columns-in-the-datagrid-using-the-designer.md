---
title: 如何：使用设计器隐藏 Windows 窗体 DataGridView 控件中的列
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: 35aa1cdeef919d4267cb27da79f183c4c52aefa2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916383"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>如何：使用设计器隐藏 Windows 窗体 DataGridView 控件中的列
有时，你会想仅显示在 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件中可用的某些列。 例如, 你可能希望向具有管理凭据的用户显示员工薪金列, 同时将其与其他用户隐藏。 或者, 您可能想要将该控件绑定到包含多个列的数据源, 其中只包含您要显示的部分列。 在这种情况下, 通常会删除不想要显示的列, 而不是隐藏它们。 有关详细信息，请参阅[如何：使用设计器](add-and-remove-columns-in-the-datagrid-using-the-designer.md)在 Windows 窗体 DataGridView 控件中添加和删除列。

 下面的过程需要一个**Windows 应用程序**项目, 该项目具有<xref:System.Windows.Forms.DataGridView>包含控件的窗体。 有关设置此类项目的信息, 请参阅[如何:创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)以及[如何:将控件添加到](how-to-add-controls-to-windows-forms.md)Windows 窗体。

## <a name="to-hide-a-column-using-the-designer"></a>使用设计器隐藏列

1. 单击<xref:System.Windows.Forms.DataGridView>控件右上角的智能标记标志符号 (![智能标记字形](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), 然后选择 "**编辑列**"。

2. 从 "**选定的列**" 列表中选择一列。

3. 在 "**列属性**" 网格中, <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A>将属性`false`设置为。

    > [!NOTE]
    > 还可以通过清除 "**添加列**" 对话框中的 "**可见**" 复选框来添加列。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [如何：使用设计器在 Windows 窗体 DataGridView 控件中添加和移除列](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)
