---
title: "对象生存期事件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e31997cfc1ff7500317bdfc59ac6ad12d3d27a23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="object-lifetime-events"></a>对象生存期事件
本主题介绍表示对象生存期（创建、使用和销毁）中的阶段的特定 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 事件。  
  

  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>先决条件  
 本主题假设你作为 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 类的现有依赖属性的使用者已经对依赖属性有所了解，并且已经阅读了[依赖属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)主题。 若要理解本主题中的示例，还应当了解 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]（请参阅 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)）并知道如何编写 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序。  
  
<a name="intro"></a>   
## <a name="object-lifetime-events"></a>对象生存期事件  
 [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] 托管代码中的所有对象都要经历类似的一系列生命阶段，即创建、使用和销毁。 许多对象还包括生命终止阶段，该阶段属于销毁阶段的一部分。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 对象（更明确的说，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 标识为元素的视觉对象）还具有对象生命的一系列常见阶段。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 编程和应用程序模型将这些阶段作为一系列事件公开。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中有四种与生存期事件有关的主要类型对象 - 即常规元素、窗口元素、导航宿主和应用程序对象。 窗口和导航宿主也都属于视觉对象（元素）这个较大的组。 本主题首先介绍所有元素的通用生存期事件，然后介绍应用于应用程序定义、窗口或导航宿主的更具针对性的生存期事件。  
  
<a name="common_events"></a>   
## <a name="common-lifetime-events-for-elements"></a>元素通用生存期事件  
 任何 WPF 框架级别元素 (从派生的那些对象<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>) 具有三个常见的生存期事件： <xref:System.Windows.FrameworkElement.Initialized>， <xref:System.Windows.FrameworkElement.Loaded>，和<xref:System.Windows.FrameworkElement.Unloaded>。  
  
### <a name="initialized"></a>Initialized  
 <xref:System.Windows.FrameworkElement.Initialized>首先，会出现，并且大致对应给其构造函数调用的对象的初始化。 由于事件为响应初始化而发生，因此可以确保对象的所有属性均已设置。 （动态资源或绑定等表达式用法除外；这些是不进行计算的表达式。）由于所有属性均都设置的序列的要求<xref:System.Windows.FrameworkElement.Initialized>所引起标记中定义的嵌套元素似乎首先，将按顺序的元素树中最深元素发生然后父直至根元素。 采用此顺序是鉴于父子关系和包容均为属性，因此在填充属性的子元素完全初始化前，父元素无法报告初始化。  
  
 当你正在编写处理程序以响应<xref:System.Windows.FrameworkElement.Initialized>事件，你必须考虑是否有是否解决附加处理程序元素树 （逻辑树或可视化树） 中的所有其他元素已创建，尤其是不能保证父元素。 成员变量可能为 null，或者基础绑定还未填充数据源（即使在表达式级别）。  
  
### <a name="loaded"></a>已加载  
 <xref:System.Windows.FrameworkElement.Loaded>接下来引发。 <xref:System.Windows.FrameworkElement.Loaded>之前的最终呈现，但在该布局系统具有计算呈现所有所需值之后，将引发事件。 <xref:System.Windows.FrameworkElement.Loaded>需要的逻辑树的元素包含在已完成，并且连接到演示文稿源提供 HWND 和呈现图面。 标准数据绑定 （绑定到本地源，例如其他属性或直接定义的数据源） 将发生之前<xref:System.Windows.FrameworkElement.Loaded>。 可能已发生异步数据绑定（外部或动态源），但是根据其异步特性的定义不能保证已发生异步数据绑定。  
  
 所依据的机制<xref:System.Windows.FrameworkElement.Loaded>引发事件不同于<xref:System.Windows.FrameworkElement.Initialized>。 <xref:System.Windows.FrameworkElement.Initialized>事件是由元素，而无需完成的元素树直接协调引发的元素。 与此相反，<xref:System.Windows.FrameworkElement.Loaded>整个元素树 （具体而言，逻辑树） 协调的结果引发事件。 当在树中的所有元素都均未处于加载，它们都将被视为的状态<xref:System.Windows.FrameworkElement.Loaded>事件第一次发生在根元素上。 <xref:System.Windows.FrameworkElement.Loaded>然后每个子元素上连续引发事件。  
  
> [!NOTE]
>  这种行为看起来可能类似于路由事件的隧道。 但是，未将任何信息在事件之间传送。 每个元素始终有机会处理其<xref:System.Windows.FrameworkElement.Loaded>事件，并标记为已处理的事件数据不起作用超出该元素。  
  
### <a name="unloaded"></a>已卸载  
 <xref:System.Windows.FrameworkElement.Unloaded>上次引发，并可由的演示文稿源或正在删除的可视父级。 当<xref:System.Windows.FrameworkElement.Unloaded>将引发并处理，是事件源父元素 (由<xref:System.Windows.FrameworkElement.Parent%2A>属性) 或向上中逻辑或视觉对象树的任何给定的元素可能已经被取消设置，这意味着该数据绑定，资源引用和样式不能设置为其正常或最后一个已知的运行时间值。  
  
<a name="application_model_elements"></a>   
## <a name="lifetime-events-application-model-elements"></a>生存期事件应用程序模型元素  
 为元素都是以下应用程序模型元素上的常见的生存期事件生成： <xref:System.Windows.Application>， <xref:System.Windows.Window>， <xref:System.Windows.Controls.Page>， <xref:System.Windows.Navigation.NavigationWindow>，和<xref:System.Windows.Controls.Frame>。 这些与特定用途相关的额外事件扩充了常见的生存期事件。 将在以下位置详细介绍这些内容：  
  
-   <xref:System.Windows.Application>:[应用程序管理概述](../../../../docs/framework/wpf/app-development/application-management-overview.md)。  
  
-   <xref:System.Windows.Window>: [WPF Windows 概述](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md)。  
  
-   <xref:System.Windows.Controls.Page><xref:System.Windows.Navigation.NavigationWindow>，和<xref:System.Windows.Controls.Frame>:[导航概述](../../../../docs/framework/wpf/app-development/navigation-overview.md)。  
  
## <a name="see-also"></a>另请参阅  
 [依赖项属性值优先级](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)  
 [路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
