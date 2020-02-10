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
ms.openlocfilehash: 64e567cd28e9458b483b0963e0dedd924ad23bab
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094483"
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
 通常，访问 <xref:System.Windows.DependencyObject> 的依赖属性的速度不会慢于访问 CLR 属性。 虽然设置属性值时存在较小的性能开销，但获取值与从 CLR 属性获取值的速度一样快。 抵销一些小的性能开销是因为依赖属性支持可靠的功能，如数据绑定、动画、继承和样式设置。 有关详细信息，请参阅[依赖项属性概述](dependency-properties-overview.md)。  
  
### <a name="dependencyproperty-optimizations"></a>DependencyProperty 优化  
 在应用程序中定义依赖属性时请务必谨慎。 如果 <xref:System.Windows.DependencyProperty> 只影响呈现类型元数据选项，而不影响其他元数据选项（如 <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>），则应通过重写其元数据将其标记为。 有关替代或获取属性元数据的详细信息，请参阅[依赖属性元数据](dependency-property-metadata.md)。  
  
 如果并非所有属性更改都会影响测量、排列和呈现，则通过属性更改处理程序手动使测量、排列和呈现阶段无效的做法可能会更高效。 例如，你可能决定仅在值大于设置限制时才重新呈现背景。 在这种情况下，值超过设置限制时，属性更改处理程序仅会使呈现无效。  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>将 DependencyProperty 设置为可继承会影响性能  
 默认情况下，注册的依赖属性是不可继承的。 但可以显式地将所有属性设置为可继承。 尽管这是一个有用的功能，但是将属性转换为可继承会影响性能，因为会增加属性无效的时长。  
  
### <a name="use-registerclasshandler-carefully"></a>谨慎使用 RegisterClassHandler  
 调用 <xref:System.Windows.EventManager.RegisterClassHandler%2A> 可以保存实例状态，因此请务必注意，在每个实例上调用处理程序，这会导致性能问题。 仅当应用程序需要保存实例状态时才使用 <xref:System.Windows.EventManager.RegisterClassHandler%2A>。  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>在注册过程中为 DependencyProperty 设置默认值  
 创建需要默认值的 <xref:System.Windows.DependencyProperty> 时，使用作为参数传递给 <xref:System.Windows.DependencyProperty>的 <xref:System.Windows.DependencyProperty.Register%2A> 方法的默认元数据设置值。 请使用此技术，而不要在构造函数中或在元素的每个实例上设置属性值。  
  
### <a name="set-the-propertymetadata-value-using-register"></a>使用 Register 设置 PropertyMetadata 值  
 创建 <xref:System.Windows.DependencyProperty>时，可以选择使用 <xref:System.Windows.DependencyProperty.Register%2A> 或 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 方法设置 <xref:System.Windows.PropertyMetadata>。 尽管对象可能具有调用 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>的静态构造函数，但这并不是最佳解决方案，会影响性能。 为了获得最佳性能，请在调用 <xref:System.Windows.DependencyProperty.Register%2A>过程中设置 <xref:System.Windows.PropertyMetadata>。  
  
<a name="Freezable_Objects"></a>   
## <a name="freezable-objects"></a>Freezable 对象  
 <xref:System.Windows.Freezable> 是一种特殊类型的对象，该对象具有两种状态：未冻结和已冻结。 尽可能冻结对象会改进应用程序性能，并缩小其工作集。 有关详细信息，请参阅 [Freezable 对象概述](freezable-objects-overview.md)。  
  
 每个 <xref:System.Windows.Freezable> 都有一个 <xref:System.Windows.Freezable.Changed> 事件，每当发生更改时都会引发该事件。 不过，更改通知会降低应用程序的性能。  
  
 请考虑以下示例，其中每个 <xref:System.Windows.Shapes.Rectangle> 使用同一个 <xref:System.Windows.Media.Brush> 对象：  
  
 [!code-csharp[Performance#PerformanceSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 默认情况下，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 为 <xref:System.Windows.Media.SolidColorBrush> 对象的 <xref:System.Windows.Freezable.Changed> 事件提供事件处理程序，以便使 <xref:System.Windows.Shapes.Rectangle> 对象的 <xref:System.Windows.Shapes.Shape.Fill%2A> 属性无效。 在这种情况下，每次 <xref:System.Windows.Media.SolidColorBrush> 必须激发其 <xref:System.Windows.Freezable.Changed> 事件时，都需要调用每个 <xref:System.Windows.Shapes.Rectangle>的回调函数，这种回调函数调用的累积会对性能产生重大影响。 此外，此时添加和删除处理程序将会严重影响性能，这是因为应用程序将不得不遍历整个列表才能执行此操作。 如果你的应用程序方案永远不会改变 <xref:System.Windows.Media.SolidColorBrush>，你将会在不必要的情况下支付维护 <xref:System.Windows.Freezable.Changed> 事件处理程序的成本。  
  
 冻结 <xref:System.Windows.Freezable> 可以提高其性能，因为它不再需要展开资源来维护更改通知。 下表显示了简单 <xref:System.Windows.Media.SolidColorBrush> 在其 <xref:System.Windows.Freezable.IsFrozen%2A> 属性设置为 `true`时的大小，而不是。 这假定将一个画笔应用于10个 <xref:System.Windows.Shapes.Rectangle> 对象的 <xref:System.Windows.Shapes.Shape.Fill%2A> 属性。  
  
|**State**|**大小**|  
|---------------|--------------|  
|已冻结 <xref:System.Windows.Media.SolidColorBrush>|212 字节|  
|非冻结 <xref:System.Windows.Media.SolidColorBrush>|972 字节|  
  
 以下代码示例演示了此概念：  
  
 [!code-csharp[Performance#PerformanceSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>解冻的可冻结对象的已更改处理程序可以使对象保持活动状态  
 对象传递到 <xref:System.Windows.Freezable> 对象的 <xref:System.Windows.Freezable.Changed> 事件的委托实际上是对该对象的引用。 因此，<xref:System.Windows.Freezable.Changed> 事件处理程序可以使对象保持活动状态的时间比预期长。 当对已注册为侦听 <xref:System.Windows.Freezable> 对象的 <xref:System.Windows.Freezable.Changed> 事件的对象执行清理时，在释放对象之前删除该委托是至关重要的。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 还会在内部挂钩 <xref:System.Windows.Freezable.Changed> 事件。 例如，将 <xref:System.Windows.Freezable> 为值的所有依赖属性都将自动侦听 <xref:System.Windows.Freezable.Changed> 事件。 使用 <xref:System.Windows.Media.Brush>的 <xref:System.Windows.Shapes.Shape.Fill%2A> 属性说明了此概念。  
  
 [!code-csharp[Performance#PerformanceSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 在将 `myBrush` 分配给 `myRectangle.Fill`时，指向 <xref:System.Windows.Shapes.Rectangle> 对象的委托将添加到 <xref:System.Windows.Media.SolidColorBrush> 对象的 <xref:System.Windows.Freezable.Changed> 事件。 这意味着以下代码实际上不会使 `myRect` 可以进行垃圾回收：  
  
 [!code-csharp[Performance#PerformanceSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 在这种情况下 `myBrush` 仍保持 `myRectangle` 活动状态，并在激发其 <xref:System.Windows.Freezable.Changed> 事件时回叫。 请注意，将 `myBrush` 分配给新 <xref:System.Windows.Shapes.Rectangle> 的 <xref:System.Windows.Shapes.Shape.Fill%2A> 属性将只是将另一个事件处理程序添加到 `myBrush`。  
  
 清除这些类型的对象的建议方法是从 <xref:System.Windows.Shapes.Shape.Fill%2A> 属性中删除 <xref:System.Windows.Media.Brush>，这会依次删除 <xref:System.Windows.Freezable.Changed> 事件处理程序。  
  
 [!code-csharp[Performance#PerformanceSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>   
## <a name="user-interface-virtualization"></a>用户界面虚拟化  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 还提供了自动 "虚拟化" 数据绑定子内容的 <xref:System.Windows.Controls.StackPanel> 元素的变体。 在此上下文中，“虚拟化”一词指的是以下技术：通过此技术，从较多的数据项中生成一个对象子集，具体取决于屏幕上哪些项可见。 如果在指定时刻只有少量 UI 元素位于屏幕上，则此时生成大量 UI 元素需要占用大量内存和处理器。 <xref:System.Windows.Controls.VirtualizingStackPanel> （通过 <xref:System.Windows.Controls.VirtualizingPanel>提供的功能）计算可见项，并使用 <xref:System.Windows.Controls.ItemsControl> 中的 <xref:System.Windows.Controls.ItemContainerGenerator> （例如 <xref:System.Windows.Controls.ListBox> 或 <xref:System.Windows.Controls.ListView>）来仅创建可见项的元素。  
  
 作为性能优化的结果，将仅生成这些项的视觉对象，或如果它们在屏幕上是可见的，则保持活动状态。 这些视觉对象不再位于控件的可视区域时，则可能已被删除。 请勿将此与数据虚拟化发生混淆，数据虚拟化中的数据对象不会全部出现在本地集合中 - 而是根据需要进行流式处理。  
  
 下表显示了将 5000 <xref:System.Windows.Controls.TextBlock> 元素添加到 <xref:System.Windows.Controls.StackPanel> 和 <xref:System.Windows.Controls.VirtualizingStackPanel>所用的时间。 在这种情况下，度量值表示将文本字符串附加到 <xref:System.Windows.Controls.ItemsControl> 对象的 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 属性到 panel 元素显示文本字符串之间的时间。  
  
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
- [Text](optimizing-performance-text.md)
- [数据绑定](optimizing-performance-data-binding.md)
- [其他性能建议](optimizing-performance-other-recommendations.md)
