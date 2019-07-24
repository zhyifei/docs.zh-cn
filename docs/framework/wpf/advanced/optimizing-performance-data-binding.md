---
title: 优化性能:数据绑定
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: 25c0906e9f23948476732b10b2c5fb10fe4eb55f
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401451"
---
# <a name="optimizing-performance-data-binding"></a>优化性能:数据绑定
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 数据绑定为应用程序呈现数据并与数据交互提供了一种简单且一致的方式。 元素可以绑定到各种数据源中的数据, 其形式为 CLR 对象和[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]。  
  
 本主题提供数据绑定性能方面的建议。  

<a name="HowDataBindingReferencesAreResolved"></a>   
## <a name="how-data-binding-references-are-resolved"></a>如何解析数据绑定引用  
 讨论数据绑定性能问题前，有必要了解 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 数据绑定引擎如何解析用于绑定的对象引用。  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]数据绑定的源可以是任何 CLR 对象。 可以绑定到 CLR 对象的属性、子属性或索引器。 使用 Microsoft .NET 框架反射或<xref:System.ComponentModel.ICustomTypeDescriptor>来解析绑定引用。 以下为解析用于绑定的对象引用的三种方法。  
  
 第一种方法涉及到使用反射。 在这种情况下<xref:System.Reflection.PropertyInfo> , 对象用于发现属性的属性并提供对属性元数据的访问权限。 使用<xref:System.ComponentModel.ICustomTypeDescriptor>接口时, 数据绑定引擎使用此接口来访问属性值。 此<xref:System.ComponentModel.ICustomTypeDescriptor>接口在对象没有静态属性集的情况下尤其有用。  
  
 可以通过实现<xref:System.ComponentModel.INotifyPropertyChanged>接口或使用<xref:System.ComponentModel.TypeDescriptor>与关联的更改通知来提供属性更改通知。 但是, 用于实现属性更改通知的首选策略是使用<xref:System.ComponentModel.INotifyPropertyChanged>。  
  
 如果源对象是 clr 对象并且源属性是 clr 属性, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]数据绑定引擎必须先在源对象上使用反射来<xref:System.ComponentModel.TypeDescriptor>获取, 然后查询<xref:System.ComponentModel.PropertyDescriptor>。 从性能角度看，此反射操作序列可能非常耗时。  
  
 解析对象引用的第二种方法涉及到一个实现<xref:System.ComponentModel.INotifyPropertyChanged>接口的 CLR 源对象, 以及一个作为 clr 属性的源属性。 这种情况下，数据绑定引擎直接在源类型上使用反射，并获取所需的属性。 这依然不是最佳方法，但相较于第一种方法，这种方法在工作集要求方面的成本低。  
  
 解析对象引用的第三种方法涉及源对象, 该对象<xref:System.Windows.DependencyObject>是一个, 源属性<xref:System.Windows.DependencyProperty>是。 这种情况下，数据绑定引擎无需使用反射。 属性引擎和数据绑定引擎共同独立地解析属性引用。 这是解析用于数据绑定的对象引用的最佳方法。  
  
 下表将使用这三个方法对 1000 <xref:System.Windows.Controls.TextBlock.Text%2A> <xref:System.Windows.Controls.TextBlock>元素的属性进行数据绑定的速度进行比较。  
  
|**绑定 TextBlock 的文本属性**|**绑定时间 (ms)**|**呈现时间 -- 包括绑定 (ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|CLR 对象的属性|115|314|  
|实现的 CLR 对象的属性<xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|<xref:System.Windows.DependencyProperty>的。<xref:System.Windows.DependencyObject>|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## <a name="binding-to-large-clr-objects"></a>绑定到大型 CLR 对象  
 当数据绑定到具有数千个属性的单个 CLR 对象时, 会对性能产生显著影响。 可以通过将单个对象分为多个具有更少属性的 CLR 对象来最大程度地减小这种影响。 该表显示了用于将数据绑定到单个大型 CLR 对象与多个较小对象的绑定和呈现时间。  
  
|**数据绑定 1000 个 TextBlock 对象**|**绑定时间 (ms)**|**呈现时间 -- 包括绑定 (ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|到具有1000属性的 CLR 对象|950|1200|  
|到1000具有一个属性的 CLR 对象|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## <a name="binding-to-an-itemssource"></a>绑定到 ItemsSource  
 假设有<xref:System.Collections.Generic.List%601>一个应用场景, 其中包含要<xref:System.Windows.Controls.ListBox>在中显示的雇员列表。 若要创建这两个对象之间的对应关系, 请将您的 employee <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>列表绑定到<xref:System.Windows.Controls.ListBox>的属性。 不妨再假设有一个加入组的新员工。 您可能认为, 若要将此新人员插入到您的<xref:System.Windows.Controls.ListBox>绑定值, 只需将此人添加到您的雇员列表, 并期望数据绑定引擎自动识别此更改。 假设会证明错误,在实际情况下, 此<xref:System.Windows.Controls.ListBox>更改不会自动反映在中。 这是因为 CLR <xref:System.Collections.Generic.List%601>对象不会自动引发集合更改事件。 为了使<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListBox>能够选取更改, 你必须重新创建员工列表, 并将其重新附加到的属性。 <xref:System.Windows.Controls.ListBox> 此解决方案尽管起作用，但是会随之产生很大的性能影响。 每次将<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>的分配给<xref:System.Windows.Controls.ListBox>新的对象时, <xref:System.Windows.Controls.ListBox>第一个对象将丢弃其以前的项并重新生成其整个列表。 如果<xref:System.Windows.Controls.ListBox>映射到的是复杂<xref:System.Windows.DataTemplate>的, 则会对性能造成影响。  
  
 此问题的一种非常有效的解决方案是将您的<xref:System.Collections.ObjectModel.ObservableCollection%601>雇员列表设为。 <xref:System.Collections.ObjectModel.ObservableCollection%601>对象引发数据绑定引擎可以接收的更改通知。 事件在中<xref:System.Windows.Controls.ItemsControl>添加或移除项, 而无需重新生成整个列表。  
  
 下表显示了在添加一个项时, 更新<xref:System.Windows.Controls.ListBox> (通过 UI 虚拟化关闭) 所花费的时间。 第一行中的数字表示 CLR <xref:System.Collections.Generic.List%601>对象绑定到<xref:System.Windows.Controls.ListBox>元素的<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>所用的时间。 第二行中的数字表示绑定<xref:System.Collections.ObjectModel.ObservableCollection%601> <xref:System.Windows.Controls.ListBox>到元素的<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>时所用的时间。 请注意, 使用<xref:System.Collections.ObjectModel.ObservableCollection%601>数据绑定策略可节省大量时间。  
  
|**数据绑定 ItemsSource**|**1 个项的更新时间 (ms)**|  
|--------------------------------------|---------------------------------------|  
|到 CLR <xref:System.Collections.Generic.List%601>对象|1656|  
|到<xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>将 IList 绑定到 ItemsControl 而非 IEnumerable  
 <xref:System.Collections.Generic.IList%601>如果可以选择将<xref:System.Collections.IEnumerable>或绑定到<xref:System.Windows.Controls.ItemsControl>对象, 请选择<xref:System.Collections.Generic.IList%601>对象。 绑定<xref:System.Collections.IEnumerable> 到[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]强制创建包装<xref:System.Collections.Generic.IList%601>对象, 这意味着你的性能受第二个对象的不必要开销的影响。 <xref:System.Windows.Controls.ItemsControl>  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>请勿仅为数据绑定而将 CLR 对象转换为 XML。  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]允许数据绑定到[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]内容; 但是, 到[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]内容的数据绑定速度慢于到 CLR 对象的数据绑定。 如果唯一目的是用于数据绑定, 请不要将 CLR 对象数据转换为 XML。  
  
## <a name="see-also"></a>请参阅

- [优化 WPF 应用程序性能](optimizing-wpf-application-performance.md)
- [规划应用程序性能](planning-for-application-performance.md)
- [利用硬件](optimizing-performance-taking-advantage-of-hardware.md)
- [布局和示例](optimizing-performance-layout-and-design.md)
- [2D 图形和图像处理](optimizing-performance-2d-graphics-and-imaging.md)
- [对象行为](optimizing-performance-object-behavior.md)
- [应用程序资源](optimizing-performance-application-resources.md)
- [文本](optimizing-performance-text.md)
- [其他性能建议](optimizing-performance-other-recommendations.md)
- [数据绑定概述](../data/data-binding-overview.md)
- [演练：在 WPF 应用程序中缓存应用程序数据](walkthrough-caching-application-data-in-a-wpf-application.md)
