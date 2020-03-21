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
ms.openlocfilehash: f5640b348ccd68819052f58756489489371862d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186399"
---
# <a name="dependency-property-security"></a>依赖项属性的安全性
依赖属性通常应当被视为公共属性。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 属性系统在本质上无法对依赖属性值提供安全保证。  

<a name="AccessSecurity"></a>
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>包装器和依赖属性的访问和安全性  
 通常，依赖项属性与"包装器"通用语言运行时 （CLR） 属性一起实现，这些属性可简化从实例获取或设置属性。 但是，包装器实际上只是实现与依赖项属互时使用<xref:System.Windows.DependencyObject.GetValue%2A>的基础<xref:System.Windows.DependencyObject.SetValue%2A>调用和静态调用的便捷方法。 换句话考虑，属性被公开为通用语言运行时 （CLR） 属性，这些属性恰好由依赖项属性而不是私有字段支持。 应用于包装器的安全机制与属性系统行为以及基础依赖属性的访问并不可比。 对包装器发出安全要求只会阻止使用方便方法，但不会阻止对 或<xref:System.Windows.DependencyObject.GetValue%2A><xref:System.Windows.DependencyObject.SetValue%2A>的调用。 同样，为包装器设置受保护或私有访问级别也不会提供任何有效的安全性。  
  
 如果要编写自己的依赖项属性，则应将包装器和<xref:System.Windows.DependencyProperty>标识符字段声明为公共成员，以便调用方不会收到有关该属性的真实访问级别的误导性信息（因为它的存储作为依赖项属性实现）。  
  
 对于自定义依赖项属性，您可以将属性注册为只读依赖项属性，这确实提供了一种有效方法，可以防止不保存该属性引用<xref:System.Windows.DependencyPropertyKey>的任何人设置属性。 有关详细信息，请参阅[只读依赖属性](read-only-dependency-properties.md)。  
  
> [!NOTE]
> 不禁止<xref:System.Windows.DependencyProperty>将标识符字段声明为私有，可以想象，它可用于帮助减少自定义类的立即公开的命名空间，但此类属性不应被视为"私有"，其意义上与通用语言运行时 （CLR） 语言定义定义该访问级别相同，原因如下一节所述。  
  
<a name="PropertySystemExposure"></a>
## <a name="property-system-exposure-of-dependency-properties"></a>依赖属性的属性系统公开  
 将 a<xref:System.Windows.DependencyProperty>声明为公共以外的任何访问级别通常没有用，而且可能具有误导性。 该访问级别设置只是防止某人从声明类获得对实例的引用。 但是，属性系统有几个方面将返回 作为<xref:System.Windows.DependencyProperty>标识特定属性的方法，因为它存在于类或派生类实例的实例上，并且此标识符在<xref:System.Windows.DependencyObject.SetValue%2A>调用中仍然可用，即使原始静态标识符声明为非公共的。 此外，<xref:System.Windows.DependencyObject.OnPropertyChanged%2A>虚拟方法接收更改值的任何现有依赖项属性的信息。 此外，<xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A>该方法返回具有本地设置值的实例上任何属性的标识符。  
  
### <a name="validation-and-security"></a>验证和安全  
 将请求应用于 和<xref:System.Windows.DependencyProperty.ValidateValueCallback%2A>预期在请求失败时无法阻止属性被设置的验证失败，这不是一个适当的安全机制。 如果这些调用方在应用程序域中<xref:System.Windows.DependencyProperty.ValidateValueCallback%2A>操作，则通过强制执行的设定值失效也可能被恶意调用方抑制。  
  
## <a name="see-also"></a>另请参阅

- [自定义依赖属性](custom-dependency-properties.md)
