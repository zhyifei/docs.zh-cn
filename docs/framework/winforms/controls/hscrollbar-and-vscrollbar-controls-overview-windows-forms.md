---
title: HScrollBar 和 VScrollBar 控件概述
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
ms.openlocfilehash: abe0c8da9723f17cb80715454f6ab7297724a21f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728171"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>HScrollBar 控件和 VScrollBar 控件概述（Windows 窗体）
使用 Windows 窗体 <xref:System.Windows.Forms.ScrollBar> 控件，可以通过在应用程序或控件中水平或垂直滚动来轻松地浏览较长的项列表或大量的信息。 滚动条是 Windows 界面的公共元素，因此 <xref:System.Windows.Forms.ScrollBar> 控件通常用于不是从 <xref:System.Windows.Forms.ScrollableControl> 类派生的控件。 同样，许多开发人员在创作自己的用户控件时选择合并 <xref:System.Windows.Forms.ScrollBar> 控件。  
  
 <xref:System.Windows.Forms.HScrollBar> （水平）和 <xref:System.Windows.Forms.VScrollBar> （垂直）控件独立于其他控件操作，并且具有其自己的一组事件、属性和方法。 <xref:System.Windows.Forms.ScrollBar> 控件与附加到文本框、列表框、组合框或 MDI 窗体的内置滚动条不相同（<xref:System.Windows.Forms.TextBox> 控件具有 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 属性，用于显示或隐藏附加到控件的滚动条）。  
  
 <xref:System.Windows.Forms.ScrollBar> 控件使用 <xref:System.Windows.Forms.ScrollBar.Scroll> 事件来监视滚动条上滚动框的移动（有时称为滚动条）。 使用 <xref:System.Windows.Forms.ScrollBar.Scroll> 事件可在拖动滚动条值时，提供对滚动条值的访问。  
  
## <a name="value-property"></a>Value 属性  
 <xref:System.Windows.Forms.ScrollBar.Value%2A> 属性（默认情况下为0）是与滚动条中滚动框的位置相对应的 `integer` 值。 当滚动框位置达到最小值时，它将移到最左侧的位置（对于水平滚动条）或顶部位置（对于垂直滚动条）。 当滚动框处于最大值时，滚动框会移动到最右侧或底部位置。 同样，范围底部和顶部中间的值将在滚动条的中间放置滚动框的上边缘。  
  
 除了使用鼠标单击更改滚动条值以外，用户还可以将滚动框拖动到滚动条上的任意点。 生成的值取决于滚动框的位置，但它始终位于 <xref:System.Windows.Forms.ScrollBar.Minimum%2A> 范围内，以 <xref:System.Windows.Forms.ScrollBar.Maximum%2A> 用户设置的属性。  
  
## <a name="largechange-and-smallchange-properties"></a>LargeChange 和 SmallChange 属性  
 当用户按下 PAGE UP 或 PAGE DOWN 键或单击滚动框两侧的滚动条轨道时，<xref:System.Windows.Forms.ScrollBar.Value%2A> 属性会根据 <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> 属性中设置的值进行更改。  
  
 当用户按下某个箭头键或单击某个滚动条按钮时，<xref:System.Windows.Forms.ScrollBar.Value%2A> 属性会根据 <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> 属性中设置的值进行更改。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.HScrollBar>
- <xref:System.Windows.Forms.VScrollBar>
- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
