---
title: 可变类型 (F#)
description: '了解如何使用 F # 灵活类型批注，这表示参数、 变量或值具有与指定的类型兼容的类型。'
ms.date: 05/16/2016
ms.openlocfilehash: a54d462d04e4e65680a4612f58da72173f04d1f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="flexible-types"></a>可变类型

A*灵活类型批注*指示参数、 变量或值具有兼容类型使用指定的类型，兼容性由面向对象的层次结构中的类或接口的位置。 灵活的类型很有用，特别是，当自动转换为的类型层次结构中较高的类型不会发生，但你仍想要启用你要使用层次结构中的任何类型或实现接口的任何类型的功能。

## <a name="syntax"></a>语法

```fsharp
#type
```

## <a name="remarks"></a>备注

在上述语法中，*类型*表示基类型或接口。

可变类型等效于具有限制到与基或接口类型相兼容的类型允许的类型的约束的泛型类型。 也就是说，以下两行代码是等效的。

```fsharp
#SomeType

'T when 'T :> SomeType
```

可变类型是几种类型的情况下有用。 例如，如果必须高阶函数 （采用一个函数作为自变量的函数），很有用具有函数返回可变类型。 在下面的示例中，带中的序列参数的灵活类型使用`iterate2`使更高版本的高阶函数，若要使用生成序列、 数组、 列表和任何其他可枚举类型的函数。

请考虑以下两项功能，其中一个的它将返回一个序列，其中其他返回可变类型。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

作为另一个示例，请考虑[Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712)库函数：

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

可以将任何以下的可枚举序列传递给此函数：

- 列表的列表
- 阵列的列表
- 列表的数组
- 序列的数组
- 可枚举的序列的任何其他组合

下面的代码使用`Seq.concat`演示您可以通过使用可变类型支持的方案。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

输出如下所示。

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

在 F # 中，如下所示其他面向对象的语言，有在其中派生的类型或实现接口的类型自动转换为基类型或接口类型的上下文。 在直接自变量，但不是在该类型位于作为一个更复杂的类型，例如函数类型，返回类型的一部分或作为类型参数的从属位置时，会发生这些自动转换。 因此，灵活类型表示法是主要适用，当你要将应用到的类型是更复杂类型的一部分。

## <a name="see-also"></a>请参阅

[F# 语言参考](index.md)

[泛型](generics/index.md)
