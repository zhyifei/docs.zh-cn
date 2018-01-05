---
title: "优化性能：数据绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c420748a9361655eeb2df33ce8426d9f167d3414
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="optimizing-performance-data-binding"></a>优化性能：数据绑定
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 数据绑定为应用程序呈现数据并与数据交互提供了一种简单且一致的方式。 元素能够以 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 对象和 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 形式绑定到来自各种数据源的数据。  
  
 本主题提供数据绑定性能方面的建议。  
  

  
<a name="HowDataBindingReferencesAreResolved"></a>   
## <a name="how-data-binding-references-are-resolved"></a>如何解析数据绑定引用  
 讨论数据绑定性能问题前，有必要了解 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 数据绑定引擎如何解析用于绑定的对象引用。  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 数据绑定的源可以是任何 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 对象。 可绑定到 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 对象的属性、子属性或索引器。 通过使用解析绑定引用[!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)]反射或<xref:System.ComponentModel.ICustomTypeDescriptor>。 以下为解析用于绑定的对象引用的三种方法。  
  
 第一种方法涉及到使用反射。 在这种情况下，<xref:System.Reflection.PropertyInfo>对象用于发现的属性的属性，并提供对属性元数据的访问权限。 使用时<xref:System.ComponentModel.ICustomTypeDescriptor>界面，数据绑定引擎使用此接口访问的属性值。 <xref:System.ComponentModel.ICustomTypeDescriptor>接口是在该对象不具有一组静态属性的情况下特别有用。  
  
 属性更改通知可以提供通过实现<xref:System.ComponentModel.INotifyPropertyChanged>接口或通过使用与关联的更改通知<xref:System.ComponentModel.TypeDescriptor>。 但是，实现属性更改通知的首选的策略是使用<xref:System.ComponentModel.INotifyPropertyChanged>。  
  
 如果源对象是[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]对象和源属性是[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]属性，[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]数据绑定引擎必须首先使用源对象上反射来获取<xref:System.ComponentModel.TypeDescriptor>，并进行查询，然后<xref:System.ComponentModel.PropertyDescriptor>。 从性能角度看，此反射操作序列可能非常耗时。  
  
 解析对象引用第二种方法涉及[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]实现的源对象<xref:System.ComponentModel.INotifyPropertyChanged>接口，并且是源属性[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]属性。 这种情况下，数据绑定引擎直接在源类型上使用反射，并获取所需的属性。 这依然不是最佳方法，但相较于第一种方法，这种方法在工作集要求方面的成本低。  
  
 解析对象的引用的第三个方法涉及到的源对象时<xref:System.Windows.DependencyObject>和的源属性<xref:System.Windows.DependencyProperty>。 这种情况下，数据绑定引擎无需使用反射。 属性引擎和数据绑定引擎共同独立地解析属性引用。 这是解析用于数据绑定的对象引用的最佳方法。  
  
 下表比较数据绑定的速度<xref:System.Windows.Controls.TextBlock.Text%2A>一千属性<xref:System.Windows.Controls.TextBlock>使用这三种方法的元素。  
  
|**绑定 TextBlock 的文本属性**|**绑定时间 (ms)**|**呈现时间 -- 包括绑定 (ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|绑定到 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 对象的属性|115|314|  
|属性[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]实现的对象<xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|到<xref:System.Windows.DependencyProperty>的<xref:System.Windows.DependencyObject>。|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## <a name="binding-to-large-clr-objects"></a>绑定到大型 CLR 对象  
 数据绑定到具有数千个属性的单个 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 对象时具有明显性能影响。 通过将单个对象分成具有较少属性的多个 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 对象可降低对性能的影响。 下表显示将数据绑定到单个大型 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 对象和多个较小对象的绑定时间和呈现时间。  
  
|**数据绑定 1000 个 TextBlock 对象**|**绑定时间 (ms)**|**呈现时间 -- 包括绑定 (ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|绑定到具有 1000 个属性的 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 对象|950|1200|  
|绑定到 1000 个具有 1 个属性的 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 对象|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## <a name="binding-to-an-itemssource"></a>绑定到 ItemsSource  
 假设您在其中具有[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]<xref:System.Collections.Generic.List%601>对象，其中包含你想要在中显示的员工列表<xref:System.Windows.Controls.ListBox>。 若要创建这两个对象之间的对应关系，将绑定到雇员列表<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性<xref:System.Windows.Controls.ListBox>。 不妨再假设有一个加入组的新员工。 可能会认为以插入您所绑定到这个新雇员<xref:System.Windows.Controls.ListBox>值，您将只需将此用户添加到你的员工列表和需要通过数据绑定引擎自动识别此更改。 这种假设将被证明是错误;在现实中，将不会更改反映在<xref:System.Windows.Controls.ListBox>自动。 这是因为[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]<xref:System.Collections.Generic.List%601>对象不会自动引发集合更改事件。 若要获取<xref:System.Windows.Controls.ListBox>以拾取所做的更改，你将需要重新创建你的员工列表，并重新将其附加到<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性<xref:System.Windows.Controls.ListBox>。 此解决方案尽管起作用，但是会随之产生很大的性能影响。 每当你重新分配<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>的<xref:System.Windows.Controls.ListBox>新对象、<xref:System.Windows.Controls.ListBox>首先会抛弃其以前的项，并重新生成其整个列表。 如果将被放大的性能影响你<xref:System.Windows.Controls.ListBox>映射到一种复杂<xref:System.Windows.DataTemplate>。  
  
 此问题的非常高效解决方案是使你的员工列表<xref:System.Collections.ObjectModel.ObservableCollection%601>。 <xref:System.Collections.ObjectModel.ObservableCollection%601>对象引发的更改通知数据绑定引擎可以接收。 事件添加或删除中的一个项<xref:System.Windows.Controls.ItemsControl>而无需重新生成整个列表。  
  
 下表显示的时间来更新<xref:System.Windows.Controls.ListBox>（与用户界面已关闭的虚拟化） 添加了一个项。 第一行中的数字表示经过的时间时[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]<xref:System.Collections.Generic.List%601>对象绑定到<xref:System.Windows.Controls.ListBox>元素的<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>。 第二行中的数字表示经过的时间时<xref:System.Collections.ObjectModel.ObservableCollection%601>绑定到<xref:System.Windows.Controls.ListBox>元素的<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>。 请注意，很长时间节省使用<xref:System.Collections.ObjectModel.ObservableCollection%601>数据绑定策略。  
  
|**数据绑定 ItemsSource**|**1 个项的更新时间 (ms)**|  
|--------------------------------------|---------------------------------------|  
|到[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]<xref:System.Collections.Generic.List%601>对象|1656|  
|到<xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>将 IList 绑定到 ItemsControl 而非 IEnumerable  
 如果你有绑定选择<xref:System.Collections.Generic.IList%601>或<xref:System.Collections.IEnumerable>到<xref:System.Windows.Controls.ItemsControl>对象，请选择<xref:System.Collections.Generic.IList%601>对象。 绑定<xref:System.Collections.IEnumerable>到<xref:System.Windows.Controls.ItemsControl>强制[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]若要创建包装器<xref:System.Collections.Generic.IList%601>对象，这意味着你的性能将受到第二个对象的不必要的开销。  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>请勿仅为数据绑定而将 CLR 对象转换为 XML。  
 通过 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 可数据绑定到 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 内容；但是，数据绑定到 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 内容与数据绑定到 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 对象相比速度更慢。 如果目的仅在于数据绑定，请勿将 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 对象数据转换为 XML。  
  
## <a name="see-also"></a>请参阅  
 [优化 WPF 应用程序性能](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [规划应用程序性能](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [利用硬件](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [布局和示例](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2D 图形和图像处理](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [对象行为](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [应用程序资源](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [文本](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [其他性能建议](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [演练：在 WPF 应用程序中缓存应用程序数据](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
