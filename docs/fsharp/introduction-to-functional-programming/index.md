---
title: F# 中的函数编程简介
description: 了解基础知识中的函数编程F#。
ms.date: 10/29/2018
ms.openlocfilehash: d4a9bb0cd826b41aca96e12e2bcb5aab80c18eb4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25724474"
---
# <a name="introduction-to-functional-programming-in-f"></a>F# 中的函数编程简介 #

函数编程是编程的一种样式的强调的函数和不可变数据使用。 类型化的函数编程是函数编程与结合使用时与静态类型，如F#。 一般情况下，在函数式编程强调了以下概念：

* 为你使用的主构造函数
* 而不是语句表达式
* 通过变量的不可变值
* 通过命令性编程的声明性编程

本系列文章将探讨概念和模式中功能的编程使用F#。 此过程中，你将了解一些F#过。

## <a name="terminology"></a>术语

函数编程，如其他编程范例中，附带了你最终需要了解的词汇。 下面是您将看到所有时间的一些常见术语：

* **函数**-函数是一个构造，它将生成在给定输入的输出。 更准确地讲，它_映射_从一个项设置为另一组。 特别是使用操作的函数的多个数据集合时，此打击被提升到在许多方面，具体。 它是最基本 （且重要） 中的功能性编程概念。 
* **表达式**-表达式是所生成的值的代码中的构造。 在F#，必须绑定或显式忽略此值。 表达式可以不费力地替换为函数调用。
* **纯度**-纯度是函数的属性，以便其返回值始终是相同的相同的参数，且其评估没有任何副作用。 纯函数完全取决于其参数。
* **引用透明度**-引用透明度是表达式的属性，以便它们可以被替换为相应的输出而不会影响程序的行为。
* **不变性**的不可变性意味着值不能更改就地。 这是与变量，可以更改在位置不同。

## <a name="examples"></a>示例

下面的示例演示这些核心概念。

### <a name="functions"></a>函数

最基本的常用在函数式编程构造是函数。 下面是将 1 添加到整数的简单函数：

```fsharp
let addOne x = x + 1
```

其类型签名如下所示：

```fsharp
val addOne: x:int -> int
```

签名可以读取，为"`addOne`接受`int`名为`x`，将产生`int`"。 更准确地讲`addOne`是_映射_到的一组整数之间的一组整数的值。 `->`令牌表示此映射。 在F#，则通常可在函数签名，了解有关它的功能查看。

因此，为何重要的签名？ 在类型化函数式编程的一个函数实现小于通常比实际类型签名重要 ！ 这一事实，`addOne`添加到一个整数值 1 是在运行时，有趣，但当构造一个程序，这一事实，它接受并返回`int`是什么就是告知如何实际将使用此函数。 此外，一旦您使用正确 （根据其类型签名） 的此函数，诊断任何问题可以仅在的正文内`addOne`函数。 这是类型化函数式编程力。

### <a name="expressions"></a>表达式

表达式是计算出值的构造。 与语句执行的操作，可以执行并发回一个值的操作被视为表达式。 几乎总是以支持函数编程中的语句中使用表达式。

上一个函数，请考虑`addOne`。 正文`addOne`是一个表达式：

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

它是此定义的结果类型的表达式的结果`addOne`函数。 例如，构成此函数的表达式无法更改以是不同的类型，如`string`:

```fsharp
let addOne x = x.ToString() + "1"
```

现在，函数的签名是：

```fsharp
val addOne: x:'a -> string
```

由于中的任何类型F#可以具有`ToString()`对它的类型调用`x`变得通用 (称为[自动泛化](../language-reference/generics/automatic-generalization.md))，和结果类型将是`string`。

表达式不是只是函数的正文。 您可以生成其他位置使用的值的表达式。 一个是一种常见`if`:

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result
```

`if`表达式会生成名为的值`result`。 请注意，可以省略`result`完全，使`if`表达式主体的`addOneIfOdd`函数。 需要记住有关表达式的关键一点是，它们生成值。

没有一种特殊类型， `unit`，当没有要返回内容时使用。 例如，考虑此简单函数：

```fsharp
let printString (str: string) =
    printfn "String is: %s" s
```

签名如下所示：

```fsharp
val printString: str:string -> unit
```

`unit`类型表示不返回任何实际值。 这是很有用，有时必须例程"正常运行"尽管没有要返回该工作的值。

这是与命令式编程中，到在其中等效`if`构造是一个语句，并生成值通常是与转变变量。 例如，在C#，可能会像这样编写的代码：

```csharp
bool IsOdd(int x) => x % 2 != 0;

int AddOneIfOdd(int input)
{
    var result = input;

    if (IsOdd(input))
    {
        result = input + 1;
    }

    return result;
}
```

值得注意的是C#和其他 C 风格语言支持[三元表达式](../../csharp/language-reference/operators/conditional-operator.md)，这样可以基于表达式的条件性编程。

在函数式编程，很难改变语句的值。 虽然一些函数式语言支持语句和变化，但它不是通常在函数式编程中使用这些概念。

### <a name="pure-functions"></a>纯函数

如前面所述，纯函数是函数：

* 计算结果始终为同一输入相同的值。
* 有没有负面影响。

它是需要考虑在此上下文中的数学函数。 在数学中，函数只能依赖于其参数，但没有任何副作用。 数学函数中`f(x) = x + 1`，值`f(x)`仅取决于值`x`。 在函数式编程的纯函数是相同的方式。

在编写纯函数，函数必须只能依赖于其参数并不执行任何操作产生负面影响。

因为它取决于全局、 可变状态，下面是一个非纯函数的示例：

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

`addOneToValue`函数是清楚地非纯，因为`value`可以具有不同的值多于 1 随时可能更改。 具体取决于全局值的模式是避免在函数式编程。

下面是的非纯函数，另一个示例，因为它执行副作用：

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

尽管此函数不依赖于全局值，但它的值写入`x`到程序的输出。 尽管没有任何问题本质上是执行此操作，但它意味着该函数不是纯。

删除`printfn`语句最终使函数纯：

```fsharp
let addOneToValue x = x + 1
```

尽管此函数本身不是_更好地_与早期版本相比`printfn`语句，它确实保证此函数的唯一用途是返回值。 调用此函数一次或 1 亿次将仍导致相同的操作： 只生成一个值。 此可预测性是函数编程中有价值，因为它意味着任何纯函数是引用透明。

### <a name="referential-transparency"></a>引用透明度

引用透明度是表达式和函数的属性。 是引用透明表达式，它必须能够将替换为其生成的值，而无需更改程序的行为。 所有纯函数是引用透明的。

与纯函数，它可以是需要考虑引用透明度从数学角度来看。 中的数学表达式`y = f(x)`，`f(x)`可以替换为函数的结果仍将等于`y`。 这是用于在函数式编程引用透明度也同样适用。

请考虑调用以前定义`addOneIfOdd`函数两次：

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result

let res1 = addOneIffOdd 1 // Produces 2
let res2 = addOneIffOdd 2 // Produces 2
```

我们可以替换该参数使用函数体中，替换每个函数调用`input`与每个值：

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result

let res1 =
    let result =
        if isOdd 1 then
            1 + 1
        else
            1

    result
let res2 =
    let result =
        if isOdd 2 then
            2 + 1
        else
            2

    result
```

这两`res1`并`res2`具有相同的值，就像调用函数时，该值指示`addOneIfOdd`是引用透明 ！

此外，函数无需是纯也显示为引用透明的。 以前的定义，请考虑`addOneTovalue`:

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

此外可以通过其正文替换为对此函数的任何调用，并将发生每次相同的情况：

* 之前，要添加的值打印到输出
* 值已添加到其中的 1

在编程时F#，它通常是引用是目标，而不是纯度的透明度。 但是，它是仍很好的做法时你可以编写纯函数。

### <a name="immutability"></a>不可变性

最后，类型化函数式编程的最基本的概念之一是不可变性。 在F#，所有值都是默认固定不变。 这意味着它们不能是就地转变，除非显式将其标记为可变。

在实践中，使用不可变值意味着从，"我需要更改某些内容"更改为编程所用的方法，向"我需要生成新值"。

例如，添加为值 1 表示生成新值，不改变现有从而：

```fsharp
let value = 1
let secondValue = value + 1
```

在F#，以下代码所示**不**改变`value`函数; 相反，它将执行相等性检查：

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

一些函数式编程语言不在所有支持的变化。 在F#，它受支持，但它不是值的默认行为。

甚至数据结构可以进一步扩展了这一概念。 在函数式编程，不可变数据结构如集 （和更多） 具有不同的实现，最初可能比预期。 从概念上讲，内容如将项添加到一组不会更改集，它会生成_新_设置为已添加值。 实际上，这是通常通过实现可用于有效地跟踪一个值，以便可以作为结果提供适当的表示形式的数据的不同的数据结构。

这种处理值和数据结构至关重要，因为它会强制您将修改内容，如同其创建该操作的新版本的任何操作。 这允许诸如相等性和可比性等的项目为您的程序中保持一致。

## <a name="next-steps"></a>后续步骤

下一步部分全面介绍函数，探索函数编程中使用它们的不同方式。

[第一类函数](first-class-functions.md)探讨功能深，显示如何在不同上下文中使用它们。

## <a name="further-reading"></a>其他阅读材料

[想就功能而言](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/)系列是另一个很好的资源，若要了解有关函数编程与F#。 它涵盖的功能性编程基础知识中以实用且易于理解的方式，使用F#功能来阐明这些概念。