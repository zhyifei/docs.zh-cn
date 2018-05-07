---
title: 继承 (F#)
description: '了解如何指定使用继承关键字的 F # 继承关系。'
ms.date: 05/16/2016
ms.openlocfilehash: 3d0c0785fc595315a8283979b99d0ec4fc5cbc0d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="inheritance"></a>继承

继承用于模型"属于"关系，或 subtyping，在面向对象的编程。


## <a name="specifying-inheritance-relationships"></a>指定的继承关系
通过使用指定的继承关系`inherit`类声明中的关键字。 基本语法形式如以下示例所示。

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

一个类可以有最多一个直接基类。 如果不指定基的类使用`inherit`关键字，类隐式继承自`System.Object`。


## <a name="inherited-members"></a>继承的成员
如果某个类继承自另一个类，方法和类的基类的成员可供派生的类的用户就像它们是直接成员的派生类。

任何 let 绑定和构造函数参数是专用于一个类，因此，不能从派生类访问。

关键字`base`是可用在派生类中，指的基的类实例。 它使用类似自我标识符。


## <a name="virtual-methods-and-overrides"></a>虚方法和替代
虚方法 （和属性） 中的工作方式略有不同 F # 相比其他.NET 语言。 若要声明新的虚拟成员，你可以使用`abstract`关键字。 无论是否为提供的默认实现，该方法执行此操作。 因此在基类中的虚方法的完整定义遵循以下模式：

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

并在派生类中，此虚拟方法的重写遵循以下模式：

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

如果省略基类中的默认实现，则基类将成为一个抽象类。

下面的代码示例说明了新的虚拟方法声明中`function1`基类以及如何在派生类中重写它。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]
    
## <a name="constructors-and-inheritance"></a>构造函数和继承
必须在派生类中调用基类的构造函数。 基类构造函数的参数的自变量列表中显示`inherit`子句。 必须从提供给派生的类构造函数的自变量确定使用的值。

下面的代码演示基类和派生的类，派生的类继承子句中调用基类构造函数的位置：

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

对于多个构造函数，可以使用下面的代码。 派生的类构造函数的第一行是`inherit`子句和字段显示为声明中的显式字段`val`关键字。 有关详细信息，请参阅[显式字段：`val`关键字](members/explicit-fields-the-val-keyword.md)。

```fsharp
type BaseClass =
    val string1 : string
    new (str) = { string1 = str }
    new () = { string1 = "" }

type DerivedClass =
    inherit BaseClass

    val string2 : string
    new (str1, str2) = { inherit BaseClass(str1); string2 = str2 }
    new (str2) = { inherit BaseClass(); string2 = str2 }

let obj1 = DerivedClass("A", "B")
let obj2 = DerivedClass("A")
```

## <a name="alternatives-to-inheritance"></a>继承的替代方法
在需要修改少量的一种类型时的情况下，请考虑使用对象表达式作为继承的替代方法。 下面的示例演示如何使用对象表达式作为创建新的派生的类型的替代方法：

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

有关对象表达式的详细信息，请参阅[对象表达式](object-expressions.md)。

当你创建的对象层次结构时，请考虑使用而不继承的可区分的联合。 可区分的联合还可以共享通用的总体类型的不同对象模型不同的行为。 单个可区分的联合通常可以消除对大量之间差别很小的每个其他的派生类的需要。 可区分联合有关的信息，请参阅[可区分联合](discriminated-unions.md)。


## <a name="see-also"></a>请参阅
[对象表达式](object-expressions.md)

[F# 语言参考](index.md)
