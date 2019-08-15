---
title: 如何：使用设计器将 Windows 窗体 DataGridView 控件中的列设为只读
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 6bdd561c863a461f43a5a7aac025fead1f971bb0
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039810"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>如何：使用设计器将 Windows 窗体 DataGridView 控件中的列设为只读
默认情况下, 用户可以修改显示在 Windows 窗体<xref:System.Windows.Forms.DataGridView>控件中的文本和数字数据。 如果要显示不用于修改的数据, 则必须将包含数据的列设置为只读。 有关如何使控件完全成为只读控件的信息, 请参阅[如何:使用设计器](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)防止在 Windows 窗体 DataGridView 控件中添加和删除行。

 下面的过程需要一个**Windows 应用程序**项目, 该项目具有<xref:System.Windows.Forms.DataGridView>包含控件的窗体。 有关设置此类项目的信息, 请参阅[如何:创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)以及[如何:将控件添加到](how-to-add-controls-to-windows-forms.md)Windows 窗体。

## <a name="to-make-a-column-read-only-by-using-the-designer"></a>使用设计器使列成为只读的

1. 单击<xref:System.Windows.Forms.DataGridView>控件右上角的智能标记标志符号 (![智能标记字形](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), 然后选择 "**编辑列**"。

2. 从 "**选定的列**" 列表中选择一列。

3. 在 "**列属性**" 网格中, <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A>将属性`true`设置为。

    > [!NOTE]
    >  您还可以通过在 "**添加列**" 对话框中选中 "**只读**" 复选框来添加列, 以使其成为只读列。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [如何：使用设计器在 Windows 窗体 DataGridView 控件中添加和移除列](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [如何：使用设计器防止在 Windows 窗体 DataGridView 控件中添加和删除行](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)
