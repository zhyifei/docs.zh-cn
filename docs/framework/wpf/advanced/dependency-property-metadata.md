---
title: 依赖项属性元数据
ms.date: 03/30/2017
helpviewer_keywords:
- APIs [WPF], metadata
- dependency properties [WPF], metadata
- metadata [WPF], for dependency properties
- overriding metadata [WPF]
ms.assetid: d01ed009-b722-41bf-b82f-fe1a8cdc50dd
ms.openlocfilehash: 3d84510fce69e81929cbe9b6088e12aaf3409769
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186367"
---
# <a name="dependency-property-metadata"></a>依赖项属性元数据
属性[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]系统包括一个元数据报告系统，该系统超出了通过反射或通用语言运行时 （CLR） 特征可以报告的属性的范围。 依赖属性的元数据还可以由定义依赖属性的类来唯一地分配，可以在依赖属性添加到另一个类时进行更改，可以由所有从定义基类继承依赖属性的派生类来明确地重写。  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>系统必备  
 本主题假定你从 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 类的现有依赖属性的使用者角度了解依赖属性，并且已阅读[依赖属性概述](dependency-properties-overview.md)。 若要理解本主题中的示例，还应当了解 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 并知道如何编写 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序。  
  
<a name="dp_metadata_contents"></a>
## <a name="how-dependency-property-metadata-is-used"></a>依赖属性元数据的使用方式  
 依赖属性的元数据作为一个对象存在，可以通过查询该对象来检查依赖属性的特征。 当属性系统处理任何给定的依赖属性时，也会经常访问这些元数据。 依赖属性的元数据对象可以包含以下类型的信息：  
  
- 依赖项属性的默认值，如果无法按本地值、样式、继承等为依赖项属性确定其他值。有关默认值在为依赖项属性分配值时如何参与属性系统使用的优先级的彻底讨论，请参阅[依赖项属性值优先级](dependency-property-value-precedence.md)。  
  
- 对影响每个所有者类型的强制行为或更改通知行为的回叫实现的引用。 请注意，这些回叫通常是用非公共访问级别定义的，因此，除非实际引用位于允许的访问范围内，否则通常无法从元数据获得这些引用。 有关依赖属性回叫的详细信息，请参阅[依赖属性回调和验证](dependency-property-callbacks-and-validation.md)。  
  
- 如果所讨论的依赖属性被视为一个 WPF 框架级别的属性，则元数据中可能包含 WPF 框架级别的依赖属性特征，这些特征报告各种服务（如 WPF 框架级别的布局引擎和属性继承逻辑）的信息和状态。 有关依赖属性元数据的这一方面的详细信息，请参阅[框架属性元数据](framework-property-metadata.md)。  
  
<a name="APIs"></a>
## <a name="metadata-apis"></a>元数据 API  
 报告属性系统使用的大部分元数据信息的类型是类<xref:System.Windows.PropertyMetadata>。 在向属性系统注册依赖属性时，可以选择指定元数据实例，并且可以为以下附加类型再次指定这些实例：将自身作为所有者添加的类型，或者重写它们从基类依赖属性定义继承的元数据的类型。 （对于属性注册不指定元数据的情况，使用该类的默认值<xref:System.Windows.PropertyMetadata>创建默认值。当您调用从<xref:System.Windows.PropertyMetadata><xref:System.Windows.DependencyObject>实例上的依赖项属性获取元数据的各种<xref:System.Windows.DependencyProperty.GetMetadata%2A>重载时，将返回已注册的元数据。  
  
 然后<xref:System.Windows.PropertyMetadata>派生类，为体系结构分区（如 WPF 框架级类）提供更具体的元数据。 <xref:System.Windows.UIPropertyMetadata>添加动画报告，并提供<xref:System.Windows.FrameworkPropertyMetadata>上一节中提到的 WPF 框架级属性。 注册依赖项属性时，可以对这些<xref:System.Windows.PropertyMetadata>派生类进行注册。 检查元数据时，可以将基<xref:System.Windows.PropertyMetadata>类型强制转换为派生类，以便可以检查更具体的属性。  
  
> [!NOTE]
> 可在 中<xref:System.Windows.FrameworkPropertyMetadata>指定的属性特征有时在本文档中称为"标志"。 创建新元数据实例以用于依赖项属性注册或元数据重写时，可以使用 Flagwise 枚<xref:System.Windows.FrameworkPropertyMetadataOptions>举指定这些值，然后将枚举的可能串联值供应给<xref:System.Windows.FrameworkPropertyMetadata>构造函数。 但是，一旦构造，这些选项特征将作为一系列<xref:System.Windows.FrameworkPropertyMetadata>布尔属性公开，而不是构造枚举值。 使用布尔属性，可以检查每个条件，而不必为了获得感兴趣的信息而向按标志枚举值应用掩码。 构造函数使用串联<xref:System.Windows.FrameworkPropertyMetadataOptions>来保持构造函数签名的长度合理，而实际构造的元数据公开离散属性，使查询元数据更加直观。  
  
<a name="override_or_subclass"></a>
## <a name="when-to-override-metadata-when-to-derive-a-class"></a>何时重写元数据以及何时派生类  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性系统已经建立了如下功能：在不必完全重新实现依赖属性的情况下，更改依赖属性的某些特征。 这是通过为特定类型上所存在的依赖属性构造不同的属性元数据实例来完成的。 请注意，现有的大多数依赖属性都不是虚拟属性，因此，严格地说，只能通过隐藏现有成员来针对继承类“重新实现”依赖属性。  
  
 如果尝试对某个类型的依赖属性启用的方案不能通过修改现有依赖属性的特征来完成，则可能有必要创建一个派生类，然后为该派生类声明一个自定义依赖属性。 自定义依赖项属性的行为与[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]API 定义的依赖项属性相同。 有关自定义依赖属性的更多详细信息，请参阅[自定义依赖属性](custom-dependency-properties.md)。  
  
 不能重写的依赖属性的一个显著特征就是它的值类型。 如果要继承的依赖属性的行为与所需的行为大体相同，但是要求它具有另一种类型，则必须实现一个自定义依赖属性，可能还需要通过类型转换或其他实现机制在自定义类上链接这些属性。 此外，您不能替换现有的<xref:System.Windows.ValidateValueCallback>，因为此回调存在于注册字段本身中，而不是在其元数据中。  
  
<a name="scenarios"></a>
## <a name="scenarios-for-changing-existing-metadata"></a>更改现有元数据的方案  
 如果要处理现有依赖属性的元数据，则更改依赖属性元数据的一种常见方案是更改默认值。 更改或添加属性系统回叫是一种更高级的方案。 如果所实现的派生类的依赖属性之间具有不同的相互关系，则你可能希望这样做。 让编程模型既支持代码又支持声明性用法的条件之一就是，属性必须能够按任何顺序设置。 因此，需要在没有上下文的情况下实时设置任何依赖属性，而且可以不必知道设置顺序（例如，可能在构造函数中找到的顺序）。 有关属性系统这一方面的详细信息，请参阅[依赖属性回调和验证](dependency-property-callbacks-and-validation.md)。 请注意，验证回叫不是元数据的一部分，而是依赖属性标识符的一部分。 因此，不能通过重写元数据来更改验证回叫。  
  
 在某些情况下，可能还希望在现有的依赖属性上改变 WPF 框架级别的属性元数据选项。 这些选项将有关 WPF 框架级别属性的某些已知条件传递到其他 WPF 框架级别的进程，例如布局系统。  设置选项通常仅在注册新的依赖项属性时完成，但也可以更改 WPF 框架级属性元数据作为 或<xref:System.Windows.DependencyProperty.OverrideMetadata%2A><xref:System.Windows.DependencyProperty.AddOwner%2A>调用的一部分。 有关要使用的特定值以及详细信息，请参阅[框架属性元数据](framework-property-metadata.md)。 有关应当如何为新注册的依赖属性设置这些选项的详细信息，请参阅[自定义依赖属性](custom-dependency-properties.md)。  
  
<a name="dp_override_metadata"></a>
### <a name="overriding-metadata"></a>重写元数据  
 重写元数据的主要目的在于，使你有机会更改各种派生自元数据的行为，这些行为应用于类型上存在的依赖属性。 [元数据](#dp_metadata_contents)一节中更详细地介绍了重写元数据的原因。 有关详细信息（包括一些代码示例），请参阅[重写依赖属性的元数据](how-to-override-metadata-for-a-dependency-property.md)。  
  
 可以在注册调用期间为依赖项属性提供属性元数据 。<xref:System.Windows.DependencyProperty.Register%2A> 但是，在许多情况下，当类继承该依赖属性时，你可能希望为该类提供特定于类型的元数据。 可以通过调用<xref:System.Windows.DependencyProperty.OverrideMetadata%2A>方法来执行此操作。  对于 API 中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的示例，<xref:System.Windows.FrameworkElement>类是首先注册<xref:System.Windows.UIElement.Focusable%2A>依赖项属性的类型。 但是，<xref:System.Windows.Controls.Control>该类重写依赖项属性的元数据以提供其自己的初始默认值，将其从`false`更改为`true`，然后重新使用原始<xref:System.Windows.UIElement.Focusable%2A>实现。  
  
 当你重写元数据时，系统会合并或替换不同的元数据特征。  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>合并。 如果添加新<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>，则回调将存储在元数据中。 如果在重写<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>中未指定<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>.  
  
- 的实际<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>属性系统行为是保留层次结构中所有元数据所有者的实现并将其添加到表中，属性系统的执行顺序是首先调用派生最多的类的回调。  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A>已更换。 如果在重写<xref:System.Windows.PropertyMetadata.DefaultValue%2A>中未指定<xref:System.Windows.PropertyMetadata.DefaultValue%2A>。  
  
- <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>将替换实现。 如果添加新<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>，则回调将存储在元数据中。 如果在重写<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>中未指定<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>.  
  
- 属性系统行为是仅调用直接元数据<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>中的。 不会保留对层次结构<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>中其他实现的引用。  
  
 此行为由<xref:System.Windows.PropertyMetadata.Merge%2A>实现，可以在派生元数据类上重写。  
  
#### <a name="overriding-attached-property-metadata"></a>重写附加属性元数据  
 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中，附加属性作为依赖属性来实现。 这意味着它们还具有能够由个别类重写的属性元数据。 中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]附加属性的范围注意事项通常是，任何<xref:System.Windows.DependencyObject>属性都可以在它们上设置附加属性。 因此，任何<xref:System.Windows.DependencyObject>派生类都可以覆盖任何附加属性的元数据，因为它可能在类的实例上设置。 可以重写默认值、回叫或 WPF 框架级别的特征报告属性。 如果针对类的实例设置了附加属性，则这些重写属性元数据特征将适用。 例如，可以重写默认值，这样，只要未以其他方式设置附加属性，重写值就会报告为类实例的附加属性的值。  
  
> [!NOTE]
> 该<xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>属性与附加属性无关。  
  
<a name="dp_add_owner"></a>
### <a name="adding-a-class-as-an-owner-of-an-existing-dependency-property"></a>将类作为现有依赖属性的所有者来添加  
 类可以使用<xref:System.Windows.DependencyProperty.AddOwner%2A>方法将自己添加为已注册的依赖项属性的所有者。 这使得该类可以使用最初针对另一个类型注册的依赖属性。 添加类通常不是首先将该依赖属性注册为所有者的类型的派生类。 实际上，这使类及其派生类可以“继承”依赖属性实现，而不需要最初的所有者类，而且添加类也不必位于同一个实际的类层次结构中。 另外，添加类（以及所有派生类）随后可以为最初的依赖属性提供特定于类型的元数据。  
  
 添加类除了通过属性系统的实用工具方法将自身添加为所有者以外，还应当在自身声明其他公共成员，以使依赖属性向代码和标记公开，从而完全参与属性系统。 就为依赖属性公开对象模型而言，添加现有依赖属性的类与定义新的自定义依赖属性的类具有相同的职责。 要公开的第一个此类成员是依赖属性标识符字段。 此字段应为 类型`public static readonly`<xref:System.Windows.DependencyProperty>字段，该字段分配给调用的<xref:System.Windows.DependencyProperty.AddOwner%2A>返回值。 要定义的第二个成员是通用语言运行时 （CLR） "包装器"属性。 包装器使在代码中操作依赖项属性变得更加方便（您避免每次都调用<xref:System.Windows.DependencyObject.SetValue%2A>，并且只能在包装器本身中进行一次调用）。 包装器的实现方式与在注册自定义依赖属性时的实现方式完全相同。 有关实现依赖属性的详细信息，请参阅[自定义依赖属性](custom-dependency-properties.md)和[为依赖属性添加所有者类型](how-to-add-an-owner-type-for-a-dependency-property.md)。  
  
#### <a name="addowner-and-attached-properties"></a>AddOwner 和附加属性  
 您可以调用<xref:System.Windows.DependencyProperty.AddOwner%2A>由所有者类定义为附加属性的依赖项属性。 这样做的目的通常是为了将以前附加的属性作为非附加依赖属性来公开。 然后，<xref:System.Windows.DependencyProperty.AddOwner%2A>您将将返回值公开为用作`public static readonly`依赖项属性标识符的字段，并将定义适当的"包装"属性，以便该属性显示在成员表中，并支持类中的非附加属性用法。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.PropertyMetadata>
- <xref:System.Windows.DependencyObject>
- <xref:System.Windows.DependencyProperty>
- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [依赖项属性概述](dependency-properties-overview.md)
- [框架属性元数据](framework-property-metadata.md)
