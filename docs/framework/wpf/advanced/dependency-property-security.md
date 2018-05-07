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
ms.openlocfilehash: 825b2a3dc79300f0cc26514398b8de0abee64fd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="dependency-property-security"></a>依赖项属性的安全性
依赖属性通常应当被视为公共属性。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 属性系统在本质上无法对依赖属性值提供安全保证。  
  
  
<a name="AccessSecurity"></a>   
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>包装器和依赖属性的访问和安全性  
 通常，依赖属性是随“包装器”[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 属性一起实现的，这些包装器属性可以简化从实例获取或设置属性的过程。 但是，包装实际上只是方便的方法，实现基础<xref:System.Windows.DependencyObject.GetValue%2A>和<xref:System.Windows.DependencyObject.SetValue%2A>交互具有依赖项属性时所使用的静态调用。 从另外一个角度考虑，这些属性作为恰好由依赖属性（而非私有字段）支持的[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 属性公开。 应用于包装器的安全机制与属性系统行为以及基础依赖属性的访问并不可比。 放置在包装上的安全要求会仅阻止以便捷方法的使用情况，但将不会阻止对调用<xref:System.Windows.DependencyObject.GetValue%2A>或<xref:System.Windows.DependencyObject.SetValue%2A>。 同样，为包装器设置受保护或私有访问级别也不会提供任何有效的安全性。  
  
 如果你正在编写自己的依赖项属性，则应声明包装器和<xref:System.Windows.DependencyProperty>标识符字段，为公共成员，以便调用方执行不获取具有误导性，有关该属性的实际访问级别的信息 （由于其存储在实现为依赖项属性）。  
  
 对于自定义的依赖项属性，可以注册你的属性，为只读依赖属性，而且这确实提供阻止不保存对引用的任何人设置的属性的有效方式<xref:System.Windows.DependencyPropertyKey>该属性。 有关详细信息，请参阅[只读依赖属性](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md)。  
  
> [!NOTE]
>  声明<xref:System.Windows.DependencyProperty>标识符字段私有不已禁止，和拿可以用于帮助减少立即公开命名空间的自定义类，但这样的属性不应被认为在相同的意义上为"私有" [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]语言定义将定义该访问级别下, 一节中描述的原因。  
  
<a name="PropertySystemExposure"></a>   
## <a name="property-system-exposure-of-dependency-properties"></a>依赖属性的属性系统公开  
 它并不通常很有用，并且它有可能误导性，若要声明<xref:System.Windows.DependencyProperty>任何访问级别不是公共。 该访问级别设置只是防止某人从声明类获得对实例的引用。 但有几个方面的属性系统的将返回<xref:System.Windows.DependencyProperty>来标识的特定属性，它存在于类的实例或派生的类实例，以及此标识符在仍可用于为<xref:System.Windows.DependencyObject.SetValue%2A>甚至调用如果原始的静态标识符声明为公共。 此外，<xref:System.Windows.DependencyObject.OnPropertyChanged%2A>虚方法接收的值更改任何现有依赖项属性的信息。 此外，<xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A>方法返回与本地设置的实例上的任何属性的标识符值。  
  
### <a name="validation-and-security"></a>验证和安全  
 应用到一个要求<xref:System.Windows.DependencyProperty.ValidateValueCallback%2A>和应请求失败，以防止属性设置为验证失败不是足够的安全性机制。 通过强制设置值失效<xref:System.Windows.DependencyProperty.ValidateValueCallback%2A>还可禁止显示由恶意调用方，如果在应用程序域内操作这些调用方。  
  
## <a name="see-also"></a>请参阅  
 [自定义依赖属性](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
