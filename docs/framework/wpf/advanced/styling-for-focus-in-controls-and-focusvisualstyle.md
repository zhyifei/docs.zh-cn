---
title: 为控件中的焦点设置样式以及 FocusVisualStyle
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard focus [WPF]
- focus [WPF], visual styling
- styles [WPF], focus visual style
ms.assetid: 786ac576-011b-4d72-913b-558deccb9b35
ms.openlocfilehash: fda7ed12d232af5a7cfb8eb43cbb09eb793da171
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141194"
---
# <a name="styling-for-focus-in-controls-and-focusvisualstyle"></a>为控件中的焦点设置样式以及 FocusVisualStyle
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供两种用于在控件接收键盘焦点时更改其视觉外观的并行机制。 第一种机制是对应用于控件的属性（如应用于控件<xref:System.Windows.UIElement.IsKeyboardFocused%2A>的样式或模板中）使用属性设置器。 第二种机制是提供单独的样式作为<xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>属性的值;"焦点视觉样式"为在控件顶部绘制的修饰器创建单独的可视化树，而不是通过替换控件或其他 UI 元素来更改该控件或其他 UI 元素的可视树。 本主题讨论上述每一种机制的适用情况。  

<a name="Purpose"></a>
## <a name="the-purpose-of-focus-visual-style"></a>焦点视觉样式的用途  
 焦点视觉样式功能提供一种通用“对象模型”，用于基于任何 UI 元素的键盘导航来引入视觉用户反馈。 即使未向控件应用新模板，或者不知道具体的模板组合，这也是可能的。  
  
 但是，正因为焦点视觉样式功能可以在不知道控件模板的情况下工作，所以必须限制可针对使用焦点视觉样式的控件显示的视觉反馈。 此功能实际执行的操作是在控件通过模板进行呈现来创建可视化树时在其上覆盖另一可视化树（装饰器）。 您可以使用填充<xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>属性的样式定义此单独的可视化树。  
  
<a name="Default"></a>
## <a name="default-focus-visual-style-behavior"></a>默认焦点视觉样式行为  
 焦点视觉样式仅在焦点操作由键盘启动时才起作用。 任何鼠标操作或者通过编程实现的焦点更改都会禁用焦点视觉样式模式。 有关焦点模式间区别的详细信息，请参阅[焦点概述](focus-overview.md)。  
  
 控件的主题包括默认焦点视觉样式行为，该焦点视觉样式成为主题中所有控件的焦点视觉样式。 此主题样式由静态键<xref:System.Windows.SystemParameters.FocusVisualStyleKey%2A>的值标识。 当在应用程序级声明自己的焦点视觉样式时，将替换主题中的这一默认样式行为。 或者，如果要定义整个主题，那么应同样使用这个键来为整个主题的默认行为定义样式。  
  
 在主题中，默认焦点视觉样式通常非常简单。 下面是一个近似的焦点视觉样式：  
  
```xaml  
<Style x:Key="{x:Static SystemParameters.FocusVisualStyleKey}">  
  <Setter Property="Control.Template">  
    <Setter.Value>  
      <ControlTemplate>  
        <Rectangle StrokeThickness="1"  
          Stroke="Black"  
          StrokeDashArray="1 2"  
          SnapsToDevicePixels="true"/>  
      </ControlTemplate>  
    </Setter.Value>  
  </Setter>  
</Style>  
```  
  
<a name="When"></a>
## <a name="when-to-use-focus-visual-styles"></a>何时使用焦点视觉样式  
 从概念上来说，应用于控件的焦点视觉样式的外观在所有控件上应该是一致的。 确保一致性的一种方法是仅在创作整个主题时才更改焦点视觉样式，这样主题中定义的每个控件都要么获得完全相同的焦点视觉样式，要么获得在视觉上与控件具有相关性的某一样式的变体。 或者，可能使用相同的样式（或类似的样式）来设置页面或 UI 中每个可通过键盘获得焦点的元素的样式。  
  
 设置<xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>不属于主题的各个控件样式不是焦点视觉样式的预期用法。 这是因为控件间的不一致视觉行为会使用户对键盘焦点产生混乱的感觉。 如果打算对键盘焦点进行特定于控件的行为，这些行为故意不协调一个主题，则更好的方法是在样式中使用触发器来处理单个输入状态属性，如<xref:System.Windows.UIElement.IsFocused%2A>或<xref:System.Windows.UIElement.IsKeyboardFocused%2A>。  
  
 焦点视觉样式专门作用于键盘焦点。 就其本身而言，焦点视觉样式是一种辅助功能。 如果希望针对任何类型的焦点来更改 UI（无论是通过鼠标、键盘还是编程方式），那么不应使用焦点视觉样式，而应在样式或模板中使用 setter 和触发器，它们根据常规焦点属性（如 <xref:System.Windows.UIElement.IsFocused%2A> 或 <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>）的值发生作用。  
  
<a name="How"></a>
## <a name="how-to-create-a-focus-visual-style"></a>如何创建焦点视觉样式  
 为焦点视觉样式创建的样式应始终具有<xref:System.Windows.Style.TargetType%2A>。 <xref:System.Windows.Controls.Control> 样式应主要由<xref:System.Windows.Controls.ControlTemplate>。 不会将目标类型指定为将焦点视觉样式分配给 的类型<xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>。  
  
 由于目标类型始终<xref:System.Windows.Controls.Control>为 ，因此必须使用所有控件共有的属性（使用<xref:System.Windows.Controls.Control>类及其基类的属性）来设置样式。 应创建将正确地用作 UI 元素的覆盖层、且不会隐藏控件的功能区域的模板。 通常，这意味着视觉反馈应显示在控件边距之外，或者显示为临时的或不显眼的效果（这样就不会阻止应用焦点视觉样式的控件上的命中测试）。 可用于确定<xref:System.Windows.FrameworkElement.ActualHeight%2A>叠加模板的大小和定位的模板绑定中的属性包括 、<xref:System.Windows.FrameworkElement.ActualWidth%2A><xref:System.Windows.FrameworkElement.Margin%2A>和<xref:System.Windows.Controls.Control.Padding%2A>。  
  
<a name="Alternatives"></a>
## <a name="alternatives-to-using-a-focus-visual-style"></a>使用焦点视觉样式的替代方法  
 对于不适合使用焦点视觉样式的情况（因为仅设置单个控件的样式或希望对控件模板有更多的控制），存在许多其他可用的属性和技术，可用来创建响应焦点更改的视觉行为。  
  
 [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)中对触发器、setter 以及事件 setter 进行了详细介绍。 [路由事件概述](routed-events-overview.md)中对路由事件处理进行了介绍。  
  
### <a name="iskeyboardfocused"></a>IsKeyboardFocused  
 如果您特别感兴趣的是键盘焦点，则<xref:System.Windows.UIElement.IsKeyboardFocused%2A>依赖项属性可用于属性<xref:System.Windows.Trigger>。 对于定义专用于单个控件且可能与其他控件的键盘焦点行为在视觉上不匹配的键盘焦点行为，一个更适合的方法是使用样式或模板中的属性触发器。  
  
 另一个类似的依赖<xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>项属性是 ，如果要直观地呼出键盘焦点位于合成中的某处或控件的功能区域中，则可能适合使用。 例如，您可以放置一个<xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>触发器，以便对多个控件进行分组的面板显示不同，即使键盘焦点可能更精确地位于该面板中的单个元素上。  
  
 您还可以使用事件<xref:System.Windows.UIElement.GotKeyboardFocus>和<xref:System.Windows.UIElement.LostKeyboardFocus>（及其预览等效项）。 可以使用这些事件作为 的基础，<xref:System.Windows.EventSetter>也可以在代码后面为事件编写处理程序。  
  
### <a name="other-focus-properties"></a>其他焦点属性  
 如果希望<xref:System.Windows.UIElement.IsFocused%2A>更改焦点的所有可能原因生成可视行为，则应基于依赖项属性或 或 基于<xref:System.Windows.UIElement.GotFocus><xref:System.Windows.UIElement.LostFocus>或<xref:System.Windows.EventSetter>  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [焦点概述](focus-overview.md)
- [输入概述](input-overview.md)
