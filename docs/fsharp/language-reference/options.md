---
title: 选项
description: 了解当命名值F#或变量可能不存在实际值时如何使用选项类型。
ms.date: 05/16/2016
ms.openlocfilehash: 9326cf04f53adac7422c09a49a59c4eecd49486d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627346"
---
# <a name="options"></a>选项

如果命名值或F#变量可能不存在实际值, 则使用中的选项类型。 选项具有基础类型并且可以保存该类型的值, 或它可能没有值。

## <a name="remarks"></a>备注

下面的代码演示了一个生成选项类型的函数。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

正如您所看到的, 如果`a`输入大于 0, `Some(a)`则生成。  否则, `None`将生成。

当选项`None`没有实际值时, 使用值。 否则, 表达式`Some( ... )`将为选项提供一个值。 值`Some` `true`和`None`可用于模式匹配, 如下面的函数`exists`中所示, 如果选项具有值, 则`false`返回; 否则返回。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>使用选项

如果搜索不返回匹配的结果, 通常会使用选项, 如下面的代码所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

在前面的代码中, 将以递归方式搜索列表。 函数`tryFindMatch`采用一个谓词函数, `pred`该函数返回布尔值和要搜索的列表。 如果找到满足该谓词的元素, 则递归结束, 并且函数以表达式`Some(head)`形式返回值。 当匹配空列表时, 递归结束。 此时, 未找到值`head` `None` , 返回。

许多F#库函数在集合中搜索可能存在也可能不存在的值将返回该`option`类型。 按照约定, 这些函数以`try`前缀开头, [`Seq.tryFindIndex`](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a)例如。

当某个值可能不存在时 (例如, 如果在尝试构造值时可能会引发异常), 选项也可能有用。 下面的代码示例阐释了这一点。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

上`openFile`一示例中的函数具有类型`string -> File option` , 因为如果文件`File`成功打开并且发生异常, `None`则它将返回一个对象。 根据具体的情况, 它可能不是捕获异常而不允许它传播的合适设计选项。

此外, 还可以传递`null`或值为 null `Some`的值, 这是一个选项。 通常可以避免这种情况, 通常在日常F#编程中, 但这可能是因为 .net 中的引用类型的性质。

## <a name="option-properties-and-methods"></a>选项属性和方法

选项类型支持以下属性和方法。

|属性或方法|类型|描述|
|------------------|----|-----------|
|[无](https://msdn.microsoft.com/library/83ef260a-aa33-4e6f-aee6-b9bf0a461476)|`'T option`|一个静态属性, 可用于创建一个具有`None`值的选项值。|
|[IsNone](https://msdn.microsoft.com/library/f08532ca-1716-4f60-ae59-8ef6256df234)|`bool`|如果`true` 选项`None`的值为, 则返回。|
|[IsSome](https://msdn.microsoft.com/library/c5088d51-c5d7-425f-a77f-12c379bb356f)|`bool`|如果`true`选项的值不`None`为, 则返回。|
|[Some](https://msdn.microsoft.com/library/12f048d2-e293-4596-accb-de036ecd63fc)|`'T option`|一个静态成员, 该成员创建的选项的值不`None`是。|
|[ReplTest1](https://msdn.microsoft.com/library/c79f68e8-11fd-45b1-a053-e8fc38b56df7)|`'T`|返回基础值, `System.NullReferenceException`如果值为`None`, 则引发。|

## <a name="option-module"></a>选项模块

有一个模块[选项](https://msdn.microsoft.com/library/e615e4d3-bbbb-49ba-addc-6061ea2e2f4c), 它包含对选项执行操作的有用函数。 某些函数会重复属性的功能, 但在需要函数的上下文中很有用。 [IsSome](https://msdn.microsoft.com/library/41ad0857-5672-4326-84b5-c33dc43dcf79)和[isNone](https://msdn.microsoft.com/library/73db6a53-15e7-40a6-94f9-a0049e5f4819)都是测试选项是否包含值的模块函数。 [Option 获取](https://msdn.microsoft.com/library/803e9fcb-6edd-4910-808c-25f08cbc55ea)值 (如果有)。 如果没有值, 则会引发`System.ArgumentException`。

如果有值, 则该[方法](https://msdn.microsoft.com/library/c3406192-24ac-49b5-bc3b-8f805187f1c0)会对值执行函数。 函数必须仅采用一个自变量, 并且其参数类型必须为选项类型。 函数的返回值是另一个选项类型。

选项模块还包括与可用于列表、数组、序列和其他集合类型的函数相对应的函数。 这些函数包括[`Option.map`](https://msdn.microsoft.com/library/91a20385-7e73-40c2-9adc-635e86d6a622) [`Option.iter`](https://msdn.microsoft.com/library/83389eef-3dff-4074-b4cc-f69581c25191) [、、`Option.exists`](https://msdn.microsoft.com/library/a606d2d4-fddc-4eab-ab37-c6138fb7ad99) [、、`Option.foldBack`](https://msdn.microsoft.com/library/a882fbaf-c019-46f0-b4f5-b8c2b8b90ffb)、[和`Option.count`](https://msdn.microsoft.com/library/2dac83a9-684e-4d0f-b50e-ff722a8bb876)。 [`Option.forall`](https://msdn.microsoft.com/library/ba884586-5eae-49c5-9e36-05481c1c3428) [`Option.fold`](https://msdn.microsoft.com/library/af896794-3d53-406c-9411-316cd5c33ad8) 这些函数可用于将选项用作零个或一个元素的集合。 有关详细信息和示例, 请参阅 "[列表](lists.md)中的集合函数讨论"。

## <a name="converting-to-other-types"></a>转换为其他类型

选项可以转换为列表或数组。 当某个选项转换为这些数据结构中的任何一个时, 生成的数据结构将包含零个或一个元素。 若要将选项转换为数组, 请[`Option.toArray`](https://msdn.microsoft.com/library/c8044873-ba17-4b52-8231-eb1a28318c64)使用。 若要将选项转换为列表, 请[`Option.toList`](https://msdn.microsoft.com/library/5f1af295-9fa9-40ad-b4a1-3578d94d44e1)使用。

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
- [F# 类型](fsharp-types.md)
