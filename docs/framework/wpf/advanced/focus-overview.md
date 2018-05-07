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
ms.openlocfilehash: 620839a0060469604d0affa6637c3cafac0f62c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="focus-overview"></a>焦点概述
在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中，有两个与焦点有关的主要概念：键盘焦点和逻辑焦点。  键盘焦点指接收键盘输入的元素，而逻辑焦点指焦点范围中具有焦点的元素。  本概述详细介绍了这些概念。  对于创建具有多个可获取焦点的区域的复杂应用程序来说，理解这些概念之间的区别非常重要。  
  
 参与焦点管理的主要类如下<xref:System.Windows.Input.Keyboard>类，<xref:System.Windows.Input.FocusManager>类和基元素类，如<xref:System.Windows.UIElement>和<xref:System.Windows.ContentElement>。  有关基元素的详细信息，请参阅[基元素概述](../../../../docs/framework/wpf/advanced/base-elements-overview.md)。  
  
 <xref:System.Windows.Input.Keyboard>类主要关心键盘焦点和<xref:System.Windows.Input.FocusManager>是主要关心逻辑焦点，但这不是一个绝对区别。  具有键盘焦点的元素也具有逻辑焦点，但具有逻辑焦点的元素不一定具有键盘焦点。  这是明显的当你使用<xref:System.Windows.Input.Keyboard>类来设置的元素具有键盘焦点时，它还在元素上设置逻辑焦点。  
  

  
<a name="Keyboard_Focus"></a>   
## <a name="keyboard-focus"></a>键盘焦点  
 键盘焦点指当前正在接收键盘输入的元素。  在整个桌面上，只能有一个具有键盘焦点的元素。  在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，具有键盘焦点的元素将具有<xref:System.Windows.IInputElement.IsKeyboardFocused%2A>设置为`true`。  静态属性<xref:System.Windows.Input.Keyboard.FocusedElement%2A>上<xref:System.Windows.Input.Keyboard>类获取当前具有键盘焦点的元素。  
  
 若要获取键盘焦点的元素顺序<xref:System.Windows.UIElement.Focusable%2A>和<xref:System.Windows.UIElement.IsVisible%2A>基元素的属性必须设置为`true`。  一些类，如<xref:System.Windows.Controls.Panel>基类、 具有<xref:System.Windows.UIElement.Focusable%2A>设置为`false`默认情况下; 因此，你必须设置<xref:System.Windows.UIElement.Focusable%2A>到`true`如果您希望此类元素能够获取键盘焦点。  
  
 可通过用户与 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 交互（例如，按 Tab 键导航到某个元素或者在某些元素上单击鼠标）来获取键盘焦点。  键盘焦点也可以获取以编程方式使用<xref:System.Windows.Input.Keyboard.Focus%2A>方法<xref:System.Windows.Input.Keyboard>类。  <xref:System.Windows.Input.Keyboard.Focus%2A>方法尝试将指定的元素键盘焦点给予。  返回的元素是具有键盘焦点的元素，如果旧的或新的焦点对象阻止请求，则具有键盘焦点的元素可能不是请求的元素。  
  
 下面的示例使用<xref:System.Windows.Input.Keyboard.Focus%2A>方法上设置键盘焦点<xref:System.Windows.Controls.Button>。  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 <xref:System.Windows.UIElement.IsKeyboardFocused%2A>上基元素类的属性获取一个值，该值指示元素是否具有键盘焦点。  <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>上基元素类的属性获取一个值，该值指示此元素或其可视子元素的任何一个具有键盘焦点。  
  
 当初始焦点设置在应用程序启动时, 要接收焦点的元素必须在初始加载应用程序的窗口的可视化树和元素必须具有<xref:System.Windows.UIElement.Focusable%2A>和<xref:System.Windows.UIElement.IsVisible%2A>设置为`true`。  若要设置初始焦点的建议的位置是在<xref:System.Windows.FrameworkElement.Loaded>事件处理程序。  A<xref:System.Windows.Threading.Dispatcher>回调还可通过调用<xref:System.Windows.Threading.Dispatcher.Invoke%2A>或<xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>。  
  
<a name="Logical_Focus"></a>   
## <a name="logical-focus"></a>逻辑焦点  
 逻辑焦点是指<xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType>焦点作用域中。  焦点作用域是一个元素，用于跟踪的<xref:System.Windows.Input.FocusManager.FocusedElement%2A>在其范围内。  键盘焦点离开焦点范围时，焦点元素会失去键盘焦点，但保留逻辑焦点。  键盘焦点返回到焦点范围时，焦点元素会再次获得键盘焦点。  这使得键盘焦点可在多个焦点范围之间切换，但确保了焦点返回到焦点范围时，焦点范围中的焦点元素重新获得键盘焦点。  
  
 一个应用程序中可以有多个具有逻辑焦点的元素，但在一个特定的焦点范围中只能有一个具有逻辑焦点的元素。  
  
 具有键盘焦点的元素还具有其所属焦点范围的逻辑焦点。  
  
 可以将元素转换中的焦点作用域[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]通过设置<xref:System.Windows.Input.FocusManager>附加属性<xref:System.Windows.Input.FocusManager.IsFocusScope%2A>到`true`。  在代码中，元素可转换为焦点范围通过调用<xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>。  
  
 下面的示例使<xref:System.Windows.Controls.StackPanel>转变通过设置为焦点范围<xref:System.Windows.Input.FocusManager.IsFocusScope%2A>附加属性。  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A> 返回指定元素的焦点作用域。  
  
 中的类[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]这是默认情况下的焦点作用域是<xref:System.Windows.Window>， <xref:System.Windows.Controls.MenuItem>， <xref:System.Windows.Controls.ToolBar>，和<xref:System.Windows.Controls.ContextMenu>。  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A> 为指定的焦点作用域中获取的已设定焦点的元素。  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> 指定的焦点作用域中设置的已设定焦点的元素。  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> 通常用于设置初始具有焦点的元素。  
  
 以下示例在焦点范围上设置焦点元素并获取焦点范围的焦点元素。  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>   
## <a name="keyboard-navigation"></a>键盘导航  
 <xref:System.Windows.Input.KeyboardNavigation>类负责实现默认键盘焦点导航时按下的导航键之一。  导航键包括：Tab、Shift+Tab、Ctrl+Tab、Ctrl+Shift+Tab、向上键、向下键、向左键和向右键。  
  
 可以通过设置附加更改导航容器的导航行为<xref:System.Windows.Input.KeyboardNavigation>属性<xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>， <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>，和<xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>。  这些属性属于类型<xref:System.Windows.Input.KeyboardNavigationMode>和可能的值为<xref:System.Windows.Input.KeyboardNavigationMode.Continue>， <xref:System.Windows.Input.KeyboardNavigationMode.Local>， <xref:System.Windows.Input.KeyboardNavigationMode.Contained>， <xref:System.Windows.Input.KeyboardNavigationMode.Cycle>， <xref:System.Windows.Input.KeyboardNavigationMode.Once>，和<xref:System.Windows.Input.KeyboardNavigationMode.None>。  默认值是<xref:System.Windows.Input.KeyboardNavigationMode.Continue>，这意味着该元素不是导航的容器。  
  
 下面的示例创建<xref:System.Windows.Controls.Menu>与大量的<xref:System.Windows.Controls.MenuItem>对象。  <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>附加的属性设置为<xref:System.Windows.Input.KeyboardNavigationMode.Cycle>上<xref:System.Windows.Controls.Menu>。  当使用 tab 键在更改焦点时<xref:System.Windows.Controls.Menu>，焦点会移从每个元素，在到达最后一个元素时焦点将返回到第一个元素。  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>   
## <a name="navigating-focus-programmatically"></a>以编程方式导航焦点  
 其他[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]用于焦点是<xref:System.Windows.UIElement.MoveFocus%2A>和<xref:System.Windows.UIElement.PredictFocus%2A>。  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A> 将焦点移到应用程序中的下一个元素。  A<xref:System.Windows.Input.TraversalRequest>用于指定的方向。   <xref:System.Windows.Input.FocusNavigationDirection>传递给<xref:System.Windows.UIElement.MoveFocus%2A>指定不同的方向焦点可以移动，例如<xref:System.Windows.Input.FocusNavigationDirection.First>， <xref:System.Windows.Input.FocusNavigationDirection.Last>，<xref:System.Windows.Input.FocusNavigationDirection.Up>和<xref:System.Windows.Input.FocusNavigationDirection.Down>。  
  
 下面的示例使用<xref:System.Windows.FrameworkElement.MoveFocus%2A>更改具有焦点的元素。  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A> 返回要更改焦点时，将接收焦点的对象。  目前，仅<xref:System.Windows.Input.FocusNavigationDirection.Up>， <xref:System.Windows.Input.FocusNavigationDirection.Down>， <xref:System.Windows.Input.FocusNavigationDirection.Left>，和<xref:System.Windows.Input.FocusNavigationDirection.Right>支持<xref:System.Windows.FrameworkElement.PredictFocus%2A>。  
  
<a name="Focus_Events"></a>   
## <a name="focus-events"></a>焦点事件  
 与键盘焦点相关的事件是<xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>，<xref:System.Windows.Input.Keyboard.GotKeyboardFocus>和<xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus>， <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>。  事件指附加事件上<xref:System.Windows.Input.Keyboard>类，但更易于访问作为基元素类上的等效路由事件。  有关事件的详细信息，请参阅[路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)。  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> 当元素获取键盘焦点时引发。  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus> 当在元素丢失键盘焦点时引发。  如果<xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>事件或<xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent>处理事件和<xref:System.Windows.RoutedEventArgs.Handled%2A>设置为`true`，然后焦点不会更改。  
  
 下面的示例将附加<xref:System.Windows.UIElement.GotKeyboardFocus>和<xref:System.Windows.UIElement.LostKeyboardFocus>到事件处理程序<xref:System.Windows.Controls.TextBox>。  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 当<xref:System.Windows.Controls.TextBox>获取键盘焦点时，<xref:System.Windows.Controls.Control.Background%2A>属性<xref:System.Windows.Controls.TextBox>更改为<xref:System.Windows.Media.Brushes.LightBlue%2A>。  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 当<xref:System.Windows.Controls.TextBox>失去键盘焦点时，<xref:System.Windows.Controls.Control.Background%2A>属性<xref:System.Windows.Controls.TextBox>将变回为空白。  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 与逻辑焦点相关的事件是<xref:System.Windows.UIElement.GotFocus>和<xref:System.Windows.UIElement.LostFocus>。  在中定义这些事件<xref:System.Windows.Input.FocusManager>为附加事件，但<xref:System.Windows.Input.FocusManager>未公开 CLR 事件包装器。  <xref:System.Windows.UIElement> 和<xref:System.Windows.ContentElement>更方便地公开这些事件。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Input.FocusManager>  
 <xref:System.Windows.UIElement>  
 <xref:System.Windows.ContentElement>  
 [输入概述](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [基元素概述](../../../../docs/framework/wpf/advanced/base-elements-overview.md)
