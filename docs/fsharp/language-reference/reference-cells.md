---
title: "引用单元格 (F#)"
description: "了解如何使您能够创建具有引用语义的可变值的存储位置 F # 引用单元格。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 09a0b221-ea21-45c4-bae8-5e4a339750c4
ms.openlocfilehash: c7470c9a36cf2cd24dd89ceffcf6e90c6dc4d2dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="reference-cells"></a>引用单元格

*引用单元格*使您能够创建具有引用语义的可变值的存储位置。

## <a name="syntax"></a>语法

```fsharp
ref expression
```

## <a name="remarks"></a>备注
可以在值前面使用 `ref` 运算符来创建用于封装该值的新引用单元格。 然后，您可以更改基础值，因为该值是可变的。

引用单元格容纳实际值；它不仅仅是一个地址。 使用 `ref` 运算符创建引用单元格时，将以封装的可变值的形式创建基础值的副本。

可以使用 `!`（感叹号）运算符取消对引用单元格的引用。

下面的代码示例阐释了引用单元格的声明和用法。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

输出为 `50`。

引用单元格是 `Ref` 泛型记录类型的实例，声明方式如下所示。

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

类型 `'a ref` 是 `Ref<'a>` 的同义词。 IDE 中的编译器和 IntelliSense 显示此类型的前者，而基础定义是后者。

`ref` 运算符创建新引用单元格。 下面的代码声明 `ref` 运算符。

```fsharp
let ref x = { contents = x }
```

下表显示了可用于引用单元格的功能。

|运算符、成员或字段|描述|类型|定义|
|--------------------------|-----------|----|----------|
|`!`（取消引用运算符）|返回基础值。|`'a ref -> 'a`|`let (!) r = r.contents`|
|`:=`（赋值运算符）|更改基础值。|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|`ref`（运算符）|将值封装到新的引用单元格中。|`'a -> 'a ref`|`let ref x = { contents = x }`|
|`Value`（属性）|获取或设置基础值。|`unit -> 'a`|`member x.Value = x.contents`|
|`contents`（记录字段）|获取或设置基础值。|`'a`|`let ref x = { contents = x }`|
可通过多种方式来访问基础值。 取消引用运算符 (`!`) 返回的值不是可赋值的值。 因此，如果要修改基础值，您必须改用赋值运算符 (`:=`)。

`Value` 属性和 `contents` 字段都是可赋值的值。 因此，你可以使用它们来访问或更改基础值，如下面的代码所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

输出如下所示。

```
10
10
11
12
```

提供字段 `contents` 的目的是为了与其他版本的 ML 兼容，并且该字段将在编译过程中产生警告。 若要禁用警告，请使用 `--mlcompatibility` 编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)。

下面的代码阐释了参数传递中引用单元格的用法。 增量类型有一个方法采用一个参数以包括 byref 参数类型中的增量。 中的参数类型 byref 指示，调用方必须传递引用单元格或指定类型的典型变量的地址在此案例 int。其余的代码演示如何使用这两种类型的参数，调用递增和上一个变量来创建引用单元格 (ref myDelta1) 演示了如何使用 ref 运算符。 然后，它演示了如何使用 address-of 运算符 (&amp;) 来生成相应的参数。 最后，由使用让的绑定声明的引用单元格再次调用 Increment 方法。 代码的最后一行演示如何使用 ！ 运算符来取消引用用于打印的单元格。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2204.fs)]

有关如何按引用传递的详细信息，请参阅[参数和自变量](parameters-and-arguments.md)。

>[!NOTE]
C# 程序员应知道该 ref 的工作方式在 F # 与在 C#。 例如，使用 ref 时传递了参数没有相同的效果在 F # 中 C# 中的一样。

## <a name="consuming-c-ref-returns"></a>使用 C#`ref`返回

F # 4.1 开始，你可以使用`ref`返回在 C# 中生成。  此类调用的结果是`byref<_>`指针。

以下 C# 方法：

```csharp
namespace RefReturns
{
    public static class RefClass
    {
        public static ref int Find(int val, int[] vals)
        {
            for (int i = 0; i < vals.Length; i++)
            {
                if (vals[i] == val)
                {
                    return ref numbers[i]; // Returns the location, not the value
                }
            }

            throw new IndexOutOfRangeException($"{nameof(number)} not found");
        }
    }
}
```

可以以透明方式由调用 F # 与任何特殊的语法：

```fsharp
open RefReturns

let consumeRefReturn() =
    let result = RefClass.Find(3, [| 1; 2; 3; 4; 5 |]) // 'result' is of type 'byref<int>'.
    ()
```

您还可以声明函数可能需要`ref`返回作为输入，例如：

```fsharp
let f (x: byref<int>) = &x
```

当前没有方法来生成`ref`返回在 F # 无法在 C# 中使用。

## <a name="see-also"></a>另请参阅
[F# 语言参考](index.md)

[参数和自变量](parameters-and-arguments.md)

[符号和运算符参考](symbol-and-operator-reference/index.md)
