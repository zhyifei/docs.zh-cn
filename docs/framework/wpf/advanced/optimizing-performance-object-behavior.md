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
ms.openlocfilehash: 2e1f56dec87de7a22aa8a0bfefe84222d74ba085
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="optimizing-performance-object-behavior"></a>优化性能：对象行为
了解 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 对象的内部行为，有助于在功能和性能之间做出适当的取舍。  
  

  
<a name="Not_Removing_Event_Handlers"></a>   
## <a name="not-removing-event-handlers-on-objects-may-keep-objects-alive"></a>不删除对象的事件处理程序可能会使对象保持活动状态  
 对象传递给其事件的委托是对该对象的有效引用。 因此，事件处理程序可以使对象保持活动状态的时间超过预期时间。 当对已注册为侦听对象事件的对象执行清理时，在释放对象前删除委托是非常必要的。 将不需要的对象保持为活动状态会增加应用程序的内存使用量。 在对象为逻辑树或可视化树的根时更是如此。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 为事件引入了弱事件侦听器模式，在很难跟踪源和侦听器之间的对象生存期关系时，这种模式特别有用。 某些现有 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 事件使用此模式。 如果要实现具有自定义事件的对象，此模式可能会有用。 有关详细信息，请参阅[弱事件模式](../../../../docs/framework/wpf/advanced/weak-event-patterns.md)。  
  
 有若干工具（如 CLR 探查器和工作集查看器）可以提供有关指定进程的内存使用量的信息。 CLR 探查器包括分配配置文件的许多非常有用的视图，其中包括已分配类型的直方图、分配和调用关系图、显示各代垃圾回收及上述回收之后托管堆的生成状态的时间线，以及显示每个方法分配和程序集加载的调用树。 有关详细信息，请参阅 [.NET Framework 开发人员中心](http://go.microsoft.com/fwlink/?LinkId=117435)。  
  
<a name="DPs_and_Objects"></a>   
## <a name="dependency-properties-and-objects"></a>依赖属性和对象  
 一般情况下，访问依赖项属性的<xref:System.Windows.DependencyObject>不低于访问[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]属性。 虽然设置属性值会产生一些小的性能开销，但是获取值与从 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 属性获取值的速度一样快。 抵销一些小的性能开销是因为依赖属性支持可靠的功能，如数据绑定、动画、继承和样式设置。 有关详细信息，请参阅[依赖项属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)。  
  
### <a name="dependencyproperty-optimizations"></a>DependencyProperty 优化  
 在应用程序中定义依赖属性时请务必谨慎。 如果你<xref:System.Windows.DependencyProperty>仅影响呈现类型元数据选项，而不是其他元数据选项如<xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>，你应将其标记为通过重写其元数据。 有关替代或获取属性元数据的详细信息，请参阅[依赖属性元数据](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)。  
  
 如果并非所有属性更改都会影响测量、排列和呈现，则通过属性更改处理程序手动使测量、排列和呈现阶段无效的做法可能会更高效。 例如，你可能决定仅在值大于设置限制时才重新呈现背景。 在这种情况下，值超过设置限制时，属性更改处理程序仅会使呈现无效。  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>将 DependencyProperty 设置为可继承会影响性能  
 默认情况下，注册的依赖属性是不可继承的。 但可以显式地将所有属性设置为可继承。 尽管这是一个有用的功能，但是将属性转换为可继承会影响性能，因为会增加属性无效的时长。  
  
### <a name="use-registerclasshandler-carefully"></a>谨慎使用 RegisterClassHandler  
 虽然通过调用<xref:System.Windows.EventManager.RegisterClassHandler%2A>允许你保存实例状态，请务必注意，每个实例，这可能导致性能问题上调用处理程序。 仅使用<xref:System.Windows.EventManager.RegisterClassHandler%2A>你的应用程序需要保存实例状态。  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>在注册过程中为 DependencyProperty 设置默认值  
 在创建时<xref:System.Windows.DependencyProperty>需要默认值，将使用作为参数传递的默认元数据值设置<xref:System.Windows.DependencyProperty.Register%2A>方法<xref:System.Windows.DependencyProperty>。 请使用此技术，而不要在构造函数中或在元素的每个实例上设置属性值。  
  
### <a name="set-the-propertymetadata-value-using-register"></a>使用 Register 设置 PropertyMetadata 值  
 在创建时<xref:System.Windows.DependencyProperty>，你可以选择设置<xref:System.Windows.PropertyMetadata>使用<xref:System.Windows.DependencyProperty.Register%2A>或<xref:System.Windows.DependencyProperty.OverrideMetadata%2A>方法。 虽然你的对象可能具有一个静态构造函数来调用<xref:System.Windows.DependencyProperty.OverrideMetadata%2A>，这不是最佳解决方案，并且会影响性能。 为了获得最佳性能，设置<xref:System.Windows.PropertyMetadata>到在呼叫期间<xref:System.Windows.DependencyProperty.Register%2A>。  
  
<a name="Freezable_Objects"></a>   
## <a name="freezable-objects"></a>Freezable 对象  
 A<xref:System.Windows.Freezable>是有两种状态的对象的特殊类型： 解冻和冻结。 尽可能冻结对象会改进应用程序性能，并缩小其工作集。 有关详细信息，请参阅 [Freezable 对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)。  
  
 每个<xref:System.Windows.Freezable>具有<xref:System.Windows.Freezable.Changed>发生更改时引发的事件。 不过，更改通知会降低应用程序的性能。  
  
 考虑下面的示例，其中的每个<xref:System.Windows.Shapes.Rectangle>使用相同<xref:System.Windows.Media.Brush>对象：  
  
 [!code-csharp[Performance#PerformanceSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 默认情况下，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供的事件处理程序<xref:System.Windows.Media.SolidColorBrush>对象的<xref:System.Windows.Freezable.Changed>事件，以使其无效<xref:System.Windows.Shapes.Rectangle>对象的<xref:System.Windows.Shapes.Shape.Fill%2A>属性。 在这种情况下，每次<xref:System.Windows.Media.SolidColorBrush>不得不激发其<xref:System.Windows.Freezable.Changed>则需要在每个调用的回调函数的事件<xref:System.Windows.Shapes.Rectangle>— 这些回调函数调用的累积施加显著的性能损失。 此外，此时添加和删除处理程序将会严重影响性能，这是因为应用程序将不得不遍历整个列表才能执行此操作。 如果你的应用场景永远不会更改<xref:System.Windows.Media.SolidColorBrush>，需付费的维护成本<xref:System.Windows.Freezable.Changed>事件处理程序不必要地。  
  
 冻结<xref:System.Windows.Freezable>可以提高其性能，因为它不再需要展开上维护更改通知的资源。 下表显示了一个简单的大小<xref:System.Windows.Media.SolidColorBrush>时其<xref:System.Windows.Freezable.IsFrozen%2A>属性设置为`true`、 与它不是相比。 这假定应用到一个画笔<xref:System.Windows.Shapes.Shape.Fill%2A>10 个属性<xref:System.Windows.Shapes.Rectangle>对象。  
  
|**状态**|**Size**|  
|---------------|--------------|  
|冻结 <xref:System.Windows.Media.SolidColorBrush>|212 字节|  
|非冻结 <xref:System.Windows.Media.SolidColorBrush>|972 字节|  
  
 以下代码示例演示了此概念：  
  
 [!code-csharp[Performance#PerformanceSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>解冻的可冻结对象的已更改处理程序可以使对象保持活动状态  
 对象传递给委托<xref:System.Windows.Freezable>对象的<xref:System.Windows.Freezable.Changed>事件实际上是对该对象的引用。 因此，<xref:System.Windows.Freezable.Changed>事件处理程序可以使对象保持活动状态时间超过预期时间。 已注册来侦听的对象执行清除时<xref:System.Windows.Freezable>对象的<xref:System.Windows.Freezable.Changed>事件，请务必在释放对象前移除该委托。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 此外挂钩<xref:System.Windows.Freezable.Changed>事件内部。 例如，所有依赖项属性需要<xref:System.Windows.Freezable>为值将侦听到<xref:System.Windows.Freezable.Changed>事件自动。 <xref:System.Windows.Shapes.Shape.Fill%2A>属性，采用<xref:System.Windows.Media.Brush>，阐述了此概念。  
  
 [!code-csharp[Performance#PerformanceSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 上的分配`myBrush`到`myRectangle.Fill`、 委托指回<xref:System.Windows.Shapes.Rectangle>对象将添加到<xref:System.Windows.Media.SolidColorBrush>对象的<xref:System.Windows.Freezable.Changed>事件。 这意味着以下代码实际上不会使 `myRect` 可以进行垃圾回收：  
  
 [!code-csharp[Performance#PerformanceSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 在这种情况下`myBrush`仍保持`myRectangle`处于活动状态并将回调到它时激发其<xref:System.Windows.Freezable.Changed>事件。 请注意，分配`myBrush`到<xref:System.Windows.Shapes.Shape.Fill%2A>属性的新<xref:System.Windows.Shapes.Rectangle>将只需将添加到另一个事件处理程序`myBrush`。  
  
 清理这些类型的对象的建议的方法是删除<xref:System.Windows.Media.Brush>从<xref:System.Windows.Shapes.Shape.Fill%2A>属性，这反过来将删除<xref:System.Windows.Freezable.Changed>事件处理程序。  
  
 [!code-csharp[Performance#PerformanceSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>   
## <a name="user-interface-virtualization"></a>用户界面虚拟化  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 此外提供了一种变体<xref:System.Windows.Controls.StackPanel>自动"显示"数据绑定子内容的元素。 在此上下文中，“虚拟化”一词指的是以下技术：通过此技术，从较多的数据项中生成一个对象子集，具体取决于屏幕上哪些项可见。 如果在指定时刻只有少量 UI 元素位于屏幕上，则此时生成大量 UI 元素需要占用大量内存和处理器。 <xref:System.Windows.Controls.VirtualizingStackPanel> (由提供的功能通过<xref:System.Windows.Controls.VirtualizingPanel>) 计算可见的项，并处理<xref:System.Windows.Controls.ItemContainerGenerator>从<xref:System.Windows.Controls.ItemsControl>(如<xref:System.Windows.Controls.ListBox>或<xref:System.Windows.Controls.ListView>) 仅创建为可见项的元素。  
  
 作为性能优化的结果，将仅生成这些项的视觉对象，或如果它们在屏幕上是可见的，则保持活动状态。 这些视觉对象不再位于控件的可视区域时，则可能已被删除。 请勿将此与数据虚拟化发生混淆，数据虚拟化中的数据对象不会全部出现在本地集合中 - 而是根据需要进行流式处理。  
  
 下表显示了经过的时间添加和呈现 5000<xref:System.Windows.Controls.TextBlock>元素与<xref:System.Windows.Controls.StackPanel>和<xref:System.Windows.Controls.VirtualizingStackPanel>。 测量值在此方案中，表示附加到的文本字符串之间的时间<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性<xref:System.Windows.Controls.ItemsControl>面板元素时显示的文本字符串的时间的对象。  
  
|**主机面板**|**呈现时间 (ms)**|  
|--------------------|----------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## <a name="see-also"></a>请参阅  
 [优化 WPF 应用程序性能](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [规划应用程序性能](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [利用硬件](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [布局和示例](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2D 图形和图像处理](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [应用程序资源](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [文本](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [数据绑定](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [其他性能建议](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
