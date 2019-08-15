---
title: 如何：在 TableLayoutPanel 控件中编辑行和列
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: 99ff3286592da0a097835b8f35d687475ca54fb0
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040293"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a>如何：在 TableLayoutPanel 控件中编辑行和列

您可以使用<xref:System.Windows.Forms.TableLayoutPanel>控件的集合编辑器 (称为 "**列和行样式**" 对话框) 来编辑控件的行和列。

> [!NOTE]
> 如果希望控件跨多个行或列, 请在控件上`RowSpan`设置`ColumnSpan`和属性。 有关详细信息，请参见[演练：使用 TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)排列 Windows 窗体上的控件。
>
> 如果要在单元格中对齐控件, 或者希望控件在单元格内伸展, 请使用控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性。 有关详细信息，请参见[演练：使用 TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)排列 Windows 窗体上的控件。

## <a name="to-edit-rows-and-columns"></a>编辑行和列

1. 从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。

2. ![](./media/vs-winformsmttagglyph.gif "")单击控件的智能标记字形 (智能标记字形 VS_WinFormSmtTagGlyph), 然后选择 "编辑行和列" 以打开 "列和行样式" 对话框。 <xref:System.Windows.Forms.TableLayoutPanel> 您还可以右键单击<xref:System.Windows.Forms.TableLayoutPanel>控件, 然后从快捷菜单中选择 "**编辑行和列**"。

3. 若要添加或删除列, 请从 "**成员类型**" 下拉列表框中选择 "**列**"。

4. 若要添加或删除行, 请从 "**成员类型**" 下拉列表框中选择 "**行**"。

5. 单击 "**添加**" 按钮可向**成员列表**的末尾添加行或列。

6. 单击 "**插入**" 按钮, 在列表中当前选定的项之前添加行或列。

7. 如果要添加行或列, 请选择新行或列的**大小类型**。 有关详细信息，请参阅 <xref:System.Windows.Forms.SizeType> 。

8. 若要删除行或列, 请单击 "**删除**" 按钮以删除**成员列表**中当前选定的项。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.SizeType>
- [TableLayoutPanel 控件](tablelayoutpanel-control-windows-forms.md)
