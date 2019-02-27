---
title: C# 7.0 中的新增功能 - C# 指南
description: 大致了解 C# 语言的版本 7.0 中的新增功能。
ms.date: 12/21/2016
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: 0646eaa999579e5347007dd71defcc643c19c7f9
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56665077"
---
# <a name="whats-new-in-c-70"></a>C# 7.0 中的新增功能

C# 7.0 向 C# 语言添加了许多新功能：
* [`out` 变量](#out-variables)
    - 可以将 `out` 值内联作为参数声明到使用这些参数的方法中。
* [元组](#tuples)
    - 可以创建包含多个公共字段的轻量级未命名类型。 编译器和 IDE 工具可理解这些类型的语义。
* [弃元](#discards)
    - 弃元是指在不关心所赋予的值时，赋值中使用的临时只写变量。 在对元组和用户定义类型进行解构，以及在使用 `out` 参数调用方法时，它们特别有用。
* [模式匹配](#pattern-matching)
    - 可以基于任意类型和这些类型的成员的值创建分支逻辑。
* [`ref` 局部变量和返回结果](#ref-locals-and-returns)
    - 方法局部参数和返回值可以是对其他存储的引用。
* [本地函数](#local-functions)
    - 可以将函数嵌套在其他函数内，以限制其范围和可见性。
* [更多的 expression-bodied 成员](#more-expression-bodied-members)
    - 可使用表达式创作的成员列表有所增长。
* [`throw` 表达式](#throw-expressions)
    - 可以在之前因为 `throw` 是语句而不被允许的代码构造中引发异常。 
* [通用的异步返回类型](#generalized-async-return-types)
    - 使用 `async` 修饰符声明的方法可以返回除 `Task` 和 `Task<T>` 以外的其他类型。
* [数字文本语法改进](#numeric-literal-syntax-improvements)
    - 新令牌可提高数值常量的可读性。

本主题的其余部分讨论了每项功能。 你将了解每项功能背后的原理。 将了解语法。 将看到一些示例方案，从中可看出使用新功能将提高你作为开发人员的工作效率。 

## <a name="out-variables"></a>`out` 变量

支持 `out` 参数的现有语法已在此版本中得到改进。  

以前，你需要将 out 变量的声明及其初始化分为两个不同的语句：

[!code-csharp[OutVariableOldStyle](../../../samples/snippets/csharp/new-in-7/program.cs#03_OutVariableOldStyle "classic out variable declaration")]

现在可以在方法调用的参数列表中声明 `out` 变量，而不是编写单独的声明语句：

[!code-csharp[OutVariableDeclarations](../../../samples/snippets/csharp/new-in-7/program.cs#01_OutVariableDeclarations "Out variable declarations")]

为清晰明了，可能需指定 `out` 变量的类型，如上所示。 但是，该语言支持使用隐式类型的局部变量：

[!code-csharp[OutVarVariableDeclarations](../../../samples/snippets/csharp/new-in-7/program.cs#02_OutVarVariableDeclarations "Implicitly typed Out variable")]

* 代码更易于阅读。 
    - 在使用 out 变量的地方声明 out 变量，而不是在上面的另一行。
* 无需分配初始值。
    - 通过在方法调用中使用 `out` 变量的位置声明该变量，使得在分配它之前不可能意外使用它。

此功能最常见的用法是 `Try` 模式。 在此模式下，方法返回指示成功或失败的 `bool`，如果方法成功，则还返回提供结果的 `out` 变量。

当使用 `out` 变量声明时，声明的变量“泄漏”到 if 语句的外部作用域。 这让你可以在之后使用该变量：

```csharp
if (!int.TryParse(input, out int result))
{    
    return null;
}

return result;
```

## <a name="tuples"></a>元组

> [!NOTE]
> 新的元组功能需要 <xref:System.ValueTuple> 类型。
> 为在不包括该类型的平台上使用它，必须添加 NuGet 包 [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/)。
>
> 这类似于依赖框架提供的类型的其他语言功能。 例如，依赖 `INotifyCompletion` 接口的 `async` 和 `await`，以及依赖 `IEnumerable<T>` 的 LINQ。 但是，随着 .NET 越来越不依赖平台，交付机制也在发生改变。 .NET Framework 交付频率可能不会与语言编译器的始终相同。 新语言功能依赖于新类型时，这些类型将在交付语言功能时以 NuGet 包的形式提供。 这些新类型添加到 .NET Standard API 并作为框架的一部分交付后，将删除 NuGet 包要求。

C# 为用于说明设计意图的类和结构提供了丰富的语法。 但是，这种丰富的语法有时会需要额外的工作，但益处却很少。 你可能经常编写需要包含多个数据元素的简单结构的方法。 为了支持这些方案，已将元组添加到了 C#。 元组是包含多个字段以表示数据成员的轻量级数据结构。
这些字段没有经过验证，并且你无法定义自己的方法

> [!NOTE]
> 低于 C# 7.0 的版本中也提供元组，但它们效率低下且不具有语言支持。
> 这意味着元组元素只能作为 `Item1` 和 `Item2` 等引用。 C# 7.0 引入了对元组的语言支持，可利用更有效的新元组类型向元组字段赋予语义名称。

通过为每个成员赋值，可以创建一个元组：

[!code-csharp[UnnamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#04_UnnamedTuple "Unnamed tuple")]

此赋值会创建其成员为 `Item1` 和 `Item2` 的元组，其使用方式与 <xref:System.Tuple> 的相同。可更改语法，以创建为每个元组成员提供语义名称的元组：

[!code-csharp[NamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#05_NamedTuple "Named tuple")]

`namedLetters` 元组包含称为 `Alpha` 和 `Beta` 的字段。 这些名称仅存在于编译时且不保留，例如在运行时使用反射来检查元组时。

在进行元组赋值时，还可以指定赋值右侧的字段的名称：

[!code-csharp[ImplicitNamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#06_ImplicitNamedTuple "Implicitly named tuple")]

可指定赋值左侧和右侧字段的名称：

[!code-csharp[NamedTupleConflict](../../../samples/snippets/csharp/new-in-7/program.cs#07_NamedTupleConflict "Named tuple conflict")]

上面的行会生成警告 `CS8123`，告知你赋值右侧的名称 `Alpha` 和 `Beta` 将被忽略，因为它们与左侧的名称 `First` 和 `Second` 冲突。

上面的示例演示了用于声明元组的基本语法。 元组在作为 `private` 和 `internal` 方法的返回类型时是最有用的。 元组为这些方法提供了一个简单语法来返回多个离散值：不用再费心创作定义返回类型的 `class` 或 `struct`。 无需创建新类型。

创建元组更有效且更高效。
它是一种更简单的轻量级语法，用于定义携带多个值的数据结构。 下面的示例方法返回在一个整数序列中找到的最小值和最大值：

[!code-csharp[TupleReturningMethod](../../../samples/snippets/csharp/new-in-7/program.cs#08_TupleReturningMethod "Tuple returning method")]

以这种方式使用元组有若干优点：

* 不用再费心创作定义返回类型的 `class` 或 `struct`。 
* 无需创建新类型。
* 借助该语言增强功能，无需调用 <xref:System.Tuple.Create``1(``0)> 方法。

此方法的声明提供返回的元组的字段的名称。 调用该方法时，返回值是字段为 `Max` 和`Min` 的元组：

[!code-csharp[CallingTupleMethod](../../../samples/snippets/csharp/new-in-7/program.cs#09_CallingTupleMethod "Calling a tuple returning method")]

在某些时候，你可能想要解包从方法返回的元组的成员。  可通过为元组中的每个值声明单独的变量来实现此目的。 这称为析构元组：

[!code-csharp[CallingWithDeconstructor](../../../samples/snippets/csharp/new-in-7/program.cs#10_CallingWithDeconstructor "Deconstructing a tuple")]

还可以为 .NET 中的任何类型提供类似的析构。 这通过将 `Deconstruct` 方法编写为类的成员来完成。 `Deconstruct` 方法为你要提取的每个属性提供一组 `out` 参数。 考虑提供析构函数方法的此 `Point` 类，该方法提取 `X` 和 `Y` 坐标：

[!code-csharp[PointWithDeconstruction](../../../samples/snippets/csharp/new-in-7/point.cs#11_PointWithDeconstruction "Point with deconstruction method")]
 
可以通过向元组分配 `Point` 来提取各个字段：

[!code-csharp[DeconstructPoint](../../../samples/snippets/csharp/new-in-7/program.cs#12_DeconstructPoint "Deconstruct a point")]

不会受到 `Deconstruct` 方法中定义的名称的约束。 可以在分配过程中重命名提取变量：  

[!code-csharp[DeconstructNames](../../../samples/snippets/csharp/new-in-7/program.cs#13_DeconstructNames "Deconstruct with new names")]

可在[元组主题](../tuples.md)中深入了解有关元组的详细信息。

## <a name="discards"></a>弃元

通常，在进行元组解构或使用 `out` 参数调用方法时，必须定义一个其值无关紧要且你不打算使用的变量。 为处理此情况，C# 增添了对弃元的支持。 弃元是一个名为 `_`（下划线字符）的只写变量，可向单个变量赋予要放弃的所有值。 弃元类似于未赋值的变量；不可在代码中使用弃元（赋值语句除外）。

在以下方案中支持弃元：

* 在对元组或用户定义的类型进行解构时。

* 在使用 [out](../language-reference/keywords/out-parameter-modifier.md) 参数调用方法时。

* 在使用 [is](../language-reference/keywords/is.md) 和 [switch](../language-reference/keywords/switch.md) 语句匹配操作的模式中。

* 在要将某赋值的值显式标识为弃元时用作独立标识符。

以下示例定义了 `QueryCityDataForYears` 方法，它返回一个包含两个不同年份的城市数据的六元组。 本例中，方法调用仅与此方法返回的两个人口值相关，因此在进行元组解构时，将元组中的其余值视为弃元。

[!code-csharp[Tuple-discard](../../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

有关详细信息，请参阅[弃元](../discards.md)。

## <a name="pattern-matching"></a>模式匹配

模式匹配是一种可让你对除对象类型以外的属性实现方法分派的功能。 你可能已经熟悉基于对象类型的方法分派。 在面向对象的编程中，虚拟和重写方法提供语言语法来实现基于对象类型的方法分派。 基类和派生类提供不同的实现。 模式匹配表达式扩展了这一概念，以便你可以通过继承层次结构为不相关的类型和数据元素轻松实现类似的分派模式。 

模式匹配支持 `is` 表达式和 `switch` 表达式。 每个表达式都允许检查对象及其属性以确定该对象是否满足所寻求的模式。 使用 `when` 关键字来指定模式的其他规则。

### <a name="is-expression"></a>`is` 表达式

`is` 模式表达式扩展了常用 [`is` 运算符](../language-reference/keywords/is.md#pattern-matching-with-is)，使其可查询其类型之外的对象。

我们以一个简单的方案为例。 我们将在此方案中添加功能，以便演示模式匹配表达式如何使处理不相关类型的算法变得简单。 我们从计算多次掷骰数之和的方法开始：

[!code-csharp[SumDieRolls](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#14_SumDieRolls "Sum die rolls")]

你可能很快就发现，有时需要在某几次掷骰中骰子多于一个的情况下得出掷骰数总和。 输入序列的一部分可以是多个结果，而非单个数字：

[!code-csharp[SumDieRollsWithGroups](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#15_SumDieRollsWithGroups "Sum die rolls with groups")]

`is` 模式表达式在此方案中相当有用处。 你可以在检查类型过程中编写变量初始化。 这将创建一个经过验证的运行时类型的新变量。

当继续扩展这些方案时，你可能会发现生成了更多的 `if` 和 `else if` 语句。 当此情况变得难以处理时，你可能需要切换到 `switch` 模式表达式。

### <a name="switch-statement-updates"></a>`switch` 语句更新

匹配表达式具有熟悉的语法，它基于已属于 C# 语言的 `switch` 语句。 在添加新 case 之前，让我们将现有代码转换为使用匹配表达式： 

[!code-csharp[SumUsingSwitch](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#16_SumUsingSwitch "Sum using switch")]

匹配表达式的语法与 `is` 表达式稍有不同，你可以在 `case` 表达式的开头声明类型和变量。

匹配表达式也支持常量。 这样可以通过分离出简单 case 来节省时间：

[!code-csharp[SwitchWithConstants](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#17_SwitchWithConstants "Switch with constants")]

上面的代码为 `0` 添加 case 作为 `int` 的特殊 case，为 `null` 添加 case 作为没有输出时的特殊 case。 这演示了 switch 模式表达式中一个重要的新功能：`case` 表达式的顺序现在很重要。 `0` case 必须出现在常规 `int` case 之前。 否则，要匹配的第一个模式将为 `int` case，即使值为 `0` 时也是如此。 如果匹配表达式进行意外排序（例如稍后的 case 已经过处理），则编译器将对其标记并生成错误。

这一相同行为可实现空输入序列的特殊 case。
可以看到，包含元素的 `IEnumerable` 项的 case 必须出现在常规 `IEnumerable` case 之前。

此版本还添加了一个 `default` case。 无论在源中出现的顺序如何，`default` case 总是最后计算的。 因此，惯例是将 `default` case 放在最后。

最后，让我们为新样式的骰子添加最后一个 `case`。 某些游戏使用百分比骰子来表示更大范围的数字。 

> [!NOTE]
> 两个 10 面百分比骰子可以表示 0 到 99 之间的每个数字。 一个骰子的各面标记为 `00`、`10`、`20`, ... `90`。 另一个骰子的各面标记为 `0`、`1`、`2`, ... `9`。 将两个骰子的值加在一起，可以得到 0 到 99 之间的每个数字。

要将此类型的骰子添加到集合，请先定义一个类型来表示百分比骰子。 `TensDigit` 属性将值存储为 `0`、`10`、`20`（依次递增，最大为 `90`）：

[!code-csharp[18_PercentileDice](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#18_PercentileDice "Percentile Die type")]

然后，为新类型添加一个 `case` 匹配表达式：

[!code-csharp[SwitchWithNewTypes](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#19_SwitchWithNewTypes "Include Percentile Die type")]

模式匹配表达式的新语法使得使用清晰简练的语法创建基于对象的类型或其他属性的分派算法更加容易。 模式匹配表达式可以在因继承而无关的数据类型上实现这些构造。

你可以在专门介绍 [C# 中的模式匹配](../pattern-matching.md)的主题中了解有关模式匹配的详细信息。

## <a name="ref-locals-and-returns"></a>Ref 局部变量和返回结果

此功能允许使用并返回对变量的引用的算法，这些变量在其他位置定义。 一个示例是使用大型矩阵并查找具有某些特征的单个位置。 有一个方法可返回矩阵中某单个位置的两个索引：

[!code-csharp[FindReturningIndices](../../../samples/snippets/csharp/new-in-7/MatrixSearch.cs#20_FindReturningIndices "Find returning indices")]

此代码存在很多问题。 首先，它是一个返回元组的公共方法。 语言支持此方法，但对公共 API 来说，用户定义的类型（类或结构）是更优选择。

其次，此方法返回的是矩阵中的项的索引。
这会导致调用方编写使用这些索引的代码来取消引用矩阵并修改单个元素：

[!code-csharp[UpdateItemFromIndices](../../../samples/snippets/csharp/new-in-7/program.cs#21_UpdateItemFromIndices "Update Item From Indices")]

与其这样，还不如编写一个方法，返回对你要更改的矩阵的元素的引用。 在以前的版本中，你只能通过使用不安全代码并返回一个指向 `int` 的指针来实现此目的。

让我们通过一系列更改来演示 ref 局部变量功能，并展示如何创建返回对内部存储的引用的方法。
与此同时，你将学习 ref 返回结果的规则以及可保护你免于意外误用它的 ref 局部变量功能。

首先修改 `Find` 方法声明，使其返回一个 `ref int`，而不是一个元组。 然后修改 return 语句，使其返回存储在矩阵中的值，而不是两个索引：

```csharp
// Note that this won't compile. 
// Method declaration indicates ref return,
// but return statement specifies a value return.
public static ref int Find2(int[,] matrix, Func<int, bool> predicate)
{
    for (int i = 0; i < matrix.GetLength(0); i++)
        for (int j = 0; j < matrix.GetLength(1); j++)
            if (predicate(matrix[i, j]))
                return matrix[i, j];
    throw new InvalidOperationException("Not found");
}
```

当你声明方法返回 `ref` 变量时，还必须向每个 return 语句添加 `ref` 关键字。 这指示按引用返回，并可帮助以后阅读代码的开发人员记住该方法按引用返回：

[!code-csharp[FindReturningRef](../../../samples/snippets/csharp/new-in-7/MatrixSearch.cs#22_FindReturningRef "Find returning by reference")]

因为该方法返回对矩阵中的整数值的引用，所以你需要修改调用它的位置。  `var` 声明意味着 `valItem` 现在是 `int` 而不是元组：

[!code-csharp[AssignRefReturnToValue](../../../samples/snippets/csharp/new-in-7/program.cs#23_AssignRefReturnToValue "Assign ref return to value")]

上例中的第二个 `WriteLine` 语句打印出值 `42`，而不是 `24`。 变量 `valItem` 是 `int`，而不是 `ref int`。 `var` 关键字使编译器能够指定类型，但不会隐式添加 `ref` 修饰符。 相反，`ref return` 引用的值会被复制到赋值左侧的变量。 该变量不是 `ref` 局部变量。

为了获得所需的结果，需要在局部变量声明中添加 `ref` 修饰符，使变量在返回值为引用时成为引用：

[!code-csharp[AssignRefReturn](../../../samples/snippets/csharp/new-in-7/program.cs#24_AssignRefReturn "Assign ref return")]

现在，上例中的第二个 `WriteLine` 语句将打印出值 `24`，指示矩阵中的存储已被修改。 局部变量已使用 `ref` 修饰符进行声明，它将返回 `ref`。 必须在声明时初始化 `ref` 变量，不能拆分声明和初始化。

C# 语言还设有三条规则，可防止你误用 `ref` 局部变量和返回结果：

* 不可向 `ref` 本地变量赋予标准方法返回值。
    - 因为那将禁止类似 `ref int i = sequence.Count();` 这样的语句
* 不能将 `ref` 返回给其生存期不超出方法执行的变量。
    - 这意味着不可返回对本地变量或对类似作用域变量的引用。
* `ref` 局部变量和返回结果不可用于异步方法。
    - 编译器无法知道异步方法返回时，引用的变量是否已设置为其最终值。

添加 ref 局部变量和 ref 返回结果可通过避免复制值或多次执行取消引用操作，允许更为高效的算法。

向返回值添加 `ref` 是[源兼容的更改](version-update-considerations.md#source-compatible-changes)。 现有代码会进行编译，但在分配时复制 ref 返回值。 调用方必须将存储的返回值更新为 `ref` 局部变量，从而将返回值存储为引用。

有关详细信息，请参阅 [ref 关键字](../language-reference/keywords/ref.md)一文。

## <a name="local-functions"></a>本地函数

许多类的设计都包括仅从一个位置调用的方法。 这些额外的私有方法使每个方法保持小且集中。 但是，它们使得在第一次阅读某个类时难以理解它。 在单个调用位置的上下文之外必须能够理解这些方法。

对于这些设计，本地函数使你能够在另一个方法的上下文内声明方法。 这使得类的阅读者更容易看到本地方法是仅从声明它的上下文中调用的。

对于本地函数有两个非常常见的用例：公共迭代器方法和公共异步方法。 这两种类型的方法都生成报告错误的时间晚于程序员期望时间的代码。 在迭代器方法中，只有在调用枚举返回的序列的代码时才会观察到任何异常。 在异步方法中，只有当返回的 `Task` 处于等待状态时才会观察到任何异常。

让我们以迭代器方法为例：

[!code-csharp[IteratorMethod](../../../samples/snippets/csharp/new-in-7/Iterator.cs#25_IteratorMethod "Iterator method")]

检查下面错误调用迭代器方法的代码：

[!code-csharp[CallIteratorMethod](../../../samples/snippets/csharp/new-in-7/program.cs#26_CallIteratorMethod "Call iterator method")]

在循环访问 `resultSet`（而不是创建 `resultSet`）时引发异常。
在这个包含的示例中，大多数开发人员都可快速诊断问题。 但是，在大型基本代码中，创建迭代器的代码通常不像枚举结果的代码那么接近。 可以重构代码，使公共方法验证所有参数，且私有方法生成枚举：

[!code-csharp[IteratorMethodRefactored](../../../samples/snippets/csharp/new-in-7/Iterator.cs#27_IteratorMethodRefactored "Iterator method refactored")]

此重构版本将立即引发异常，因为公共方法不是迭代器方法；只有私有方法才使用 `yield return` 语法。 但是，这种重构存在潜在问题。 私有方法只应从公共接口方法调用，因为如果不这样，就将跳过所有参数验证。
类的阅读者必须通过阅读整个类并搜索对 `alphabetSubsetImplementation` 方法的任何其他引用来发现这个事实。

通过在公共 API 方法内将 `alphabetSubsetImplementation` 声明为本地函数，可以使该设计意图更清楚：

[!code-csharp[22_IteratorMethodLocal](../../../samples/snippets/csharp/new-in-7/Iterator.cs#28_IteratorMethodLocal "Iterator method with local function")]

上面的版本清楚地表明，本地方法仅在外部方法的上下文中引用。 本地函数的规则还确保开发人员不会意外地从类中的另一个位置调用本地函数和绕过参数验证。

可以对 `async` 方法采用相同的技术，以确保在异步工作开始之前引发由参数验证引起的异常：

[!code-csharp[TaskExample](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]

> [!NOTE]
> 本地函数支持的某些设计也可以使用 lambda 表达式来完成。 感兴趣的人可以[阅读有关差异的详细信息](../local-functions-vs-lambdas.md)

## <a name="more-expression-bodied-members"></a>更多的 expression-bodied 成员

C# 6 为成员函数和只读属性引入了 [expression-bodied 成员](csharp-6.md#expression-bodied-function-members)。 C# 7.0 扩展了可作为表达式实现的允许的成员。 在 C# 7.0 中，你可以在属性和索引器上实现构造函数、终结器以及 `get` 和 `set` 访问器。 以下代码演示了每种情况的示例：

[!code-csharp[ExpressionBodiedMembers](../../../samples/snippets/csharp/new-in-7/expressionmembers.cs#36_ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> 本示例不需要终结器，但显示它是为了演示语法。 不应在类中实现终结器，除非有必要发布非托管资源。 还应考虑使用 <xref:System.Runtime.InteropServices.SafeHandle> 类，而不是直接管理非托管资源。

这些 expression-bodied 成员的新位置代表了 C# 语言的一个重要里程碑：这些功能由致力于开发开放源代码 [Roslyn](https://github.com/dotnet/Roslyn) 项目的社区成员实现。

将方法更改为 expression bodied 成员是[二进制兼容的更改](version-update-considerations.md#binary-compatible-changes)。

## <a name="throw-expressions"></a>引发表达式

在 C# 中，`throw` 始终是一个语句。 因为 `throw` 是一个语句而非表达式，所以在某些 C# 构造中无法使用它。 它们包括条件表达式、null 合并表达式和一些 lambda 表达式。 添加 expression-bodied 成员将添加更多位置，在这些位置中，`throw` 表达式会很有用。 为了可以编写任何这些构造，C# 7.0 引入了引发表达式。

语法与你一直以来用于 `throw` 语句的语法相同。 唯一的区别是，现在你可以将它们放在新位置中（例如条件表达式中）：

[!code-csharp[Throw_ExpressionExample](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#37_Throw_ExpressionExample "conditional throw expressions")]

此功能允许在初始化表达式中使用引发表达式：

[!code-csharp[ThrowInInitialization](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#38_ThrowInInitialization "conditional throw expressions")]

以前，这些初始化需要位于构造函数中，且 throw 语句在构造函数的正文中：


[!code-csharp[ThrowInConstructor](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#39_ThrowInConstructor "throw statements")]

> [!NOTE]
> 前述两种构造都将导致在构造对象过程中引发异常。 通常很难从这些异常中恢复。
> 为此，不建议使用在构造过程中引发异常的设计。

## <a name="generalized-async-return-types"></a>通用的异步返回类型

从异步方法返回 `Task` 对象可能在某些路径中导致性能瓶颈。 `Task` 是引用类型，因此使用它意味着分配对象。 如果使用 `async` 修饰符声明的方法返回缓存结果或以同步方式完成，那么额外的分配在代码的性能关键部分可能要耗费相当长的时间。 如果这些分配发生在紧凑循环中，则成本会变得非常高。

新语言功能意味着异步方法可以返回除 `Task`、`Task<T>` 和 `void` 以外的其他类型。 返回类型必须仍满足异步模式，这意味着 `GetAwaiter` 方法必须是可访问的。 作为一个具体示例，已将 `ValueTask` 类型添加到 .NET framework 中，以使用这一新语言功能： 

[!code-csharp[UsingValueTask](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#30_UsingValueTask "Using ValueTask")]

> [!NOTE]
> 需要添加 NuGet 包 [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) 才能使用 <xref:System.Threading.Tasks.ValueTask%601> 类型。

一个简单的优化是在之前使用 `Task` 的地方使用 `ValueTask`。 但是，如果要手动执行额外的优化，则可以缓存来自异步工作的结果，并在后续调用中重用结果。 `ValueTask` 结构具有带 `Task` 参数的构造函数，以便你可以从任何现有异步方法的返回值构造 `ValueTask`：

[!code-csharp[AsyncOptimizedValueTask](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#31_AsyncOptimizedValueTask "Return async result or cached value")]

与所有性能建议一样，应在对代码进行大规模更改之前对两个版本进行基准测试。

如果返回值是 `await` 语句的目标，那么将 API 从 <xref:System.Threading.Tasks.Task%601> 更改为 <xref:System.Threading.Tasks.ValueTask%601> 是[源兼容的更改](version-update-considerations.md#source-compatible-changes)。 一般情况下，更改为 `ValueTask` 则不是如此。

## <a name="numeric-literal-syntax-improvements"></a>数字文本语法改进

误读的数值常量可能使第一次阅读代码时更难理解。 当这些数字被用作位掩码或其他符号而非数字值时，通常会发生这种情况。 C# 7.0 包括两项新功能，使得更容易以最可读的方式写入数字来用于预期用途：二进制文本和数字分隔符。

在创建位掩码时，或每当数字的二进制表示形式使代码最具可读性时，以二进制形式写入该数字：

[!code-csharp[BinaryConstants](../../../samples/snippets/csharp/new-in-7/Program.cs#32_BinaryConstants "Binary constants")]

常量开头的 `0b` 表示该数字以二进制数形式写入。

二进制数可能会很长，因此通过引入 `_` 作为数字分隔符通常更易于查看位模式：

[!code-csharp[ThousandSeparators](../../../samples/snippets/csharp/new-in-7/Program.cs#33_ThousandSeparators "Thousands separators")]

数字分隔符可以出现在常量的任何位置。 对于十进制数字，通常将其用作千位分隔符：

[!code-csharp[LargeIntegers](../../../samples/snippets/csharp/new-in-7/Program.cs#34_LargeIntegers "Large integer")]

数字分隔符也可以与 `decimal`、`float` 和 `double` 类型一起使用：

[!code-csharp[OtherConstants](../../../samples/snippets/csharp/new-in-7/Program.cs#35_OtherConstants "non-integral constants")]

综观来说，你可以声明可读性更强的数值常量。
