---
title: DataRepeater 控件疑难解答 (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, troubleshooting
ms.assetid: c0ab9469-eced-4f52-aa18-4bd8dd4f1a9a
ms.openlocfilehash: 092bbe89bb73a40dee7161f014d40a581b0ddc06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-the-datarepeater-control-visual-studio"></a>DataRepeater 控件疑难解答 (Visual Studio)
本主题列出了你正在使用时可能发生的常见问题<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
## <a name="datarepeater-keyboard-and-mouse-events-are-not-raised"></a>不引发 DataRepeater 键盘和鼠标事件  
 某些<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件事件，如键盘和鼠标事件，则不引发。 这是设计使然。 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件本身是容器<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>对象，并不能在运行时访问。 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>不会在设计时公开的事件。 因此，如果单击的项，或当项具有焦点时按某个键不会引发事件。  
  
 此规则的例外是当<xref:System.Windows.Forms.Control.Padding%2A>属性设置为一个较大要公开的边缘足够值<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 在这种情况下，公开距中单击将引发鼠标事件。  
  
 若要解决此问题，将添加<xref:System.Windows.Forms.Panel>控制转移到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>部分<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控制，，然后添加到控件的其余部分<xref:System.Windows.Forms.Panel>。 你可以然后将代码添加到<xref:System.Windows.Forms.Panel>键盘和鼠标事件的控件的事件处理程序。  
  
## <a name="the-datarepeater-is-partially-hidden-behind-the-binding-navigator"></a>DataRepeater 部分隐藏在绑定导航器  
 当您首次添加<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>到窗体控件，然后添加数据绑定控件从**数据源**窗口中，<xref:System.Windows.Forms.BindingNavigator>控件可能会出现的顶部<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 这是已知的限制**数据源**窗口并且在与其他控件的行为一致如<xref:System.Windows.Forms.DataGridView>控件。  
  
 你可以移动<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>低于<xref:System.Windows.Forms.BindingNavigator>控制在设计时，或添加类似于以下的代码`Load`事件处理程序。  
  
```vb  
DataRepeater1.Top = ProductsBindingNavigator.Height  
```  
  
```csharp  
dataRepeater1.Top = productsBindingNavigator.Height;  
```  
  
## <a name="controls-are-not-displayed-correctly-at-run-time"></a>在运行时未正确显示控件  
 中的某些控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件可能不会按预期运行时显示。 用于克隆从控件的过程<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>不总是可以确定的所有控件的所有属性。 例如，如果你将添加未绑定<xref:System.Windows.Forms.ListBox>控制转移到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控制在设计时和填充其<xref:System.Windows.Forms.ListBox.Items%2A>字符串，与列表集合<xref:System.Windows.Forms.ListBox>在运行时将为空。 这是因为克隆过程不能考虑<xref:System.Windows.Forms.ListBox.Items%2A>属性。  
  
 可通过还原缺少的属性中修复此问题<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned>事件，在默认克隆过程完成之后发生。 下面的示例演示如何修复<xref:System.Windows.Forms.ListBox.Items%2A>集合<xref:System.Windows.Forms.ListBox>中控制<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned>事件处理程序。  
  
 [!code-csharp[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/troubleshooting-the-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/troubleshooting-the-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="the-selection-symbol-on-the-item-header-is-missing"></a>项标头上的选择符号是缺少  
 当你更改<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>项标头中的属性<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件，某些颜色选择可能会导致选择符号消失。 更改<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>属性也可能会导致选择符号消失。  
  
 不能更改颜色和选择符号的大小。  
  
-   如果你设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>到<xref:System.Drawing.Color.White%2A>，选择符号首先选择项目时将不可见。  
  
-   如果你设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>到<xref:System.Drawing.Color.Black%2A>，选择符号控件被选定，且铅笔符号当控件处于编辑模式时将不可见时将不可见。  
  
-   如果<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>属性设置为小于 11 一个值，将不会显示项标头中的指示器符号。  
  
 通过使用你可以提供你自己的项标头和选择符号<xref:System.Windows.Forms.PictureBox>控制和监视<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>属性<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>中<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 有关详细信息，请参阅<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>。  
  
## <a name="see-also"></a>请参阅  
 [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [如何：在 DataRepeater 控件中显示绑定数据](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [如何：在 DataRepeater 控件中显示未绑定的控件](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [如何：更改 DataRepeater 控件的布局](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [如何：更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [如何：在 DataRepeater 控件中显示项标题](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)  
 [如何：禁止添加和删除 DataRepeater 项](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)  
 [如何：在 DataRepeater 控件中搜索数据](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)  
 [如何： 使用两个 DataRepeater 控件 (Visual Studio) 中创建主/从窗体](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
