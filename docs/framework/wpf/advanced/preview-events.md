---
title: 预览事件
ms.date: 03/30/2017
helpviewer_keywords:
- Preview events [WPF]
- suppressing events [WPF]
- events [WPF], Preview
- events [WPF], suppressing
ms.assetid: b5032308-aa9c-4d02-af11-630ecec8df7e
ms.openlocfilehash: 2d6c1ab32cb43730af2f935f4bd4405059994c12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="preview-events"></a>预览事件
预览事件，也称为隧道事件，是路由的事件的路由的方向从应用程序根的元素，引发事件并报告为事件数据中的源的传输其中。 并非所有事件方案支持或要求预览事件;本主题介绍其中预览事件存在时，应用程序或组件应如何处理它们，情况和采用的情况下可能适合在自定义组件或类中创建预览事件。  
  
## <a name="preview-events-and-input"></a>预览事件和输入  
 在处理事件时一般情况下，应该格外谨慎的预览时将标记事件在事件中处理数据。 引发它 （报告为中的事件数据的源的元素） 的元素而不处理任何元素上的预览事件具有使得元素没有机会处理产生的事件的效果。 有时这是所需的结果，尤其是所涉及的元素存在于在该控件的组合中的关系。  
  
 输入事件具体而言，预览事件还具有事件数据实例等效冒泡事件。 如果使用预览版事件类处理程序将处理该输入的事件标记，将不会调用冒泡输入的事件类处理程序。 或者，如果使用预览版事件实例处理程序将处理该事件标记，冒泡事件的处理将不通常会调用。 可以注册或附加的选项要调用即使事件被标记为已处理，但该方法不常用于处理程序类或实例处理程序。  
  
 有关类处理和它如何与预览事件相关的详细信息请参阅[标记作为 Handled，和类处理的路由事件](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)。  
  
### <a name="working-around-event-suppression-by-controls"></a>通过控件解决事件禁止问题  
 通常用于预览事件的一个方案适用于复合控件处理输入事件。 有时，该控件的作者禁止显示中的某些事件可能是为了替换具备更多信息或意味着更具体的行为的组件定义事件源自其控件。 例如， [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.Button>取消<xref:System.Windows.UIElement.MouseLeftButtonDown>和<xref:System.Windows.UIElement.MouseLeftButtonDown>引发事件，冒泡<xref:System.Windows.Controls.Button>或复合元素捕获鼠标并引发为支持<xref:System.Windows.Controls.Primitives.ButtonBase.Click>始终由引发的事件<xref:System.Windows.Controls.Button>本身。 事件和其数据仍继续沿路由，但是，由于<xref:System.Windows.Controls.Button>标记形式的事件数据<xref:System.Windows.RoutedEventArgs.Handled%2A>，仅专门指示它们应中处理事件的处理`handledEventsToo`调用用例。  如果向你的应用程序的根目录的其他元素仍想要处理控件抑制的事件的机会，一个替代方法是将在代码中使用的处理程序附加`handledEventsToo`指定为`true`。 但通常更简单的技术是更改处理输入事件的预览等效的路由方向。 例如，如果控件禁止<xref:System.Windows.UIElement.MouseLeftButtonDown>，请尝试附加的处理程序<xref:System.Windows.UIElement.PreviewMouseLeftButtonDown>相反。 此方法仅适用于基元素输入事件例如<xref:System.Windows.UIElement.MouseLeftButtonDown>。 这些输入的事件使用隧道/气泡对、 引发两个事件和共享的事件数据。  
  
 上述每种方法具有负面影响或限制。 处理预览事件的副作用是在该点处理事件可能会禁用希望处理该冒泡事件的处理程序，并因此的限制是，它通常是不标记为已处理仍在 Previ 上时一个好办法新的路由的部分。 限制`handledEventsToo`种方法是，不能指定`handledEventsToo`中的处理程序[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]作为属性，你必须注册事件处理程序代码中获取对元素的对象引用该处理程序是其中要附加后。  
  
## <a name="see-also"></a>请参阅  
 [将路由事件标记为“已处理”和“类处理”](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
