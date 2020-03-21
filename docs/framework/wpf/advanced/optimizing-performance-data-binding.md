---
title: 优化性能：数据绑定
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: 3128f453378f9d74f867b571e30f2be4e8add8a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186763"
---
# <a name="optimizing-performance-data-binding"></a>优化性能：数据绑定
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 数据绑定为应用程序呈现数据并与数据交互提供了一种简单且一致的方式。 元素可以绑定到来自各种数据源的数据，其形式是 CLR 对象和 XML。  
  
 本主题提供数据绑定性能方面的建议。  

<a name="HowDataBindingReferencesAreResolved"></a>
## <a name="how-data-binding-references-are-resolved"></a>如何解析数据绑定引用  
 讨论数据绑定性能问题前，有必要了解 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 数据绑定引擎如何解析用于绑定的对象引用。  
  
 数据绑定的[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]源可以是任何 CLR 对象。 您可以绑定到 CLR 对象的属性、子属性或索引器。 使用 Microsoft .NET 框架反射或 解析绑定引用<xref:System.ComponentModel.ICustomTypeDescriptor>。 以下为解析用于绑定的对象引用的三种方法。  
  
 第一种方法涉及到使用反射。 在这种情况下，<xref:System.Reflection.PropertyInfo>对象用于发现属性的属性并提供对属性元数据的访问。 使用<xref:System.ComponentModel.ICustomTypeDescriptor>接口时，数据绑定引擎使用此接口访问属性值。 在<xref:System.ComponentModel.ICustomTypeDescriptor>对象没有静态属性集的情况下，该接口特别有用。  
  
 属性更改通知可以通过实现<xref:System.ComponentModel.INotifyPropertyChanged>接口或使用 与 关联的更改通知来提供。 <xref:System.ComponentModel.TypeDescriptor> 但是，实现属性更改通知的首选策略是使用<xref:System.ComponentModel.INotifyPropertyChanged>。  
  
 如果源对象是 CLR 对象，并且源属性是 CLR 属性，[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]则数据绑定引擎必须首先使用对源对象的反射来获取 ，<xref:System.ComponentModel.TypeDescriptor>然后查询 。 <xref:System.ComponentModel.PropertyDescriptor> 从性能角度看，此反射操作序列可能非常耗时。  
  
 解析对象引用的第二种方法涉及实现接口的<xref:System.ComponentModel.INotifyPropertyChanged>CLR 源对象和作为 CLR 属性的源属性。 这种情况下，数据绑定引擎直接在源类型上使用反射，并获取所需的属性。 这依然不是最佳方法，但相较于第一种方法，这种方法在工作集要求方面的成本低。  
  
 解析对象引用的第三种方法涉及源对象，该对象是<xref:System.Windows.DependencyObject>和 源属性<xref:System.Windows.DependencyProperty>。 这种情况下，数据绑定引擎无需使用反射。 属性引擎和数据绑定引擎共同独立地解析属性引用。 这是解析用于数据绑定的对象引用的最佳方法。  
  
 下表比较了使用这三种方法绑定一千<xref:System.Windows.Controls.TextBlock.Text%2A><xref:System.Windows.Controls.TextBlock>个元素属性的数据速度。  
  
|**绑定 TextBlock 的文本属性**|**绑定时间 (ms)**|**呈现时间 -- 包括绑定 (ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|到 CLR 对象的属性|115|314|  
|到实现的 CLR 对象的属性<xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|到<xref:System.Windows.DependencyProperty>的<xref:System.Windows.DependencyObject>。|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>
## <a name="binding-to-large-clr-objects"></a>绑定到大型 CLR 对象  
 当数据绑定到具有数千个属性的单个 CLR 对象时，将显著的性能影响。 通过将单个对象划分为多个具有较少属性的 CLR 对象，可以最大程度地减少此影响。 该表显示了与多个较小对象绑定到单个大型 CLR 对象的数据的绑定和呈现时间。  
  
|**数据绑定 1000 个 TextBlock 对象**|**绑定时间 (ms)**|**呈现时间 -- 包括绑定 (ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|到具有 1000 个属性的 CLR 对象|950|1200|  
|到具有一个属性的 1000 个 CLR 对象|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>
## <a name="binding-to-an-itemssource"></a>绑定到 ItemsSource  
 请考虑一个方案，其中 CLR<xref:System.Collections.Generic.List%601>对象包含要在 中显示的员工列表。 <xref:System.Windows.Controls.ListBox> 要在这两个对象之间创建对应关系，您可以将员工列表绑定到<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>的属性。 <xref:System.Windows.Controls.ListBox> 不妨再假设有一个加入组的新员工。 您可能认为，为了将此人插入到绑定<xref:System.Windows.Controls.ListBox>值中，只需将此人添加到您的员工列表中，并期望数据绑定引擎自动识别此更改。 这一假设将被证明是错误的;实际上，更改不会自动反映在 中<xref:System.Windows.Controls.ListBox>。 这是因为 CLR<xref:System.Collections.Generic.List%601>对象不会自动引发集合更改的事件。 要获取 更改<xref:System.Windows.Controls.ListBox>，必须重新创建员工列表，并将其<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>重新附加到 的属性。 <xref:System.Windows.Controls.ListBox> 此解决方案尽管起作用，但是会随之产生很大的性能影响。 每次将 的<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>重新<xref:System.Windows.Controls.ListBox>分配给新对象时，<xref:System.Windows.Controls.ListBox>第一个对象都会放弃其以前的项并重新生成其整个列表。 如果将<xref:System.Windows.Controls.ListBox>性能影响映射到复杂位置<xref:System.Windows.DataTemplate>，则性能影响将放大。  
  
 解决这个问题的一个非常有效的方法是使员工列表成为<xref:System.Collections.ObjectModel.ObservableCollection%601>. 对象<xref:System.Collections.ObjectModel.ObservableCollection%601>将引发数据绑定引擎可以接收的更改通知。 事件从 中添加或删除项，<xref:System.Windows.Controls.ItemsControl>而无需重新生成整个列表。  
  
 下表显示了添加一<xref:System.Windows.Controls.ListBox>个项目时更新（关闭 UI 虚拟化）所需的时间。 第一行中的数字表示 CLR<xref:System.Collections.Generic.List%601>对象绑定到<xref:System.Windows.Controls.ListBox>元素 的<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>时经过的时间。 第二行中的数字表示绑定到<xref:System.Collections.ObjectModel.ObservableCollection%601><xref:System.Windows.Controls.ListBox>元素 的<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>时经过的时间。 请注意使用<xref:System.Collections.ObjectModel.ObservableCollection%601>数据绑定策略显著节省时间。  
  
|**数据绑定 ItemsSource**|**1 个项的更新时间 (ms)**|  
|--------------------------------------|---------------------------------------|  
|到 CLR<xref:System.Collections.Generic.List%601>对象|1656|  
|到<xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>将 IList 绑定到 ItemsControl 而非 IEnumerable  
 如果在将 对象绑定 为<xref:System.Collections.Generic.IList%601>对象或<xref:System.Collections.IEnumerable><xref:System.Windows.Controls.ItemsControl>对象之间可以选择，请选择<xref:System.Collections.Generic.IList%601>该对象。 绑定<xref:System.Collections.IEnumerable>到<xref:System.Windows.Controls.ItemsControl>强制[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]以创建包装<xref:System.Collections.Generic.IList%601>对象，这意味着您的性能受到第二个对象的不必要的开销的影响。  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>请勿仅为数据绑定而将 CLR 对象转换为 XML。  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]允许您将数据绑定到 XML 内容;但是，与对 CLR 对象绑定的数据绑定速度要慢。 如果唯一的目的是数据绑定，则不要将 CLR 对象数据转换为 XML。  
  
## <a name="see-also"></a>另请参阅

- [优化 WPF 应用程序性能](optimizing-wpf-application-performance.md)
- [规划应用程序性能](planning-for-application-performance.md)
- [利用硬件](optimizing-performance-taking-advantage-of-hardware.md)
- [布局和设计](optimizing-performance-layout-and-design.md)
- [2D 图形和图像处理](optimizing-performance-2d-graphics-and-imaging.md)
- [对象行为](optimizing-performance-object-behavior.md)
- [应用程序资源](optimizing-performance-application-resources.md)
- [文本](optimizing-performance-text.md)
- [其他性能建议](optimizing-performance-other-recommendations.md)
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [演练：在 WPF 应用程序中缓存应用程序数据](walkthrough-caching-application-data-in-a-wpf-application.md)
