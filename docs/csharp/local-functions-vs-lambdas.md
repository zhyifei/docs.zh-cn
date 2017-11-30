---
title: "本地函数与 Lambda 表达式"
description: "了解为什么选择本地函数比选择 Lambda 表达式更好。"
keywords: "C#, .NET, .NET Core, 最新功能, 新增功能, 本地函数, Lambda 表达式"
author: BillWagner
ms.author: wiwagn
ms.date: 06/27/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.openlocfilehash: 20312b58a24dc991791edad4bb92d3a8ca6d501a
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2017
---
# <a name="local-functions-compared-to-lambda-expressions"></a>相比于 lambda 表达式的本地函数

乍看之下，[本地函数](programming-guide/classes-and-structs/local-functions.md)和 [lambda 表达式](lambda-expressions.md)非常相似。 在许多情况下，使用 lambda 表达式和本地函数之间的选择是一种样式和个人首选项。 但是，有在其中你可以使用一个或其他你应注意的实际差异。

让我们检查一下阶乘算法的本地函数实现和 lambda 表达式实现之间的差异。 首先使用本地函数的版本：

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

将该实现与使用 Lambda 表达式的版本对比：

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

本地函数具有名称。 Lambda 表达式是分配给变量的匿名方法`Func`或`Action`类型。 在声明局部函数时，自变量类型和返回类型是函数声明的一部分。 而不是主体的 lambda 的一部分表达式、 参数类型和返回类型是主体的 lambda 表达式的变量类型声明的一部分。 这些两个差异可能会导致更清晰的代码。

本地函数具有比 lambda 表达式的明确赋值的不同规则。 可以从任何位置处于范围内的代码位置引用本地函数声明。 必须将 lambda 表达式分配给一个委托变量，然后它才能访问 （或通过引用 lambda 表达式 delgate 调用。）请注意，使用 lambda 表达式的版本必须先定义 lambda 表达式 `nthFactorial`，然后再对其进行声明并实例化。 否则，会导致分配前引用 `nthFactorial` 时出现编译时错误。
这些差异意味着递归算法是更轻松地创建使用本地函数。 你可以声明并定义调用其自身的本地函数。 Lambda 表达式必须是声明，并且它们可以是重新分配给引用的相同的 lambda 表达式的主体之前分配默认值。

明确赋值规则也会影响任何通过本地的函数或 lamdba epression 捕获的变量。 本地函数和 lambda 表达式规则要求，任何捕获的变量，则肯定分配的点处时本地的函数或 lambda 表达式转换为的委托。 不同之处在于，进行声明时，将 lambda 表达式转换为委托。 本地函数将转换为委托仅当使用作为代理。 如果声明了局部函数只能引用它通过调用方法一样，它将转换为的委托。 该规则，可声明在其封闭范围中的任何方便的位置的本地函数。 很普遍后返回的任何语句声明在父方法的末尾的本地函数。

第三，编译器可以执行静态分析，使本地函数，以明确分配封闭范围中捕获的变量。 请看以下示例：

```csharp
bool M()
{
    int y;
    Local();
    return y;

    void Local() => y = 0;
}
```

编译器可以确定`Local`明确分配`y`时调用。 因为`Local`之前调用`return`语句， `y` definitiely 分配在`return`语句。

启用分析允许的第四个差异分析。
具体取决于其使用本地函数可以避免始终所需的 lambda 表达式的堆分配。 如果本地函数永远不会转换为的委托，并且无本地函数捕获的变量捕获由其他 lambda 或转换为委托的本地函数，编译器可以避免堆分配。 

请看以下异步示例：

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

该 lambda 表达式的闭包包含 `address`、`index` 和 `name` 变量。 就本地函数而言，实现闭包的对象可能为 `struct` 类型。 将通过对本地函数的引用传递该结构类型。 实现这种差异将保存在分配上。

Lambda 表达式所需实例化意味着额外的内存分配，可能是在时间关键代码路径中的一个性能因素。
本地函数不会产生这种开销。 在以上示例中，本地函数版本具有的分配比 lambda 表达式版本少 2 个。

> [!NOTE]
> 等效于此方法的本地函数还将类用于闭包。 实现详细信息包括本地函数的闭包是作为 `class` 还是 `struct` 实现。 本地函数可能使用 `struct`，而 lambda 将始终使用 `class`。

[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]

在本示例中尚未演示的最后一个优点是，可将本地函数作为迭代器实现，使用 `yield return` 语法生成一系列值。 `yield return`语句不允许在 lambda 表达式中。

虽然本地函数对 lambda 表达式可能有点冗余，但实际上它们的目的和用法都不一样。
如果想要编写仅从上下文或其他方法中调用的函数，则使用本地函数更高效。
