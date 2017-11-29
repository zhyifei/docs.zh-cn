---
title: "结构 (F#)"
description: "了解有关 F # 结构，紧凑对象类型通常比具有少量的数据和简单的行为的类型的类更有效。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 50819506-3210-418f-9602-0ee1c9a52177
ms.openlocfilehash: 542b69a5aacb8fcfb0e8f6d6c943fe1954c4c59c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="structures"></a>结构

A*结构*是一种紧凑对象类型，可能比具有少量数据且行为简单类型的类更有效。

## <a name="syntax"></a>语法

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements
```

## <a name="remarks"></a>备注
结构是*值类型*，这意味着它们存储在堆栈上直接中，或当它们用作字段或数组元素的父代中的内联键入。 与类和记录不同，结构具有按值传递语义。 这意味着它们主要用于经常访问和复制的少量聚合数据。

在前面的语法中，将显示两个窗体。 第一个窗体不是轻量级语法，但其仍然经常使用，因为当使用 `struct` 和 `end` 关键字时，你可以忽略第二个窗体中出现的 `StructAttribute` 特性。 你可以将 `StructAttribute` 缩写为 `Struct`。

*类型定义元素*在上述语法中表示成员声明和定义。 结构可以具有构造函数以及可变和不可变字段，并且可以声明成员和接口实现。 有关详细信息，请参阅[成员](members/index.md)。

结构不能参与继承、不能包含 `let` 或 `do` 绑定、不能以递归方式包含其自身类型的字段（但可以包含引用其自身类型的引用单元格）。

由于结构不允许 `let` 绑定，你必须通过使用 `val` 关键字在结构中声明字段。 `val` 关键字定义字段及其类型，但不允许初始化。 相反，`val` 声明会初始化零或 null。 因此，具有隐式构造函数（即，在声明中的结构名称后直接给定参数）的结构要求使用 `val` 特性批注 `DefaultValue` 声明。 具有定义构造函数的结构仍支持零初始化。 因此，`DefaultValue` 特性是此类零值对字段有效的声明。 由于此类型上不允许 `let` 和 `do` 绑定，结构的隐式构造函数不执行任何操作，但所传入的隐式构造函数参数值作为私有字段提供。

显式构造函数可能涉及字段值的初始化。 当你的结构具有显式构造函数时，它仍支持零初始化；但是，由于它与显式构造函数冲突，请勿在 `DefaultValue` 声明上使用 `val` 特性。 有关详细信息`val`声明，请参阅[显式字段：`val`关键字](members/explicit-fields-the-val-keyword.md)。

结构上允许特性和可访问性修饰符，并遵循与其他类型相同的规则。 有关详细信息，请参阅[属性](attributes.md)和[访问控制](access-control.md)。

以下代码示例说明结构定义。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="struct-records-and-discriminated-unions"></a>结构记录和可区分的联合

F # 4.1 开始，您可以表示[记录](records.md)和[可区分联合](discriminated-unions.md)为与结构`[<Struct>]`属性。  请查看每个文章以了解详细信息。
    
## <a name="see-also"></a>另请参阅
[F# 语言参考](index.md)

[类](classes.md)

[记录](records.md)

[成员](members/index.md)
