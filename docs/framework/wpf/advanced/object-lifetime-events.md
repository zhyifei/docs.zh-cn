---
title: 对象生存期事件
ms.date: 03/30/2017
helpviewer_keywords:
- events [WPF], ContentRendered
- events [WPF], Deactivated
- events [WPF], Unloaded
- Activated events [WPF]
- events [WPF], Loaded
- Application objects [WPF], lifetime events
- events [WPF], Activated
- ContentRendered events [WPF]
- Deactivated events [WPF]
- events [WPF], Initialized
- events [WPF], Closing
- Unloaded events [WPF]
- exit events [WPF]
- objects' lifetime events [WPF]
- Loaded events [WPF]
- Closing events [WPF]
- events [WPF], Closed
- Initialized events [WPF]
- Closed events [WPF]
- startup events [WPF]
- lifetime events of objects [WPF]
ms.assetid: face6fc7-465b-4502-bfe5-e88d2e729a78
ms.openlocfilehash: 3b761674bd2464ee87e07d9299c805431f8fdeb7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141102"
---
# <a name="object-lifetime-events"></a>对象生存期事件
本主题介绍表示对象生存期（创建、使用和销毁）中的阶段的特定 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 事件。  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>系统必备  
 本主题假设你作为 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 类的现有依赖属性的使用者已经对依赖属性有所了解，并且已经阅读了[依赖属性概述](dependency-properties-overview.md)主题。 若要理解本主题中的示例，还应当了解 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]（请参阅 [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)）并知道如何编写 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序。  
  
<a name="intro"></a>
## <a name="object-lifetime-events"></a>对象生存期事件  
 Microsoft .NET 框架托管代码中的所有对象都经历一组类似的生命周期、创建、使用和销毁阶段。 许多对象还包括生命终止阶段，该阶段属于销毁阶段的一部分。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 对象（更明确的说，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 标识为元素的视觉对象）还具有对象生命的一系列常见阶段。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 编程和应用程序模型将这些阶段作为一系列事件公开。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中有四种与生存期事件有关的主要类型对象 - 即常规元素、窗口元素、导航宿主和应用程序对象。 窗口和导航宿主也都属于视觉对象（元素）这个较大的组。 本主题首先介绍所有元素的通用生存期事件，然后介绍应用于应用程序定义、窗口或导航宿主的更具针对性的生存期事件。  
  
<a name="common_events"></a>
## <a name="common-lifetime-events-for-elements"></a>元素通用生存期事件  
 任何 WPF 框架级元素（从<xref:System.Windows.FrameworkElement>任一或<xref:System.Windows.FrameworkContentElement>派生的对象）都有三个常见的生存<xref:System.Windows.FrameworkElement.Initialized>期<xref:System.Windows.FrameworkElement.Loaded>事件：<xref:System.Windows.FrameworkElement.Unloaded>和 。  
  
### <a name="initialized"></a>Initialized  
 <xref:System.Windows.FrameworkElement.Initialized>首先引发，并且大致对应于对象的初始化，由调用其构造函数。 由于事件为响应初始化而发生，因此可以确保对象的所有属性均已设置。 （一个例外是表达式用法，如动态资源或绑定;这些表达式将是未计算的表达式。由于要求设置所有属性，标记中定义的嵌套元素的引发顺序<xref:System.Windows.FrameworkElement.Initialized>似乎首先以元素树中最深的元素的顺序发生，然后是父元素对根的顺序。 采用此顺序是鉴于父子关系和包容均为属性，因此在填充属性的子元素完全初始化前，父元素无法报告初始化。  
  
 编写处理程序以响应<xref:System.Windows.FrameworkElement.Initialized>事件时，必须考虑不能保证元素树中附加处理程序的所有其他元素（逻辑树或可视化树）已创建处理程序，尤其是父元素。 成员变量可能为 null，或者基础绑定还未填充数据源（即使在表达式级别）。  
  
### <a name="loaded"></a>已加载  
 <xref:System.Windows.FrameworkElement.Loaded>下次引发。 事件<xref:System.Windows.FrameworkElement.Loaded>在最终渲染之前引发，但在布局系统计算了渲染所需的所有值之后。 <xref:System.Windows.FrameworkElement.Loaded>需要元素中包含的逻辑树已完成，并连接到提供 HWND 和呈现曲面的表示源。 标准数据绑定（绑定到本地源，如其他属性或直接定义的数据源）将在<xref:System.Windows.FrameworkElement.Loaded>之前发生。 可能已发生异步数据绑定（外部或动态源），但是根据其异步特性的定义不能保证已发生异步数据绑定。  
  
 引发<xref:System.Windows.FrameworkElement.Loaded>事件的机制与<xref:System.Windows.FrameworkElement.Initialized>不同。 事件<xref:System.Windows.FrameworkElement.Initialized>按元素引发，无需由已完成的元素树直接协调。 相反，事件<xref:System.Windows.FrameworkElement.Loaded>在整个元素树（特别是逻辑树）中作为协调工作提出。 当树中的所有元素都处于被视为加载状态时，首先在<xref:System.Windows.FrameworkElement.Loaded>根元素上引发该事件。 然后<xref:System.Windows.FrameworkElement.Loaded>，在每个子元素上依次引发该事件。  
  
> [!NOTE]
> 这种行为看起来可能类似于路由事件的隧道。 但是，未将任何信息在事件之间传送。 每个元素始终有机会处理其<xref:System.Windows.FrameworkElement.Loaded>事件，并将事件数据标记为已处理，除了该元素之外，没有任何效果。  
  
### <a name="unloaded"></a>已卸载  
 <xref:System.Windows.FrameworkElement.Unloaded>上次引发，由要删除的表示源或可视父级启动。 引发<xref:System.Windows.FrameworkElement.Unloaded>和处理时，作为事件源父元素的元素（由<xref:System.Windows.FrameworkElement.Parent%2A>属性确定）或逻辑或可视化树中向上的任何给定元素可能已取消设置，这意味着数据绑定、资源引用和样式可能未设置为其正常或最后已知的运行时值。  
  
<a name="application_model_elements"></a>
## <a name="lifetime-events-application-model-elements"></a>生存期事件应用程序模型元素  
 基于元素的常见生存期事件，下面是以下应用程序模型<xref:System.Windows.Application>元素： 、 <xref:System.Windows.Window> <xref:System.Windows.Controls.Page>、<xref:System.Windows.Navigation.NavigationWindow>和<xref:System.Windows.Controls.Frame>。 这些与特定用途相关的额外事件扩充了常见的生存期事件。 将在以下位置详细介绍这些内容：  
  
- <xref:System.Windows.Application>：[应用程序管理概述](../app-development/application-management-overview.md)。  
  
- <xref:System.Windows.Window>[：WPF 窗口概述](../app-development/wpf-windows-overview.md)。  
  
- <xref:System.Windows.Controls.Page>、<xref:System.Windows.Navigation.NavigationWindow>和<xref:System.Windows.Controls.Frame>：[导航概述](../app-development/navigation-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- [依赖项属性值优先级](dependency-property-value-precedence.md)
- [路由事件概述](routed-events-overview.md)
