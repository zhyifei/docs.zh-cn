---
title: "约束 (F#)"
description: "了解有关 F # 约束将应用于泛型类型参数在泛型类型或函数中指定的类型自变量的要求。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2f232a3a-9486-48fb-9759-f23404ed4b52
ms.openlocfilehash: 91854fd2f692688e0f1c27aba1422eff64156048
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="constraints"></a>约束

本主题描述约束可应用于泛型类型参数在泛型类型或函数中指定的类型自变量的要求。


## <a name="syntax"></a>语法

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a>备注
有几个不同的约束可用于限制可在泛型类型的类型。 下表列出并描述这些约束。

|约束|语法|描述|
|----------|------|-----------|
|类型约束|*类型参数*:&gt; *类型*|所提供的类型必须等于或派生从指定的类型，或者，如果类型是接口，所提供的类型必须实现接口。|
|Null 约束|*类型参数*: null|所提供的类型必须支持 null 字面值。 这包括所有.NET 对象类型，但不是 F # 列表、 元组、 函数、 类、 记录或联合类型。|
|显式成员约束|[（)]*类型参数*[或...或*类型参数*)]: (* 成员签名 *)|在至少其中一个提供的类型自变量必须有一个具有指定的签名; 的成员不能供公共使用。 成员必须要么显式定义为一个显式成员约束的有效目标的类型或隐式类型扩展的一部分。|
|构造函数约束|*类型参数*: (新： 单位-&gt; )|所提供的类型必须具有默认构造函数。|
|值类型约束|： 结构|所提供的类型必须是一个.NET 值类型。|
|引用类型约束|： 不结构|所提供的类型必须是.NET 引用类型。|
|枚举类型约束|： 枚举&lt;*基础类型*&gt;|所提供的类型必须是具有指定的基础类型; 的枚举的类型不能供公共使用。|
|委托约束|： 委托&lt;*元组参数类型*，*返回类型*&gt;|所提供的类型必须是委托类型具有指定的参数和返回值;不能供公共使用。|
|比较约束|： 比较|所提供的类型必须支持比较。|
|等同性约束|： 相等|所提供的类型必须支持相等性。|
|非托管的约束|： 非托管|所提供的类型必须是非托管的类型。 非托管的类型包括： 任一某些基元类型 (`sbyte`， `byte`， `char`， `nativeint`， `unativeint`， `float32`， `float`， `int16`， `uint16`， `int32`， `uint32`， `int64`， `uint64`，或`decimal`)，枚举类型`nativeptr&lt;_&gt;`，或其字段都为非托管的类型的非泛型结构。|
你需要添加约束，当你的代码必须使用通常在约束类型但不是在类型上可用的功能时。 例如，如果你使用的类型约束指定类类型，你可以使用任意一种该类中的泛型函数或类型的方法。

指定约束因有时需要显式，编写类型参数时不指定约束，编译器具有无法验证你使用的功能将可在运行时类型可能提供任何类型参数。

F # 代码中使用的最常见约束不指定基类或接口的类型约束。 其他约束也用于 F # 库实现某些功能，例如显式成员约束，用于实现针对算术运算符重载的运算符也提供了主要是因为 F # 支持完整公共语言运行时支持的组的约束。

在类型推理过程中，一些约束会自动由编译器推断。 例如，如果你使用`+`函数中的运算符，编译器推断出在表达式中使用的变量类型显式成员约束。

下面的代码演示了一些约束声明。

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> = 
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with static member
type Class4<'T when 'T : (static member staticMethod1 : unit -> 'T) > =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a>另请参阅
[泛型](index.md)

[约束](constraints.md)
