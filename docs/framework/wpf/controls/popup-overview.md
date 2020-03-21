---
title: Popup 概述
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: 911130d52744c5ba54750f214829a5d1900e083c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185952"
---
# <a name="popup-overview"></a>Popup 概述
该<xref:System.Windows.Controls.Primitives.Popup>控件提供了一种在单独的窗口中显示内容的方法，该窗口相对于指定的元素或屏幕坐标浮动在当前应用程序窗口中。 本主题介绍控件<xref:System.Windows.Controls.Primitives.Popup>，并提供有关其使用的信息。  

<a name="What_Is_a_Popup_"></a>
## <a name="what-is-a-popup"></a>什么是 Popup？  
 控件<xref:System.Windows.Controls.Primitives.Popup>显示与屏幕上的元素或点相关的单独窗口中的内容。 当<xref:System.Windows.Controls.Primitives.Popup>可见 时，<xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A>属性设置为`true`。  
  
> [!NOTE]
> 当<xref:System.Windows.Controls.Primitives.Popup>鼠标指针在其父对象上移动时，不会自动打开。 如果要自动打开<xref:System.Windows.Controls.Primitives.Popup>， 请使用 或<xref:System.Windows.Controls.ToolTip><xref:System.Windows.Controls.ToolTipService>类。 有关详细信息，请参阅 [ToolTip 概述](tooltip-overview.md)。  
  
<a name="APopupExample"></a>
## <a name="creating-a-popup"></a>创建弹出项。  
 下面的示例演示如何定义作为<xref:System.Windows.Controls.Primitives.Popup><xref:System.Windows.Controls.Button>控件的子元素的控件。 由于<xref:System.Windows.Controls.Button>只能有一个子元素，因此此示例将 和<xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.Popup>控件的文本放在 中。 <xref:System.Windows.Controls.StackPanel> 的内容<xref:System.Windows.Controls.Primitives.Popup>显示在<xref:System.Windows.Controls.TextBlock>控件中，该控件在单独的窗口中显示其文本，该窗口浮动在相关<xref:System.Windows.Controls.Button>控件附近的应用程序窗口上。  
  
 [!code-xaml[PopupSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>
## <a name="controls-that-implement-a-popup"></a>实现 Popup 的控件  
 可以将控件构建<xref:System.Windows.Controls.Primitives.Popup>到其他控件中。 以下控件为<xref:System.Windows.Controls.Primitives.Popup>特定用途实现控件：  
  
- <xref:System.Windows.Controls.ToolTip>. 如果要为元素创建工具提示，请使用 和<xref:System.Windows.Controls.ToolTip><xref:System.Windows.Controls.ToolTipService>类。 有关详细信息，请参阅 [ToolTip 概述](tooltip-overview.md)。  
  
- <xref:System.Windows.Controls.ContextMenu>. 如果要为元素创建上下文菜单，请使用 控件<xref:System.Windows.Controls.ContextMenu>。 有关详细信息，请参阅 [ContextMenu 概述](contextmenu-overview.md)。  
  
- <xref:System.Windows.Controls.ComboBox>. 如果要创建具有可显示或隐藏的下拉列表框的选择控件，请使用 该<xref:System.Windows.Controls.ComboBox>控件。  
  
- <xref:System.Windows.Controls.Expander>. 如果要创建显示具有可折叠区域显示内容的标头的控件，请使用 该<xref:System.Windows.Controls.Expander>控件。 有关详细信息，请参阅 [Expander 概述](expander-overview.md)。  
  
<a name="PopupBehaviorandAppearance"></a>
## <a name="popup-behavior-and-appearance"></a>Popup 行为和外观  
 该<xref:System.Windows.Controls.Primitives.Popup>控件提供的功能使您能够自定义其行为和外观。 例如，您可以设置打开和关闭行为、动画、不一公开性和位图效果以及<xref:System.Windows.Controls.Primitives.Popup>大小和位置。  
  
<a name="OpenandCloseBehavior"></a>
### <a name="open-and-close-behavior"></a>打开和关闭行为  
 当<xref:System.Windows.Controls.Primitives.Popup>属性设置为<xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A>`true`时，控件将显示其内容。 默认情况下，<xref:System.Windows.Controls.Primitives.Popup>保持打开状态，<xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A>直到属性设置为`false`。 但是，您可以通过将<xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A>属性设置为`false`来更改默认行为。 将此属性设置为`false`时，<xref:System.Windows.Controls.Primitives.Popup>内容窗口具有鼠标捕获。 当<xref:System.Windows.Controls.Primitives.Popup>鼠标事件发生在<xref:System.Windows.Controls.Primitives.Popup>窗口外部时，丢失鼠标捕获和窗口关闭。  
  
 当<xref:System.Windows.Controls.Primitives.Popup.Opened><xref:System.Windows.Controls.Primitives.Popup>内容<xref:System.Windows.Controls.Primitives.Popup.Closed>窗口打开或关闭时，将引发 和 事件。  
  
<a name="Animation"></a>
### <a name="animation"></a>动画  
 该<xref:System.Windows.Controls.Primitives.Popup>控件具有内置支持通常与淡入和滑入等行为关联的动画。 通过将属性设置为<xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A><xref:System.Windows.Controls.Primitives.PopupAnimation>枚举值，可以打开这些动画。 要<xref:System.Windows.Controls.Primitives.Popup>使动画正常工作，必须将<xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A>属性设置为`true`。  
  
 您还可以将控件等<xref:System.Windows.Media.Animation.Storyboard>动画应用于<xref:System.Windows.Controls.Primitives.Popup>控件。  
  
<a name="OpacityandBitmapEffects"></a>
### <a name="opacity-and-bitmap-effects"></a>不透明度和位图效果  
 <xref:System.Windows.Controls.Primitives.Popup>控件<xref:System.Windows.UIElement.Opacity%2A>的属性对其内容没有影响。 默认情况下，<xref:System.Windows.Controls.Primitives.Popup>内容窗口不透明。 要创建透明<xref:System.Windows.Controls.Primitives.Popup>，请将<xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A>属性设置为`true`。  
  
 的内容<xref:System.Windows.Controls.Primitives.Popup>不继承位图效果，例如<xref:System.Windows.Media.Effects.DropShadowBitmapEffect>，您直接在<xref:System.Windows.Controls.Primitives.Popup>控件或父窗口中的任何其他元素上设置。 要将位图效果显示在 的内容上<xref:System.Windows.Controls.Primitives.Popup>，必须直接在其内容上设置位图效果。 例如，如果 的<xref:System.Windows.Controls.Primitives.Popup>子级为<xref:System.Windows.Controls.StackPanel>， 在 上设置位图效果<xref:System.Windows.Controls.StackPanel>。  
  
<a name="PopupSize"></a>
### <a name="popup-size"></a>Popup 大小  
 默认情况下，应<xref:System.Windows.Controls.Primitives.Popup>自动调整其内容的大小。 发生自动大小调整时，可能会隐藏某些位图效果，因为为<xref:System.Windows.Controls.Primitives.Popup>内容定义的屏幕区域的默认大小无法为位图效果提供足够的空间来显示。  
  
 <xref:System.Windows.Controls.Primitives.Popup>在内容上设置 时<xref:System.Windows.UIElement.RenderTransform%2A>，内容也会被遮盖。 在这种情况下，如果转换的内容<xref:System.Windows.Controls.Primitives.Popup>超出原始<xref:System.Windows.Controls.Primitives.Popup>区域的范围，则某些内容可能会隐藏。 如果位图效果或变换需要更多空间，则可以在<xref:System.Windows.Controls.Primitives.Popup>内容周围定义边距，以便为控件提供更多区域。  
  
<a name="DefiningPopupPosition"></a>
## <a name="defining-the-popup-position"></a>定义 Popup 位置  
 您可以通过设置<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>、 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>、<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>和<xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A><xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty>属性来定位弹出窗口。 有关详细信息，请参阅 [Popup 放置行为](popup-placement-behavior.md)。 当<xref:System.Windows.Controls.Primitives.Popup>显示在屏幕上时，如果重新定位其父级，它不会重新定位自身。  
  
<a name="CustomizingPopupPlacement"></a>
### <a name="customizing-popup-placement"></a>自定义 Popup 放置  
 可以通过指定一组相对于要<xref:System.Windows.Controls.Primitives.Popup><xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A><xref:System.Windows.Controls.Primitives.Popup>显示的位置的坐标来自定义控件的位置。  
  
 要自定义放置，请将<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>设置为 。 然后定义一<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>个委托，该委托返回 一<xref:System.Windows.Controls.Primitives.Popup>组可能的放置点和主轴（按首选项顺序排列） 。 显示 的最大部分<xref:System.Windows.Controls.Primitives.Popup>的点将自动选择。 有关示例，请参阅[指定自定义 Popup 位置](how-to-specify-a-custom-popup-position.md)。  
  
<a name="PopupandtheVisualTree"></a>
## <a name="popup-and-the-visual-tree"></a>Popup 和可视化树  
 控件<xref:System.Windows.Controls.Primitives.Popup>没有自己的可视树;因此，控件没有自己的可视树。相反，当调用 方法<xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A><xref:System.Windows.Controls.Primitives.Popup>时，它返回大小 0（零）。 但是，当您将 属性<xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A><xref:System.Windows.Controls.Primitives.Popup>设置为`true`时，将创建具有其自身可视树的新窗口。 新窗口包含<xref:System.Windows.Controls.Primitives.Popup.Child%2A>的内容<xref:System.Windows.Controls.Primitives.Popup>。 新窗口的宽度和高度不能超过屏幕宽度或高度的 75%。  
  
 控件<xref:System.Windows.Controls.Primitives.Popup>将引用内容<xref:System.Windows.Controls.Primitives.Popup.Child%2A>作为逻辑子级。 创建新窗口时，的内容<xref:System.Windows.Controls.Primitives.Popup>将成为窗口的视觉子级，并且仍然是<xref:System.Windows.Controls.Primitives.Popup>的逻辑子级。 相反，<xref:System.Windows.Controls.Primitives.Popup>仍然是其内容<xref:System.Windows.Controls.Primitives.Popup.Child%2A>的逻辑父级。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Primitives.Popup>
- <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>
- <xref:System.Windows.Controls.Primitives.PlacementMode>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [如何使用主题](popup-how-to-topics.md)
- [如何使用主题](tooltip-how-to-topics.md)
