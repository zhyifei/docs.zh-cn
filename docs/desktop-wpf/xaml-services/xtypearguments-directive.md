---
title: x:TypeArguments 指令
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 69da9329f140121b66c71d4cf2e99e9d14a1b207
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432628"
---
# <a name="xtypearguments-directive"></a>x:TypeArguments 指令

将泛型的约束类型参数传递给泛型类型的构造函数。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|`object`|XAML 类型的对象元素声明，由 CLR 泛型类型支持。 如果`object`引用的 XAML 类型不是来自默认的 XAML 命名空间`object`，则需要一个前缀来指示存在存在的`object`XAML 命名空间。|
|`typeString`|将一个或多个 XAML 类型名称声明为字符串的字符串，该字符串提供 CLR 泛型类型的类型参数。 有关其他语法注释，请参阅备注。|

## <a name="remarks"></a>备注

在大多数情况下，用作字符串中的信息项的 XAML 类型是预固定的`typeString`。 CLR 泛型约束的典型类型（例如<xref:System.Int32>和<xref:System.String>） 来自 CLR 基类库。 这些库不映射到典型的特定于框架的默认 XAML 命名空间，因此需要 XAML 用法的前缀映射。

可以使用逗号分隔符指定多个 XAML 类型名称。

如果泛型约束本身使用泛型类型，则嵌套约束类型参数可以由括号 （） 包含。

请注意，此`x:TypeArguments`定义特定于 .NET XAML 服务并使用 CLR 支持。 可在[\[MS-XAML\]第 5.3.11 节中](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))找到语言级别的定义。

## <a name="usage-examples"></a>用法示例

对于这些示例，假定声明了以下 XAML 命名空间定义：

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a>列表\<字符串>

`<scg:List x:TypeArguments="sys:String" ...>`实例化具有类型参数的新<xref:System.Collections.Generic.List%601><xref:System.String>。

### <a name="dictionarystringstring"></a>字典\<字符串，字符串>

`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`实例化具有两<xref:System.Collections.Generic.Dictionary%602><xref:System.String>个类型参数的新参数。

### <a name="queuekeyvaluepairstringstring"></a>队列<键值字符串\<，字符串>>

`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`实例化具有 内部约束<xref:System.Collections.Generic.Queue%601>类型 参数<xref:System.String>和<xref:System.String><xref:System.Collections.Generic.KeyValuePair%602>约束的新。

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 和 WPF 通用 XAML 用法

对于用于 WPF 应用程序的 XAML 2006 用法和 XAML，一般`x:TypeArguments`对 XAML 和泛型类型用法存在以下限制：

- 只有 XAML 文件的根元素才能支持引用泛型类型的泛型 XAML 用法。

- 根元素必须映射到具有至少一个类型参数的泛型类型。 示例为 <xref:System.Windows.Navigation.PageFunction%601>。 页面函数是 WPF 中 XAML 通用使用支持的主要方案。

- 泛型的根元素 XAML 对象元素还必须使用`x:Class`声明部分类。 即使定义 WPF 生成操作也是如此。

- `x:TypeArguments`不能引用嵌套的泛型约束。

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 或 XAML 2006，没有 WPF 3.0 或 WPF 3.5 依赖项

在 .NET XAML 服务中，XAML 2006 或 XAML 2009 中，放宽了与 WPF 相关的通用 XAML 使用限制。 您可以在支持类型系统和对象模型可以支持的任何位置实例化 XAML 标记中的任何位置的泛型对象元素。

如果使用 XAML 2009 而不是映射 CLR 基类型以获取通用语言基元中的 XAML 类型，则可以[将通用 XAML 语言基元的内置类型](types-for-primitives.md)用作 中`typeString`的信息项。 例如，您可以声明以下内容（未显示前缀映射，但 x 是 XAML 2009 的 XAML 语言 XAML 命名空间）：

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

在 WPF 中，当定位 .NET 框架 4 或 .NET Core 3.0（或更高版本）时，`x:TypeArguments`您可以将 XAML 2009 功能与松散的 XAML（未标记编译的 XAML）一起使用，但仅限于这些功能。 WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。 如果需要标记编译 XAML，则必须在[XAML 2006 和 WPF 通用 XAML 用法](#xaml-2006-and-wpf-generic-xaml-usages)部分中所述的限制下操作。 BAML 仅在 .NET 框架中受支持。

## <a name="see-also"></a>请参阅

- [x:Class 指令](xclass-directive.md)
- [x:Type 标记扩展](xtype-markup-extension.md)
- [常见 XAML 语言基元的内置类型](types-for-primitives.md)
- [XAML 中的泛型](generics.md)
