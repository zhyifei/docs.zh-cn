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
ms.openlocfilehash: 57c25297f995acd1ef307466258b5f4e03cc3098
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459541"
---
# <a name="xaml-loading-and-dependency-properties"></a>XAML 加载和依赖项属性
[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器的当前 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 实现固有地知道依赖属性。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器在加载二进制 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 和处理作为依赖属性的特性时对依赖属性使用属性系统方法。 这会有效地跳过属性包装器。 实现自定义依赖项属性时，必须考虑此行为，并且应避免在属性包装器中除属性系统方法之外的任何其他代码 <xref:System.Windows.DependencyObject.GetValue%2A> 和 <xref:System.Windows.DependencyObject.SetValue%2A>。  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisites  
 本主题假定你已从使用者和创作者角度了解依赖属性，并已阅读[依赖属性概述](dependency-properties-overview.md)和[自定义依赖属性](custom-dependency-properties.md)。 你应也已阅读 [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md) 和 [XAML 语法详述](xaml-syntax-in-detail.md)。  
  
<a name="implementation"></a>   
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>WPF XAML 加载程序实现和性能  
 出于实现原因，将属性标识为依赖属性并访问属性系统 <xref:System.Windows.DependencyObject.SetValue%2A> 方法来设置该属性，而不是使用属性包装及其 setter，计算成本更低。 这是因为 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器必须仅通过了解由标记结构和多种字符串所指示的类型和成员关系来推断支持代码的整个对象模型。  
  
 该类型通过 xmlns 和程序集特性的组合进行查找，但标识成员，确定哪些成员可以支持设置为属性，并解析属性值支持的类型将需要广泛的反射使用 <xref:System.Reflection.PropertyInfo>。 由于给定类型上的依赖属性可通过属性系统作为存储表进行访问，因此，其 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 实现将使用此表，并推断可以更有效地设置任何给定的属性*ABC*使用依赖项属性标识符*ABCProperty*对包含 <xref:System.Windows.DependencyObject> 派生类型调用 <xref:System.Windows.DependencyObject.SetValue%2A>。  
  
<a name="implications"></a>   
## <a name="implications-for-custom-dependency-properties"></a>自定义依赖属性的影响  
 由于进行属性设置的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器行为的当前 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 实现会完全跳过包装器，因此对于自定义依赖属性不应将任何其他逻辑放入包装器的设置定义中。 如果将此类逻辑放入设置定义，则在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 而不是代码中设置属性时不会执行逻辑。  
  
 同样，从 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理获得属性值的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器的其他方面也使用 <xref:System.Windows.DependencyObject.GetValue%2A>，而不是使用包装。 因此，除了 <xref:System.Windows.DependencyObject.GetValue%2A> 调用以外，还应避免 `get` 定义中的任何附加实现。  
  
 如下示例是包装器的推荐依赖属性定义，其中属性标识符存储为 `public` `static` `readonly` 字段，`get` 和 `set` 定义不包含除定义依赖属性支持所需属性系统方法外的任何代码。  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>请参阅

- [依赖项属性概述](dependency-properties-overview.md)
- [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [依赖属性元数据](dependency-property-metadata.md)
- [集合类型依赖属性](collection-type-dependency-properties.md)
- [依赖属性的安全性](dependency-property-security.md)
- [DependencyObject 的安全构造函数模式](safe-constructor-patterns-for-dependencyobjects.md)
