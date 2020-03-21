---
title: XAML 加载和依赖项属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom dependency properties [WPF]
- dependency properties [WPF], XAML loading and
- loading XML data [WPF]
ms.assetid: 6eea9f4e-45ce-413b-a266-f08238737bf2
ms.openlocfilehash: de8050e582f5b1a5a288c350c179cfa24fb5471c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186253"
---
# <a name="xaml-loading-and-dependency-properties"></a>XAML 加载和依赖项属性
[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器的当前 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 实现固有地知道依赖属性。 加载[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]作为依赖项属性的二进制[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]属性和处理属性时，处理器对依赖项属性使用属性系统方法。 这会有效地跳过属性包装器。 实现自定义依赖项属性时，必须考虑此行为，并且应避免将任何其他代码放在属性系统方法和<xref:System.Windows.DependencyObject.GetValue%2A><xref:System.Windows.DependencyObject.SetValue%2A>以外的属性包装器中。  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>系统必备  
 本主题假定你已从使用者和创作者角度了解依赖属性，并已阅读[依赖属性概述](dependency-properties-overview.md)和[自定义依赖属性](custom-dependency-properties.md)。 你应也已阅读 [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md) 和 [XAML 语法详述](xaml-syntax-in-detail.md)。  
  
<a name="implementation"></a>
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>WPF XAML 加载程序实现和性能  
 出于实现原因，将属性标识为依赖项属性并访问属性系统<xref:System.Windows.DependencyObject.SetValue%2A>方法来设置属性比使用属性包装器及其 setter 的成本更低。 这是因为 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器必须仅通过了解由标记结构和多种字符串所指示的类型和成员关系来推断支持代码的整个对象模型。  
  
 类型通过 xmlns 和程序集属性的组合进行查看，但标识成员，确定哪些可以支持设置为属性，并解析属性值支持的类型，否则需要使用<xref:System.Reflection.PropertyInfo>进行广泛的反射。 由于给定类型的依赖项属性可通过属性系统作为存储[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]表访问，因此其[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器的实现使用此表，并推断任何给定属性 ABC 可以通过使用依赖<xref:System.Windows.DependencyObject.SetValue%2A><xref:System.Windows.DependencyObject>项属性标识符 ABC*属性*调用，更有效地设置任何给定属性*ABC。*  
  
<a name="implications"></a>
## <a name="implications-for-custom-dependency-properties"></a>自定义依赖属性的影响  
 由于进行属性设置的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器行为的当前 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 实现会完全跳过包装器，因此对于自定义依赖属性不应将任何其他逻辑放入包装器的设置定义中。 如果将此类逻辑放入设置定义，则在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 而不是代码中设置属性时不会执行逻辑。  
  
 同样，从[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理中获取属性值的处理器的其他方面也使用<xref:System.Windows.DependencyObject.GetValue%2A>而不是使用包装器。 因此，还应避免在`get`<xref:System.Windows.DependencyObject.GetValue%2A>调用之外的定义中的任何其他实现。  
  
 下面的示例是建议使用包装器的依赖项属性定义，其中属性标识符存储为字段`public``static``readonly`，`get`和`set`定义不包含定义依赖项属性支持的必要属性系统方法之外的代码。  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>另请参阅

- [依赖项属性概述](dependency-properties-overview.md)
- [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [依赖属性元数据](dependency-property-metadata.md)
- [集合类型依赖属性](collection-type-dependency-properties.md)
- [依赖属性的安全性](dependency-property-security.md)
- [DependencyObject 的安全构造函数模式](safe-constructor-patterns-for-dependencyobjects.md)
