---
title: 特性
description: 了解属性F#如何使元数据应用于编程构造。
ms.date: 05/16/2016
ms.openlocfilehash: 3f3c3469192c09aa51f31ef3f00aca0196e3c382
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630087"
---
# <a name="attributes"></a>特性

特性使元数据可以应用于编程构造。

## <a name="syntax"></a>语法

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a>备注

在前面的语法中,*目标*是可选的, 如果存在, 则指定应用该属性的程序实体的类型。 *目标*的有效值显示在本文档后面的表中。

*特性名称*是指具有有效属性类型的名称 (可能用命名空间限定), 其中使用或不使用通常在`Attribute`属性类型名称中使用的后缀。 例如, `Obsolete`在此上下文`ObsoleteAttribute`中, 类型只能缩短到。

*参数*是属性类型的构造函数的参数。 如果特性具有默认构造函数, 则可以省略参数列表和括号。 特性支持位置参数和命名参数。 *位置参数*是按其出现顺序使用的参数。 如果特性具有公共属性, 则可以使用命名参数。 可以通过在参数列表中使用以下语法来设置这些参数。

```
*property-name* = *property-value*
```

此类属性初始化可以按任意顺序进行, 但必须遵循任何位置自变量。 下面是使用位置参数和属性初始化的特性的一个示例。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

在此示例中, 属性为`DllImportAttribute`, 此处以缩写形式使用。 第一个参数是位置参数, 第二个参数是一个属性。

特性是一个 .NET 编程构造, 使称为*属性*的对象可与类型或其他程序元素相关联。 应用特性的程序元素称为*属性目标*。 该属性通常包含有关其目标的元数据。 在这种情况下, 元数据可以是除字段和成员之外的任何类型的数据。

中F#的属性可应用于以下编程构造: 函数、方法、程序集、模块、类型 (类、记录、结构、接口、委托、枚举、联合等等)、构造函数、属性、字段、参数、类型参数和返回值。 不允许在类、 `let`表达式或工作流表达式中的绑定上使用特性。

通常, 特性声明直接出现在属性目标的声明之前。 可以将多个属性声明一起使用, 如下所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

可以通过使用 .NET 反射在运行时查询属性。

如前面的代码示例中所示, 可以单独声明多个特性, 也可以在一组方括号中将它们声明为, 前提是使用分号分隔各个特性和构造函数, 如下所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

通常, 所遇到的`Obsolete`属性包括属性、安全注意事项属性、COM 支持的属性、与代码所有权相关的属性, 以及指示类型是否可以序列化的属性。 下面的示例演示`Obsolete`属性的用法。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

对于特性目标`assembly`和`module`, 将特性应用于程序集中的顶级`do`绑定。 可以在属性声明中`assembly`包含`module`单词或, 如下所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

如果省略应用`do`于绑定的属性的属性目标, 则编译器将F#尝试确定对于该属性有意义的属性目标。 许多特性类都有一个类型`System.AttributeUsageAttribute`为的属性, 其中包括有关该特性支持的可能目标的信息。 `System.AttributeUsageAttribute`如果指示该特性支持作为目标的函数, 则会将该特性应用于程序的主入口点。 `System.AttributeUsageAttribute`如果指示特性支持作为目标的程序集, 则编译器会将特性应用于程序集。 大多数特性并不适用于函数和程序集, 但在这些特性的情况下, 会将特性应用于程序的 main 函数。 如果显式指定了特性目标, 则该特性将应用于指定的目标。

尽管通常不需要显式指定属性目标, 但下表中显示了属性中 "*目标*" 的有效值, 以及用法示例。

<table>
  <tr>
    <th>特性目标</td>
    <th>示例</td> 
  </tr>
  <tr>
    <td>程序集</td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]<code></pre></td> 
  </tr>
  <tr>
    <td>return</td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1<code></pre></td> 
  </tr>
  <tr>
    <td>Field — 字段</td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int<code></pre></td> 
  </tr>
  <tr>
    <td>属性</td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x<code></pre></td> 
  </tr>
  <tr>
    <td>param</td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10<code></pre></td> 
  </tr>
  <tr>
    <td>类型</td>
    <td>
        <pre lang="fsharp"><code>
        [&lt;type: StructLayout(Sequential)&gt;] 
        type MyStruct = 
        struct 
        x : byte
        y : int
        end
        <code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
