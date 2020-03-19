---
title: 继承
description: 了解如何使用"继承"关键字指定 F# 继承关系。
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401129"
---
# <a name="inheritance"></a>继承

继承用于在面向对象的编程中对"is-a"关系或子类型化建模。

## <a name="specifying-inheritance-relationships"></a>指定继承关系

通过在类声明中使用 关键字`inherit`指定继承关系。 基本语法形式如下例所示。

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

类最多只能有一个直接基类。 如果不使用`inherit`关键字指定基类，则类隐式继承从`System.Object`。

## <a name="inherited-members"></a>继承成员

如果类从其他类继承，则派生类的用户可以使用基类的方法和成员，就像它们是派生类的直接成员一样。

任何 let 绑定和构造函数参数都是类的私有参数，因此无法从派生类访问。

关键字`base`在派生类中可用，并引用基类实例。 它像自标识符一样使用。

## <a name="virtual-methods-and-overrides"></a>虚拟方法和重写

与其他 .NET 语言相比，虚拟方法（和属性）在 F# 中的工作方式略有不同。 要声明新的虚拟成员，请使用 关键字`abstract`。 无论是否为该方法提供默认实现，都可以执行此操作。 因此，基类中虚拟方法的完整定义遵循此模式：

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

在派生类中，此虚拟方法的重写遵循此模式：

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

如果在基类中省略默认实现，则基类将成为抽象类。

以下代码示例演示了基类中新虚拟方法`function1`的声明以及如何在派生类中重写它。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a>构造函数和继承

基类的构造函数必须在派生类中调用。 基类构造函数的参数出现在`inherit`子句中的参数列表中。 使用的值必须根据提供给派生类构造函数的参数确定。

以下代码显示基类和派生类，其中派生类调用继承子句中的基类构造函数：

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

在多个构造函数的情况下，可以使用以下代码。 派生类构造函数的第一行是`inherit`子句，字段显示为使用 关键字声明的`val`显式字段。 有关详细信息，请参阅[显式字段：`val`关键字](./members/explicit-fields-the-val-keyword.md)。

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

如果需要对类型进行细微修改，请考虑使用对象表达式作为继承的替代方法。 以下示例说明了使用对象表达式作为创建新派生类型的替代方法：

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

有关对象表达式的详细信息，请参阅[对象表达式](object-expressions.md)。

创建对象层次结构时，请考虑使用受歧视的联合而不是继承。 受歧视的联合还可以对共享公共整体类型的不同对象的不同行为建模。 单个受歧视的联合通常可以消除对一些派生类的需求，这些类彼此的微小变化。 有关受歧视工会的信息，请参阅[歧视工会](discriminated-unions.md)。

## <a name="see-also"></a>另请参阅

- [对象表达式](object-expressions.md)
- [F# 语言参考](index.md)
