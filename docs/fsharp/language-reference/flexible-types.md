---
title: 可变类型
description: 了解如何使用F#可变类型批注，该批注指示参数、变量或值具有与指定类型兼容的类型。
ms.date: 05/16/2016
ms.openlocfilehash: bf05f78f163d1f9c73c667df60925b66a5315627
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083063"
---
# <a name="flexible-types"></a>可变类型

*可变类型批注*指示参数、变量或值具有与指定类型兼容的类型，其中的兼容性由类或接口的面向对象的层次结构中的位置确定。 当不发生类型层次结构中较高的类型的自动转换但仍希望使你的功能可以与层次结构中的任何类型或实现接口的任何类型一起使用时，灵活类型特别有用。

## <a name="syntax"></a>语法

```fsharp
#type
```

## <a name="remarks"></a>备注

在前面的语法中，*类型*表示基类型或接口。

灵活类型等效于具有约束的泛型类型，该约束将允许的类型限制为与基类型或接口类型兼容的类型。 也就是说，以下两行代码是等效的。

```fsharp
#SomeType

'T when 'T :> SomeType
```

灵活类型在多种情况下都很有用。 例如，如果您具有高阶函数（采用函数作为参数的函数），则使函数返回灵活类型通常很有用。 在下面的示例中，在中`iterate2`使用带序列参数的灵活类型使高阶函数能够使用生成序列、数组、列表和任何其他可枚举类型的函数。

请考虑以下两个函数，其中一个函数返回一个序列，另一个返回一个可变类型。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

作为另一个示例，请考虑[Seq](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library 函数：

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

可以将以下任一可枚举序列传递到此函数：

- 列表列表
- 数组的列表
- 列表的数组
- 序列数组
- 可枚举序列的任何其他组合

下面的代码使用`Seq.concat`灵活的类型来演示可支持的方案。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

输出如下所示。

```console
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

在F#中，与在其他面向对象的语言中一样，某些上下文中实现接口的派生类型或类型会自动转换为基类型或接口类型。 这些自动转换在直接参数中进行，但当类型位于从属位置时，不会发生在作为更复杂类型（如函数类型的返回类型）或类型参数的一部分的情况下。 因此，当您要将它应用到的类型是更复杂类型的一部分时，灵活的类型表示法主要非常有用。

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
- [泛型](./generics/index.md)
