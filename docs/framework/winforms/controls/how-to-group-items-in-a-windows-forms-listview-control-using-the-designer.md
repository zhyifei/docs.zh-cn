---
title: 如何：使用设计器对 Windows 窗体 ListView 控件中的项进行分组
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: b63bcd9e5e357db350cc2987e09af84eb58bdcff
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039396"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>如何：使用设计器对 Windows 窗体 ListView 控件中的项进行分组

<xref:System.Windows.Forms.ListView>控件的分组功能使你能够以组的形式显示相关项集。 这些组按包含组标题的水平组标头在屏幕上进行分隔。 你可以使用<xref:System.Windows.Forms.ListView>组, 通过按字母顺序、日期或任何其他逻辑分组对项进行分组来更轻松地导航大型列表。 下图显示了一些分组项:

![数字分为奇数甚至是组。](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

下面的过程需要一个**Windows 应用程序**项目, 该项目具有<xref:System.Windows.Forms.ListView>包含控件的窗体。 有关设置此类项目的信息, 请参阅[如何:创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)以及[如何:将控件添加到](how-to-add-controls-to-windows-forms.md)Windows 窗体。

若要启用分组, 必须先在设计器中<xref:System.Windows.Forms.ListViewGroup>或以编程方式创建一个或多个对象。 定义组后, 可以为其分配项。

> [!NOTE]
> <xref:System.Windows.Forms.ListView>[!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]当应用程序<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>调用方法时, 组才可用。 在早期的操作系统上, 与组相关的任何代码都不起作用, 并且不会显示这些组。 有关详细信息，请参阅 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType> 。

## <a name="to-add-or-remove-groups-in-the-designer"></a>在设计器中添加或删除组

1. 在 "**属性**" 窗口中<xref:System.Windows.Forms.ListView.Groups%2A> , 单击属性![旁边的**省略号**("Visual Studio](./media/visual-studio-ellipsis-button.png)" 的属性窗口中的省略号按钮 (...)。

     此时将显示 " **ListViewGroup 集合编辑器**"。

2. 若要添加组, 请单击 "**添加**" 按钮。 然后, 可以设置新组的属性, 如<xref:System.Windows.Forms.ListViewGroup.Header%2A>和<xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A>属性。 若要删除某个组, 请选择该组, 然后单击 "**删除**" 按钮。

## <a name="to-assign-items-to-groups-in-the-designer"></a>在设计器中向组分配项

1. 在 "**属性**" 窗口中<xref:System.Windows.Forms.ListView.Items%2A> , 单击属性![旁边的**省略号**("Visual Studio](./media/visual-studio-ellipsis-button.png)" 的属性窗口中的省略号按钮 (...)。

     此时将显示 " **ListViewItem 集合编辑器**"。

2. 若要添加新项, 请单击 "**添加**" 按钮。 然后, 可以设置新项的属性, 如<xref:System.Windows.Forms.ListViewItem.Text%2A>和<xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>属性。

3. 选择该<xref:System.Windows.Forms.ListViewItem.Group%2A>属性, 然后从下拉列表中选择一个组。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView 控件](listview-control-windows-forms.md)
- [ListView 控件概述](listview-control-overview-windows-forms.md)
- [如何：通过 Windows 窗体 ListView 控件添加和移除项](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
