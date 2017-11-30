---
title: "DataRepeater 控件中的虚拟模式 (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- virtual data binding [Visual Basic]
- DataRepeater
- DataRepeater, virtual mode
ms.assetid: 5fb805dc-2d8b-4139-b1e3-86e4c2667221
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4c85ce4541e32991bfa09b1436385281d27ad355
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="virtual-mode-in-the-datarepeater-control-visual-studio"></a>DataRepeater 控件中的虚拟模式 (Visual Studio)
如果想要显示大量的表格数据<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件，您可以通过设置改善性能<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>属性`True`和显式管理与其数据源的控件的交互。 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件提供可以处理与数据源进行交互并根据需要在运行时显示的数据的多个事件。  
  
## <a name="how-virtual-mode-works"></a>虚拟模式的工作原理  
 最常见方案<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件将绑定的子控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>到数据源在设计时，并允许<xref:System.Windows.Forms.BindingSource>传递来回根据需要的数据。 当你使用的虚拟模式时，这些控件将不会绑定到数据源，并且数据在运行时基础数据源来回传递。  
  
 当<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>属性设置为`True`，通过添加从控件创建的用户界面**工具箱**而不是添加绑定的控件从**数据源**窗口。  
  
 根据控件的控件引发事件，并且必须添加代码来处理数据的显示。 当新<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>滚动到视图，<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>将引发一次为每个控件的事件，并且你必须提供中每个控件的值<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>事件处理程序。  
  
 如果在每个控件的数据更改，用户<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>引发事件，必须验证数据和将其保存到您的数据源。  
  
 如果用户将添加一个新项目，<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>引发事件。 此事件处理程序用于在您的数据源中创建一条新记录。 若要防止意外的更改，你还必须监视<xref:System.Windows.Forms.Control.KeyDown>事件对于每个控件和调用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A>如果用户按下 ESC 键。  
  
 如果你的数据源发生更改，则可以刷新<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>通过调用控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>和<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>方法。 必须按顺序调用这两种方法。  
  
 最后，必须实现事件处理程序<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>事件，发生当删除项时，还可以选择实现<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems>和<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems>事件，每当用户通过按 DELETE 键删除项时出现。  
  
## <a name="implementing-virtual-mode"></a>实现虚拟模式  
 下面是实现虚拟模式所需的步骤。  
  
#### <a name="to-implement-virtual-mode"></a>若要实现虚拟模式  
  
1.  拖动<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。 将 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> 属性设置为 `True`。  
  
2.  将控件从**工具箱**拖动的项模板区域 （上半部分区域） 到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 对于你想要显示的数据源中的每个字段，将需要一个控件。  
  
3.  实现的处理程序<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>事件，以便为每个控件提供值。 当新时，将引发此事件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>滚动到视图。 该代码将类似以下示例中，对于名为数据源即`Employees`。  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_1.cs)]  
  
4.  实现的处理程序<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>事件来存储数据。 当用户将更改提交到的子控件时，将引发此事件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>。 该代码将类似以下示例中，对于名为数据源即`Employees`。  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_2.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_2.cs)]  
  
5.  实现的处理程序每个子控件<xref:System.Windows.Forms.Control.KeyDown>事件和监视器 ESC 键。 调用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A>方法，以阻止<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>引发的事件。 代码将类似于下面的示例。  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_3.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_3.cs)]  
  
6.  实现的处理程序<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>事件。 当用户添加到一个新项时，将引发此事件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 该代码将类似以下示例中，对于名为数据源即`Employees`。  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_4.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_4.cs)]  
  
7.  实现的处理程序<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>事件。 当用户中删除现有项，将发生此事件。 该代码将类似以下示例中，对于名为数据源即`Employees`。  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_5.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_5.cs)]  
  
8.  对于控制级别的验证，可以选择实现处理程序<xref:System.Windows.Forms.Control.Validating>子控件的事件。 代码将类似于下面的示例。  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_6.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_6.cs)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>  
 [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
