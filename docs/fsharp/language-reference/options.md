---
title: "选项 (F#)"
description: "了解如何使用 F # 类型时的实际值可能不存在的选项为命名的值或变量。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a15b5cf1-9055-4481-918c-4c8a051b5829
ms.openlocfilehash: 537ba69aecc1ab489de63d67c5f9ff857afb4a28
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="options"></a>选项

实际值可能不存在为已命名的值或变量时使用 F # 中的选项类型。 选项有一个基础类型，并可以保持该类型的值，或者它可能不具有值。

## <a name="remarks"></a>备注
下面的代码演示生成选项类型的函数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

你可以看到，如果输入`a`大于 0，`Some(a)`生成。  否则为`None`生成。

值`None`选项没有实际值时使用。 否则为表达式`Some( ... )`为提供的选项值。 值`Some`和`None`可在模式匹配，如下面的函数中所示`exists`，它将返回`true`如果选项的值和`false`如果它不存在。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>使用选项
选项时常用的搜索不返回匹配的结果，如下面的代码中所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

在前面的代码中，将以递归方式搜索的列表。 该函数`tryFindMatch`采用一个谓词函数`pred`，返回一个布尔值和要搜索的列表。 如果找到满足谓词的元素，则递归结束，并且该函数返回的值作为表达式中的一个选项`Some(head)`。 递归过程结束时匹配空列表。 在该点的值`head`未找到，和`None`返回。

很多 F # 库函数可能或可能不存在返回的值在集合中搜索`option`类型。 按照约定，这些函数开头`try`前缀，例如， [ `Seq.tryFindIndex` ](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a)。

例如，如果有可能时尝试构造一个值，将引发异常，可能不存在的值时，选项也会很有用。 下面的代码示例阐释了这一点。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

`openFile`上一示例中的函数具有类型`string -> File option`因为它返回`File`对象如果成功地打开了文件和`None`如果发生异常。 具体取决于这种情况，它可能不是合适的设计选择，来捕获异常，而不是使其能够传播。


## <a name="option-properties-and-methods"></a>选项属性和方法
选项类型支持以下属性和方法。



|属性或方法|类型|描述|
|------------------|----|-----------|
|[无](https://msdn.microsoft.com/library/83ef260a-aa33-4e6f-aee6-b9bf0a461476)|`'T option`|静态属性，可用于创建具有的选项值`None`值。|
|[IsNone](https://msdn.microsoft.com/library/f08532ca-1716-4f60-ae59-8ef6256df234)|`bool`|返回`true`如果选项具有`None`值。|
|[IsSome](https://msdn.microsoft.com/library/c5088d51-c5d7-425f-a77f-12c379bb356f)|`bool`|返回`true`如果选项具有一个值，不是`None`。|
|[某些](https://msdn.microsoft.com/library/12f048d2-e293-4596-accb-de036ecd63fc)|`'T option`|静态成员，它创建一个选项可有一个值，不是`None`。|
|[值](https://msdn.microsoft.com/library/c79f68e8-11fd-45b1-a053-e8fc38b56df7)|`'T`|返回基础值，或引发`System.NullReferenceException`如果值为`None`。|

## <a name="option-module"></a>Option 模块
将某个模块[选项](https://msdn.microsoft.com/library/e615e4d3-bbbb-49ba-addc-6061ea2e2f4c)，其中包含有用的函数执行操作的选项。 某些函数重复的属性的功能，但很有用的上下文中需要一个函数的位置。 [Option.isSome](https://msdn.microsoft.com/library/41ad0857-5672-4326-84b5-c33dc43dcf79)和[Option.isNone](https://msdn.microsoft.com/library/73db6a53-15e7-40a6-94f9-a0049e5f4819)是这两个测试是否选项持有值的模块函数。 [Option.get](https://msdn.microsoft.com/library/803e9fcb-6edd-4910-808c-25f08cbc55ea)获取值，如果有一个。 如果没有值，它将引发`System.ArgumentException`。

[Option.bind](https://msdn.microsoft.com/library/c3406192-24ac-49b5-bc3b-8f805187f1c0)函数值，执行的函数，如果没有一个值。 该函数必须采用一个自变量，并且其参数类型必须是选项类型。 该函数的返回值是另一个选项类型。

Option 模块还包含对应于所提供的列表、 数组、 序列和其他集合类型的函数的函数。 这些功能包括[ `Option.map` ](https://msdn.microsoft.com/library/91a20385-7e73-40c2-9adc-635e86d6a622)， [ `Option.iter` ](https://msdn.microsoft.com/library/83389eef-3dff-4074-b4cc-f69581c25191)， [ `Option.forall` ](https://msdn.microsoft.com/library/ba884586-5eae-49c5-9e36-05481c1c3428)， [ `Option.exists` ](https://msdn.microsoft.com/library/a606d2d4-fddc-4eab-ab37-c6138fb7ad99)， [ `Option.foldBack` ](https://msdn.microsoft.com/library/a882fbaf-c019-46f0-b4f5-b8c2b8b90ffb)， [ `Option.fold` ](https://msdn.microsoft.com/library/af896794-3d53-406c-9411-316cd5c33ad8)，和[ `Option.count` ](https://msdn.microsoft.com/library/2dac83a9-684e-4d0f-b50e-ff722a8bb876)。 这些函数启用像零个或一个元素的集合使用的选项。 有关详细信息和示例，请参阅集合中的函数的讨论[列出](lists.md)。


## <a name="converting-to-other-types"></a>将转换为其他类型
选项可以转换为列表或数组。 当一个选项转换为上述任一这些数据结构时，生成的数据结构中有零个或一个元素。 若要转换为数组的一个选项，请使用[ `Option.toArray` ](https://msdn.microsoft.com/library/c8044873-ba17-4b52-8231-eb1a28318c64)。 若要将一个选项转换为列表中，使用[ `Option.toList` ](https://msdn.microsoft.com/library/5f1af295-9fa9-40ad-b4a1-3578d94d44e1)。


## <a name="see-also"></a>另请参阅
[F# 语言参考](index.md)

[F# 类型](fsharp-types.md)
