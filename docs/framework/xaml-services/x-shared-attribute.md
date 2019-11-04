---
title: x:Shared 特性
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: c820a9b1d9708e24b1460378199a6addc1e20899
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459923"
---
# <a name="xshared-attribute"></a>x:Shared 特性
如果设置为 "`false`"，则将修改 WPF 资源检索行为，以便对特性化资源的请求为每个请求创建一个新的实例，而不是为所有请求共享同一个实例。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a>备注  
 `x:Shared` 映射到 XAML 语言 XAML 命名空间，并通过 .NET Framework XAML 服务及其 XAML 读取器识别为有效的 XAML 语言元素。 但 `x:Shared` 的指定功能仅与 WPF 应用程序和 WPF XAML 分析器相关。 在 WPF 中，`x:Shared` 仅在应用于 WPF <xref:System.Windows.ResourceDictionary>中存在的对象时用作特性。 其他用法不会引发分析异常或其他错误，但它们不起作用。  
  
 XAML 语言规范中未指定 `x:Shared` 的含义。 其他 XAML 实现（如 .NET Framework XAML 服务上构建的实现）不一定提供资源共享支持。 此类 XAML 实现可以在支持框架中提供类似的行为，此行为也 `x:Shared` 值。  
  
 在 WPF 中，资源的默认 `x:Shared` 条件 `true`。 这种情况意味着，任何给定的资源请求始终返回相同的实例。  
  
 修改通过资源 API 返回的对象（如 <xref:System.Windows.FrameworkElement.FindResource%2A>）或直接在 <xref:System.Windows.ResourceDictionary>中修改对象会更改原始资源。 如果对该资源的引用是动态资源引用，则该资源的使用者将获取更改的资源。  
  
 如果对资源的引用是静态资源引用，则 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理时间之后对资源所做的更改是不相关的。 有关静态和动态资源引用的详细信息，请参阅[XAML 资源](../../desktop-wpf/fundamentals/xaml-resources-define.md)。  
  
 显式指定 `x:Shared="true"` 很少完成，因为它已是默认值。 WPF 对象模型中的 `x:Shared` 没有直接的代码等效项;如果使用 .NET Framework XAML 服务及其 XAML 读取器进行处理，则它只能在 XAML 用法中指定，并且必须由默认的 WPF 行为或在加载路径的中间 XAML 节点流中处理。  
  
 `x:Shared="false"` 方案适用于将 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement> 派生类定义为资源，然后将元素资源引入内容模型。 `x:Shared="false"` 允许在同一集合中多次引入某个元素资源（如 <xref:System.Windows.Controls.UIElementCollection>）。 无 `x:Shared="false"` 这是无效的，因为集合会强制其内容的唯一性。 但 `x:Shared="false"` 行为会创建资源的另一个相同实例，而不是返回同一个实例。  
  
 `x:Shared="false"` 的另一种情况是，将 <xref:System.Windows.Freezable> 资源用于动画值，但要基于动画修改资源。  
  
 `false` 的字符串处理不区分大小写。  
  
 在 WPF 中，`x:Shared` 仅在以下情况下有效：  
  
- 必须编译包含具有 `x:Shared` 的项的 <xref:System.Windows.ResourceDictionary>。 <xref:System.Windows.ResourceDictionary> 不能位于松散 XAML 内或用于主题。  
  
- 包含项的 <xref:System.Windows.ResourceDictionary> 不得嵌套在另一个 <xref:System.Windows.ResourceDictionary>中。 例如，不能将 `x:Shared` 用于 <xref:System.Windows.ResourceDictionary> 处于已 <xref:System.Windows.ResourceDictionary> 项的 <xref:System.Windows.Style> 中的项。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.ResourceDictionary>
- [XAML 资源](../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [基元素](../wpf/advanced/base-elements.md)
