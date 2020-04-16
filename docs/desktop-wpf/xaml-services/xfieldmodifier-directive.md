---
title: x:FieldModifier 指令
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 3e104b4c464d545e048f29901701c1c3dbb68229
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432778"
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier 指令
修改 XAML 编译行为，以便使用<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>访问而不是默认行为定义命名对象引用的<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>字段。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object x:FieldModifier="Public".../>
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|*公共*|传递给指定的<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>确切字符串因<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>所使用的代码后面编程语言而异。 请参阅“备注”。|

## <a name="dependencies"></a>依赖项

 如果 XAML 生产`x:FieldModifier`在任何地方使用，则 XAML 生产的根元素必须声明[x：类指令](xclass-directive.md)。

## <a name="remarks"></a>备注

`x:FieldModifier`与声明类或其成员的一般访问级别无关。 它仅与 XAML 处理行为相关，因为处理属于 XAML 生产一部分的特定 XAML 对象，并成为在应用程序的对象图中可能可访问的对象。 默认情况下，此类对象的字段引用保持私有，这可以防止控件使用者直接修改对象图。 相反，控件使用者应该使用编程模型启用的标准模式来修改对象图，例如通过获取布局根、子元素集合、专用公共属性等。

`x:FieldModifier`属性的值因编程语言而异，并且其用途可能因特定框架而异。 要使用的字符串取决于每种语言如何实现其<xref:System.CodeDom.Compiler.CodeDomProvider>和返回的类型转换器来定义<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>和<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>的含义，以及该语言是否区分大小写。

- 对于 C#，要传递到指定的<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>字符串为`public`。

- 对于 Microsoft Visual Basic .NET，要传递<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>要`Public`指定的字符串为 。

- 对于C++/CLI，目前不存在 XAML 的目标;因此，要传递的字符串未定义。

<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>您还可以指定（`internal`在 C# 中`Friend`，在 Visual Basic<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>中），`NotPublic`但指定是不寻常的，因为行为已经是默认值。

<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>是默认行为，因为编译 XAML 的程序集外部的代码很少需要访问 XAML 创建的元素。 WPF 安全体系结构以及 XAML 编译行为不会声明存储元素实例的字段为公共，除非您专门设置`x:FieldModifier`允许公共访问。

`x:FieldModifier`仅与[具有 x：name 指令](xname-directive.md)的元素相关，因为该名称用于在字段公开后引用该字段。

默认情况下，根元素的部分类是公共的;因此，根元素的部分类为公共类。但是，您可以使用[x：Class 修改器指令](xclassmodifier-directive.md)将其非公开。 [x：Class 修改器指令](xclassmodifier-directive.md)还影响根元素类实例的访问级别。 您可以将 和`x:FieldModifier``x:Name`放在根元素上，但这仅使根元素的公共字段副本，真正的根元素类访问级别仍由[x：Class修改器指令](xclassmodifier-directive.md)控制。

## <a name="see-also"></a>请参阅

- [XAML 及 WPF 的自定义类](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [WPF 中的代码隐藏和 XAML](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:Name 指令](xname-directive.md)
- [Building a WPF Application (WPF)](../../framework/wpf/app-development/building-a-wpf-application-wpf.md)（生成 WPF 应用程序 (WPF)）
- [x:ClassModifier 指令](xclassmodifier-directive.md)
