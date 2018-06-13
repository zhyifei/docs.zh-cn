---
title: HScrollBar 控件和 VScrollBar 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
ms.openlocfilehash: 572ba9f16d1c78e1825d0c9db7530c6c78175d27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538460"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>HScrollBar 控件和 VScrollBar 控件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.ScrollBar>控件用于提供较长列表项或大量信息中的轻松导航，请水平或垂直滚动内的应用程序或控件。 滚动条是一种常见元素的 Windows 界面中，因此<xref:System.Windows.Forms.ScrollBar>控件通常用于是非派生自的控件<xref:System.Windows.Forms.ScrollableControl>类。 同样，许多开发人员选择合并<xref:System.Windows.Forms.ScrollBar>控制创建其自己的用户控件时。  
  
 <xref:System.Windows.Forms.HScrollBar> （水平） 和<xref:System.Windows.Forms.VScrollBar>（垂直） 控件运行独立于其他控件，并且具有其自己的事件、 属性和方法集。 <xref:System.Windows.Forms.ScrollBar> 控件不是附加到文本框、 列表框、 组合框或 MDI 窗体的内置滚动条相同 (<xref:System.Windows.Forms.TextBox>控件具有<xref:System.Windows.Forms.TextBox.ScrollBars%2A>属性来显示或隐藏附加到控件的滚动条)。  
  
 <xref:System.Windows.Forms.ScrollBar>控制是否使用<xref:System.Windows.Forms.ScrollBar.Scroll>事件来监视沿滚动条的滚动框 （有时称为滚动块） 的移动。 使用<xref:System.Windows.Forms.ScrollBar.Scroll>事件提供滚动栏值的访问，如进行拖动。  
  
## <a name="value-property"></a>Value 属性  
 <xref:System.Windows.Forms.ScrollBar.Value%2A>属性 （它，默认情况下，为 0） 是`integer`到滚动条中滚动框的位置相对应的值。 最小值的滚动框位置时，它将移动到的最左边的位置 （水平滚动条） 或 （对于垂直滚动条） 的最顶部位置。 在最大值、 滚动框移到最右侧或底部位置时滚动框。 同样，值的范围顶部和底部的中间值将置于中间的滚动条的滚动框的前边缘。  
  
 除了使用鼠标单击的滚动条值更改，用户可以还将滚动框拖动到沿条任何点。 生成的值取决于滚动框的位置，但它并总是的范围内<xref:System.Windows.Forms.ScrollBar.Minimum%2A>到<xref:System.Windows.Forms.ScrollBar.Maximum%2A>由用户设置的属性。  
  
## <a name="largechange-and-smallchange-properties"></a>是它和 SmallChange 属性  
 当用户按 PAGE UP 或 PAGE DOWN 键或单击中的滚动框中，任何一侧的滚动条轨道<xref:System.Windows.Forms.ScrollBar.Value%2A>根据中设置的值的属性更改<xref:System.Windows.Forms.ScrollBar.LargeChange%2A>属性。  
  
 当用户按某个箭头键或单击滚动条按钮时，之一<xref:System.Windows.Forms.ScrollBar.Value%2A>根据中设置的值的属性更改<xref:System.Windows.Forms.ScrollBar.SmallChange%2A>属性。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.HScrollBar>  
 <xref:System.Windows.Forms.VScrollBar>  
 [用于.NET Framework 2.0 向 Windows 窗体的添加件](http://msdn.microsoft.com/library/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)  
 [在 Windows 窗体上使用的控件](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
