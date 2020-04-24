---
title: 自定义依赖项属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- implementing [WPF], wrappers
- registering properties [WPF]
- properties [WPF], metadata
- metadata [WPF], for properties
- custom dependency properties [WPF]
- properties [WPF], registering
- wrappers [WPF], implementing
- dependency properties [WPF], custom
ms.assetid: e6bfcfac-b10d-4f58-9f77-a864c2a2938f
ms.openlocfilehash: e4117d7add2a34d6d989d9222e7688361cf6b379
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646357"
---
# <a name="custom-dependency-properties"></a>自定义依赖项属性

本主题介绍了 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 应用程序开发者和组件作者想要创建自定义依赖属性的原因，并介绍了一些可以提高属性的性能、可用性或通用性的实现步骤以及实现选项。

<a name="prerequisites"></a>

## <a name="prerequisites"></a>先决条件

本主题假设你作为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 类的现有依赖属性的使用者已经对依赖属性有所了解，并且已经阅读了[依赖属性概述](dependency-properties-overview.md)主题。 若要理解本主题中的示例，还应当了解 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 并知道如何编写 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序。

<a name="whatis"></a>

## <a name="what-is-a-dependency-property"></a>什么是依赖属性？

您可以启用本来是通用语言运行时 （CLR） 属性，通过将其作为依赖项属性实现来支持样式设置、数据绑定、继承、动画和默认值。 依赖项属性[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]是通过调用<xref:System.Windows.DependencyProperty.Register%2A>方法 （或<xref:System.Windows.DependencyProperty.RegisterReadOnly%2A>） 并在<xref:System.Windows.DependencyProperty>标识符字段中备份的属性在属性系统中注册的属性。 依赖项属性只能<xref:System.Windows.DependencyObject>由类型使用，但在<xref:System.Windows.DependencyObject>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]类层次结构中相当高，因此 中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]大多数可用的类可以支持依赖项属性。 有关依赖项属性以及用于在此 SDK 中描述它们的一些术语和约定的详细信息，请参阅[依赖项属性概述](dependency-properties-overview.md)。

<a name="example_dp"></a>

## <a name="examples-of-dependency-properties"></a>依赖属性示例

在类[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]上实现的依赖项属性的示例<xref:System.Windows.Controls.Control.Background%2A>包括属性、<xref:System.Windows.FrameworkElement.Width%2A>属性和<xref:System.Windows.Controls.TextBox.Text%2A>属性等。 类公开的每个依赖项属性都有在同一类上公开的相应的公共静态<xref:System.Windows.DependencyProperty>类型字段。 这是依赖属性的标识符。 此标识符的命名约定为：依赖属性名称后面加上字符串 `Property`。 例如，属性的<xref:System.Windows.DependencyProperty><xref:System.Windows.Controls.Control.Background%2A>相应标识符字段为<xref:System.Windows.Controls.Control.BackgroundProperty>。 标识符在注册时存储有关依赖项属性的信息，然后标识符稍后用于涉及依赖项属性的其他操作，如调用<xref:System.Windows.DependencyObject.SetValue%2A>。

如[依赖项属性概述](dependency-properties-overview.md)中所述，由于实现"包装[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]"，中的所有依赖项属性（大多数附加属性除外）也是 CLR 属性。 因此，通过代码，可以通过调用 CLR 访问器来获取或设置依赖项属性，这些访问器以与其他 CLR 属性相同的方式定义包装器。 作为已建立的依赖项属性的使用者，您通常不使用<xref:System.Windows.DependencyObject>与基础属性系统<xref:System.Windows.DependencyObject.GetValue%2A>的连接<xref:System.Windows.DependencyObject.SetValue%2A>点的方法和 。 <xref:System.Windows.DependencyObject.GetValue%2A>相反，CLR 属性的现有实现已经调用，并在<xref:System.Windows.DependencyObject.SetValue%2A>属性的`get`和`set`包装器实现中，适当地使用标识符字段。 若要自己实现自定义依赖属性，则需要使用类似的方法定义包装器。

<a name="backing_with_dp"></a>

## <a name="when-should-you-implement-a-dependency-property"></a>应该何时实现依赖属性？

在类上实现属性时，只要类派生自<xref:System.Windows.DependencyObject>，可以选择使用<xref:System.Windows.DependencyProperty>标识符支持属性，从而使该属性成为依赖项属性。 不必总是将属性实现为依赖属性，这不一定合适，具体取决于方案需要。 有时，使用私有字段支持属性的通常方法已足够满足需求。 但是，如果要使属性支持以下一个或多个 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 功能，则应该将属性实现为依赖属性：

- 需要可以在样式中设置属性。 有关详细信息，请参阅[样式和模板](../../../desktop-wpf/fundamentals/styles-templates-overview.md)化。

- 需要属性支持数据绑定。 有关数据绑定依赖属性的详细信息，请参阅[绑定两个控件的属性](../data/how-to-bind-the-properties-of-two-controls.md)。

- 需要可以使用动态资源引用设置属性。 有关详细信息，请参阅 [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。

- 需要从元素树中的父元素自动继承属性值。 在这种情况下，请向 方法<xref:System.Windows.DependencyProperty.RegisterAttached%2A>注册，即使您也为 CLR 访问创建了属性包装器。 有关详细信息，请参阅[属性值继承](property-value-inheritance.md)。

- 需要属性可以进行动画处理。 有关详细信息，请参阅 [动画概述](../graphics-multimedia/animation-overview.md)。

- 需要属性系统在先前的值因属性系统、环境或用户执行的操作而发生更改，或者因读取和使用样式而发生更改时进行报告。 通过使用属性元素据，属性可以指定回调方法，每次属性系统确定属性值已明确改动时将调用此回调方法。 与此相关的一个概念是属性值强制转换。 有关详细信息，请参阅[依赖属性回调和验证](dependency-property-callbacks-and-validation.md)。

- 需要使用同时也被 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 进程使用的已建立的元数据约定，例如报告更改属性值是否应需要布局系统重新安排元素的可视内容。 或者需要能够使用元素据替代，以便派生类可以更改基于元数据的特性，例如默认值。

- 您希望自定义控件的属性接收 Visual Studio WPF 设计器支持，例如**属性**窗口编辑。 有关详细信息，请参阅[控件创作概述](../controls/control-authoring-overview.md)。

检查这些方案时，还应考虑是否可以通过替代现有依赖属性的元素据而不是通过实现一个全新的属性来实现方案。 元素据替代是否可行取决于方案以及方案与现有的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 依赖属性和类中的实现的相似度。 有关替代现有属性上的元素据的详细信息，请参阅[依赖属性元素据](dependency-property-metadata.md)。

<a name="checklist"></a>

## <a name="checklist-for-defining-a-dependency-property"></a>定义依赖属性的检查清单

定义依赖属性包含 4 个不同的概念。 这些概念并不一定是严格的过程步骤，因为其中一些概念在实现中会被合并为一行代码：

- （可选）创建依赖属性的属性元素据。

- 在属性系统中注册属性名称，并指定所有者类型和属性值类型。 此外，还应指定属性元素据（如果用到）。

- 将<xref:System.Windows.DependencyProperty>标识符定义为`public``static``readonly`所有者类型的字段。

- 定义 CLR"包装器"属性，其名称与依赖项属性的名称匹配。 实现 CLR"包装器"属性`get`和`set`访问器，以便与支持它的依赖项属性连接。

<a name="registering"></a>

### <a name="registering-the-property-with-the-property-system"></a>在属性系统中注册属性

为使属性成为依赖属性，必须在属性系统维护的表中注册该属性，并为属性指定一个唯一标识符。此唯一标识符会用作后续属性系统操作的限定符。 这些操作可能是内部操作，或者您自己的代码调用属性系统 API。 要注册该属性，请在类正文<xref:System.Windows.DependencyProperty.Register%2A>中调用 方法（类内部，但超出任何成员定义）。 标识符字段也由<xref:System.Windows.DependencyProperty.Register%2A>方法调用作为返回值提供。 <xref:System.Windows.DependencyProperty.Register%2A>调用是在其他成员定义之外完成的，因为您使用此返回值作为类的一`public``static``readonly`部分分配和创建类型<xref:System.Windows.DependencyProperty>字段。 此字段会作为依赖属性的标识符。

[!code-csharp[WPFAquariumSln#RegisterAG](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerag)]
[!code-vb[WPFAquariumSln#RegisterAG](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerag)]

<a name="nameconventions"></a>

### <a name="dependency-property-name-conventions"></a>依赖属性命名约定

必需完全遵循已有的依赖属性命名约定，例外情况除外。

依赖项属性本身将具有基本名称"水族馆图"，如本示例中所示，该名称作为<xref:System.Windows.DependencyProperty.Register%2A>的第一个参数给出。 此名称在每个注册类型内必须唯一。 通过基类型继承的依赖属性会被视为注册类型的已有部分；无法再次注册已继承属性的名称。 但是，即使不继承依赖属性，也有方法可将类添加为依赖属性的所有者；有关详细信息，请参阅[依赖属性元素据](dependency-property-metadata.md)。

创建标识符字段时，按注册时的属性名称命名此字段，再加上后缀 `Property`。 此字段是依赖项属性的标识符，稍后将用作包装器中要进行的<xref:System.Windows.DependencyObject.SetValue%2A>和<xref:System.Windows.DependencyObject.GetValue%2A>调用的输入、您自己的代码对该属性的任何其他代码访问、您允许的任何外部代码访问、属性系统以及可能由[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器访问。

> [!NOTE]
> 在类的主体中定义依赖属性是典型的实现，但也可以在类静态构造函数中定义依赖属性。 需要多行代码来初始化依赖属性时，此方法会很有用。

<a name="wrapper1"></a>

### <a name="implementing-the-wrapper"></a>实现“包装器”

包装<xref:System.Windows.DependencyObject.GetValue%2A>器实现应在`get`实现和<xref:System.Windows.DependencyObject.SetValue%2A>`set`实现中调用（此处也显示原始注册调用和字段，以便清楚）。

在除了特殊情况外，包装器实现应分别执行 和<xref:System.Windows.DependencyObject.GetValue%2A><xref:System.Windows.DependencyObject.SetValue%2A>操作。 其原因请参阅 [XAML 加载和依赖属性](xaml-loading-and-dependency-properties.md)主题。

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 类上提供的所有现有公共依赖属性都使用这一简单的包装器实现模型；大多数情况下，依赖属性工作原理的复杂性本质上在于它是属性系统的行为，还是通过其他概念（例如强制转换或通过属性元数据进行的属性更改回调）实现的行为。

[!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
[!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]

同样，按照惯例，包装器属性的名称必须与选择的名称相同，并作为注册该属性的<xref:System.Windows.DependencyProperty.Register%2A>调用的第一个参数给出。 如果属性不遵从此约定，尽管不一定会禁用所有可能的用法，但你会遇到几个比较突出的问题：

- 样式和模板的某些方面不起作用。

- 大多数工具和设计器必须依赖命名约定，才能正确序列化 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 或在每个属性级别提供设计器环境帮助。

- 加载程序的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]当前实现完全绕过包装器，在处理属性值时依赖于命名约定。 有关详细信息，请参阅 [XAML 加载和依赖属性](xaml-loading-and-dependency-properties.md)。

<a name="metadata"></a>

### <a name="property-metadata-for-a-new-dependency-property"></a>新依赖属性的属性元数据

注册依赖属性时，通过属性系统进行注册会创建一个存储属性特征的元素据对象。 如果属性注册了<xref:System.Windows.DependencyProperty.Register%2A>的简单签名，则这些特征中有许多具有默认设置。 的其他签名<xref:System.Windows.DependencyProperty.Register%2A>允许您在注册属性时指定所需的元数据。 为依赖属性使用的最常见元数据是为其使用默认值。该默认值适用于使用此属性的新实例。

如果要创建存在于 派生类的依赖项属性，则可以使用更专用的<xref:System.Windows.FrameworkElement>元数据类<xref:System.Windows.FrameworkPropertyMetadata>而不是基<xref:System.Windows.PropertyMetadata>类。 类的<xref:System.Windows.FrameworkPropertyMetadata>构造函数具有多个签名，您可以在其中组合指定各种元数据特征。 如果只想指定默认值，请使用采用类型 为<xref:System.Object>的单个参数的签名。 将该对象参数作为属性的特定于类型的默认值传递（提供的默认值必须是您在`propertyType`<xref:System.Windows.DependencyProperty.Register%2A>调用中作为参数提供的类型）。

对于<xref:System.Windows.FrameworkPropertyMetadata>，还可以为属性指定元数据选项标志。 注册后这些标记会转换为属性元素据上的不同属性，并用于将某些条件传送给布局引擎等其他进程。

#### <a name="setting-appropriate-metadata-flags"></a>设置合适的元数据标记

- 如果属性（或其值的更改）影响[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]，并且特别影响布局系统在页中的大小或呈现元素的方式，请设置以下一个或多个标志： <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure>。 <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange> <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>。

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure>指示对此属性的更改需要更改为[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]呈现，其中包含对象可能需要父对象中或多或少的空间。 例如，“宽度”属性应该设置此标记。

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>指示对此属性的更改需要更改[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]渲染，这通常不需要在专用空间中进行更改，但确实表示空间中的定位已更改。 例如，“对齐”属性应该设置此标记。

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>指示发生了一些其他更改，这些更改不会影响布局和度量值，但确实需要另一个渲染。 更改现有元素的颜色的属性便是一个示例，例如“背景”。

  - 对属性系统或布局回调进行自己的替代实现时，这些标记通常用作元数据中的协议。 例如，如果实例的任何属性报告<xref:System.Windows.DependencyObject.OnPropertyChanged%2A>值更改且其元数据<xref:System.Windows.UIElement.InvalidateArrange%2A>中具有<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>，`true`则可能具有回调。

- 超出上述所需大小时，某些属性可能会影响所含父元素的呈现特征。 例如，流文档<xref:System.Windows.Documents.Paragraph.MinOrphanLines%2A>模型中使用的属性，其中对该属性的更改可以更改包含段落的流文档的总体呈现。 使用<xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentArrange><xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentMeasure>或在您自己的属性中识别类似情况。

- 默认情况下，依赖属性支持数据绑定。 在无实际的数据绑定方案或大型对象的数据绑定性能构成问题的情况下，可有意禁用数据绑定。

- 默认情况下，依赖项属性<xref:System.Windows.Data.Binding.Mode%2A>的数据绑定默认为<xref:System.Windows.Data.BindingMode.OneWay>。 您可以随时将绑定更改为<xref:System.Windows.Data.BindingMode.TwoWay>每个绑定实例;因此，您可以将绑定更改为每个绑定实例。有关详细信息，请参阅[指定绑定的方向](../data/how-to-specify-the-direction-of-the-binding.md)。 但是，作为依赖项属性作者，您可以选择使属性默认使用<xref:System.Windows.Data.BindingMode.TwoWay>绑定模式。 现有依赖项属性的示例是<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A?displayProperty=nameWithType>。此属性的方案是<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A>设置逻辑和组合与<xref:System.Windows.Controls.MenuItem>默认主题样式交互。 属性<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A>逻辑使用本机绑定的数据来根据其他状态属性和方法调用维护属性的状态。 默认情况下绑定<xref:System.Windows.Data.BindingMode.TwoWay>的另一个示例属性是<xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>。

- 还可以通过设置<xref:System.Windows.FrameworkPropertyMetadataOptions.Inherits>标志在自定义依赖项属性中启用属性继承。 在父元素和子元素具有相同属性的情况中，属性继承非常有用，它可以使子元素将该特定属性值设置为与父元素设置的值相同。 可继承属性的示例为<xref:System.Windows.FrameworkElement.DataContext%2A>，用于绑定操作，以启用数据表示的重要主详细信息方案。 通过使<xref:System.Windows.FrameworkElement.DataContext%2A>可继承，任何子元素也继承该数据上下文。 因为使用了属性值继承，你可以在页面或应用程序根目录上指定数据上下文，而无需对所有可能子元素中的绑定重新指定上下文。 <xref:System.Windows.FrameworkElement.DataContext%2A>也是一个很好的例子，说明继承重写默认值，但它始终可以在本地设置在任何特定的子元素上;有关详细信息，请参阅[使用具有分层数据的主详细信息模式](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)。 属性值继承确实可能存在性能成本，因此应谨慎使用；有关详细信息，请参阅[属性值继承](property-value-inheritance.md)。

- 设置标志<xref:System.Windows.FrameworkPropertyMetadataOptions.Journal>以指示是否应检测到依赖项属性或由导航日记服务使用。 属性就是一<xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>个示例;导航日记历史记录时，应保留选择控件中选择的任何项。

<a name="RODP"></a>

## <a name="read-only-dependency-properties"></a>只读依赖项属性

可以定义只读的依赖属性。 但是，为何将属性定义为只读的情况略有不同，其过程与在属性系统中注册属性并公开标识符相同。 有关详细信息，请参阅[只读依赖属性](read-only-dependency-properties.md)。

<a name="CTDP"></a>

## <a name="collection-type-dependency-properties"></a>集合类型依赖项属性

集合类型依赖属性要考虑一些其他实现问题。 有关详细信息，请参阅[集合类型依赖属性](collection-type-dependency-properties.md)。

<a name="SecurityC"></a>

## <a name="dependency-property-security-considerations"></a>依赖属性安全注意事项

依赖属性应声明为公共属性。 依赖属性标识符字段应声明为公共静态字段。 即使您尝试声明其他访问级别（如受保护），也始终可以通过标识符与属性系统 API 一起访问依赖项属性。 由于元数据报告或作为属性系统的一部分的值确定 API（如<xref:System.Windows.LocalValueEnumerator>），即使受保护的标识符字段也可能访问。 有关详细信息，请参阅[依赖属性的安全性](dependency-property-security.md)。

<a name="DPCtor"></a>

## <a name="dependency-properties-and-class-constructors"></a>依赖属性和类构造函数

托管代码编程（通常通过FxCop 等代码分析工具强制执行）的一般原则是：类构造函数不应调用虚方法。 这是因为构造函数可以作为派生的类构造函数的基本初始化来调用，并且可能会在所构造的对象实例不完全初始化状态下通过构造函数输入虚方法。 当您从已经派生的任何<xref:System.Windows.DependencyObject>类派生时，应注意属性系统本身在内部调用并公开虚拟方法。 这些虚方法属于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性系统服务。 替代方法会使派生类参与值确定。 为避免运行时初始化出现潜在问题，，不应该在类的构造函数中设置依赖属性值，除非遵循特定的构造函数模式进行操作。 有关详细信息，请参阅 [DependencyObject 的安全构造函数模式](safe-constructor-patterns-for-dependencyobjects.md)。

## <a name="see-also"></a>另请参阅

- [依赖项属性概述](dependency-properties-overview.md)
- [依赖项属性元数据](dependency-property-metadata.md)
- [控件创作概述](../controls/control-authoring-overview.md)
- [集合类型依赖项属性](collection-type-dependency-properties.md)
- [依赖项属性的安全性](dependency-property-security.md)
- [XAML 加载和依赖项属性](xaml-loading-and-dependency-properties.md)
- [DependencyObject 的安全构造函数模式](safe-constructor-patterns-for-dependencyobjects.md)
