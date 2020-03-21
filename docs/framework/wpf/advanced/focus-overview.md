---
title: 焦点概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], focus
- focus in applications [WPF]
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
ms.openlocfilehash: de788ec3f0628ff2f7c422c76c73ff7985424113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186672"
---
# <a name="focus-overview"></a>焦点概述
在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中，有两个与焦点有关的主要概念：键盘焦点和逻辑焦点。  键盘焦点指接收键盘输入的元素，而逻辑焦点指焦点范围中具有焦点的元素。  本概述详细介绍了这些概念。  对于创建具有多个可获取焦点的区域的复杂应用程序来说，理解这些概念之间的区别非常重要。  
  
 参与焦点<xref:System.Windows.Input.Keyboard>管理的主要类是类、<xref:System.Windows.Input.FocusManager>类和基元素类，如<xref:System.Windows.UIElement>和<xref:System.Windows.ContentElement>。  有关基元素的详细信息，请参阅[基元素概述](base-elements-overview.md)。  
  
 类<xref:System.Windows.Input.Keyboard>主要关注键盘焦点，主要关注逻辑焦点，<xref:System.Windows.Input.FocusManager>但这不是绝对的区别。  具有键盘焦点的元素也具有逻辑焦点，但具有逻辑焦点的元素不一定具有键盘焦点。  当您使用<xref:System.Windows.Input.Keyboard>类设置具有键盘焦点的元素时，这是显而易见的，因为它还会对元素设置逻辑焦点。  

<a name="Keyboard_Focus"></a>
## <a name="keyboard-focus"></a>键盘焦点  
 键盘焦点指当前正在接收键盘输入的元素。  在整个桌面上，只能有一个具有键盘焦点的元素。  在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中，具有键盘焦点的元素将<xref:System.Windows.IInputElement.IsKeyboardFocused%2A>设置为`true`。  类上的<xref:System.Windows.Input.Keyboard>静态<xref:System.Windows.Input.Keyboard.FocusedElement%2A>属性获取当前具有键盘焦点的元素。  
  
 为了使元素获得键盘焦点，必须将 基元素<xref:System.Windows.UIElement.Focusable%2A>上的<xref:System.Windows.UIElement.IsVisible%2A>和 属性设置为`true`。  默认情况下，<xref:System.Windows.Controls.Panel>某些类（如基类）已<xref:System.Windows.UIElement.Focusable%2A>设置为;`false`因此，它已设置为"基类"。因此，如果希望此类<xref:System.Windows.UIElement.Focusable%2A>元素`true`能够获得键盘焦点，则必须设置为。  
  
 可通过用户与 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 交互（例如，按 Tab 键导航到某个元素或者在某些元素上单击鼠标）来获取键盘焦点。  键盘焦点也可以使用<xref:System.Windows.Input.Keyboard.Focus%2A><xref:System.Windows.Input.Keyboard>类上的方法以编程方式获得。  该方法<xref:System.Windows.Input.Keyboard.Focus%2A>尝试为指定元素键盘焦点提供。  返回的元素是具有键盘焦点的元素，如果旧的或新的焦点对象阻止请求，则具有键盘焦点的元素可能不是请求的元素。  
  
 下面的示例使用 方法<xref:System.Windows.Input.Keyboard.Focus%2A>将键盘焦点设置为<xref:System.Windows.Controls.Button>。  
  
 [!code-csharp[focussample#FocusSampleSetFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 基<xref:System.Windows.UIElement.IsKeyboardFocused%2A>元素类上的属性获取一个值，指示该元素是否具有键盘焦点。  基<xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>元素类上的属性获取一个值，指示该元素或其任何可视子元素是否具有键盘焦点。  
  
 在应用程序启动时设置初始焦点时，接收焦点的元素必须位于应用程序加载的初始窗口的可视树中，并且该元素必须具有<xref:System.Windows.UIElement.Focusable%2A>并<xref:System.Windows.UIElement.IsVisible%2A>设置为`true`。  设置初始焦点的建议位置位于事件处理程序中<xref:System.Windows.FrameworkElement.Loaded>。  <xref:System.Windows.Threading.Dispatcher>回调也可以通过调用<xref:System.Windows.Threading.Dispatcher.Invoke%2A>或<xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>使用。  
  
<a name="Logical_Focus"></a>
## <a name="logical-focus"></a>逻辑焦点  
 逻辑焦点是指焦点范围内<xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType>的。  焦点范围是跟踪其范围内的元素<xref:System.Windows.Input.FocusManager.FocusedElement%2A>。  键盘焦点离开焦点范围时，焦点元素会失去键盘焦点，但保留逻辑焦点。  键盘焦点返回到焦点范围时，焦点元素会再次获得键盘焦点。  这使得键盘焦点可在多个焦点范围之间切换，但确保了焦点返回到焦点范围时，焦点范围中的焦点元素重新获得键盘焦点。  
  
 一个应用程序中可以有多个具有逻辑焦点的元素，但在一个特定的焦点范围中只能有一个具有逻辑焦点的元素。  
  
 具有键盘焦点的元素还具有其所属焦点范围的逻辑焦点。  
  
 通过将[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]<xref:System.Windows.Input.FocusManager>附加属性<xref:System.Windows.Input.FocusManager.IsFocusScope%2A>设置为 ，可以将元素转换为焦点范围。 `true`  在代码中，可以通过调用<xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>将 元素转换为焦点范围。  
  
 下面的示例通过设置<xref:System.Windows.Controls.StackPanel><xref:System.Windows.Input.FocusManager.IsFocusScope%2A>附加属性将 焦点范围设置为焦点范围。  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A>返回指定元素的焦点范围。  
  
 默认情况下，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]在其中作为焦点作用域的类是<xref:System.Windows.Window> <xref:System.Windows.Controls.MenuItem>、<xref:System.Windows.Controls.ToolBar>和<xref:System.Windows.Controls.ContextMenu>。  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>获取指定焦点范围的聚焦元素。  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>在指定的焦点范围内设置焦点元素。  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>通常用于设置初始焦点元素。  
  
 以下示例在焦点范围上设置焦点元素并获取焦点范围的焦点元素。  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>
## <a name="keyboard-navigation"></a>键盘导航  
 当<xref:System.Windows.Input.KeyboardNavigation>按下其中一个导航键时，该类负责实现默认键盘焦点导航。  导航键包括：Tab、Shift+Tab、Ctrl+Tab、Ctrl+Shift+Tab、向上键、向下键、向左键和向右键。  
  
 <xref:System.Windows.Input.KeyboardNavigation>可以通过设置附加<xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>属性 和<xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>来更改导航容器的导航行为。 <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>  <xref:System.Windows.Input.KeyboardNavigationMode>这些属性的类型和可能的值是<xref:System.Windows.Input.KeyboardNavigationMode.Continue>、、、、、、<xref:System.Windows.Input.KeyboardNavigationMode.Once><xref:System.Windows.Input.KeyboardNavigationMode.None><xref:System.Windows.Input.KeyboardNavigationMode.Local><xref:System.Windows.Input.KeyboardNavigationMode.Contained><xref:System.Windows.Input.KeyboardNavigationMode.Cycle>和 。  默认值为<xref:System.Windows.Input.KeyboardNavigationMode.Continue>，这意味着元素不是导航容器。  
  
 下面的示例创建具有多个<xref:System.Windows.Controls.Menu><xref:System.Windows.Controls.MenuItem>对象的 。  附加<xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>属性设置为<xref:System.Windows.Input.KeyboardNavigationMode.Cycle>。 <xref:System.Windows.Controls.Menu>  当使用 中的选项卡键更改焦点时<xref:System.Windows.Controls.Menu>，焦点将从每个元素移动，到达最后一个元素时，焦点将返回到第一个元素。  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>
## <a name="navigating-focus-programmatically"></a>以编程方式导航焦点  
 要使用焦点的其他 API<xref:System.Windows.UIElement.MoveFocus%2A>是<xref:System.Windows.UIElement.PredictFocus%2A>和 。  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A>将焦点更改为应用程序中的下一个元素。  A<xref:System.Windows.Input.TraversalRequest>用于指定方向。   <xref:System.Windows.Input.FocusNavigationDirection><xref:System.Windows.UIElement.MoveFocus%2A>传递给指定<xref:System.Windows.Input.FocusNavigationDirection.First>可以移动的不同方向焦点，例如 ，<xref:System.Windows.Input.FocusNavigationDirection.Last><xref:System.Windows.Input.FocusNavigationDirection.Up>和<xref:System.Windows.Input.FocusNavigationDirection.Down>。  
  
 下面的示例用于<xref:System.Windows.FrameworkElement.MoveFocus%2A>更改焦点元素。  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A>返回如果焦点被更改，将接收焦点的对象。  目前，只有<xref:System.Windows.Input.FocusNavigationDirection.Up> <xref:System.Windows.Input.FocusNavigationDirection.Down>、<xref:System.Windows.Input.FocusNavigationDirection.Left>和<xref:System.Windows.Input.FocusNavigationDirection.Right>受<xref:System.Windows.FrameworkElement.PredictFocus%2A>的支持。  
  
<a name="Focus_Events"></a>
## <a name="focus-events"></a>焦点事件  
 与键盘<xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>焦点相关的事件是 和<xref:System.Windows.Input.Keyboard.GotKeyboardFocus> <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus>。 <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>  事件被定义为类上的<xref:System.Windows.Input.Keyboard>附加事件，但更容易访问为基元素类上的等效路由事件。  有关事件的详细信息，请参阅[路由事件概述](routed-events-overview.md)。  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus>当元素获取键盘焦点时引发。  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>当元素失去键盘焦点时引发。  如果<xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>事件或<xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent>事件已处理并<xref:System.Windows.RoutedEventArgs.Handled%2A>设置为`true`，则焦点不会更改。  
  
 以下示例将<xref:System.Windows.UIElement.GotKeyboardFocus>和<xref:System.Windows.UIElement.LostKeyboardFocus>事件处理程序附加到<xref:System.Windows.Controls.TextBox>。  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 <xref:System.Windows.Controls.TextBox>获取键盘焦点时，<xref:System.Windows.Controls.Control.Background%2A>的属性<xref:System.Windows.Controls.TextBox>将更改为<xref:System.Windows.Media.Brushes.LightBlue%2A>。  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 当<xref:System.Windows.Controls.TextBox>失去键盘焦点时，<xref:System.Windows.Controls.Control.Background%2A>属性<xref:System.Windows.Controls.TextBox>将更改回白色。  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 与逻辑焦点相关的事件是<xref:System.Windows.UIElement.GotFocus>和<xref:System.Windows.UIElement.LostFocus>。  这些事件在 附加事件上<xref:System.Windows.Input.FocusManager>定义，但不会<xref:System.Windows.Input.FocusManager>公开 CLR 事件包装器。  <xref:System.Windows.UIElement>并<xref:System.Windows.ContentElement>更方便地公开这些事件。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Input.FocusManager>
- <xref:System.Windows.UIElement>
- <xref:System.Windows.ContentElement>
- [输入概述](input-overview.md)
- [基元素概述](base-elements-overview.md)
