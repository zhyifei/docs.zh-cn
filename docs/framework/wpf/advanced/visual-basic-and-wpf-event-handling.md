---
title: "Visual Basic 和 WPF 事件处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Basic [WPF], event handlers
- event handlers [WPF], Visual Basic
ms.assetid: ad4eb9aa-3afc-4a71-8cf6-add3fbea54a1
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed10e52c59112714a500fe52ccf5b398c14a97b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="visual-basic-and-wpf-event-handling"></a>Visual Basic 和 WPF 事件处理
有关[!INCLUDE[TLA#tla_visualbnet](../../../../includes/tlasharptla-visualbnet-md.md)]语言具体而言，可以使用特定于语言的`Handles`实例，而不是附加的属性的事件处理程序或使用与关联事件处理程序关键字<xref:System.Windows.UIElement.AddHandler%2A>方法。 但是，用于将处理程序附加到实例的 `Handles` 技术存在一些限制，因为 `Handles` 语法不支持 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 事件系统的某些特定路由事件功能。  
  
## <a name="using-handles-in-a-wpf-application"></a>在 WPF 应用程序中使用“Handles”  
 通过 `Handles` 连接到实例和事件的事件处理程序必须全部在实例的分部类声明中定义，此要求也适用于通过元素上的特性值进行分配的事件处理程序。 你只能指定`Handles`具有的页面上的元素<xref:System.Windows.FrameworkContentElement.Name%2A>属性值 (或[X:name 指令](../../../../docs/framework/xaml-services/x-name-directive.md)声明)。 这是因为<xref:System.Windows.FrameworkContentElement.Name%2A>中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]创建是支持所需的实例引用*实例.事件*所需的引用格式`Handles`语法。 可用于的唯一元素`Handles`而无需<xref:System.Windows.FrameworkContentElement.Name%2A>引用是定义分部类的根元素实例。  
  
 可以通过使用逗号分隔 `Handles` 后面的 Instance.Event 引用，向多个元素分配相同的处理程序。  
  
 可以使用 `Handles` 将多个处理程序分配给同一 Instance.Event 引用。 请勿对 `Handles` 引用中特定处理程序的提供顺序赋予任何重要性；应假定可按任何顺序调用处理相同事件的处理程序。  
  
 若要删除的处理程序添加了与`Handles`在声明中，你可以调用<xref:System.Windows.UIElement.RemoveHandler%2A>。  
  
 如果要将处理程序附加到实例成员表中用于定义要处理的事件的实例，可使用 `Handles` 附加路由事件的处理程序。 路由事件处理程序与连接`Handles`一样作为附加的处理程序遵循相同的路由规则[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]属性，或使用的公用签名<xref:System.Windows.UIElement.AddHandler%2A>。 这意味着，如果事件已标记为已处理 (<xref:System.Windows.RoutedEventArgs.Handled%2A>事件数据中的属性是`True`)，然后处理程序与连接`Handles`不在响应该事件实例中调用。 可通过路由中另一个元素上的实例处理程序，或通过在路由中当前元素或更早元素上进行类处理，将事件标记为已处理。 对于可支持成对的隧道事件/冒泡事件的输入事件，隧道路由可能已将事件对标记为已处理。 有关路由事件的详细信息，请参阅[路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)。  
  
## <a name="limitations-of-handles-for-adding-handlers"></a>添加处理程序时的“Handles”限制  
 `Handles` 无法引用附加事件的处理程序。 必须对该附加事件使用 `add` 访问方法，或使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的 typename.eventname 事件特性。 有关详细信息，请参阅[路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)。  
  
 对于路由事件，只能使用 `Handles` 为实例成员表中存在该事件的实例分配处理程序。 但是，对于一般的路由事件，父元素可以是来自子元素的事件的侦听器，即使该父元素的成员表中没有此事件也是如此。 在特性语法中，这可以通过 typename.membername 特性形式来指定，此形式限定哪种类型实际定义要处理的事件。 例如，父`Page`(不带`Click`定义的事件) 可以通过分配窗体中的属性处理程序侦听的按钮单击事件`Button.Click`。 但 `Handles` 不支持 typename.membername 形式，因为它必须支持与该形式冲突的 Instance.Event 形式。 有关详细信息，请参阅[路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)。  
  
 `Handles` 无法附加针对标记为已处理的事件而调用的处理程序。 相反，你必须使用代码和调用`handledEventsToo`重载<xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>。  
  
> [!NOTE]
>  在 XAML 中为相同事件指定事件处理程序时，请勿在 [!INCLUDE[vb_current_short](../../../../includes/vb-current-short-md.md)] 代码中使用 `Handles` 语法。 在这种情况下，将调用事件处理程序两次。  
  
## <a name="how-wpf-implements-handles-functionality"></a>WPF 如何实现“Handles”功能  
 当[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]页已编译，中间文件声明`Friend``WithEvents`对具有的页面上的每个元素的引用<xref:System.Windows.FrameworkContentElement.Name%2A>属性集 (或[X:name 指令](../../../../docs/framework/xaml-services/x-name-directive.md)声明)。 每个命名实例都可能是可通过 `Handles` 分配给处理程序的元素。  
  
> [!NOTE]
>  在 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 中，[!INCLUDE[TLA2#tla_intellisense](../../../../includes/tla2sharptla-intellisense-md.md)] 可完整显示可用于页中的 `Handles` 引用的全部元素。 但是，这可能需要执行一个编译传递，以便中间文件可以填充所有 `Friends` 引用。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.UIElement.AddHandler%2A>  
 [将路由事件标记为“已处理”和“类处理”](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
