---
title: 处理中的事件 Visual Basic
ms.date: 03/30/2017
helpviewer_keywords:
- Visual Basic [WPF], event handlers
- event handlers [WPF], Visual Basic
ms.assetid: ad4eb9aa-3afc-4a71-8cf6-add3fbea54a1
ms.openlocfilehash: 959ef66f41f6c5f06e18a202109fba058c522d1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735405"
---
# <a name="visual-basic-and-wpf-event-handling"></a>Visual Basic 和 WPF 事件处理
具体而言，对于 Microsoft Visual Basic .NET 语言，你可以使用特定于语言的 `Handles` 关键字将事件处理程序与实例关联，而不是将事件处理程序附加到特性或使用 <xref:System.Windows.UIElement.AddHandler%2A> 方法。 但是，用于将处理程序附加到实例的 `Handles` 技术存在一些限制，因为 `Handles` 语法不支持 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 事件系统的某些特定路由事件功能。  
  
## <a name="using-handles-in-a-wpf-application"></a>在 WPF 应用程序中使用“Handles”  
 通过 `Handles` 连接到实例和事件的事件处理程序必须全部在实例的分部类声明中定义，此要求也适用于通过元素上的特性值进行分配的事件处理程序。 只能为页面上具有 <xref:System.Windows.FrameworkContentElement.Name%2A> 属性值（或声明了[X：Name 指令](../../../desktop-wpf/xaml-services/xname-directive.md)）的元素指定 `Handles`。 这是因为 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的 <xref:System.Windows.FrameworkContentElement.Name%2A> 会创建支持实例所必需的实例引用。 `Handles` 语法要求的*事件*引用格式。 唯一可用于没有 <xref:System.Windows.FrameworkContentElement.Name%2A> 引用的 `Handles` 元素是用于定义分部类的根元素实例。  
  
 可以通过使用逗号分隔 `Handles` 后面的 Instance.Event 引用，向多个元素分配相同的处理程序。  
  
 可以使用 `Handles` 将多个处理程序分配给同一 Instance.Event 引用。 请勿对 `Handles` 引用中特定处理程序的提供顺序赋予任何重要性；应假定可按任何顺序调用处理相同事件的处理程序。  
  
 若要删除在声明中使用 `Handles` 添加的处理程序，可以调用 <xref:System.Windows.UIElement.RemoveHandler%2A>。  
  
 如果要将处理程序附加到实例成员表中用于定义要处理的事件的实例，可使用 `Handles` 附加路由事件的处理程序。 对于路由事件，与 `Handles` 一起附加的处理程序遵循的路由规则与作为 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 属性附加的处理程序相同，或与 <xref:System.Windows.UIElement.AddHandler%2A>的通用签名相同。 这意味着，如果事件已标记为已处理（事件数据中的 <xref:System.Windows.RoutedEventArgs.Handled%2A> 属性为 `True`），则不会调用与 `Handles` 一起附加的处理程序来响应该事件实例。 可通过路由中另一个元素上的实例处理程序，或通过在路由中当前元素或更早元素上进行类处理，将事件标记为已处理。 对于可支持成对的隧道事件/冒泡事件的输入事件，隧道路由可能已将事件对标记为已处理。 有关路由事件的详细信息，请参阅[路由事件概述](routed-events-overview.md)。  
  
## <a name="limitations-of-handles-for-adding-handlers"></a>添加处理程序时的“Handles”限制  
 `Handles` 无法引用附加事件的处理程序。 必须对该附加事件使用 `add` 访问方法，或使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的 typename.eventname事件特性。 有关详细信息，请参阅[路由事件概述](routed-events-overview.md)。  
  
 对于路由事件，只能使用 `Handles` 为实例成员表中存在该事件的实例分配处理程序。 但是，对于一般的路由事件，父元素可以是来自子元素的事件的侦听器，即使该父元素的成员表中没有此事件也是如此。 在特性语法中，这可以通过 typename.membername 特性形式来指定，此形式限定哪种类型实际定义要处理的事件。 例如，未定义任何 `Click` 事件的父 `Page` 可以通过以 `Button.Click`形式分配属性处理程序来侦听按钮单击事件。 但 `Handles` 不支持 typename.membername 形式，因为它必须支持与该形式冲突的 Instance.Event 形式。 有关详细信息，请参阅[路由事件概述](routed-events-overview.md)。  
  
 `Handles` 无法附加针对标记为已处理的事件而调用的处理程序。 相反，您必须使用代码并调用 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>的 `handledEventsToo` 重载。  
  
> [!NOTE]
> 在 XAML 中为同一事件指定事件处理程序时，请不要在 Visual Basic 代码中使用 `Handles` 语法。 在这种情况下，将调用事件处理程序两次。  
  
## <a name="how-wpf-implements-handles-functionality"></a>WPF 如何实现“Handles”功能  
 `Friend` `WithEvents` <xref:System.Windows.FrameworkContentElement.Name%2A> 编译页面时, 中间文件声明对页面上设置了属性 (或声明了 [x:Name](../../../desktop-wpf/xaml-services/xname-directive.md) 指令) 的每个元素的引用。 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 每个命名实例都可能是可通过 `Handles` 分配给处理程序的元素。  
  
> [!NOTE]
> 在 Visual Studio 中，IntelliSense 可向你显示哪些元素可用于页面中 `Handles` 引用。 但是，这可能需要执行一个编译传递，以便中间文件可以填充所有 `Friends` 引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.UIElement.AddHandler%2A>
- [将路由事件标记为“已处理”和“类处理”](marking-routed-events-as-handled-and-class-handling.md)
- [路由事件概述](routed-events-overview.md)
- [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
