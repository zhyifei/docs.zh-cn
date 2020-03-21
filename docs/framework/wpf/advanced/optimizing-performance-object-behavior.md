---
title: 优化性能：对象行为
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user interface virtualization [WPF]
- dependency properties [WPF], performance
- event handlers [WPF]
- object performance considerations [WPF]
- Freezable objects [WPF], performance
ms.assetid: 73aa2f47-1d73-439a-be1f-78dc4ba2b5bd
ms.openlocfilehash: 67184db7fc1459e83ac7b1e6ff09ef56e43f0ca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187078"
---
# <a name="optimizing-performance-object-behavior"></a>优化性能：对象行为
了解 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 对象的内部行为，有助于在功能和性能之间做出适当的取舍。  

<a name="Not_Removing_Event_Handlers"></a>
## <a name="not-removing-event-handlers-on-objects-may-keep-objects-alive"></a>不删除对象的事件处理程序可能会使对象保持活动状态  
 对象传递给其事件的委托是对该对象的有效引用。 因此，事件处理程序可以使对象保持活动状态的时间超过预期时间。 当对已注册为侦听对象事件的对象执行清理时，在释放对象前删除委托是非常必要的。 将不需要的对象保持为活动状态会增加应用程序的内存使用量。 在对象为逻辑树或可视化树的根时更是如此。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 为事件引入了弱事件侦听器模式，在很难跟踪源和侦听器之间的对象生存期关系时，这种模式特别有用。 某些现有 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 事件使用此模式。 如果要实现具有自定义事件的对象，此模式可能会有用。 有关详细信息，请参阅[弱事件模式](weak-event-patterns.md)。  
  
 有若干工具（如 CLR 探查器和工作集查看器）可以提供有关指定进程的内存使用量的信息。 CLR 探查器包括分配配置文件的许多非常有用的视图，其中包括已分配类型的直方图、分配和调用关系图、显示各代垃圾回收及上述回收之后托管堆的生成状态的时间线，以及显示每个方法分配和程序集加载的调用树。 有关更多信息，请参阅[性能](https://docs.microsoft.com/previous-versions/aa497289(v=msdn.10))。  
  
<a name="DPs_and_Objects"></a>
## <a name="dependency-properties-and-objects"></a>依赖属性和对象  
 通常，访问 的依赖<xref:System.Windows.DependencyObject>项属性不会比访问 CLR 属性慢。 虽然设置属性值的性能开销很小，但获取值的速度与从 CLR 属性获取值的速度一样快。 抵销一些小的性能开销是因为依赖属性支持可靠的功能，如数据绑定、动画、继承和样式设置。 有关详细信息，请参阅[依赖项属性概述](dependency-properties-overview.md)。  
  
### <a name="dependencyproperty-optimizations"></a>DependencyProperty 优化  
 在应用程序中定义依赖属性时请务必谨慎。 如果<xref:System.Windows.DependencyProperty>影响仅影响呈现类型元数据选项，而不是其他元数据选项（如<xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>），则应通过重写其元数据来标记它。 有关替代或获取属性元数据的详细信息，请参阅[依赖属性元数据](dependency-property-metadata.md)。  
  
 如果并非所有属性更改都会影响测量、排列和呈现，则通过属性更改处理程序手动使测量、排列和呈现阶段无效的做法可能会更高效。 例如，你可能决定仅在值大于设置限制时才重新呈现背景。 在这种情况下，值超过设置限制时，属性更改处理程序仅会使呈现无效。  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>将 DependencyProperty 设置为可继承会影响性能  
 默认情况下，注册的依赖属性是不可继承的。 但可以显式地将所有属性设置为可继承。 尽管这是一个有用的功能，但是将属性转换为可继承会影响性能，因为会增加属性无效的时长。  
  
### <a name="use-registerclasshandler-carefully"></a>谨慎使用 RegisterClassHandler  
 虽然调用<xref:System.Windows.EventManager.RegisterClassHandler%2A>允许您保存实例状态，但请务必注意每个实例上都调用处理程序，这可能会导致性能问题。 仅当应用程序<xref:System.Windows.EventManager.RegisterClassHandler%2A>要求您保存实例状态时才使用。  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>在注册过程中为 DependencyProperty 设置默认值  
 创建需要默认值<xref:System.Windows.DependencyProperty>的 创建 时，请使用作为参数<xref:System.Windows.DependencyProperty.Register%2A>传递给 的<xref:System.Windows.DependencyProperty>默认元数据设置值。 请使用此技术，而不要在构造函数中或在元素的每个实例上设置属性值。  
  
### <a name="set-the-propertymetadata-value-using-register"></a>使用 Register 设置 PropertyMetadata 值  
 创建 时<xref:System.Windows.DependencyProperty>，可以选择<xref:System.Windows.PropertyMetadata>使用<xref:System.Windows.DependencyProperty.Register%2A>或<xref:System.Windows.DependencyProperty.OverrideMetadata%2A>方法设置 。 尽管对象可能有一个静态构造函数要调用<xref:System.Windows.DependencyProperty.OverrideMetadata%2A>，但这不是最佳解决方案，会影响性能。 为获得最佳性能，请在<xref:System.Windows.PropertyMetadata>调用 期间设置为<xref:System.Windows.DependencyProperty.Register%2A>。  
  
<a name="Freezable_Objects"></a>
## <a name="freezable-objects"></a>Freezable 对象  
 A<xref:System.Windows.Freezable>是具有特殊类型的对象，具有两种状态：解冻和冻结。 尽可能冻结对象会改进应用程序性能，并缩小其工作集。 有关详细信息，请参阅 [Freezable 对象概述](freezable-objects-overview.md)。  
  
 每个<xref:System.Windows.Freezable>都有一<xref:System.Windows.Freezable.Changed>个事件，每当它发生更改时都会引发该事件。 不过，更改通知会降低应用程序的性能。  
  
 请考虑以下示例，其中每个对象<xref:System.Windows.Shapes.Rectangle>使用相同的<xref:System.Windows.Media.Brush>对象：  
  
 [!code-csharp[Performance#PerformanceSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]默认情况下，为<xref:System.Windows.Media.SolidColorBrush>对象<xref:System.Windows.Freezable.Changed>的事件提供事件处理程序，以使<xref:System.Windows.Shapes.Rectangle>对象<xref:System.Windows.Shapes.Shape.Fill%2A>的属性无效。 在这种情况下，每次<xref:System.Windows.Media.SolidColorBrush>必须触发其<xref:System.Windows.Freezable.Changed>事件时，都需要为每个事件<xref:System.Windows.Shapes.Rectangle>调用回调函数 — 这些回调函数调用的累积会带来巨大的性能损失。 此外，此时添加和删除处理程序将会严重影响性能，这是因为应用程序将不得不遍历整个列表才能执行此操作。 如果应用程序方案从未更改 ，<xref:System.Windows.Media.SolidColorBrush>则不必要地需要支付维护<xref:System.Windows.Freezable.Changed>事件处理程序的成本。  
  
 冻结可以<xref:System.Windows.Freezable>提高其性能，因为它不再需要将资源用于维护更改通知。 下表显示了简单<xref:System.Windows.Media.SolidColorBrush><xref:System.Windows.Freezable.IsFrozen%2A>属性设置为`true`时的大小，而不是设置为 时的大小。 这假定将一个画笔应用于<xref:System.Windows.Shapes.Shape.Fill%2A>十<xref:System.Windows.Shapes.Rectangle>个对象的属性。  
  
|**状态**|**大小**|  
|---------------|--------------|  
|冷冻<xref:System.Windows.Media.SolidColorBrush>|212 字节|  
|非冻结<xref:System.Windows.Media.SolidColorBrush>|972 字节|  
  
 以下代码示例演示了此概念：  
  
 [!code-csharp[Performance#PerformanceSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>解冻的可冻结对象的已更改处理程序可以使对象保持活动状态  
 对象传递给<xref:System.Windows.Freezable>对象<xref:System.Windows.Freezable.Changed>事件的委托实际上是对该对象的引用。 因此，<xref:System.Windows.Freezable.Changed>事件处理程序可以使对象保持比预期的时间更长。 执行已注册以侦听<xref:System.Windows.Freezable>对象<xref:System.Windows.Freezable.Changed>事件的对象的清理时，在释放该对象之前必须删除该委托。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]也连接<xref:System.Windows.Freezable.Changed>内部的事件。 例如，所有作为<xref:System.Windows.Freezable>值的依赖项属性将自动侦听<xref:System.Windows.Freezable.Changed>事件。 属性<xref:System.Windows.Shapes.Shape.Fill%2A>（采用 ）<xref:System.Windows.Media.Brush>说明了这个概念。  
  
 [!code-csharp[Performance#PerformanceSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 在`myBrush`分配`myRectangle.Fill`时，<xref:System.Windows.Shapes.Rectangle>指向对象的委托将添加到<xref:System.Windows.Media.SolidColorBrush>对象的<xref:System.Windows.Freezable.Changed>事件。 这意味着以下代码实际上不会使 `myRect` 可以进行垃圾回收：  
  
 [!code-csharp[Performance#PerformanceSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 在这种情况下`myBrush`，仍然保持`myRectangle`活动状态，并在触发事件<xref:System.Windows.Freezable.Changed>时将其回电。 `myBrush`请注意，<xref:System.Windows.Shapes.Shape.Fill%2A>分配给 new<xref:System.Windows.Shapes.Rectangle>的属性只会向`myBrush`添加另一个事件处理程序。  
  
 清除这些类型的对象的推荐方法是从<xref:System.Windows.Media.Brush><xref:System.Windows.Shapes.Shape.Fill%2A>属性中删除 ，这反过来将删除<xref:System.Windows.Freezable.Changed>事件处理程序。  
  
 [!code-csharp[Performance#PerformanceSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>
## <a name="user-interface-virtualization"></a>用户界面虚拟化  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]还提供了自动"虚拟化"<xref:System.Windows.Controls.StackPanel>数据绑定子内容的元素的变体。 在此上下文中，“虚拟化”一词指的是以下技术：通过此技术，从较多的数据项中生成一个对象子集，具体取决于屏幕上哪些项可见。 如果在指定时刻只有少量 UI 元素位于屏幕上，则此时生成大量 UI 元素需要占用大量内存和处理器。 <xref:System.Windows.Controls.VirtualizingStackPanel>（通过<xref:System.Windows.Controls.VirtualizingPanel>提供的功能计算可见项，并与<xref:System.Windows.Controls.ItemContainerGenerator>从<xref:System.Windows.Controls.ItemsControl>（如<xref:System.Windows.Controls.ListBox>）<xref:System.Windows.Controls.ListView>到仅为可见项创建元素。  
  
 作为性能优化的结果，将仅生成这些项的视觉对象，或如果它们在屏幕上是可见的，则保持活动状态。 这些视觉对象不再位于控件的可视区域时，则可能已被删除。 请勿将此与数据虚拟化发生混淆，数据虚拟化中的数据对象不会全部出现在本地集合中 - 而是根据需要进行流式处理。  
  
 下表显示了向 和<xref:System.Windows.Controls.TextBlock><xref:System.Windows.Controls.StackPanel>添加和渲染 5000 个元素的<xref:System.Windows.Controls.VirtualizingStackPanel>经过时间。 在这种情况下，度量值表示将文本字符串附加到<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A><xref:System.Windows.Controls.ItemsControl>对象属性到面板元素显示文本字符串的时间之间的时间。  
  
|**主机面板**|**呈现时间 (ms)**|  
|--------------------|----------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## <a name="see-also"></a>另请参阅

- [优化 WPF 应用程序性能](optimizing-wpf-application-performance.md)
- [规划应用程序性能](planning-for-application-performance.md)
- [利用硬件](optimizing-performance-taking-advantage-of-hardware.md)
- [布局和设计](optimizing-performance-layout-and-design.md)
- [2D 图形和图像处理](optimizing-performance-2d-graphics-and-imaging.md)
- [应用程序资源](optimizing-performance-application-resources.md)
- [文本](optimizing-performance-text.md)
- [数据绑定](optimizing-performance-data-binding.md)
- [其他性能建议](optimizing-performance-other-recommendations.md)
