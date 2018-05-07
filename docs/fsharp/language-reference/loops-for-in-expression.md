---
title: 循环：for...in 表达式 (F#)
description: '请参阅如何 F # 为..表达式中循环构造用于循环访问的可枚举集合中的模式的匹配项。'
ms.date: 05/16/2016
ms.openlocfilehash: 926f0a9940021b3dc0deefc12ea158c35975e949
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="loops-forin-expression"></a>循环：for...in 表达式

此循环构造用于循环访问如范围表达式、 序列、 列表、 数组或其他构造，用于支持枚举的可枚举集合中的模式的匹配项。


## <a name="syntax"></a>语法

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a>备注
`for...in`表达式可以相比`for each`中其他.NET 语言语句因为它用于循环访问的可枚举集合中的值。 但是，`for...in`还支持针对的模式匹配集合，而不仅仅是迭代不必对整个集合。

可以指定的可枚举的表达式，可枚举集合形式，或通过使用`..`运算符，作为在整数类型的范围。 可枚举的集合包括列表、 序列、 数组、 集、 映射和等等。 实现任何类型`System.Collections.IEnumerable`可用。

当使用表示范围`..`运算符，你可以使用以下语法。

*启动*... *完成*

你还可以使用一种包括递增调用*跳过*，如下面的代码。

*启动*... *跳过*... *完成*

当你使用作为一种模式的整数范围和一个简单的计数器变量时，典型的行为是计数器变量递增 1 在每次迭代，但如果范围还包括 skip 值，该计数器就会递增 skip 值改为。

此外可以正文表达式中使用匹配模式中的值。

下面的代码示例阐释使用`for...in`表达式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

输出如下所示。

```
1
5
100
450
788
```

下面的示例演示如何循环访问序列，以及如何使用而不是简单变量的元组模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

输出如下所示。

```
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

下面的示例演示如何循环简单整数范围内。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

Function1 的输出如下所示。

```
1 2 3 4 5 6 7 8 9 10
```

下面的示例演示如何循环访问一系列具有 skip 值为 2，其中包括每个其他元素的范围。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

输出`function2`如下。

```
1 3 5 7 9
```

下面的示例演示如何使用字符范围。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

输出`function3`如下。

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

下面的示例演示如何使用负的 skip 值来进行反向迭代。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

输出`function4`如下。

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

开始和结束范围也可以是表达式，如函数，如以下代码所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

输出`function5`此输入与，如下所示。

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

元素不需要在循环中时下, 一个示例演示了利用通配符字符 (_)。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

输出如下所示。

```
Number of elements in list1: 5
```

`Note` 你可以使用`for...in`序列表达式和其他计算表达式，在这种情况下的自定义的版本`for...in`使用表达式。 有关详细信息，请参阅[序列](sequences.md)，[异步工作流](asynchronous-workflows.md)，和[计算表达式](computation-expressions.md)。


## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)

[循环：`for...to` 表达式](loops-for-to-expression.md)

[循环：`while...do` 表达式](loops-while-do-expression.md)
