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
ms.openlocfilehash: 28e121e73ad4bd8ab70aed5f651418eb309b0c03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="xaml-loading-and-dependency-properties"></a>XAML 加载和依赖项属性
[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器的当前 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 实现固有地知道依赖属性。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器在加载二进制 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 和处理作为依赖属性的特性时对依赖属性使用属性系统方法。 这会有效地跳过属性包装器。 当实现自定义的依赖项属性时，你必须考虑此行为，并应避免置于属性包装器的属性系统方法以外的任何其他代码<xref:System.Windows.DependencyObject.GetValue%2A>和<xref:System.Windows.DependencyObject.SetValue%2A>。  
  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>系统必备  
 本主题假定你已从使用者和创作者角度了解依赖属性，并已阅读[依赖属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)和[自定义依赖属性](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)。 你应也已阅读 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) 和 [XAML 语法详述](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)。  
  
<a name="implementation"></a>   
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>WPF XAML 加载程序实现和性能  
 对于实现的原因，它是成本计算较低，来标识作为依赖项属性的属性和访问属性系统<xref:System.Windows.DependencyObject.SetValue%2A>方法来设置它，而不是使用属性包装和其 setter。 这是因为 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器必须仅通过了解由标记结构和多种字符串所指示的类型和成员关系来推断支持代码的整个对象模型。  
  
 类型通过 xmlns 和程序集特性，但标识的成员，确定被设置为一个属性，因为后者无法支持的组合查找和解析的属性值支持哪些类型否则将需要大量反射使用<xref:System.Reflection.PropertyInfo>。 由于给定类型的依赖项属性是通过属性系统的存储表的可访问性[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]实现其[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器将使用此表和推断对任何给定属性*ABC*可以通过调用更有效地设置<xref:System.Windows.DependencyObject.SetValue%2A>上包含<xref:System.Windows.DependencyObject>派生类型，使用依赖项属性标识符*ABCProperty*。  
  
<a name="implications"></a>   
## <a name="implications-for-custom-dependency-properties"></a>自定义依赖属性的影响  
 由于进行属性设置的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器行为的当前 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 实现会完全跳过包装器，因此对于自定义依赖属性不应将任何其他逻辑放入包装器的设置定义中。 如果将此类逻辑放入设置定义，则在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 而不是代码中设置属性时不会执行逻辑。  
  
 同样的其他方面[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]获取的属性值的处理器[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理还使用<xref:System.Windows.DependencyObject.GetValue%2A>而不是使用包装。 因此，你还应该避免在任何其他实现`get`超出定义<xref:System.Windows.DependencyObject.GetValue%2A>调用。  
  
 如下示例是包装器的推荐依赖属性定义，其中属性标识符存储为 `public` `static` `readonly` 字段，`get` 和 `set` 定义不包含除定义依赖属性支持所需属性系统方法外的任何代码。  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>请参阅  
 [依赖项属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [依赖属性元数据](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)  
 [集合类型依赖属性](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)  
 [依赖属性的安全性](../../../../docs/framework/wpf/advanced/dependency-property-security.md)  
 [DependencyObject 的安全构造函数模式](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)
