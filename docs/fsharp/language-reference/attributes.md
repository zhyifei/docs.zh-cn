---
title: 特性 (F#)
description: '了解如何 F # 属性启用要应用到编程构造的元数据。'
ms.date: 05/16/2016
ms.openlocfilehash: 107f5d9cbcce28c97fc5b738759ef27649fc45a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565420"
---
# <a name="attributes"></a>特性

属性启用元数据要应用到编程构造。

## <a name="syntax"></a>语法

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a>备注

在上述语法中，*目标*是可选的如果存在，则指定此特性应用于程序实体的类型。 有效值为*目标*出现在本文档后面的表所示。

*属性名称*引用 （可能用命名空间限定） 名称的有效的属性类型，或如果没有后缀`Attribute`通常用在特性类型名称。 例如，类型`ObsoleteAttribute`可以缩短至只有`Obsolete`在此上下文中。

*参数*属性类型的自变量的构造函数。 如果某一特性有一个默认构造函数，可以省略自变量列表和括号。 特性支持位置自变量和命名自变量。 *位置自变量*是以它们出现的顺序使用的自变量。 如果该属性具有公共属性，可以使用命名自变量。 可以通过使用以下语法自变量列表中的这些设置。

```
*property-name* = *property-value*
```

此类属性初始化操作可以采用任何顺序，但它们必须遵循的任何位置的自变量。 下面是特性的使用位置自变量和属性的初始化过程中的示例。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

在此示例中，该特性是`DllImportAttribute`，此处使用缩写形式。 第一个参数是位置参数，并且第二个是属性。

属性是一个.NET 编程构造，用于使对象称为*属性*要与类型或其他程序元素相关联。 向其应用的特性的程序元素称为*属性目标*。 属性通常包含有关其目标的元数据。 在此上下文中，元数据可能是其字段和成员以外的类型有关的任何数据。

F # 中的特性可以应用于以下的编程构造： 函数、 方法、 程序集、 模块、 类型 （类、 记录、 结构、 接口、 委托、 枚举、 联合和等等）、 构造函数、 属性、 字段、 参数，类型参数，并返回值。 属性不能存在于`let`绑定到类、 表达式或工作流表达式。

通常情况下，特性声明出现直接之前的属性目标的声明。 在一起，如下所示，可以使用多个属性声明。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

通过使用.NET 反射，可以在运行时查询属性。

如前面的代码示例所示，声明单独，多个属性或如果你使用分号来分隔各个属性和构造函数，如此处所示可以声明它们在一组方括号中。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

通常会遇到的属性包括`Obsolete`COM 支持、 所有权的代码中，相关的属性和属性，该值指示是否可以序列化类型的属性，为了安全起见，特性属性。 下面的示例演示了利用`Obsolete`属性。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

对于特性目标`assembly`和`module`，将特性应用于顶级`do`中程序集的绑定。 你可以纳入单词`assembly`或`module`，请在属性声明，如下所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

如果你省略应用于属性的属性目标`do`绑定，F # 编译器将尝试确定适合该属性的属性目标。 许多属性类具有类型的属性`System.AttributeUsageAttribute`，包括有关可能的目标支持该属性的信息。 如果`System.AttributeUsageAttribute`指示特性支持使用作为目标的函数，则会特性将应用于程序的主入口点。 如果`System.AttributeUsageAttribute`指示特性支持使用作为目标的程序集，编译器采用要应用于程序集的特性。 大多数属性不适用于函数和程序集，但在它们执行操作的情况下，会将特性应用于程序的主函数。 如果显式指定的属性目标，则属性应用于指定的目标。

尽管您不通常需要指定特性显式，目标的有效值*目标*特性中所示下表中，以及用法的示例。

<table>
  <tr>
    <th>特性目标</td>
    <th>示例</td> 
  </tr>
  <tr>
    <td>程序集</td>
    <td>`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</td> 
  </tr>
  <tr>
    <td>return</td>
    <td>让 function1 x: [<return: Obsolete>] int = x + 1</td> 
  </tr>
  <tr>
    <td>Field — 字段</td>
    <td>[<field: DefaultValue>] val 可变 x: int</td> 
  </tr>
  <tr>
    <td>属性</td>
    <td>[<property: Obsolete>] 这。MyProperty = x</td> 
  </tr>
  <tr>
    <td>Param</td>
    <td>成员这。MyMethod ([<param: Out>] x: ref<int>) = x: = 10</td> 
  </tr>
  <tr>
    <td>类型</td>
    <td>
        ```
        [<type: StructLayout(Sequential)>] 键入 MyStruct = 结构 x： 字节 y: int 结束 ```
    </td> 
  </tr>
</table>

## <a name="see-also"></a>请参阅

[F# 语言参考](index.md)
