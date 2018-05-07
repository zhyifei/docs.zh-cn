---
title: 静态解析的类型参数 (F#)
description: '了解如何使用 F # 静态解析的类型参数，它将被替换为实际类型在编译时而不是在运行时。'
ms.date: 05/16/2016
ms.openlocfilehash: 30a7de0a3bc523ef17c1f89d6f88549069f752f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="statically-resolved-type-parameters"></a>静态解析的类型参数

A*静态解析的类型参数*是将被替换为实际类型在编译时而不是在运行时的类型参数。 它们的前面有脱字号 (^) 符号。


## <a name="syntax"></a>语法

```
ˆtype-parameter
```

## <a name="remarks"></a>备注
在 F # 语言中，有两种不同的类型参数。 第一种是标准的泛型类型参数。 这些类型由撇号 （'），作为 in 参数指示`'T`和`'U`。 它们是等效于其他.NET Framework 语言中的泛型类型参数。 另外一种类型是静态解析并由一个插入符号，如指示`^T`和`^U`。

静态解析的类型参数是主要适用于与成员限制，这是允许你指定的类型自变量必须才可以使用具有特定的成员的约束一起使用。 没有方法来通过使用正则泛型类型参数创建这种类型的约束。

下表总结了两种类型的类型参数之间的异同。

|功能|泛型|静态解析的|
|-------|-------|-------------------|
|语法|`'T`, `'U`|`^T`, `^U`|
|解决时间|运行时|编译时间|
|成员约束|不能与成员约束使用。|可以与成员约束一起使用。|
|代码生成|使用标准的泛型类型参数的类型 （或方法） 产生的单个泛型类型或方法的生成结果。|生成的类型和方法的多个实例化，每个类型的需要。|
|与类型一起使用|可以在类型上使用。|不能在类型上使用。|
|使用内联函数|不是。 内联函数不能使用标准的泛型类型参数参数化。|可以。 静态解析的类型参数不能用于函数或不是内联的方法。|

许多 F # 核心库函数，尤其是运算符，具有静态解析的类型参数。 这些函数和运算符将以内联方式，并且导致数值计算的高效的代码生成。

内联方法和函数，使用运算符，或使用其他具有静态解析的类型参数的函数还可以使用自己的静态解析的类型参数。 通常情况下，类型推断功能来推断此类为具有静态解析类型参数的内联函数。 下面的示例演示推断为具有静态解析的类型参数的运算符定义。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

解析的类型的`(+@)`取决于如何使用`(+)`和`(*)`，这两个的这导致类型推理来推断成员的静态解析的类型参数约束。 解析的类型，F # 解释器中, 所示是，如下所示。

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

输出如下所示。

```
2
1.500000
```

F # 4.1 开始，你还可以指定具体的类型名称静态解析的类型的参数签名中。  在以前版本的语言，类型名称实际上无法由编译器推断，但无法实际指定的签名中。  截至 F # 4.1，还可以在静态解析的类型的参数签名中指定具体的类型名称。 以下是一个示例：

```fsharp
type CFunctor() = 
      static member inline fmap (f: ^a -> ^b, a: ^a list) = List.map f a
      static member inline fmap (f: ^a -> ^b, a: ^a option) =
        match a with
        | None -> None
        | Some x -> Some (f x)

      // default implementation of replace
      static member inline replace< ^a, ^b, ^c, ^d, ^e when ^a :> CFunctor and (^a or ^d): (static member fmap: (^b -> ^c) * ^d -> ^e) > (a, f) =
        ((^a or ^d) : (static member fmap : (^b -> ^c) * ^d -> ^e) (konst a, f))

      // call overridden replace if present
      static member inline replace< ^a, ^b, ^c when ^b: (static member replace: ^a * ^b -> ^c)>(a: ^a, f: ^b) =
        (^b : (static member replace: ^a * ^b -> ^c) (a, f))

let inline replace_instance< ^a, ^b, ^c, ^d when (^a or ^c): (static member replace: ^b * ^c -> ^d)> (a: ^b, f: ^c) =
      ((^a or ^c): (static member replace: ^b * ^c -> ^d) (a, f))

// Note the concrete type 'CFunctor' specified in the signature
let inline replace (a: ^a) (f: ^b): ^a0 when (CFunctor or  ^b): (static member replace: ^a *  ^b ->  ^a0) =
    replace_instance<CFunctor, _, _, _> (a, f)
```

## <a name="see-also"></a>请参阅
[泛型](index.md)

[类型推断](../type-inference.md)

[自动泛化](automatic-generalization.md)

[约束](constraints.md)

[内联函数](../functions/inline-functions.md)
