---
title: DataRepeater 控件疑难解答 (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, troubleshooting
ms.assetid: c0ab9469-eced-4f52-aa18-4bd8dd4f1a9a
ms.openlocfilehash: 7b045e1c45221cbde82c88286da8e698a763d844
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580598"
---
# <a name="troubleshooting-the-datarepeater-control-visual-studio"></a>DataRepeater 控件疑难解答 (Visual Studio)
本主题列出了你正在使用时，可能发生的常见问题<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
## <a name="datarepeater-keyboard-and-mouse-events-are-not-raised"></a>DataRepeater 键盘和鼠标事件不会引发  
 某些<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件事件，如键盘和鼠标事件不会引发。 这是设计使然。 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件本身是一个用于<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>对象，并不能在运行时访问。 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>不会在设计时公开的事件。 因此，单击某一项或项具有焦点时按某个键不会引发一个事件。  
  
 此规则的例外是何时<xref:System.Windows.Forms.Control.Padding%2A>属性设置为一个较大要公开的边缘足够值<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 在这种情况下，单击公开边缘，将引发鼠标事件。  
  
 若要解决此问题，请添加<xref:System.Windows.Forms.Panel>控制对<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>一部分<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控制，以及如何将控件到其余<xref:System.Windows.Forms.Panel>。 然后，可以添加到代码<xref:System.Windows.Forms.Panel>键盘和鼠标事件的控件的事件处理程序。  
  
## <a name="the-datarepeater-is-partially-hidden-behind-the-binding-navigator"></a>DataRepeater 部分隐藏在绑定导航器  
 当首次添加<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>向窗体控件以及如何将数据绑定控件从**数据源**窗口中，<xref:System.Windows.Forms.BindingNavigator>控件可能出现的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 这是一个已知的限制**数据源**窗口中，为与其他控件的行为一致例如<xref:System.Windows.Forms.DataGridView>控件。  
  
 可以是移动<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>低于<xref:System.Windows.Forms.BindingNavigator>控制在设计时，或将类似于中的以下代码添加`Load`事件处理程序。  
  
```vb  
DataRepeater1.Top = ProductsBindingNavigator.Height  
```  
  
```csharp  
dataRepeater1.Top = productsBindingNavigator.Height;  
```  
  
## <a name="controls-are-not-displayed-correctly-at-run-time"></a>控件不在运行时正确显示  
 中的某些控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件可能不会按预期方式运行时显示。 用于克隆中的控件的过程<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>始终无法确定的所有控件的所有属性。 例如，如果您将添加未绑定<xref:System.Windows.Forms.ListBox>控制对<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>在设计时控件并填充其<xref:System.Windows.Forms.ListBox.Items%2A>集合具有列表的字符串，<xref:System.Windows.Forms.ListBox>在运行时将为空。 这是因为克隆过程不能考虑到<xref:System.Windows.Forms.ListBox.Items%2A>属性。  
  
 可以通过还原中缺少的属性来解决此问题<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned>默认克隆完成后发生的事件。 下面的示例演示如何修复<xref:System.Windows.Forms.ListBox.Items%2A>的集合<xref:System.Windows.Forms.ListBox>控制中<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned>事件处理程序。  
  
 [!code-csharp[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/troubleshooting-the-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/troubleshooting-the-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="the-selection-symbol-on-the-item-header-is-missing"></a>缺少的项标头上的选择符号  
 当你更改<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>属性中的项标头<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件中，一些颜色选择可能会导致选择符号消失。 更改<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>属性也可能会导致选择符号消失。  
  
 不能更改颜色和选择符号的大小。  
  
-   如果您设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>到<xref:System.Drawing.Color.White%2A>，选择符号首次选定项时将不可见。  
  
-   如果您设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>到<xref:System.Drawing.Color.Black%2A>，选择符号控件被选定，且铅笔符号将不会显示在控件处于编辑模式时将不可见。  
  
-   如果<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>属性设置为小于 11 的值，将不会显示项标头中的指示符符号。  
  
 可以通过使用提供你自己的项标头和选择符号<xref:System.Windows.Forms.PictureBox>控制和监视<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>的属性<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>中<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>的事件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 有关详细信息，请参阅 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>。  
  
## <a name="see-also"></a>请参阅
- [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [如何：DataRepeater 控件中显示绑定的数据](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [如何：DataRepeater 控件中显示未绑定的控件](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)
- [如何：更改 DataRepeater 控件的布局](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)
- [如何：更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [如何：DataRepeater 控件中显示项标头](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
- [如何：禁止添加和删除 DataRepeater 项](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)
- [如何：DataRepeater 控件中搜索数据](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)
- [如何：使用两个 DataRepeater 控件 (Visual Studio) 创建母版/详细信息窗体](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
