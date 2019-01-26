---
title: 如何：禁止添加和删除 DataRepeater 项 (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, disabling delete
- DataRepeater, disabling add
ms.assetid: 298d8f60-ddfe-4361-ab66-cf76d0df5220
ms.openlocfilehash: 3a304132d0514da4c19811be2536c9516e2838f0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618537"
---
# <a name="how-to-disable-adding-and-deleting-datarepeater-items-visual-studio"></a>如何：禁止添加和删除 DataRepeater 项 (Visual Studio)
默认情况下，用户可以添加和删除项<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 用户可以通过按 CTRL + N 添加新项时<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A>具有焦点或通过单击**AddNewItem**按钮<xref:System.Windows.Forms.BindingNavigator>控件。 用户可以通过按删除项时删除<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A>具有焦点或通过单击**DeleteItem**按钮<xref:System.Windows.Forms.BindingNavigator>控件。  
  
 您可以禁用添加和/或删除在设计时或在运行时。  
  
### <a name="to-disable-adding-and-deleting-at-design-time"></a>若要禁用在设计时添加和删除  
  
1.  在 Windows 窗体设计器中，选择<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
    > [!NOTE]
    >  必须选择该控件的下半部分。 如果选择项模板部分，将显示一组不同的属性。  
  
2.  在属性窗口中设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A>属性设置为**False**。  
  
3.  设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A>属性设置为**False**。  
  
4.  在 Windows 窗体设计器中，选择<xref:System.Windows.Forms.BindingNavigator>控件，，然后单击**AddNewItem**按钮 （带有其上的加号按钮）。  
  
5.  在属性窗口中设置<xref:System.Windows.Forms.ToolBarButton.Enabled%2A>属性设置为**False**。  
  
6.  在 Windows 窗体设计器中，选择<xref:System.Windows.Forms.BindingNavigator>控件，，然后单击**DeleteItem**按钮 （带有红色 X 上的按钮）。  
  
7.  在属性窗口中设置<xref:System.Windows.Forms.ToolBarButton.Enabled%2A>属性设置为**False**。  
  
8.  在组件栏中，选择<xref:System.Windows.Forms.BindingSource>到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>绑定。  
  
9. 在属性窗口中设置<xref:System.Windows.Forms.BindingSource.AllowNew%2A>属性设置为**False**。  
  
10. 在 Windows 窗体设计器中，双击**DeleteItem**按钮以打开代码编辑器。  
  
11. 在事件下拉列表中选择`BindingNavigatorDeleteItem_EnabledChanged`事件。  
  
12. 将以下代码添加到 `BindingNavigatorDeleteItem_EnabledChanged` 事件处理程序中：  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  此步骤是必需的因为<xref:System.Windows.Forms.BindingSource>将启用**DeleteItem**按钮每次当前记录更改时。  
  
### <a name="to-disable-adding-and-deleting-at-run-time"></a>若要禁止添加和删除在运行时  
  
1.  在 Windows 窗体设计器中，双击窗体打开代码编辑器。  
  
2.  将以下代码添加到 `Form_Load` 事件中：  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.vb)]  
  
3.  将以下代码添加到 `BindingNavigatorDeleteItem_EnabledChanged` 事件处理程序中：  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  此步骤是必需的因为<xref:System.Windows.Forms.BindingSource>将启用**DeleteItem**按钮每次当前记录更改时。  
  
## <a name="see-also"></a>请参阅
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
