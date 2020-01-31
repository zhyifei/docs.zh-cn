---
title: SplitContainer 控件概述
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: 5cb5240ed4ebe3e27c20844681068711c222e9a9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742921"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>SplitContainer 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.SplitContainer> 控件可视为一个复合控件；它是由可移动条隔开的两个面板。 当鼠标指针位于条上方时，指针将改变形状以表示条可移动。  
  
> [!IMPORTANT]
> 在 "**工具箱**" 中，<xref:System.Windows.Forms.SplitContainer> 控件将替换在以前版本的 Visual Studio 中存在的 <xref:System.Windows.Forms.Splitter> 控件。 相较于 <xref:System.Windows.Forms.Splitter> 控件，优先选择 <xref:System.Windows.Forms.SplitContainer> 控件。 <xref:System.Windows.Forms.Splitter> 类仍包含在 .NET Framework 中，以便与现有应用程序兼容，但我们强烈建议为新项目使用 <xref:System.Windows.Forms.SplitContainer> 控件。  
  
 利用 <xref:System.Windows.Forms.SplitContainer> 控件，可以创建复杂的用户界面;通常，在一个面板中所做的选择决定了哪些对象显示在其他面板中。 这种安排对于显示和浏览信息非常有效。 通过具有两个面板，可以在区域、栏或 "拆分器" 中聚合信息，使用户可以轻松地调整面板的大小。  
  
 还可以嵌套多个 <xref:System.Windows.Forms.SplitContainer> 控件，并水平面向第二个 <xref:System.Windows.Forms.SplitContainer> 控件，以创建顶部面板和底部面板。  
  
 请注意，<xref:System.Windows.Forms.SplitContainer> 控件在默认情况下可通过键盘访问;如果 <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 属性设置为 `false`，用户可以按箭头键移动拆分器。  
  
 <xref:System.Windows.Forms.SplitContainer> 控件的 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 属性决定拆分器的方向，而不是控件本身的方向。 因此，在将此属性设置为 <xref:System.Windows.Forms.Orientation.Vertical>时，拆分器将从上到下运行，从而创建左右面板。  
  
 此外，请注意，<xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> 属性的值因 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 属性的值而异。 有关详细信息，请参阅 <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> 属性。  
  
 您还可以限制 <xref:System.Windows.Forms.SplitContainer> 控件的大小和移动。 <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> 属性确定调整 <xref:System.Windows.Forms.SplitContainer> 控件大小后哪个面板将保持相同的大小，<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 属性确定是通过键盘还是鼠标来可移动拆分器。  
  
> [!NOTE]
> 即使 <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 属性设置为 `true`，拆分器可能仍以编程方式移动;例如，使用 "<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>" 属性。  
  
 最后，<xref:System.Windows.Forms.SplitContainer> 控件的每个面板都具有用于确定其各个大小的属性。  
  
## <a name="commonly-used-properties-methods-and-events"></a>常用的属性、方法和事件  
  
|Name|描述|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> 属性|确定调整 <xref:System.Windows.Forms.SplitContainer> 控件大小后哪个面板将保持相同的大小。|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 属性|确定是否可以用键盘或鼠标移动拆分器。|  
|<xref:System.Windows.Forms.SplitContainer.Orientation%2A> 属性|确定拆分器是垂直排列还是水平排列。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 属性|确定从左边缘或上边缘到可移动拆分栏的距离（以像素为单位）。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 属性|确定用户可以移动拆分器的最小距离（以像素为单位）。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A> 属性|确定拆分器的粗细（以像素为单位）。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoving> 事件|在拆分器移动时发生。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoved> 事件|在拆分器移动后发生。|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer 控件](splitcontainer-control-windows-forms.md)
- [SplitContainer 控件示例](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/0ffz7d1b(v=vs.90))
