---
title: 依赖项属性的安全性
ms.date: 03/30/2017
helpviewer_keywords:
- wrappers [WPF], access
- wrappers [WPF], security
- dependency properties [WPF], security
- security [WPF], wrappers
- validation [WPF], dependency properties
- dependency properties [WPF], access
- security [WPF], dependency properties
ms.assetid: d10150ec-90c5-4571-8d35-84bafa2429a4
ms.openlocfilehash: d9dd9306980b80f7845c10e8c0ccb59f29821245
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940843"
---
# <a name="dependency-property-security"></a>依赖项属性的安全性
依赖属性通常应当被视为公共属性。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 属性系统在本质上无法对依赖属性值提供安全保证。  

<a name="AccessSecurity"></a>   
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>包装器和依赖属性的访问和安全性  
 通常, 依赖属性是随 "包装器" 公共语言运行时 (CLR) 属性实现的, 这些属性可以简化从实例获取或设置属性的过程。 但包装实际上只是一种简便方法, 可实现<xref:System.Windows.DependencyObject.GetValue%2A>在<xref:System.Windows.DependencyObject.SetValue%2A>与依赖属性交互时使用的基础调用和静态调用。 以另一种方式思考, 属性会作为公共语言运行时 (CLR) 属性公开, 而这些属性确实会由依赖属性 (而不是私有字段) 支持。 应用于包装器的安全机制与属性系统行为以及基础依赖属性的访问并不可比。 在包装上放置安全要求仅会阻止使用便捷方法, 但不会阻止对<xref:System.Windows.DependencyObject.GetValue%2A>或<xref:System.Windows.DependencyObject.SetValue%2A>的调用。 同样，为包装器设置受保护或私有访问级别也不会提供任何有效的安全性。  
  
 如果你正在编写自己的依赖项属性, 则应将该包装和<xref:System.Windows.DependencyProperty>标识符字段声明为公共成员, 以便调用方不会获得有关该属性的 true 访问级别的误导性信息 (因为其存储正在作为依赖属性实现。  
  
 对于自定义依赖属性, 可以将属性注册为只读依赖属性, 这确实提供了一种有效的方法来防止不包含对该属性的<xref:System.Windows.DependencyPropertyKey>引用的任何人设置属性。 有关详细信息，请参阅[只读依赖属性](read-only-dependency-properties.md)。  
  
> [!NOTE]
> 不禁止将标识符字段声明为私有的, 因此可以使用它来帮助减少自定义类的直接公开命名空间, 但在与公共语言相同的意义上, 此类属性不应被视为 "私有" <xref:System.Windows.DependencyProperty>运行时 (CLR) 语言定义定义该访问级别, 原因如下部分所述。  
  
<a name="PropertySystemExposure"></a>   
## <a name="property-system-exposure-of-dependency-properties"></a>依赖属性的属性系统公开  
 这种方法通常并不有用, 它可能会产生误导性, <xref:System.Windows.DependencyProperty>将声明为除 public 以外的任何访问级别。 该访问级别设置只是防止某人从声明类获得对实例的引用。 但是, 属性系统有多个方面将返回<xref:System.Windows.DependencyProperty>作为标识某个特定属性的方法, 因为该属性存在于类或派生类实例的实例上, 而此标识符仍可<xref:System.Windows.DependencyObject.SetValue%2A>在调用中使用。如果将原始静态标识符声明为非公共标识符, 则为。 此外, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>虚方法接收任何现有依赖属性的信息, 该属性更改了值。 此外, 该<xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A>方法为实例上具有本地设置值的任何属性返回标识符。  
  
### <a name="validation-and-security"></a>验证和安全  
 将需求应用到<xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> , 并预期在请求失败时验证失败, 以防止设置属性的安全机制。 如果执行<xref:System.Windows.DependencyProperty.ValidateValueCallback%2A>的设置值无效, 则如果这些调用方在应用程序域中运行, 则它也会被恶意调用方抑制。  
  
## <a name="see-also"></a>请参阅

- [自定义依赖属性](custom-dependency-properties.md)
