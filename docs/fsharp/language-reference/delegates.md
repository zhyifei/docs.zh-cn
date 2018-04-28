---
title: 委托 (F#)
description: '了解如何使用 F # 中的委托。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 56520cc631d889f390a7d4300be1cb3185306be9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="delegates"></a>委托

委托表示为对象的函数调用。 在 F # 中，你通常应使用函数值来表示作为一类值; 函数但是，委托在.NET Framework 中使用，并且因此时，需要与所希望的 Api 进行互操作。 它们还可能创作库用于从其他.NET Framework 语言使用时将使用。


## <a name="syntax"></a>语法

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a>备注
在上述语法中，`type1`表示或多个自变量类型和`type2`表示的返回类型。 由表示的参数类型`type1`会自动进行扩充。 这表示，对于你使用元组形式，如果目标函数的自变量会进行扩充，此类型，并已采用元组形式的自变量用圆括号括起来元组。 自动扩充将移除一套圆括号，同时保留目标方法相匹配的元组参数。 请参阅应在每个用例中使用的语法的代码示例。

委托可以附加到 F # 函数值，和静态方法或实例方法。 F # 函数值可以直接作为要委托构造函数自变量传递。 对于静态方法，您可以通过使用类和方法的名称构造委托。 对于实例方法，你可以提供的对象实例和一个自变量中的方法。 在这两种情况下，成员访问运算符 (`.`) 使用。

`Invoke`委托类型的方法调用封装的函数。 此外，还可以引用不带括号的 Invoke 方法名称作为函数值传递委托。

下面的代码演示创建表示类中的各种方法的委托的语法。 具体取决于该方法是否是静态方法或实例方法，以及是否具有元组形式或扩充窗体中的自变量，用于声明和分配委托的语法是稍有不同。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

下面的代码显示了一些你可以使用委托的不同方式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

前面的代码示例的输出如下所示。

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)

[参数和自变量](parameters-and-arguments.md)

[事件](members/events.md)
