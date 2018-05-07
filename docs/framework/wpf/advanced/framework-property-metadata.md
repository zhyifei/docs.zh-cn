---
title: 框架属性元数据
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: d968bc7a3033bd994590520c5cd5062d3c212b4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="framework-property-metadata"></a>框架属性元数据
对于 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 体系结构中被视为 WPF 框架级的对象元素的属性，将报告框架属性元数据选项。 通常，WPF 框架级指示要求 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 演示 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 和可执行文件处理呈现、数据绑定和属性系统优化等功能。 这些系统对框架属性元数据进行查询，以便为特定的元素属性确定特定于功能的特征。  
  
 
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>先决条件  
 本主题假定你从 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 类的现有依赖属性的使用者角度了解依赖属性，并且已阅读[依赖属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)。 另外，应当已阅读[依赖属性元数据](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)。  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## <a name="what-is-communicated-by-framework-property-metadata"></a>框架属性元数据传达的信息  
 框架属性元数据分为以下类别：  
  
-   报告的影响元素布局属性 (<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>， <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>， <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>)。 只有当的属性会影响这些各自方面的问题，并且你要实现，可能会在元数据中设置这些标志<xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>在类中提供具体的呈现行为和到布局的信息的方法系统。 通常，如果在属性元数据中有布局属性为 true，则此类实现会在依赖属性中检查属性是否无效，并且只有无效属性才必须请求新的布局处理过程。  
  
-   报告的影响元素的父元素布局属性 (<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>， <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>)。 默认情况下设置了这些标志一些示例包括<xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType>和<xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>。  
  
-   <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>。 默认情况下，依赖属性不会继承值。 <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A> 允许的继承路径进入可视化树中，这是某些控件组合方案所必需的途径。  
  
    > [!NOTE]
    >  属性值上下文中的术语“继承”指特定于依赖属性的情况；它意味着由于存在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性系统的 WPF 框架级功能，子元素可以从父元素继承实际的依赖属性值。 它与通过派生类型的托管代码类型和成员继承没有直接关系。 有关详细信息，请参阅[属性值继承](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)。  
  
-   报告数据绑定特性 (<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>， <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>)。 默认情况下，框架中的依赖属性支持具有单向绑定行为的数据绑定。 如果数据绑定没有适用的方案，则可禁用数据绑定（因为这些属性应该是灵活且可扩展的，所以在默认的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 中没有太多此类属性的示例）。 您可以设置要将绑定在一起在其组件部分之间的控件的行为的属性的双向默认绑定 (<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A>是一个示例) 或双向绑定，其中是用户的常见和预期方案 (<xref:System.Windows.Controls.TextBox.Text%2A>是一个示例)。 更改与数据绑定相关的元数据只会影响默认值；始终可以根据各个绑定更改此默认值。 若要详细了解常规的绑定模式和绑定，请参阅[数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)。  
  
-   报告属性是否应由应用程序或支持日志记录服务日志 (<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>)。 对于一般的元素，默认情况下不会启用日记记录功能，但可针对特定用户输入控件有选择性地启用。 此属性专门由日记记录的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 实现等日记记录服务读取，并且通常针对用户控件（例如用户在列表中选择的应在各导航步骤中保留的控件）设置此属性。 有关日记的信息，请参阅[导航概述](../../../../docs/framework/wpf/app-development/navigation-overview.md)。  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## <a name="reading-frameworkpropertymetadata"></a>读取 FrameworkPropertyMetadata  
 每个以上链接的属性是特定的属性，<xref:System.Windows.FrameworkPropertyMetadata>将添加到其直接基类<xref:System.Windows.UIPropertyMetadata>。 默认情况下，这些属性都为 `false`。 其中了解这些属性的值是重要的属性元数据请求应尝试强制转换为返回的元数据<xref:System.Windows.FrameworkPropertyMetadata>，，然后根据需要检查的各个属性的值。  
  
<a name="Specifying_Metadata"></a>   
## <a name="specifying-metadata"></a>指定元数据  
 在创建供将元数据应用于新注册的依赖项属性的新元数据实例时，你可以选择要使用哪些元数据类： 基<xref:System.Windows.PropertyMetadata>或某些派生类，如<xref:System.Windows.FrameworkPropertyMetadata>。 一般情况下，应使用<xref:System.Windows.FrameworkPropertyMetadata>，尤其是在你的属性具有与属性系统的任何交互和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]如布局和数据绑定的函数。 有关更复杂的方案的另一个选项是派生自<xref:System.Windows.FrameworkPropertyMetadata>创建你自己的元数据报表使用的额外信息的类成员中执行。 你也可以<xref:System.Windows.PropertyMetadata>或<xref:System.Windows.UIPropertyMetadata>通信对您的实现的功能的支持程度。  
  
 对于现有的属性 (<xref:System.Windows.DependencyProperty.AddOwner%2A>或<xref:System.Windows.DependencyProperty.OverrideMetadata%2A>调用)，则应始终会重写与原始注册使用的元数据类型。  
  
 如果要创建<xref:System.Windows.FrameworkPropertyMetadata>实例时，有两种方法来填充该元数据与特定通信框架属性特性的属性的值：  
  
1.  使用<xref:System.Windows.FrameworkPropertyMetadata>构造函数的签名，使`flags`参数。 此参数应为所需的全部组合值填充<xref:System.Windows.FrameworkPropertyMetadataOptions>枚举标志。  
  
2.  使用不签名之一`flags`参数，并将每个报告布尔属性<xref:System.Windows.FrameworkPropertyMetadata>到`true`每个所需特征的更改。 为此，必须在构造具有此依赖属性的任何元素之前对这些属性进行设置；布尔属性是可读写属性，以允许此项避免 `flags` 参数的行为，同时仍然可以填充元数据，但元数据必须在属性使用之前进行有效密封。 因此，尝试在请求元数据之后设置属性是无效操作。  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## <a name="framework-property-metadata-merge-behavior"></a>框架属性元数据合并行为  
 重写框架属性元数据时，会合并或替换不同的元数据特征。  
  
-   <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 合并。 如果你添加新<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>，该回调将存储在元数据。 如果不指定<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>中重写时，值<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>提升为从元数据中指定的最近上级的引用。  
  
-   实际的属性系统行为<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>是实现为层次结构中的所有元数据所有者会保留，并添加到表中，使用属性系统的最深派生的类的回调的执行顺序第一次调用。 继承的回叫仅运行一次，当将这些回叫放置在元数据中的类占有时计数。  
  
-   <xref:System.Windows.PropertyMetadata.DefaultValue%2A> 将被替换。 如果不指定<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>中重写时，值<xref:System.Windows.PropertyMetadata.DefaultValue%2A>来自元数据中指定的最近上级。  
  
-   <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 实现将被替换。 如果你添加新<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>，该回调将存储在元数据。 如果不指定<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>中重写时，值<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>提升为从元数据中指定的最近上级的引用。  
  
-   属性的系统行为是仅<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>调用即时元数据中。 没有对其他引用<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>保留层次结构中的实现。  
  
-   所用的标志<xref:System.Windows.FrameworkPropertyMetadataOptions>枚举合并为按位或运算。  如果指定<xref:System.Windows.FrameworkPropertyMetadataOptions>，不会覆盖原始的选项。  若要更改某个选项，设置对应的属性上<xref:System.Windows.FrameworkPropertyMetadata>。 例如，如果原始<xref:System.Windows.FrameworkPropertyMetadata>对象集<xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType>标志，可以更改此默认设置<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType>到`false`。  
  
 通过实现此行为<xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>，和可以对派生的元数据类中重写。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.DependencyProperty.GetMetadata%2A>  
 [依赖属性元数据](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)  
 [依赖项属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [自定义依赖属性](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
