---
title: 可区分联合 (F#)
description: '了解如何使用 F # 可区分联合。'
ms.date: 05/16/2016
ms.openlocfilehash: 617c659e26df52819a98294bcbfa081ab82fed03
ms.sourcegitcommit: e5bb395ec86f536e114314184288f40a8c745e2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2018
ms.locfileid: "34149070"
---
# <a name="discriminated-unions"></a>可区分联合

可区分的联合可以是数量的已命名的情况下，可能是每个具有不同值和类型之一的值为提供支持。 可区分的联合可用于异类数据;可以包括有效的特殊情况和错误情况; 的数据在从一个实例的类型到另一个; 中各不相同数据和为小对象层次结构的替代方法。 此外，递归可区分联合用于表示树数据结构。

## <a name="syntax"></a>语法

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]
...
```

## <a name="remarks"></a>备注
可区分的联合类似于其他语言版本，联合类型，但有差异。 作为使用 c + + 中的联合类型或在 Visual Basic 中的变量类型的值中存储的数据不被固定;它可以是几个不同的选项之一。 与联合不同这些其他语言中，但是，每个可能的选项提供*用例标识符*。 用例标识符是各种可能的值可能是此类型的对象; 类型的名称值是可选的。 如果值不存在，这种情况相当于枚举用例。 如果值存在，则每个值可以是单个值的指定的类型或聚合的相同或不同类型的多个字段的元组。 可以为单个字段提供一个名称，但名称是可选的即使在相同情况下的其他字段的名称。

可区分联合的辅助功能默认为`public`。

例如，考虑形状类型的以下声明。

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

上面的代码声明可区分的联合形状，可以具有的任何三个用例的值： 矩形、 圆形和 Prism。 每种情况下具有一组不同的字段。 用例有两个名为的矩形字段，这两个类型`float`，具有名称宽度和长度。 圆用例都只是一个命名的字段，radius。 Prism 用例具有三个字段，哪些 （宽度和高度） 的两个命名的字段。 未命名的字段称为匿名字段。

通过提供根据下面的示例的匿名和命名的字段值构造对象。

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

此代码演示你可以使用初始化中的命名的字段，也可以依赖于在声明中的字段的顺序，并只需提供值对于每个字段反过来。 对的构造函数调用`rect`在前面的代码使用命名的字段中，但对的构造函数调用`circ`使用的顺序。 您可以混用的已排序的字段和命名的字段，如下所示的构造`prism`。

`option`类型是简单的可区分的联合中的 F # 核心库。 `option`类型声明，如下所示。

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

前面的代码中指定类型`Option`是具有两种情况下，可区分的联合`Some`和`None`。 `Some`用例都由其类型由类型参数的一个匿名字段组成的关联的值`'a`。 `None`用例都没有关联的值。 因此`option`类型指定既可以具有某些类型或空值的值的泛型类型。 类型`Option`还有小写的类型别名`option`，即更常用。

用例标识符可以用作可区分联合类型的构造函数。 例如，下面的代码用于创建值`option`类型。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

用例标识符也用在匹配表达式的模式。 在模式匹配的表达式中，标识符提供了与各个事例关联的值。 例如，在下面的代码中，`x`标识符提供了与关联的值`Some`用例`option`类型。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

在匹配表达式的模式中，你可以使用命名的字段指定可区分联合的匹配项。 对于以前已声明的形状类型，可以使用命名的字段，如下面的代码演示要提取的字段的值。

```fsharp
let getShapeHeight shape =
    match shape with
    | Rectangle(height = h) -> h
    | Circle(radius = r) -> 2. * r
    | Prism(height = h) -> h
```

通常情况下，用例标识符可以使用而不必限定它们具有联合的名称。 如果你想要始终用联合的名称进行限定的名称，则可以应用[RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15)属性设为的联合类型定义。

### <a name="unwrapping-discriminated-unions"></a>解包可区分的联合

在 F # 可区分联合通常用于在域建模包装单一类型。 很容易通过模式以及匹配的基础价值。 你不需要要匹配表达式用于将单个用例：
```fsharp
let ([UnionCaseName] [values]) = [UnionValue]
```

下面的示例演示这一操作：

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someMethodUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ..
```

## <a name="struct-discriminated-unions"></a>结构可区分联合

F # 4.1 开始，你还可以表示可区分联合为结构。  这通过完成`[<Struct>]`属性。

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

因为这些是值类型和引用类型，所以一些额外注意事项与引用比较可区分联合：

1. 它们值类型作为复制，并且具有值类型语义。
2. 不能具有 multicase 的结构可区分联合使用递归类型定义。
3. 必须提供 multicase 结构可区分联合的唯一大小写的名称。

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a>而不对象层次结构中使用可区分的联合
通常，还可以使用可区分的联合作为小对象层次结构一个更简单的替代方法。 例如，下面的可区分的联合无法使用而不是`Shape`基类包含派生类型圆形、 平方形，依次类推。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

改为要计算的区域或外围虚拟方法，你将使用在面向对象的实现，你可以使用模式匹配分支到合适的公式来计算这些数量。 在下面的示例中，不同的公式用于计算区域，具体取决于形状。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

输出如下所示：

```
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a>可区分的联合用于树数据结构
可区分的联合可以是递归的这意味着，可以在类型的一个或多个用例中包含联合本身。 递归可区分的联合可以用于创建树状结构，习惯于编程语言中的模型表达式。 在下面的代码中，递归可区分联合用于创建二元树数据结构。 该联合的两种情况，包括`Node`，这是一个包含一个整数值和左侧和右侧子树节点和`Tip`，后者用于终结树。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

在前面的代码中，`resultSumTree`具有值 10。 下图显示树状结构`myTree`。

![MyTree 的树结构](../media/TreeStructureDiagram.png)

如果在树中的节点是异类是可行的可区分的联合。 在下面的代码中，类型`Expression`表示一种简单的编程语言支持添加中的表达式的抽象语法树和乘法的数字和变量。 某些联合用例都不是递归的表示数字 (`Number`) 或变量 (`Variable`)。 其他情况下是递归的并且表示操作 (`Add`和`Multiply`)，其中操作数也是表达式。 `Evaluate`函数使用匹配到以递归方式进程语法树表达式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

执行此代码时，值`result`为 5。

## <a name="common-attributes"></a>通用属性

以下属性常见可区分联合中：

* `[RequireQualifiedAccess]`
* `[NoEquality]`
* `[NoComparison]`
* `[Struct]` （F # 4.1 和更高版本）

## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)
