---
title: 结构
description: 了解 F# 结构，对于具有少量数据和简单行为的类型，通常比类更有效。
ms.date: 05/16/2016
ms.openlocfilehash: 1e9652cc4776e4d1d52eb20e41b6dd87a6c5ba05
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401123"
---
# <a name="structures"></a>结构

*结构*是一种紧凑的对象类型，对于具有少量数据和简单行为的类型，该类型可能比类更有效。

## <a name="syntax"></a>语法

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements-and-members
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements-and-members
```

## <a name="remarks"></a>备注

结构是*值类型*，这意味着它们直接存储在堆栈上，或者当它们用作字段或数组元素时，它们在父类型中内联。 与类和记录不同，结构具有按值传递语义。 这意味着它们主要用于经常访问和复制的少量聚合数据。

在前面的语法中，将显示两个窗体。 第一个窗体不是轻量级语法，但其仍然经常使用，因为当使用 `struct` 和 `end` 关键字时，你可以忽略第二个窗体中出现的 `StructAttribute` 特性。 你可以将 `StructAttribute` 缩写为 `Struct`。

前一个语法中*的类型定义元素和成员*表示成员声明和定义。 结构可以具有构造函数以及可变和不可变字段，并且可以声明成员和接口实现。 有关详细信息，请参阅[成员](./members/index.md)。

结构不能参与继承、不能包含 `let` 或 `do` 绑定、不能以递归方式包含其自身类型的字段（但可以包含引用其自身类型的引用单元格）。

由于结构不允许 `let` 绑定，你必须通过使用 `val` 关键字在结构中声明字段。 `val` 关键字定义字段及其类型，但不允许初始化。 相反，`val` 声明会初始化零或 null。 因此，具有隐式构造函数（即，在声明中的结构名称后直接给定参数）的结构要求使用 `val` 特性批注 `DefaultValue` 声明。 具有定义构造函数的结构仍支持零初始化。 因此，`DefaultValue` 特性是此类零值对字段有效的声明。 由于此类型上不允许 `let` 和 `do` 绑定，结构的隐式构造函数不执行任何操作，但所传入的隐式构造函数参数值作为私有字段提供。

显式构造函数可能涉及字段值的初始化。 当你的结构具有显式构造函数时，它仍支持零初始化；但是，由于它与显式构造函数冲突，请勿在 `DefaultValue` 声明上使用 `val` 特性。 有关`val`声明的详细信息，请参阅[显式字段：`val`关键字](./members/explicit-fields-the-val-keyword.md)。

结构上允许特性和可访问性修饰符，并遵循与其他类型相同的规则。 有关详细信息，请参阅[属性](attributes.md)和[访问控制](access-control.md)。

以下代码示例说明结构定义。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a>按参考样结构

您可以定义可以遵循`byref`类似语义的您自己的结构：有关详细信息，请参阅[Byrefs。](byrefs.md) 这与属性一<xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>起完成：

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike`并不意味着`Struct`. 两者都必须存在于类型上。

F#`byref`中的"类似"结构是一种堆栈绑定值类型。 它永远不会在托管堆上分配。 `byref`类似结构对于高性能编程非常有用，因为它通过一组有关生存期和非捕获的强检查强制执行。 规则包括：

- 它们可用作函数参数、方法参数、局部变量、方法返回。
- 它们不能是类的静态或实例成员或正常结构。
- 它们不能被任何闭包构造（`async`方法或 lambda 表达式）捕获。
- 它们不能用作泛型参数。

尽管这些规则非常强烈地限制了使用，但它们这样做是为了以安全的方式实现高性能计算的承诺。

## <a name="readonly-structs"></a>只读结构

您可以使用<xref:System.Runtime.CompilerServices.IsReadOnlyAttribute>属性对结构进行分项。 例如：

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsReadOnly`并不意味着`Struct`. 必须同时添加两者才能有`IsReadOnly`一个结构。

使用此属性会发出元数据，让 F# 和 C# 知道它分别`inref<'T>`将其`in ref`视为 和 。

在只读结构内定义可变值会产生错误。

## <a name="struct-records-and-discriminated-unions"></a>结构记录和歧视联盟

您可以将["记录](records.md)"和["歧视联合"](discriminated-unions.md)表示为具有`[<Struct>]`属性的结构。  请参阅每篇文章以了解更多信息。

## <a name="see-also"></a>另请参阅

- [F# 语言参考](index.md)
- [类](classes.md)
- [记录](records.md)
- [成员](./members/index.md)
