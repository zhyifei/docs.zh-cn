---
title: Popup 概述
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: c9261e2151f116b46a0c25d8dc775bf41bf932b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557571"
---
# <a name="popup-overview"></a>Popup 概述
<xref:System.Windows.Controls.Primitives.Popup>控件提供了如何通过当前的应用程序窗口相对于指定的元素或屏幕坐标浮动的单独窗口中显示内容。 本主题介绍<xref:System.Windows.Controls.Primitives.Popup>控件并提供有关其使用情况信息。  
  
 
  
<a name="What_Is_a_Popup_"></a>   
## <a name="what-is-a-popup"></a>什么是 Popup？  
 A<xref:System.Windows.Controls.Primitives.Popup>控件相对于元素或在屏幕上的点的单独窗口中显示内容。 当<xref:System.Windows.Controls.Primitives.Popup>可见，<xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A>属性设置为`true`。  
  
> [!NOTE]
>  A<xref:System.Windows.Controls.Primitives.Popup>不会自动打开当鼠标指针移到其父对象。 如果你想<xref:System.Windows.Controls.Primitives.Popup>自动打开，请使用<xref:System.Windows.Controls.ToolTip>或<xref:System.Windows.Controls.ToolTipService>类。 有关详细信息，请参阅 [ToolTip 概述](../../../../docs/framework/wpf/controls/tooltip-overview.md)。  
  
<a name="APopupExample"></a>   
## <a name="creating-a-popup"></a>创建弹出项。  
 下面的示例演示如何定义<xref:System.Windows.Controls.Primitives.Popup>即控制的子元素<xref:System.Windows.Controls.Button>控件。 因为<xref:System.Windows.Controls.Button>可以具有只有一个子元素，此示例中的文本放<xref:System.Windows.Controls.Button>和<xref:System.Windows.Controls.Primitives.Popup>中控制<xref:System.Windows.Controls.StackPanel>。 内容<xref:System.Windows.Controls.Primitives.Popup>出现在<xref:System.Windows.Controls.TextBlock>控件，通过靠近相关应用程序窗口浮动的单独窗口中显示其文本<xref:System.Windows.Controls.Button>控件。  
  
 [!code-xaml[PopupSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>   
## <a name="controls-that-implement-a-popup"></a>实现 Popup 的控件  
 你可以生成<xref:System.Windows.Controls.Primitives.Popup>到其他控件的控件。 以下控件实现<xref:System.Windows.Controls.Primitives.Popup>特定用途的控件：  
  
-   <xref:System.Windows.Controls.ToolTip>。 如果你想要创建一个元素的工具提示，使用<xref:System.Windows.Controls.ToolTip>和<xref:System.Windows.Controls.ToolTipService>类。 有关详细信息，请参阅 [ToolTip 概述](../../../../docs/framework/wpf/controls/tooltip-overview.md)。  
  
-   <xref:System.Windows.Controls.ContextMenu>。 如果你想要创建的元素的上下文菜单，使用<xref:System.Windows.Controls.ContextMenu>控件。 有关详细信息，请参阅 [ContextMenu 概述](../../../../docs/framework/wpf/controls/contextmenu-overview.md)。  
  
-   <xref:System.Windows.Controls.ComboBox>。 如果你想要创建具有可以显示或隐藏，使用下拉列表框的选择控件<xref:System.Windows.Controls.ComboBox>控件。  
  
-   <xref:System.Windows.Controls.Expander>。 如果你想要创建用于显示具有的可折叠区域的标头控件的显示内容，请使用<xref:System.Windows.Controls.Expander>控件。 有关详细信息，请参阅 [Expander 概述](../../../../docs/framework/wpf/controls/expander-overview.md)。  
  
<a name="PopupBehaviorandAppearance"></a>   
## <a name="popup-behavior-and-appearance"></a>Popup 行为和外观  
 <xref:System.Windows.Controls.Primitives.Popup>控件提供功能，可用于自定义其行为和外观。 例如，你可以在其中设置打开和关闭行为、 动画、 不透明度和位图效果和<xref:System.Windows.Controls.Primitives.Popup>大小和位置。  
  
<a name="OpenandCloseBehavior"></a>   
### <a name="open-and-close-behavior"></a>打开和关闭行为  
 A<xref:System.Windows.Controls.Primitives.Popup>控件将显示其内容时<xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A>属性设置为`true`。 默认情况下，<xref:System.Windows.Controls.Primitives.Popup>保持打开状态，除非<xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A>属性设置为`false`。 但是，可以通过设置更改默认行为<xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A>属性`false`。 当设置此属性为`false`、<xref:System.Windows.Controls.Primitives.Popup>内容窗口具有鼠标捕获。 <xref:System.Windows.Controls.Primitives.Popup>外部发生鼠标事件时失去鼠标捕获并且该窗口将关闭<xref:System.Windows.Controls.Primitives.Popup>窗口。  
  
 <xref:System.Windows.Controls.Primitives.Popup.Opened>和<xref:System.Windows.Controls.Primitives.Popup.Closed>引发事件时<xref:System.Windows.Controls.Primitives.Popup>内容的窗口是打开还是关闭。  
  
<a name="Animation"></a>   
### <a name="animation"></a>动画  
 <xref:System.Windows.Controls.Primitives.Popup>控件有内置支持通常与淡入和滑入行为与关联的动画。 你可以通过设置打开这些动画<xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A>属性<xref:System.Windows.Controls.Primitives.PopupAnimation>枚举值。 有关<xref:System.Windows.Controls.Primitives.Popup>动画能够正常工作，必须设置<xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A>属性`true`。  
  
 你还可以应用之类的动画<xref:System.Windows.Media.Animation.Storyboard>到<xref:System.Windows.Controls.Primitives.Popup>控件。  
  
<a name="OpacityandBitmapEffects"></a>   
### <a name="opacity-and-bitmap-effects"></a>不透明度和位图效果  
 <xref:System.Windows.UIElement.Opacity%2A>属性<xref:System.Windows.Controls.Primitives.Popup>控制对其内容无效。 默认情况下，<xref:System.Windows.Controls.Primitives.Popup>内容的窗口是不透明。 若要创建一个透明<xref:System.Windows.Controls.Primitives.Popup>，将其设置<xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A>属性`true`。  
  
 内容<xref:System.Windows.Controls.Primitives.Popup>不是继承的位图效果，如<xref:System.Windows.Media.Effects.DropShadowBitmapEffect>，直接设置上<xref:System.Windows.Controls.Primitives.Popup>控件或在父窗口的任何其他元素上。 位图效果，使其出现的内容在<xref:System.Windows.Controls.Primitives.Popup>，必须设置直接对其内容的位图效果。 例如，如果的子级<xref:System.Windows.Controls.Primitives.Popup>是<xref:System.Windows.Controls.StackPanel>上, 设置的位图效果<xref:System.Windows.Controls.StackPanel>。  
  
<a name="PopupSize"></a>   
### <a name="popup-size"></a>Popup 大小  
 默认情况下，<xref:System.Windows.Controls.Primitives.Popup>对其内容自动调整大小。 由于某些位图效果时自动调整大小后，可能被隐藏为定义的屏幕区域的默认大小<xref:System.Windows.Controls.Primitives.Popup>内容不提供足够的空间要显示的位图效果。  
  
 <xref:System.Windows.Controls.Primitives.Popup> 设置时，内容可以也被遮盖<xref:System.Windows.UIElement.RenderTransform%2A>的内容。 如果某些内容可能隐藏在此方案中，转换后的内容<xref:System.Windows.Controls.Primitives.Popup>超出的原始区域<xref:System.Windows.Controls.Primitives.Popup>。 如果位图效果或转换需要更多空间，则可以定义边距<xref:System.Windows.Controls.Primitives.Popup>内容以便为控件提供更多的区域。  
  
<a name="DefiningPopupPosition"></a>   
## <a name="defining-the-popup-position"></a>定义 Popup 位置  
 您可以通过设置定位一个弹出窗口<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>， <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>， <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>， <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>，和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty>属性。 有关详细信息，请参阅 [Popup 放置行为](../../../../docs/framework/wpf/controls/popup-placement-behavior.md)。 当<xref:System.Windows.Controls.Primitives.Popup>显示在屏幕上，它不会重新本身如果其父重新定位。  
  
<a name="CustomizingPopupPlacement"></a>   
### <a name="customizing-popup-placement"></a>自定义 Popup 放置  
 你可以自定义的放置<xref:System.Windows.Controls.Primitives.Popup>通过指定的坐标，相对于一组控件<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>想在其中<xref:System.Windows.Controls.Primitives.Popup>显示。  
  
 若要自定义放置，设置<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>。 然后定义<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>返回一组的可能放置点和主轴 （按首选项的顺序） 的委托<xref:System.Windows.Controls.Primitives.Popup>。 显示的最大一部分的点<xref:System.Windows.Controls.Primitives.Popup>自动选择。 有关示例，请参阅[指定自定义 Popup 位置](../../../../docs/framework/wpf/controls/how-to-specify-a-custom-popup-position.md)。  
  
<a name="PopupandtheVisualTree"></a>   
## <a name="popup-and-the-visual-tree"></a>Popup 和可视化树  
 A<xref:System.Windows.Controls.Primitives.Popup>控件不具有其自己的可视化树; 它而是返回大小为 0 （零） 时<xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A>方法<xref:System.Windows.Controls.Primitives.Popup>调用。 但是，当设置<xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A>属性<xref:System.Windows.Controls.Primitives.Popup>到`true`，创建一个具有其自己的可视化树新窗口。 新窗口包含<xref:System.Windows.Controls.Primitives.Popup.Child%2A>内容的<xref:System.Windows.Controls.Primitives.Popup>。 新窗口的宽度和高度不能超过屏幕宽度或高度的 75%。  
  
 <xref:System.Windows.Controls.Primitives.Popup>控制保留的引用其<xref:System.Windows.Controls.Primitives.Popup.Child%2A>内容作为一个逻辑子级。 在创建新的窗口中，内容<xref:System.Windows.Controls.Primitives.Popup>成为窗口的可视子并且仍保持的逻辑子级<xref:System.Windows.Controls.Primitives.Popup>。 相反，<xref:System.Windows.Controls.Primitives.Popup>保持的逻辑父级其<xref:System.Windows.Controls.Primitives.Popup.Child%2A>内容。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Primitives.Popup>  
 <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>  
 <xref:System.Windows.Controls.Primitives.PlacementMode>  
 <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>  
 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [帮助主题](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)  
 [帮助主题](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
