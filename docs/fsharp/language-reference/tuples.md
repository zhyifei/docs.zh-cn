---
title: 元组
description: 了解F#元组, 一组未命名但有序值, 可能不同类型。
ms.date: 05/16/2016
ms.openlocfilehash: 7a15d7e0c6c9b42118dd75066f02cbb2e05335fc
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630237"
---
# <a name="tuples"></a>元组

*元组*是未命名但有序值的分组, 可能不同类型。  元组可以是引用类型或结构。

## <a name="syntax"></a>语法

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a>备注

前面语法中的每个*元素*可以是任何F#有效的表达式。

## <a name="examples"></a>示例

元组的示例包括对相同类型或不同类型的成对、三元组等。 下面的代码演示了一些示例。

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a>获取单个值

可以使用模式匹配来访问和分配元组元素的名称, 如下面的代码所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

还可以通过`match` `let`绑定, 通过表达式外部的模式匹配析构元组:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

或者, 你可以将元组的匹配方式作为函数的输入进行模式:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

如果只需要元组的一个元素, 则可以使用通配符 (下划线) 来避免为不需要的值创建新名称。

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

将引用元组中的元素复制到结构元组中也很简单:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

函数`fst` 和`snd` (仅引用元组) 分别返回元组的第一个和第二个元素。

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

没有任何内置函数返回三方的第三个元素, 但您可以按如下所示轻松编写一个元素。

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

通常情况下, 最好使用模式匹配来访问各个元组元素。

## <a name="using-tuples"></a>使用元组

元组提供一种从函数返回多个值的便捷方法, 如下面的示例中所示。 此示例执行整数除法运算, 并将运算的舍入结果作为元组对的第一个成员, 并将余数作为成对的第二个成员返回。

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

如果要避免使用常规函数语法所隐含的函数参数的隐式 currying, 则元组也可以用作函数自变量。

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

定义函数`let sum a b = a + b`的常用语法允许您定义一个函数, 该函数是函数的第一个自变量的部分应用程序, 如下面的代码所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

使用元组作为参数将禁用 currying。 有关详细信息, 请参阅[函数](./functions/index.md)中的 "参数的部分应用"。

## <a name="names-of-tuple-types"></a>元组类型的名称

写出作为元组的类型的名称时, 使用`*`符号分隔元素。 对于包含`int` `string`、 `float`和的元组(如),将按如下`(10, 10.0, "ten")`方式编写类型。

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a>与C#元组互操作

C#7.0 引入了元组到语言。  中C#的元组是结构, 等效于中F#的结构元组。  如果需要与C#进行互操作, 则必须使用结构元组。

这很简单。  例如, 假设您必须将元组传递给某个C#类, 然后使用它的结果, 这也是一个元组:

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

然后, F#你可以在代码中将结构元组作为参数传递, 并将结果用作结构元组。

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a>引用元组与结构元组之间的转换

由于引用元组和结构元组具有完全不同的基础表示形式, 因此它们不能隐式转换。  也就是说, 以下代码将不会编译:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

您必须对一个元组进行匹配模式, 并用构成部分构造另一个元组。  例如:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a>引用元组的编译形式

本部分说明元组在编译时的形式。  除非目标 .NET Framework 3.5 或更低, 否则此处不需要阅读此处的信息。

元组将编译为多个泛型类型之一的对象, `System.Tuple`这些泛型类型都是在 arity 上重载的, 或者是类型参数的数目。 当你从另一种语言 (如C#或 Visual Basic) 查看这些元组类型时, 或者当你使用的工具无法识别F#构造时, 元组类型会显示在此窗体中。 类型`Tuple`是在 .NET Framework 4 中引入的。 如果以 .NET Framework 的早期版本为目标, 则编译器将使用2.0 版本的[System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) F#核心库中的版本。 此库中的类型仅用于面向2.0、3.0 和3.5 版本的 .NET Framework 的应用程序。 类型转发用于确保 .NET Framework 2.0 和 .NET Framework 4 F#组件之间的二进制兼容性。

### <a name="compiled-form-of-struct-tuples"></a>结构元组的编译形式

结构元组 (例如`struct (x, y)`) 在本质上不同于引用元组。  它们被编译到<xref:System.ValueTuple>类型中, 由 arity 重载或类型参数的数目。  它们等效于[ C# 7.0 元](../../csharp/tuples.md)组和[Visual Basic 2017 元组](../../visual-basic/programming-guide/language-features/data-types/tuples.md), 并互操作双向。

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
- [F# 类型](fsharp-types.md)
