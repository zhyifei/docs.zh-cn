---
title: 框架属性元数据
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: 3e40dfbcbe88f424337ee5a32fb3e3aaaddd68d0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460466"
---
# <a name="framework-property-metadata"></a>框架属性元数据
对于 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 体系结构中被视为 WPF 框架级的对象元素的属性，将报告框架属性元数据选项。 通常，WPF 框架级别的指定要求由 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 表示 Api 和可执行文件处理呈现、数据绑定和属性系统优化等功能。 这些系统对框架属性元数据进行查询，以便为特定的元素属性确定特定于功能的特征。  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisites  
 本主题假定你从 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 类的现有依赖属性的使用者角度了解依赖属性，并且已阅读[依赖属性概述](dependency-properties-overview.md)。 另外，应当已阅读[依赖属性元数据](dependency-property-metadata.md)。  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## <a name="what-is-communicated-by-framework-property-metadata"></a>框架属性元数据传达的信息  
 框架属性元数据分为以下类别：  
  
- 报表影响元素的布局属性（<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>、<xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A><xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>）。 如果属性影响各个方面，则可以在元数据中设置这些标志，并且还会在类中实现 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> / <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 方法，以便向布局系统提供特定的呈现行为和信息。 通常，如果在属性元数据中有布局属性为 true，则此类实现会在依赖属性中检查属性是否无效，并且只有无效属性才必须请求新的布局处理过程。  
  
- 报告影响元素的父元素的布局属性（<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>、<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>）。 默认情况下，将设置这些标志 <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>。  
  
- <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> 默认情况下，依赖属性不会继承值。 <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A> 允许将继承路径传递到可视化树，这对于某些控件组合方案来说是必需的。  
  
    > [!NOTE]
    > 属性值上下文中的术语“继承”指特定于依赖属性的情况；它意味着由于存在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性系统的 WPF 框架级功能，子元素可以从父元素继承实际的依赖属性值。 它与通过派生类型的托管代码类型和成员继承没有直接关系。 有关详细信息，请参阅[属性值继承](property-value-inheritance.md)。  
  
- 报告数据绑定特性（<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>，<xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>）。 默认情况下，框架中的依赖属性支持具有单向绑定行为的数据绑定。 如果没有此类应用程序的方案，则可以禁用数据绑定（因为它们是灵活且可扩展的，所以在默认 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Api 中没有此类属性的很多示例）。 你可以将绑定设置为对在其组件块（例如<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A>）中的控件行为相互关联的属性使用双向默认值，或者双向绑定是用户的常见和预期方案（<xref:System.Windows.Controls.TextBox.Text%2A> 为示例）。 更改与数据绑定相关的元数据只会影响默认值；始终可以根据各个绑定更改此默认值。 若要详细了解常规的绑定模式和绑定，请参阅[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)。  
  
- 报告支持日志记录的应用程序或服务是否应记录属性（<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>）。 对于一般的元素，默认情况下不会启用日记记录功能，但可针对特定用户输入控件有选择性地启用。 此属性专门由日记记录的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 实现等日记记录服务读取，并且通常针对用户控件（例如用户在列表中选择的应在各导航步骤中保留的控件）设置此属性。 有关日记的信息，请参阅[导航概述](../app-development/navigation-overview.md)。  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## <a name="reading-frameworkpropertymetadata"></a>读取 FrameworkPropertyMetadata  
 以上链接的每个属性都是 <xref:System.Windows.FrameworkPropertyMetadata> 添加到其直接基类 <xref:System.Windows.UIPropertyMetadata>的特定属性。 默认情况下，这些属性都为 `false`。 在知道这些属性的值的情况下，属性的元数据请求应尝试将返回的元数据强制转换为 <xref:System.Windows.FrameworkPropertyMetadata>，然后根据需要检查各个属性的值。  
  
<a name="Specifying_Metadata"></a>   
## <a name="specifying-metadata"></a>指定元数据  
 当你创建新的元数据实例以将元数据应用于新的依赖属性注册时，你可以选择要使用的元数据类：基本 <xref:System.Windows.PropertyMetadata> 或某个派生类（如 <xref:System.Windows.FrameworkPropertyMetadata>）。 通常情况下，应使用 <xref:System.Windows.FrameworkPropertyMetadata>，特别是在属性与属性系统和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 函数（如布局和数据绑定）的任何交互时。 对于更复杂的方案，另一个选项是从 <xref:System.Windows.FrameworkPropertyMetadata> 派生，以创建自己的元数据报告类，并在其成员中携带额外的信息。 或者，您可以使用 <xref:System.Windows.PropertyMetadata> 或 <xref:System.Windows.UIPropertyMetadata> 来传达对实现功能的支持程度。  
  
 对于现有属性（<xref:System.Windows.DependencyProperty.AddOwner%2A> 或 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 调用），应始终使用初始注册使用的元数据类型重写。  
  
 如果要创建 <xref:System.Windows.FrameworkPropertyMetadata> 实例，可通过两种方法使用传达框架属性特征的特定属性的值填充该元数据：  
  
1. 使用允许 `flags` 参数 <xref:System.Windows.FrameworkPropertyMetadata> 构造函数签名。 应为此参数填充 <xref:System.Windows.FrameworkPropertyMetadataOptions> 枚举标志的所有所需的组合值。  
  
2. 使用不带 `flags` 参数的其中一个签名，然后将 <xref:System.Windows.FrameworkPropertyMetadata> 上的每个报表布尔属性设置为每个所需的特征更改 `true`。 为此，必须在构造具有此依赖属性的任何元素之前对这些属性进行设置；布尔属性是可读写属性，以允许此项避免 `flags` 参数的行为，同时仍然可以填充元数据，但元数据必须在属性使用之前进行有效密封。 因此，尝试在请求元数据之后设置属性是无效操作。  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## <a name="framework-property-metadata-merge-behavior"></a>框架属性元数据合并行为  
 重写框架属性元数据时，会合并或替换不同的元数据特征。  
  
- 合并 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>。 如果添加新的 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>，则该回调将存储在元数据中。 如果未在重写中指定 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>，则 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 的值将从在元数据中指定的最接近的上级中升级为引用。  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 的实际属性系统行为是：保留层次结构中所有元数据所有者的实现并将其添加到表中，属性系统执行顺序是调用最深层派生类的回调1. 继承的回叫仅运行一次，当将这些回叫放置在元数据中的类占有时计数。  
  
- 替换 <xref:System.Windows.PropertyMetadata.DefaultValue%2A>。 如果未在替代中指定 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>，则 <xref:System.Windows.PropertyMetadata.DefaultValue%2A> 的值来自在元数据中指定它的最接近的上级。  
  
- 替换 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 实现。 如果添加新的 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>，则该回调将存储在元数据中。 如果未在重写中指定 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>，则 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 的值将从在元数据中指定的最接近的上级中升级为引用。  
  
- 属性系统行为是只调用直接元数据中的 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>。 不会保留对层次结构中的其他 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 实现的引用。  
  
- <xref:System.Windows.FrameworkPropertyMetadataOptions> 枚举的标志合并为按位 "或" 运算。  如果指定 <xref:System.Windows.FrameworkPropertyMetadataOptions>，则不会覆盖原始选项。  若要更改选项，请在 <xref:System.Windows.FrameworkPropertyMetadata>上设置相应的属性。 例如，如果原始 <xref:System.Windows.FrameworkPropertyMetadata> 对象设置了 <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> 标志，则可以通过将 <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> 设置为 `false`来更改该标志。  
  
 此行为由 <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>实现，并且可在派生的元数据类上重写。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [依赖属性元数据](dependency-property-metadata.md)
- [依赖项属性概述](dependency-properties-overview.md)
- [自定义依赖属性](custom-dependency-properties.md)
