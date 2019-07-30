---
title: 继承
description: 了解如何使用 " F# inherit" 关键字指定继承关系。
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627663"
---
# <a name="inheritance"></a>继承

在面向对象的编程中, 使用继承来为 "is a" 关系或子类型化建模。

## <a name="specifying-inheritance-relationships"></a>指定继承关系

在类声明中使用`inherit`关键字指定继承关系。 下面的示例演示了基本语法形式。

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

一个类最多只能有一个直接基类。 如果未使用`inherit`关键字指定基类, 则该类将隐式继承自`System.Object`。

## <a name="inherited-members"></a>继承成员

如果某个类继承自另一个类, 则派生类的用户可以使用基类的方法和成员, 就像它们是派生类的直接成员。

任何 let 绑定和构造函数参数都是类的专用, 因此无法从派生类访问。

关键字`base`可用于派生类, 引用基类实例。 它与自标识符一样使用。

## <a name="virtual-methods-and-overrides"></a>虚方法和重写

与其他 .NET 语言相比, 虚方法 (和F#属性) 在中的工作方式有些不同。 若要声明新的虚拟成员, 请使用`abstract`关键字。 不管是否为该方法提供默认实现, 都可以执行此操作。 因此, 基类中的虚方法的完整定义遵循此模式:

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

在派生类中, 此虚方法的重写遵循此模式:

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

如果在基类中省略默认实现, 则基类成为抽象类。

下面的代码示例演示了基类中新虚方法`function1`的声明, 以及如何在派生类中重写它。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a>构造函数和继承

必须在派生类中调用基类的构造函数。 基类构造函数的自变量出现在`inherit`子句中的参数列表中。 必须从提供给派生类构造函数的参数确定所使用的值。

下面的代码演示基类和派生类, 其中派生的类在 inherit 子句中调用基类构造函数:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

对于多个构造函数, 可以使用以下代码。 派生类构造函数的第一行是`inherit`子句, 字段显示为`val`用关键字声明的显式字段。 有关详细信息, 请[参阅显式字段:`val`关键字。](./members/explicit-fields-the-val-keyword.md)

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

如果需要对类型进行次要修改, 请考虑使用对象表达式作为继承的替代方法。 下面的示例演示了如何使用对象表达式来创建新的派生类型:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

有关对象表达式的详细信息, 请参阅[对象表达式](object-expressions.md)。

创建对象层次结构时, 请考虑使用可区分联合, 而不是继承。 可区分联合还可以为共享公共总体类型的不同对象建模各种行为。 单个的可区分联合通常可以避免需要多个派生类, 这些派生类是彼此之间的细微差异。 有关可区分联合的信息, 请参阅可[区分联合](discriminated-unions.md)。

## <a name="see-also"></a>请参阅

- [对象表达式](object-expressions.md)
- [F# 语言参考](index.md)
