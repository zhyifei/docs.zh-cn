---
title: 如何：使用设计器对 Windows 窗体 ListView 控件中的项进行分组
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 03958109d4daa3fc369660de66973bb659e29c60
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960178"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>如何：使用设计器对 Windows 窗体 ListView 控件中的项进行分组

利用 <xref:System.Windows.Forms.ListView> 控件的分组功能，您可以在组中显示相关的项集。 这些组按包含组标题的水平组标头在屏幕上进行分隔。 您可以使用 <xref:System.Windows.Forms.ListView> 组，通过按字母顺序、日期或任何其他逻辑分组对项进行分组来更轻松地导航大型列表。 下图显示了一些分组项：

![数字分为奇数甚至是组。](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.ListView> 控件的窗体。 有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

若要启用分组，必须先在设计器中或以编程方式创建一个或多个 <xref:System.Windows.Forms.ListViewGroup> 对象。 定义组后，可以为其分配项。

## <a name="to-add-or-remove-groups-in-the-designer"></a>在设计器中添加或删除组

1. 在 "**属性**" 窗口中，单击 "<xref:System.Windows.Forms.ListView.Groups%2A>" 属性旁边的**省略号**按钮（!["Visual](./media/visual-studio-ellipsis-button.png)Studio 的属性窗口中的省略号按钮（...）"。

     此时将显示 " **ListViewGroup 集合编辑器**"。

2. 若要添加组，请单击 "**添加**" 按钮。 然后，可以设置新组的属性，例如 <xref:System.Windows.Forms.ListViewGroup.Header%2A> 和 <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> 属性。 若要删除某个组，请选择该组，然后单击 "**删除**" 按钮。

## <a name="to-assign-items-to-groups-in-the-designer"></a>在设计器中向组分配项

1. 在 "**属性**" 窗口中，单击 "<xref:System.Windows.Forms.ListView.Items%2A>" 属性旁边的**省略号**按钮（!["Visual](./media/visual-studio-ellipsis-button.png)Studio 的属性窗口中的省略号按钮（...）"。

     此时将显示 " **ListViewItem 集合编辑器**"。

2. 若要添加新项，请单击 "**添加**" 按钮。 然后，可以设置新项的属性，例如 <xref:System.Windows.Forms.ListViewItem.Text%2A> 和 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 属性。

3. 选择 "<xref:System.Windows.Forms.ListViewItem.Group%2A>" 属性，然后从下拉列表中选择一个组。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView 控件](listview-control-windows-forms.md)
- [ListView 控件概述](listview-control-overview-windows-forms.md)
- [如何：使用 Windows 窗体 ListView 控件添加和删除项](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
