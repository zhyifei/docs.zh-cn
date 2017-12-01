---
title: "快速入门的分支和 lops-C# 指南"
description: "有关分支和循环本快速入门，在编写 C# 代码来浏览支持的条件分支和循环，以重复执行语句的语言语法。"
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 4b077a29cf42072a93b054f50a13a4580ad54304
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2017
---
# <a name="branches-and-loops"></a>分支和循环

本快速入门介绍了如何编写代码来检查变量并更改基于这些变量的执行路径。 编写 C# 代码，并请参阅编译和运行它的结果。 快速入门包含一系列的浏览分支和循环构造在 C# 中的课程。 这些课程介绍了 C# 语言的基础知识。

本快速入门希望有一台计算机可用于开发。 .NET 主题[开始在 10 分钟后](https://www.microsoft.com/net/core)已设置你在 Mac、 PC 或 Linux 上的本地开发环境的说明。

## <a name="make-decisions-using-the-if-statement"></a>使用做出决策`if`语句

创建一个名为目录**分支快速入门**。 将新建的目录设为当前目录，并运行 `dotnet new console -n BranchesAndLoops -o .`。 此命令在当前目录中创建一个新的.NET Core 控制台应用程序。 

打开**Program.cs**行替换你喜爱的编辑器中`Console.Writeline("Hello World!");`替换为以下代码：

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

请尝试此代码，通过键入`dotnet run`在控制台窗口。 你应看到消息"答案大于 10。" 打印到控制台。

修改 `b` 的声明，让总和小于 10： 

```csharp
int b = 3;
```

类型`dotnet run`试。 由于答案小于 10，因此什么也没有打印出来。 要测试的条件为 false。 没有任何可供执行的代码，因为仅为 `if` 语句编写了一个可能分支，即 true 分支。

> [!TIP]
> 在探索 C#（或任何编程语言）的过程中，可能会在编写代码时犯错。 编译器将找出并报告错误。 仔细查看的错误输出，并生成错误的代码。 Compler 错误通常可帮助你找出问题。 

此第一个示例显示的电源`if`和布尔值类型。 A*布尔*是一个变量，可以具有两个值之一：`true`或`false`。 C# 定义一种特殊类型，`bool`布尔变量。 `if` 语句检查 `bool` 的值。 如果值为 `true`，执行 `if` 后面的语句。 否则，跳过上述语句。 

这种检查条件并根据条件执行语句的过程非常强大。


## <a name="make-if-and-else-work-together"></a>让 if 和 else 完美配合

若要执行 true 和 false 分支中的不同代码，请创建在条件为 false 时执行的 `else` 分支。 尝试此操作。 在下面的代码以便中添加的最后两行你`Main`（你应该已前四个） 的方法：

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

只有当条件的测试结果为 `false` 时，才执行 `else` 关键字后面的语句。 组合`if`和`else`使用布尔值条件提供你需要同时处理的所有 power`true`和`false`条件。

> [!IMPORTANT]
> `if` 和 `else` 语句下的缩进是为了方便读者阅读。
> C# 语言忽略缩进或空格。 `if` 或 `else` 关键字后面的语句根据条件决定是否执行。 本快速入门中的所有示例都按照常见的做法，缩进基于语句的控制流的行。

由于缩进会被忽略，因此需要使用 `{` 和 `}`，指明要在根据条件决定是否执行的代码块中添加多个语句。 C# 程序员通常会对所有 `if` 和 `else` 子句使用这些大括号。 下面的示例是与你刚刚创建的一个相同。 修改代码更高版本以匹配下面的代码：

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
{
    Console.WriteLine("The answer is greater than 10");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
}
```

> [!TIP]
> 完成本快速入门的其余部分，所有的代码示例包括大括号，以下接受做法。

你可以测试更复杂的条件。 添加以下代码中的你`Main`方法之后你到目前为止已编写的代码：

```csharp
    int c = 4;
    if ((a + b + c > 10) && (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("And the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("Or the first number is not greater than the second");
}
```

`&&` 表示“且”。 也就是说，两个条件必须都为 true，才能执行 true 分支中的语句。  这些示例还表明，可以在每个条件分支中添加多个语句，前提是将它们用 `{` 和 `}` 括住。

你还可以使用`||`来表示"。 你到目前为止已编写之后添加以下代码：

```csharp
if ((a + b + c > 10) || (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("Or the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("And the first number is not greater than the second");
}
```

你已完成的第一步。 开始进入下一部分前，先将当前代码移到单独的方法中。 这样一来，可以更轻松地开始处理新示例。 将 `Main` 方法重命名为 `ExploreIf`，并编写调用 `ExploreIf` 的新 `Main` 方法。 完成后，代码应如下所示：

```csharp
using System;

namespace BranchesAndLoops
{
    class Program
    {
        static void ExploreIf()
        {
            int a = 5;
            int b = 3;
            if (a + b > 10)
            {
                Console.WriteLine("The answer is greater than 10");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
            }

            if ((a + b + c > 10) && (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("And the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("Or the first number is not greater than the second");
            }

            if ((a + b + c > 10) || (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("Or the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("And the first number is not greater than the second");
            }            
        }

        static void Main(string[] args)
        {
            ExploreIf();
        }
    }
}
```

注释掉对的调用`ExploreIf()`。 它将使整洁的当您在本部分工作的输出：

```csharp
//ExploreIf();
```

`//`启动**注释**C# 中。 注释是你想要保留在源代码中，但不是能作为代码执行的任何文本。 从注释，编译器不生成任何可执行代码。

## <a name="use-loops-to-repeat-operations"></a>使用循环重复执行运算

在本部分中使用**循环**重复语句。 请尝试此代码中的你`Main`方法：

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

`while`语句检查的条件，并执行的语句或后面的语句块`while`。 它会重复检查的条件和执行这些语句，直到条件为 false。

此示例新引入了另外一个运算符。 `counter` 变量后面的 `++` 是增量运算符。 它将 1 添加到的值`counter`，并将存储中的该值`counter`变量。

> [!IMPORTANT]
> 请确保`while`循环条件更改为 false，如执行代码。 否则，创建的就是无限循环，即程序永不结束。 程序不演示此示例中，因为你必须以强制程序若要停止使用**CTRL-C**或其他方法。

`while` 循环先测试条件，然后再执行 `while` 后面的代码。 `do` ... `while` 循环先执行代码，然后再检查条件。 以下代码所示循环时执行：

```csharp
counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

这`do`循环及更早版本`while`循环生成相同的输出。

## <a name="work-with-the-for-loop"></a>使用 for 循环

**为**循环通常用在 C#。 请尝试此代码在 main （） 方法中：

```csharp
for(int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
} 
```

此循环的工作原理与已用过的 `while` 循环和 `do` 循环相同。 `for` 语句包含三个控制具体工作方式的部分。 

第一部分是 for 初始值设定项：`for index = 0;` 声明 `index` 是循环变量，并将它的初始值设置为 `0`。

中间部分是 for 条件：`index < 10` 声明只要计数器值小于 10，此 `for` 循环就会继续执行。

最后一部分是 for 迭代器：`index++` 指定在执行 `for` 语句后面的代码块后，如何修改循环变量。 在此示例中，它指定 `index` 应在代码块每次执行时递增 1。

亲自试运行这些部分的代码。 试着执行下列两项操作：

- 将初始值设定项更改为其他初始值。
- 将结束条件设定项更改为其他值。

完成后，继续利用所学知识，试着自己编写一些代码。

## <a name="combine-branches-and-loops"></a>将分支和循环结合起来

支持，大家已了解 C# 语言中的 `if` 语句和循环构造。看看能否编写 C# 代码，计算 1 到 20 中所有可被 3 整除的整数的总和。  下面提供了一些提示：

- `%` 运算符可用于获取除法运算的余数。
- `if`语句，为你提供的条件，以查看是否数应为之和的一部分。
- `for` 循环有助于对 1 到 20 中的所有数字重复执行一系列步骤。

亲自试一试吧。 然后，看看自己是怎么做到的。 你可以看到由一个可能的答案[GitHub 上查看代码的已完成的](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54)。

您已完成"分支和循环"快速入门。

您可以使用继续[数组和集合](arrays-and-collections.md)开发环境中的快速入门。

若要详细了解这些概念，请参阅下列主题：

[If 和 else 语句](../language-reference/keywords/if-else.md)   
[While 语句](../language-reference/keywords/while.md)   
[Do 语句](../language-reference/keywords/do.md)   
[For 语句](../language-reference/keywords/for.md)   
