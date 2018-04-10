---
title: 强制转换和转换 (F#)
description: '了解如何 F # 编程语言提供转换运算符的各种基元类型之间的算术转换。'
keywords: visual f#, f#, 函数编程
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: db30db67-da21-4206-bf0c-9211bd3cb22f
ms.openlocfilehash: df8352b0dd8651f1480515311454a218ea79b971
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="casting-and-conversions-f"></a>强制转换和转换 (F#)

本主题介绍对 F # 中的类型转换的支持。

## <a name="arithmetic-types"></a>算术类型
F # 提供了转换运算符算术之间的转换各种基元类型，如整数和浮点类型之间。 整型和 char 转换运算符已选中和取消选中窗体;浮点运算符和`enum`转换运算符不这样做。 未选中的表单定义中`Microsoft.FSharp.Core.Operators`和检查的形式定义在`Microsoft.FSharp.Core.Operators.Checked`。 选中窗体溢出检查，并生成运行时异常，如果生成的值超出目标类型的限制。

每个这些运算符具有相同名称作为目标类型的名称。 例如，在下面的代码，在其中的类型已显式批注，`byte`随即出现，两个不同的含义。 第一个匹配项的类型，第二个是转换运算符。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

下表显示 F # 中定义的转换运算符。

|运算符|描述|
|--------|-----------|
|`byte`|将转换为字节，8 位无符号类型。|
|`sbyte`|将转换为有符号字节。|
|`int16`|将转换为 16 位有符号整数。|
|`uint16`|将转换为 16 位无符号整数。|
|`int32, int`|将转换为 32 位有符号整数。|
|`uint32`|将转换为 32 位无符号整数。|
|`int64`|将转换为 64 位有符号整数。|
|`uint64`|将转换为 64 位无符号整数。|
|`nativeint`|将转换为本机的整数。|
|`unativeint`|将转换为本机的无符号整数。|
|`float, double`|将转换为 64 位双精度 IEEE 浮点数。|
|`float32, single`|将转换为 32 位单精度 IEEE 浮点数。|
|`decimal`|将转换为`System.Decimal`。|
|`char`|将转换为`System.Char`，Unicode 字符。|
|`enum`|将转换为枚举类型。|
除了内置的基元类型，你可以与实现的类型使用这些运算符`op_Explicit`或`op_Implicit`具有适当的签名方法。 例如，`int`转换运算符适用于提供一个静态方法的任何类型`op_Explicit`，采用类型作为参数并返回`int`。 作为一般规则，无法由返回类型重载这些方法的特例，你可以这样做`op_Explicit`和`op_Implicit`。

## <a name="enumerated-types"></a>枚举的类型
`enum`运算符是采用一个表示的类型的类型参数的泛型运算符`enum`将转换为。 当它将转换为枚举类型时，键入推理会尝试确定的一种`enum`你想要将转换为。 在下面的示例中，变量`col1`未显示批注，但其类型推断从更高版本的相等性测试。 因此，编译器可以推断出你要转换为`Color`枚举。 或者，你可以提供一个类型批注，与`col2`在下面的示例。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]
    
你可以显式指定的目标枚举类型，作为类型参数，如以下代码所示：

```fsharp
let col3 = enum<Color> 3
```

请注意在枚举转换工作，仅当在枚举的基础类型为与要转换的类型兼容。 在下面的代码中，则转换失败由于之间不匹配编译`int32`和`uint32`。

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

有关详细信息，请参阅[枚举](enumerations.md)。

## <a name="casting-object-types"></a>强制转换对象类型
对象层次结构中的类型之间的转换是面向对象的编程的基础。 有两种基本类型的转换： 向上 （向上转换） 强制转换和向下转换）。 沿层次结构向上的强制转换意味着强制转换为基对象引用是派生的对象引用。 此类强制转换可保证只要的基类派生的类的继承层次结构中正常工作。 在层次结构，为派生的对象引用，是基对象引用强制转换时才会成功对象实际上是正确的目标 （派生） 类型或从目标类型派生的类型的实例。

F # 提供了为这些类型的转换的运算符。 `:>`层次结构向上转换运算符与`:?>`运算符将沿层次结构强制转换。

### <a name="upcasting"></a>向上转换
在许多面向对象语言中，向上转换是隐式;F # 中的规则是略有不同。 在传递给方法上的对象类型自变量时，将自动应用向上转换。 但是，对于模块中的 let 绑定函数，向上转换不是自动进行的除非参数类型声明为灵活类型。 有关详细信息，请参阅[可变类型](flexible-Types.md)。

`:>`运算符执行静态强制转换，这意味着在编译时确定转换是否成功。 如果使用强制转换`:>`编译成功，它是有效的强制转换并在运行时具有不可能将失败。

你还可以使用`upcast`运算符来执行这种转换。 以下表达式指定层次结构向上转换：

```fsharp
upcast expression
```

当使用向上转换运算符时，编译器将尝试推断要从上下文转换为的类型。 如果编译器无法确定目标类型，编译器将报告错误。

### <a name="downcasting"></a>向下转换
`:?>`运算符执行动态强制转换，这意味着在运行时确定转换是否成功。 使用强制转换`:?>`运算符不检查在编译时; 但在运行时，尝试强制转换为指定的类型。 如果对象是与目标类型兼容，该强制转换会成功。 如果对象不是与目标类型兼容的则运行时将引发`InvalidCastException`。

你还可以使用`downcast`运算符执行的动态类型转换。 以下表达式指定沿层次结构到从程序上下文中推断出类型的转换：

```fsharp
downcast expression
```

同样适用于`upcast`运算符，如果编译器无法推断特定的目标类型从上下文，则将报告错误。

下面的代码演示如何使用`:>`和`:?>`运算符。 该代码演示`:?>`当你知道，转换将失败，因为它将引发时，最好使用运算符`InvalidCastException`如果转换失败。 如果你不知道，转换将失败，使用的类型测试`match`表达式是更好，因为它避免生成异常的开销。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

因为泛型运算符`downcast`和`upcast`依赖类型推断来确定自变量和返回类型，在上述代码中，你可以替换

```fsharp
let base1 = d1 :> Base1
```

替换为

```fsharp
let base1 = upcast d1
```

在前面的代码中，自变量类型和返回类型是`Derived1`和`Base1`分别。

有关类型测试的详细信息，请参阅[匹配表达式](match-Expressions.md)。

## <a name="see-also"></a>另请参阅
[F# 语言参考](index.md)
