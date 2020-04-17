---
title: x:Shared 特性
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: e1cd1d9db5c19decd840b433f986e0ba53557a8b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432646"
---
# <a name="xshared-attribute"></a>x:Shared 特性

设置为 时`false`，将修改 WPF 资源检索行为，以便对属性化资源的请求为每个请求创建一个新实例，而不是为所有请求共享相同的实例。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a>备注

`x:Shared`映射到 XAML 语言 XAML 命名空间，并由 .NET XAML 服务及其 XAML 读取器识别为有效的 XAML 语言元素。 但是，声明`x:Shared`的功能仅与 WPF 应用程序和 WPF XAML 解析器相关。 在 WPF`x:Shared`中，仅当属性应用于存在于 WPF<xref:System.Windows.ResourceDictionary>中的对象时，它才可用作属性。 其他用法不会引发解析异常或其他错误，但它们没有效果。

在 XAML 语言规范中未指定 其`x:Shared`含义。 其他 XAML 实现（例如基于 .NET XAML 服务实现）不一定提供资源共享支持。 此类 XAML 实现可以在支持框架中提供类似的行为，该框架`x:Shared`也使用值。

在 WPF 中`x:Shared`，资源的默认条件是`true`。 此条件表示任何给定的资源请求始终返回同一实例。

修改通过资源 API 返回的对象（如 ，或<xref:System.Windows.FrameworkElement.FindResource%2A>直接修改 中的对象<xref:System.Windows.ResourceDictionary>）会更改原始资源。 如果对该资源的引用是动态资源引用，则该资源的使用者将获取已更改的资源。

如果对资源的引用是静态资源引用，则处理时间后[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]对资源的更改不相关。 有关静态资源引用和动态资源引用的详细信息，请参阅[XAML 资源](../fundamentals/xaml-resources-define.md)。

显式指定`x:Shared="true"`很少完成，因为这已经是默认值。 在 WPF 对象模型中`x:Shared`没有直接代码等效;它只能在 XAML 用法中指定，并且如果使用 .NET XAML 服务及其 XAML 读取器进行处理，则必须通过默认的 WPF 行为或在负载路径上的中间 XAML 节点流中进行处理。

的方案`x:Shared="false"`是，如果将 或<xref:System.Windows.FrameworkElement><xref:System.Windows.FrameworkContentElement>派生类定义为资源，然后将元素资源引入内容模型。 `x:Shared="false"`使元素资源在同一集合（如<xref:System.Windows.Controls.UIElementCollection>） 中多次引入。 如果没有`x:Shared="false"`此选项无效，因为集合会强制其内容的唯一性。 但是，该`x:Shared="false"`行为将创建资源的另一个相同实例，而不是返回相同的实例。

的另一<xref:System.Windows.Freezable>个`x:Shared="false"`方案是，如果将资源用于动画值，但希望根据每个动画修改资源。

的`false`字符串处理不区分大小写。

在 WPF`x:Shared`中，仅在以下条件下有效：

- <xref:System.Windows.ResourceDictionary>必须编译包含 的`x:Shared`项。 <xref:System.Windows.ResourceDictionary>不能在松散的 XAML 内或用于主题。

- <xref:System.Windows.ResourceDictionary>包含项的 不能嵌套在另一个<xref:System.Windows.ResourceDictionary>中。 例如`x:Shared`，不能用于<xref:System.Windows.ResourceDictionary>已属于<xref:System.Windows.Style><xref:System.Windows.ResourceDictionary>项 的 中的 项。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.ResourceDictionary>
- [XAML 资源](../fundamentals/xaml-resources-define.md)
- [基元素](../../framework/wpf/advanced/base-elements.md)
