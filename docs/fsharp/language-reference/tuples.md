---
title: 元组 (F#)
description: '了解有关 F # 元组的未命名，但有序值，可能具有不同的类型的组。'
ms.date: 05/16/2016
ms.openlocfilehash: d017a2ce8a6ad9b3cec8dfa2ee15b47f06d8f67c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564751"
---
# <a name="tuples"></a>元组

A*元组*是未命名但有序值，可能具有不同的类型的分组。  元组可以是引用类型或结构。

## <a name="syntax"></a>语法

```fsharp
(element, ... , element)
struct(element, ... ,element )
```
## <a name="remarks"></a>备注
每个*元素*在上述语法中可以是任何有效的 F # 表达式。

## <a name="examples"></a>示例
元组的示例包括对、 三元组和等等的相同或不同类型。 在下面的代码阐释了一些示例。

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]
    
## <a name="obtaining-individual-values"></a>获取单个值
你可以使用模式匹配来访问和分配名称对于元组元素，如下面的代码中所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

你还可以解构通过外部的模式匹配的元组`match`通过表达式`let`绑定：

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

可以模式或作为函数的输入匹配的元组：

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

如果你需要此元组仅有一个元素，可以使用通配符字符 （下划线），以避免创建一个值，不需要的新名称。

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

将引用元组中的元素复制到结构元组也非常简单：

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

函数`fst`和`snd`（引用元组仅） 返回第一个和第二个元素的一个元组，将分别。

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

没有内置函数，它返回第三个元素的三元组，但你可以轻松地编写一个，如下所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

通常，最好使用模式匹配来访问各个元组元素。

## <a name="using-tuples"></a>使用元组
元组提供一种简便方式从函数返回多个值，如下面的示例中所示。 此示例对执行整数除法运算并返回的元组对的第一个成员操作，作为对的第二个成员的其余部分舍入的结果。

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

元组也可用作函数自变量用在你想要避免通过常用函数语法隐式的函数自变量的隐式扩充时。

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

用于定义函数的常见语法`let sum a b = a + b`可以定义一个函数，则部分应用函数的第一个参数，如下面的代码中所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

作为参数使用一个元组，将禁用扩充。 有关详细信息，请参阅"部分应用程序的自变量"[函数](functions/index.md)。

## <a name="names-of-tuple-types"></a>元组类型的名称
在写出的类型是一个元组的名称时，你使用`*`符号来分隔元素。 Tuple 组成`int`、 `float`，和一个`string`，如`(10, 10.0, "ten")`，类型，则会写入，如下所示。

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a>与 C# 元组间的互操作

C# 7.0 引入语言的元组。  在 C# 中的元组是结构，并且等效于在 F # 中的结构元组。  如果你需要与 C# 进行互操作，你必须使用结构元组。

这是很简单的操作。  例如，假设你需要将元组传递给 C# 类并随后使用其结果，也是一个元组：

```csharp
namespace CSharpTupleInterop
{
    public static class Example
    {
        public static (int, int) AddOneToXAndY((int x, int y) a) =>
            (a.x + 1, a.y + 1);
    }
}
```

在 F # 代码中，然后可以将作为参数传递结构元组并使用结构的元组形式的结果。

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a>引用的元组和结构元组之间进行转换

引用的元组和结构元组具有完全不同的基础表示形式，因为它们不是隐式转换。  也就是说，如下所示的代码不会编译：

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

必须模式匹配上一个元组，并构造另一种具有构成部分。  例如：

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a>引用的元组的已编译的形式
它们在编译时，本部分说明元组的形式。  此处的信息不需要读取除非面向.NET Framework 3.5 或更低。

元组被编译到的多个泛型类型之一，所有已命名的对象`System.Tuple`，该重载 arity 或数目的类型参数上。 当你从另一种语言，如 C# 或 Visual Basic 中，查看它们，或使用一种工具，不知道的 F # 构造时，元组类型出现在此窗体。 `Tuple`类型在.NET Framework 4 中引入。 如果你面向的.NET Framework 的早期版本，则编译器将使用的版本[System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3)从 2.0 的 F # 核心库版本。 此库中的类型仅用于面向 2.0、 3.0 和 3.5 版本的.NET Framework 的应用程序。 类型转发用于确保.NET Framework 2.0 和.NET Framework 4 F # 组件之间的二进制兼容性。

### <a name="compiled-form-of-struct-tuples"></a>结构元组的已编译的形式

结构元组 (例如， `struct (x, y)`)，从根本上不同于引用元组。  编译为<xref:System.ValueTuple>arity 或类型参数的数目的重载的类型。  它们是等效于[C# 7.0 元组](../../csharp/tuples.md)和[Visual Basic 自 2017 年 1 元组](../../visual-basic/programming-guide/language-features/data-types/tuples.md)，又能交互双向。

## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)

[F# 类型](fsharp-types.md)
