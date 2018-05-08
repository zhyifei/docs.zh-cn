---
title: 如何：为路由事件添加类处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
ms.openlocfilehash: 85c3491c9035d807b4c654659a8641121bb5709f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a>如何：为路由事件添加类处理
通过类处理程序或路线中的任何给定节点上的实例处理程序，可以处理路由的事件。 首先，调用和类的实现可以使用取消实例处理的事件，或引入其他事件所拥有的基类的事件的特定行为的类处理。 此示例阐释用来实现类处理程序的两个密切相关的技术。  
  
## <a name="example"></a>示例  
 此示例使用自定义类基于<xref:System.Windows.Controls.Canvas>面板。 应用程序的基本前提是自定义类引入了对其子元素，包括截获任何鼠标左键单击并标记它们的处理，然后将调用的子元素类或在其上的任何实例处理行为。  
  
 <xref:System.Windows.UIElement>类公开一个虚拟方法，使类上处理<xref:System.Windows.UIElement.PreviewMouseLeftButtonDown>事件，只需重写该事件。 这是你的类层次结构中的某个位置可用这样的虚方法是否实现类处理的最简单方法。 下面的代码演示<xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A>派生自"MyEditContainer"中的实现<xref:System.Windows.Controls.Canvas>。 实现将事件标记为参数，处理，然后添加某些代码来提供基本明显的变化的源元素。  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 如果任何虚拟基类上或针对该特定的方法可用，可以直接使用的实用程序方法添加类处理<xref:System.Windows.EventManager>类， <xref:System.Windows.EventManager.RegisterClassHandler%2A>。 仅应要添加类处理的类的静态初始化内部调用此方法。 此示例将添加另一个处理程序<xref:System.Windows.UIElement.PreviewMouseLeftButtonDown>，并且在这种情况下为注册的类自定义类。 与此相反，使用虚方法，已注册的类时，实际上<xref:System.Windows.UIElement>基类。 在基的类和子类每个在其中注册类处理的情况下，首先调用子类处理程序。 在应用程序行为将是，此处理程序将首先显示其消息框，然后将显示了虚拟方法的处理程序中的可视化变更。  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.EventManager>  
 [将路由事件标记为“已处理”和“类处理”](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [处理路由事件](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)  
 [路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
