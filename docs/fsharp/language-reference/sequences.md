---
title: 序列 (F#)
description: '了解如何使用 F # 序列，当你具有大型，排序的数据集合，但是不一定是希望使用的所有元素。'
ms.date: 05/16/2016
ms.openlocfilehash: ebebec3a69fd0f4fb8e3ad8d554541fa1cc8945e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="sequences"></a>序列

> [!NOTE]
本文中的 API 参考链接将转至 MSDN。  Docs.microsoft.com API 参考尚未完成。

A*序列*是逻辑的一系列元素类型相同的所有。 当你具有大型，排序的数据集合，但一定不希望使用的所有元素时，序列会特别有用。 各个序列元素计算仅为必需的因此序列都可以提供更好的性能比在情况下在不使用的所有元素的列表。 序列由`seq<'T>`类型，这是一个别名为`System.Collections.Generic.IEnumerable`。 因此，任何.NET Framework 类型实现`System.IEnumerable`可用作一个序列。 [Seq 模块](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684)对涉及多个序列的操作提供支持。

## <a name="sequence-expressions"></a>序列表达式
A*序列表达式*是计算结果为一个序列的表达式。 序列表达式可以采用多种形式。 最简单的形式指定范围。 例如，`seq { 1 .. 5 }`创建包含五个元素，包括 1 和 5 的终结点的序列。 也可以指定一个增量 （或递减） 之间两个双句点。 例如，以下代码创建为 10 的倍数的序列。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

序列表达式组成的序列的值为生成的 F # 表达式。 他们可以使用`yield`关键字来生成将成为序列的一部分的值。

下面是一个示例。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

你可以使用`->`运算符而不是`yield`，在这种情况下则可以省略`do`关键字，如下面的示例中所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

下面的代码生成到一个数组，表示网格坐标对以及索引的列表。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

`if`序列中，使用的表达式是一个筛选器。 例如，若要生成只包含质数，假设您有一个函数的序列`isprime`类型的`int -> bool`，按以下方式构造序列。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

当你使用`yield`或`->`迭代后，在每次迭代都应生成序列的单个元素。 如果每次迭代将生成一个序列的元素，使用`yield!`。 在这种情况下，每个迭代上生成的元素串联在一起以生成最终的序列。

你可以组合在一起在序列表达式中的多个表达式。 由每个表达式生成的元素连接在一起。 有关示例，请参阅本主题的"示例"一节。

## <a name="examples"></a>示例
第一个示例使用包含迭代、 筛选器，yield 来生成一个数组为序列表达式。 此代码将打印介于 1 和 100 到控制台之间的质数的序列。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

下面的代码使用`yield`若要创建的三个元素，其中每个包括的两个因素和产品的元组组成一个乘法表。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

下面的示例演示了利用`yield!`组合到一个最终序列的单个序列。 在这种情况下，二进制树中每个子树的序列串联在一起的递归函数，以生成最终的序列中。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]
    
## <a name="using-sequences"></a>使用序列
序列支持许多功能与成员相同[列出](lists.md)。 序列还支持分组，然后通过使用键生成函数计算等操作。 序列还支持多不同的功能，用于提取子序列。

许多数据类型，如列表、 数组、 组和地图隐式是序列，因为它们是可枚举集合。 将一个序列，作为参数的工作方式与任何常见的 F # 数据类型，此外为实现任何.NET Framework 数据类型的函数`System.Collections.Generic.IEnumerable<'T>`。 正好相反，将列表作为参数，它只能使用列表的函数。 类型`seq<'T>`是类型缩写`IEnumerable<'T>`。 这意味着，可以实现泛型的任何类型`System.Collections.Generic.IEnumerable<'T>`，其中包括数组、 列表、 设置，并在 F # 中，并还大多数.NET Framework 集合类型，映射是与兼容`seq`键入和可以在一个序列的任何地方使用。


## <a name="module-functions"></a>模块函数
[Seq 模块](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684)中[Microsoft.FSharp.Collections 命名空间](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f)包含用于使用序列函数。 这些函数处理列表、 数组、 映射和集，因为所有这些类型是可枚举的并因此会被视为序列。


## <a name="creating-sequences"></a>创建序列
通过使用序列表达式，如前面所述，或通过使用某些函数，您可以创建序列。

你可以通过创建空序列[Seq.empty](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59)，也可以通过使用来创建只在一个指定元素的序列[Seq.singleton](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7)。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet9.fs)]

你可以使用[Seq.init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576)创建为其元素通过使用你提供的函数创建的序列。 您还可以为序列提供大小。 此函数就像是[List.init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83)，只不过循环访问序列时才会创建元素。 下面的代码演示如何使用`Seq.init`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet10.fs)]

输出为

```
0 10 20 30 40
```

通过使用[Seq.ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99)和[Seq.ofList&#60;无法&#62;函数](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d)，你可以从数组和列表创建序列。 但是，你还可以将转换数组和列表到序列使用转换运算符。 在下面的代码演示了这两种技术。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet11.fs)]

通过使用[Seq.cast](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334)，您可以创建一个序列，从弱类型的集合，如中定义的那些`System.Collections`。 此类弱类型的集合具有元素类型`System.Object`并通过使用非泛型枚举`System.Collections.Generic.IEnumerable&#96;1`类型。 下面的代码演示如何使用`Seq.cast`要转换`System.Collections.ArrayList`为一个序列。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet12.fs)]

您可以通过使用定义无限的序列[Seq.initInfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef)函数。 此类的序列，你可以提供生成每个元素从元素的索引的函数。 之所以可行无限的序列是由于迟缓计算;根据需要通过调用你指定的函数，则会创建元素。 下面的代码示例将生成一系列交替出现的连续整数的平方的倒数浮点数，在此情况下无限序列。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet13.fs)]

[Seq.unfold](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21)从计算函数，它接受状态，并将其以生成序列中的每个后续元素转换生成的序列。 状态为只是一个值，用于计算每个元素，并且可以将更改为计算每个元素。 第二个参数`Seq.unfold`是用于启动序列的初始值。 `Seq.unfold` 使用状态时，它使你可以通过返回终止序列选项类型`None`值。 下面的代码演示的序列，两个示例`seq1`和`fib`，由生成`unfold`操作。 首先， `seq1`，是只具有最多 100 个数字的简单序列。 第二个， `fib`，使用`unfold`来计算斐波那契序列。 因为斐波那契序列中的每个元素之和的前两个斐波那契数字，状态的值将是一个元组组成的序列中前两个数字。 初始值是`(1,1)`，该序列中的前两个数字。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet14.fs)]

输出如下所示：

```
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

下面的代码演示了使用许多序列模块函数此处所述来生成和计算无限的序列的值。 该代码可能需要几分钟才能运行。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet15.fs)]
    
## <a name="searching-and-finding-elements"></a>搜索和查找元素
序列支持适用于列表的功能： [Seq.exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1)， [Seq.exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565)， [Seq.find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8)， [Seq.findIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3)， [Seq.pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d)， [Seq.tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47)，和[Seq.tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a)。 可用于序列这些函数的版本的计算结果仅到进行搜索的元素序列。 有关示例，请参阅[列出](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d)。


## <a name="obtaining-subsequences"></a>获取子序列
[Seq.filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770)和[Seq.choose](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395)是否与相应的函数，只不过的筛选和选择不会发生之前计算序列元素所提供的列表，类似。

[Seq.truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244)从另一个序列，创建一个序列，但会指定数量的元素的序列。 [Seq.take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596)创建新的序列，其中包含仅的指定的数量的序列的开始的元素。 如果有较少元素序列中的超过您指定要执行，`Seq.take`引发`System.InvalidOperationException`。 之间的差异`Seq.take`和`Seq.truncate`在于`Seq.truncate`数少于指定的元素数是否不会生成错误。

下面的代码显示的行为和之间的差异`Seq.truncate`和`Seq.take`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet16.fs)]

输出中，发生此错误之前，是，如下所示。

```
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100 
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100
```

通过使用[Seq.takeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92)，可以指定的谓词函数 （布尔函数），并从为其谓词是对原始序列的这些元素组成的另一个序列中创建序列`true`，但停止谓词为其返回的第一个元素之前`false`。 [Seq.skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1)返回序列，可跳过指定的数目的另一个序列的第一个元素并返回剩余元素。 [Seq.skipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16)返回跳过另一个序列的第一个元素，只要该谓词返回的序列`true`，然后返回剩余元素，谓词为其返回的第一个元素开始`false`.

下面的代码示例阐释了的行为和之间的差异`Seq.takeWhile`， `Seq.skip`，和`Seq.skipWhile`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet17.fs)]

输出如下所示。

```
1 4 9 
36 49 64 81 100 
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>转换序列
[Seq.pairwise](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1)创建新的序列中对输入序列的连续元素组合到元组。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet18.fs)]

[Seq.windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744)类似`Seq.pairwise`，只不过而不是生成的元组序列，它会生成一个序列包含的相邻元素副本的数组 (*窗口*) 从序列。 每个数组中指定所需的相邻元素的数目。

以下代码示例演示了 `Seq.windowed` 的用法。 在这种情况下的窗口中的元素数为 3。 该示例使用`printSeq`，前面的代码示例中定义。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet180.fs)]

输出如下所示。

初始序列：

```
1.0 1.5 2.0 1.5 1.0 1.5 

Windows of length 3: 
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|] 

Moving average: 
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a>具有多个序列的操作
[Seq.zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4)和[Seq.zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16)采用两个或三个序列并生成一个元组序列。 这些函数是与相应的函数可用于类似[列出](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d)。 没有相应的功能将一个序列分成两个或多个序列。 如果你需要此功能的序列，将序列转换为列表，并使用[List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)。


## <a name="sorting-comparing-and-grouping"></a>排序、 比较和分组
对于列表中支持的排序函数也适用于序列中。 这包括[Seq.sort](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e)和[Seq.sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f)。 这些函数循环访问整个序列。

通过比较两个序列[Seq.compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f)函数。 该函数反过来，比较连续元素，并在遇到第一个不相等对时停止。 比较不有利于实现任何其他元素。

以下代码显示了 `Seq.compareWith` 的用法。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet19.fs)]

在前面的代码中，仅第一个元素是计算和检查，并且结果为-1。

[Seq.countBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f)采用生成名为的值的函数*密钥*每个元素。 通过对每个元素调用此函数的每个元素生成一个密钥。 `Seq.countBy` 然后返回一个序列，其中包含的项的值，并生成密钥的每个值的元素数的计数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet201.fs)]

输出如下所示。

```
(1, 34) (2, 33) (0, 33)
```

前面的输出显示有 34 元素生成的项 1，对原始序列的 33 个值生成的密钥 2 和 33 生成了键 0 的值。

你可以通过调用分组的序列的元素[Seq.groupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd)。 `Seq.groupBy` 采用一个序列和从元素中生成一个键的函数。 序列的每个元素执行函数。 `Seq.groupBy` 返回的元组，其中每个元组的第一个元素是键，而第二个是生成该密钥的元素的序列的序列。

下面的代码示例演示了利用`Seq.groupBy`进行分区的从 1 到 100 的数字序列分成三个具有不同的密钥值 0、 1 和 2 的组。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet202.fs)]

输出如下所示。

```
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

你可以创建通过调用中消除重复的元素的序列[Seq.distinct](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401)。 也可以使用[Seq.distinctBy](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75)，这需要对每个元素调用的键生成函数。 所产生的序列包含具有唯一键; 对原始序列的元素更高版本生成的更早版本的元素的重复键的元素将被丢弃。

下面的代码示例演示如何使用`Seq.distinct`。 `Seq.distinct` 通过生成表示二进制数字的序列，然后显示仅非重复元素为 0 和 1 演示了。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet22.fs)]

下面的代码演示`Seq.distinctBy`通过启动包含正负数字的序列使用绝对值的数值函数作为键生成函数。 所产生的序列缺少对应于序列中的负数字，因为负数出现在序列中提前但因此选择而不是具有相同的绝对正数的所有正数值值或密钥。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet23.fs)]
    
## <a name="readonly-and-cached-sequences"></a>Readonly 和缓存的序列
[Seq.readonly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7)创建的序列的只读副本。 `Seq.readonly` 有一个读写的集合，如数组，并且你不想要修改原始集合时非常有用。 此函数可用来保留数据封装。 在下面的代码示例中，创建包含数组的类型。 属性可公开数组，但而不是返回一个数组，它将返回一个序列，其中通过使用从该数组创建`Seq.readonly`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet24.fs)]

[Seq.cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0)创建一个序列的存储的版本。 使用`Seq.cache`以避免重新评估的序列，或如果你具有多个线程，使用一个序列，但你必须确保每个元素执行操作时只进行一次。 如果你正在使用多个线程的序列，你可以枚举并计算的原始序列的值的一个线程，并且剩余线程可以使用缓存的序列。


## <a name="performing-computations-on-sequences"></a>对序列执行计算
简单的算术运算是类似的列表，如[Seq.average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8)， [Seq.sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a)， [Seq.averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8)， [Seq.sumBy](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1)，依次类推。

[Seq.fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3)， [Seq.reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9)，和[Seq.scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e)是否与可用于列出的相应函数类似。 序列支持列出了支持的这些函数的完全变体的子集。 有关详细信息和示例，请参阅[列出](lists.md)。

## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)

[F# 类型](fsharp-types.md)
