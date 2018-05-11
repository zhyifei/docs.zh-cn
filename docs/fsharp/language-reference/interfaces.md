---
title: 接口 (F#)
description: '了解如何 F # 接口指定的其他类实现的相关成员集。'
ms.date: 05/16/2016
ms.openlocfilehash: 54ae8a2840ce26814be25f08c3ed02e12df6b7c0
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2018
---
# <a name="interfaces"></a>接口

*接口*指定的其他类实现的相关成员集。

## <a name="syntax"></a>语法

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a>备注
接口声明类似于类声明，只不过未实现成员。 相反，所有成员都是抽象的由关键字`abstract`。 抽象方法不提供方法体。 但是，可以通过包括单独定义的成员作为连同方法提供的默认实现`default`关键字。 这样相当于在基类中其他.NET 语言中创建的虚拟方法。 可以实现接口的类中重写此类的虚拟方法。

接口的默认可访问性是`public`。

你可以根据需要为每个方法参数提供一个名称使用常规 F # 语法：

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

在上述`ISprintable`示例中，`Print`方法只有一个参数的类型`string`同名`format`。

有两种方法来实现接口： 通过使用对象表达式以及通过使用类类型。 在任一情况下，类类型或对象表达式提供接口的抽象方法的方法体合并。 实现都是特定于每个实现接口的类型。 因此，对不同类型的接口方法可能彼此不同。

关键字`interface`和`end`，如果你使用轻量语法用于标记的开始和结束的定义，则可选。 如果不使用这些关键字，编译器将尝试推断类型通过分析你使用的构造是否是一个类或接口。 如果你定义成员，或使用其他类的语法，类型将被解释为一个类。

将开始带有大写字母的所有接口的.NET 编码样式的`I`。


## <a name="implementing-interfaces-by-using-class-types"></a>通过使用类类型实现接口
你可以通过使用类类型中实现一个或多个接口`interface`关键字，该接口的名称和`with`关键字后, 跟接口成员定义，如下面的代码中所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

继承接口实现，因此任何派生的类不需要重新实现它们。


## <a name="calling-interface-methods"></a>调用接口方法
可以仅通过该接口，不能通过实现接口的类型的任何对象调用接口方法。 因此，可能来向上转换的接口类型必须通过使用`:>`运算符或`upcast`以调用这些方法的运算符。

若要在具有类型的对象时调用的接口方法`SomeClass`，你必须将向上转换为接口类型的对象，如下面的代码中所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

一种替代方法是向上转换的对象上声明一个方法，并调用接口方法，如以下示例所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]
    
## <a name="implementing-interfaces-by-using-object-expressions"></a>通过使用对象表达式实现接口
对象表达式提供了一种快捷的方法来实现接口。 当不需要创建一个名为的类型，而你只是需要支持的接口方法，而无需任何其他方法的对象，它们非常有用。 对象表达式是下面的代码所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]
    
## <a name="interface-inheritance"></a>接口继承
接口可从一个或多个基接口继承。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]
    
## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)

[对象表达式](object-expressions.md)

[类](classes.md)
