---
title: 框架属性元数据
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: 8fb6e1b4cf6aed9454e9e9f1a77277d2f3611ca8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186651"
---
# <a name="framework-property-metadata"></a>框架属性元数据
对于 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 体系结构中被视为 WPF 框架级的对象元素的属性，将报告框架属性元数据选项。 通常，WPF 框架级别指定需要由[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]呈现 API 和可执行文件处理呈现、数据绑定和属性系统优化等功能。 这些系统对框架属性元数据进行查询，以便为特定的元素属性确定特定于功能的特征。  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>系统必备  
 本主题假定你从 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 类的现有依赖属性的使用者角度了解依赖属性，并且已阅读[依赖属性概述](dependency-properties-overview.md)。 另外，应当已阅读[依赖属性元数据](dependency-property-metadata.md)。  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>
## <a name="what-is-communicated-by-framework-property-metadata"></a>框架属性元数据传达的信息  
 框架属性元数据分为以下类别：  
  
- 影响元素 （的报表布局属性<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>。 如果属性影响这些相关方面，并且还在实现<xref:System.Windows.FrameworkElement.MeasureOverride%2A> / <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>类中的方法向布局系统提供特定的呈现行为和信息，则可以在元数据中设置这些标志。 通常，如果在属性元数据中有布局属性为 true，则此类实现会在依赖属性中检查属性是否无效，并且只有无效属性才必须请求新的布局处理过程。  
  
- 影响元素的父元素 （） 的报告布局属性<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A> <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>。 默认情况下设置这些标志的一些示例是<xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType>和<xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>。  
  
- <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>. 默认情况下，依赖属性不会继承值。 <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A>允许继承路径也进入可视化树，这是某些控制合成方案所必需的。  
  
    > [!NOTE]
    > 属性值上下文中的术语“继承”指特定于依赖属性的情况；它意味着由于存在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性系统的 WPF 框架级功能，子元素可以从父元素继承实际的依赖属性值。 它与通过派生类型的托管代码类型和成员继承没有直接关系。 有关详细信息，请参阅[属性值继承](property-value-inheritance.md)。  
  
- 报告数据绑定特征<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>（。 <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A> 默认情况下，框架中的依赖属性支持具有单向绑定行为的数据绑定。 如果没有任何方案，则可以禁用数据绑定（因为它们旨在灵活且可扩展，因此默认[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]API 中此类属性的示例并不多）。 您可以将绑定设置为具有双向默认值，这些属性将控件的行为绑定到其组件部分（<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A>示例），或者双向绑定是用户常见和预期方案（<xref:System.Windows.Controls.TextBox.Text%2A>示例）。 更改与数据绑定相关的元数据只会影响默认值；始终可以根据各个绑定更改此默认值。 若要详细了解常规的绑定模式和绑定，请参阅[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)。  
  
- 报告是否应由支持日记的应用程序或服务进行日记。<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A> 对于一般的元素，默认情况下不会启用日记记录功能，但可针对特定用户输入控件有选择性地启用。 此属性专门由日记记录的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 实现等日记记录服务读取，并且通常针对用户控件（例如用户在列表中选择的应在各导航步骤中保留的控件）设置此属性。 有关日记的信息，请参阅[导航概述](../app-development/navigation-overview.md)。  
  
<a name="Reading_FrameworkPropertyMetadata"></a>
## <a name="reading-frameworkpropertymetadata"></a>读取 FrameworkPropertyMetadata  
 上面链接的每个属性都是添加到<xref:System.Windows.FrameworkPropertyMetadata>其直接基类<xref:System.Windows.UIPropertyMetadata>的特定属性。 默认情况下，这些属性都为 `false`。 知道这些属性的值很重要的属性的元数据请求应尝试将返回的元数据强制转换为<xref:System.Windows.FrameworkPropertyMetadata>，然后根据需要检查各个属性的值。  
  
<a name="Specifying_Metadata"></a>
## <a name="specifying-metadata"></a>指定元数据  
 当您创建新的元数据实例以将元数据应用于新的依赖项属性注册时，您可以选择要使用的元数据类：基<xref:System.Windows.PropertyMetadata>或某些派生类（如<xref:System.Windows.FrameworkPropertyMetadata>）。 通常，应使用<xref:System.Windows.FrameworkPropertyMetadata>，特别是如果属性与属性系统和布局和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]数据绑定等函数有任何交互。 更复杂的方案的另一个选项是从中派生<xref:System.Windows.FrameworkPropertyMetadata>来创建自己的元数据报告类，其中包含了额外的信息。 或者，<xref:System.Windows.PropertyMetadata>您可以使用或<xref:System.Windows.UIPropertyMetadata>传达对实现功能的支持程度。  
  
 对于现有属性（<xref:System.Windows.DependencyProperty.AddOwner%2A>或<xref:System.Windows.DependencyProperty.OverrideMetadata%2A>调用），应始终使用原始注册使用的元数据类型进行重写。  
  
 如果要创建<xref:System.Windows.FrameworkPropertyMetadata>实例，有两种方法可以用传达框架属性特征的特定属性的值填充该元数据：  
  
1. 使用允许<xref:System.Windows.FrameworkPropertyMetadata>参数`flags`的构造函数签名。 此参数应用<xref:System.Windows.FrameworkPropertyMetadataOptions>枚举标记的所有所需组合值填充。  
  
2. 使用没有参数的签名之一`flags`，然后为每个所需的特征更改设置每个报告布尔属性。 <xref:System.Windows.FrameworkPropertyMetadata> `true` 为此，必须在构造具有此依赖属性的任何元素之前对这些属性进行设置；布尔属性是可读写属性，以允许此项避免 `flags` 参数的行为，同时仍然可以填充元数据，但元数据必须在属性使用之前进行有效密封。 因此，尝试在请求元数据之后设置属性是无效操作。  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>
## <a name="framework-property-metadata-merge-behavior"></a>框架属性元数据合并行为  
 重写框架属性元数据时，会合并或替换不同的元数据特征。  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>合并。 如果添加新<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>，则回调将存储在元数据中。 如果在重写<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>中未指定<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>.  
  
- 的实际<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>属性系统行为是保留层次结构中所有元数据所有者的实现并将其添加到表中，属性系统的执行顺序是首先调用最深入派生的类的回调。 继承的回叫仅运行一次，当将这些回叫放置在元数据中的类占有时计数。  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A>已更换。 如果在重写<xref:System.Windows.PropertyMetadata.DefaultValue%2A>中未指定<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>。  
  
- <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>将替换实现。 如果添加新<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>，则回调将存储在元数据中。 如果在重写<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>中未指定<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>.  
  
- 属性系统行为是仅调用直接元数据<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>中的。 不会保留对层次结构<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>中其他实现的引用。  
  
- <xref:System.Windows.FrameworkPropertyMetadataOptions>枚举标志合并为位或操作。  如果指定<xref:System.Windows.FrameworkPropertyMetadataOptions>，则原始选项不会覆盖。  要更改选项，在 上<xref:System.Windows.FrameworkPropertyMetadata>设置相应的属性。 例如，<xref:System.Windows.FrameworkPropertyMetadata>如果原始对象设置<xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType>标志，则可以通过设置为<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType>`false`更改该标志。  
  
 此行为由<xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>实现，可以在派生元数据类上重写。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [依赖属性元数据](dependency-property-metadata.md)
- [依赖项属性概述](dependency-properties-overview.md)
- [自定义依赖属性](custom-dependency-properties.md)
