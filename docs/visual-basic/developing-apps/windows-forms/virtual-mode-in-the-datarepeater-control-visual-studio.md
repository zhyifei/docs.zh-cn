---
title: DataRepeater 控件中的虚拟模式 (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- virtual data binding [Visual Basic]
- DataRepeater
- DataRepeater, virtual mode
ms.assetid: 5fb805dc-2d8b-4139-b1e3-86e4c2667221
ms.openlocfilehash: 3988c16746606de9f20f9a66b87539b6cea04758
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700801"
---
# <a name="virtual-mode-in-the-datarepeater-control-visual-studio"></a>DataRepeater 控件中的虚拟模式 (Visual Studio)
当你想要显示表格数据中的大量<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件，可以通过设置提高性能<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>属性设置为`True`和显式管理与其数据源控件的交互。 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件提供了可以处理与数据源交互并根据需要在运行时显示的数据的多个事件。  
  
## <a name="how-virtual-mode-works"></a>如何虚拟模式的工作原理  
 最常见方案<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件将绑定的子控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>到数据源在设计时，并允许<xref:System.Windows.Forms.BindingSource>传递来回根据需要的数据。 在使用的虚拟模式时，控件未绑定到数据源和数据来回传递到基础数据源在运行时。  
  
 当<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>属性设置为`True`，可通过添加控件从创建的用户界面**工具箱**而不是添加绑定的控件从**数据源**窗口。  
  
 在控件的控件模式中，引发事件，并且必须添加代码来处理数据的显示。 新建<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>滚动到视图中，<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>为每个控件一次引发事件，并且必须提供每个控件中的值<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>事件处理程序。  
  
 如果其中一个控件中的数据更改的用户，<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>引发事件，并且必须验证数据并将其保存到您的数据源。  
  
 如果用户将添加新项，<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>引发事件。 使用此事件处理程序在您的数据源中创建一条新记录。 若要防止意外的更改，您必须监视<xref:System.Windows.Forms.Control.KeyDown>为每个控件和调用事件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A>如果用户按 ESC 键。  
  
 如果您的数据源的更改，则可以刷新<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件通过调用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>和<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>方法。 必须按顺序调用这两种方法。  
  
 最后，必须实现的事件处理程序<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>事件都发生在删除某个项时，还可以选择实现<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems>和<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems>事件，每当用户通过按 DELETE 键删除项时出现。  
  
## <a name="implementing-virtual-mode"></a>实现虚拟模式  
 下面是实现虚拟模式下所需的步骤。  
  
#### <a name="to-implement-virtual-mode"></a>若要实现虚拟模式  
  
1.  拖动<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。 将 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> 属性设置为 `True`。  
  
2.  将控件从**工具箱**到项模板区域 （上半部分区域） 的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 对于您想要显示的数据源中的每个字段，将需要一个控件。  
  
3.  实现的处理程序<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>事件，以便为每个控件提供的值。 当新时，将引发此事件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>滚动到视图。 该代码将类似于以下示例中，这是一个名为的数据源`Employees`。  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_1.cs)]  
  
4.  实现的处理程序<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>事件来存储数据。 当用户更改提交到的子控件时，将引发此事件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>。 该代码将类似于以下示例中，这是一个名为的数据源`Employees`。  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_2.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_2.cs)]  
  
5.  实现每个子控件的处理程序<xref:System.Windows.Forms.Control.KeyDown>事件和监视器 ESC 键。 调用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A>方法，以阻止<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>引发的事件。 该代码将类似于下面的示例。  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_3.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_3.cs)]  
  
6.  实现的处理程序<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>事件。 当用户添加到一个新项时，将引发此事件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 该代码将类似于以下示例中，这是一个名为的数据源`Employees`。  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_4.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_4.cs)]  
  
7.  实现的处理程序<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>事件。 当用户删除现有项时，将发生此事件。 该代码将类似于以下示例中，这是一个名为的数据源`Employees`。  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_5.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_5.cs)]  
  
8.  对于控制级别验证，可以选择实现的处理程序<xref:System.Windows.Forms.Control.Validating>子控件的事件。 该代码将类似于下面的示例。  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_6.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_6.cs)]  
  
## <a name="see-also"></a>请参阅
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>
- [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
