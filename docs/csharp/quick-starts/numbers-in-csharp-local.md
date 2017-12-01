---
title: "快速入门-C# 中的数字的 C# 指南"
description: "了解 C# 通过浏览数值类型、 其属性和方法。"
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 821cca4ea6d6148410e9b179f05d5b74c4844628
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2017
---
# <a name="numbers-in-c-quick-start"></a>C# 快速入门中的数字 #

本快速入门介绍了有关在 C# 中的数字类型以交互方式。 你将在其中编写少量的代码，然后将编译并运行该代码。 快速入门包含一系列的浏览数字和 C# 中的数学运算的课程。 这些课程介绍了 C# 语言的基础知识。

本快速入门希望有一台计算机可用于开发。 .NET 主题[开始在 10 分钟后](https://www.microsoft.com/net/core)已设置你在 Mac、 PC 或 Linux 上的本地开发环境的说明。

## <a name="explore-integer-math"></a>探索整数数学运算

创建一个名为目录**数字快速入门**。 将新建的目录设为当前目录，并运行 `dotnet new console -n NumbersInCSharp -o .`。

打开**Program.cs**行替换你喜爱的编辑器中`Console.Writeline("Hello World!");`替换为以下：

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

通过键入运行此代码`dotnet run`命令窗口中。 

刚刚看到的是一种基本的整数数学运算。 `int` 类型表示整数（正整数或负整数）。 使用 `+` 符号执行加法运算。 其他常见的整数数学运算包括：

- `-`：减法运算
- `*`：乘法运算
- `/`：除法运算

首先，探索这些不同类型的运算。 值写入行后添加以下行`c`:

```csharp
c = a - b;
Console.WriteLine(c);
c = a * b;
Console.WriteLine(c);
c = a / b;
Console.WriteLine(c);
```

通过键入运行此代码`dotnet run`命令窗口中。 
    
如果愿意，也可以尝试在同一行中执行多个数学运算。 请尝试`c = a + b - 12 * 17;`例如。 允许混合使用变量和常量的数字。

> [!TIP]
> 在探索 C#（或任何编程语言）的过程中，可能会在编写代码时犯错。 编译器会发现并报告这些错误。 当输出中包含错误消息时，仔细查看此代码示例和你的窗口以查看要修复的内容中的代码。
> 这样做有助于了解 C# 代码结构。     

你已完成的第一步。 开始进入下一部分前，先将当前代码移到单独的方法中。 这样一来，可以更轻松地开始处理新示例。 将 `Main` 方法重命名为 `WorkingWithIntegers`，并编写调用 `WorkingWithIntegers` 的新 `Main` 方法。 完成后，代码应如下所示：

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
            c = a / b;
            Console.WriteLine(c);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();
        }
    }
}
```

## <a name="explore-order-of-operations"></a>探索运算顺序

注释掉对的调用`WorkingWithIntegers()`。 它将使整洁的当您在本部分工作的输出：

```csharp
//WorkingWithIntegers();
```

`//`启动**注释**C# 中。 注释是你想要保留在源代码中，但不是能作为代码执行的任何文本。 从注释，编译器不生成任何可执行代码。

C# 语言使用与数学运算规则一致的规则，定义不同数学运算的优先级。
乘法和除法的优先级高于加法和减法。
通过添加以下代码中浏览，你`Main`方法，并 execuing `dotnet run`:

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

输出结果表明，乘法先于加法执行。

你可以通过添加圆括号操作强制操作的不同的顺序或第一次执行所需的操作。 添加以下行，重新运行：

```csharp
d = (a  + b) * c;
Console.WriteLine(d);
```

通过组合多个不同的运算，进一步探索运算顺序。 在底部添加以下行类似你`Main`方法。 请尝试`dotnet run`试。

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

可能已注意到，整数有一个非常有趣的行为。 整数除法始终生成整数结果，即使你预期的结果包含小数或分数部分。

如果尚未看到此行为，请尝试下面的代码的末尾你`Main`方法：

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e  + f) / g;
Console.WriteLine(h);
```

类型`dotnet run`试以查看结果。

继续之前，让我们需要你编写在本部分并将其放入新的方法的所有代码。 可以调用该新方法`OrderPrecedence`。
你应会得到类似如下内容：

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
            c = a / b;
            Console.WriteLine(c);
        }

        static void OrderPrecedence()
        {   
            int a = 5;
            int b = 4;
            int c = 2;
            int d = a + b * c;
            Console.WriteLine(d);

            d = (a  + b) * c;
            Console.WriteLine(d);

            d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
            Console.WriteLine(d);

            int e = 7;
            int f = 4;
            int g = 3;
            int h = (e  + f) / g;
            Console.WriteLine(h);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();

            OrderPrecedence();

        }
    }
}
```

## <a name="explore-integer-precision-and-limits"></a>探索整数运算精度和限值
在上一个示例中，整数除法截断了结果。
你可以获取**余数**使用**取模**运算符，`%`字符。 尝试使用以下代码中的你`Main`方法：

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a  + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

C# 整数类型不同于数学上的整数的另一点是，`int` 类型有最小限值和最大限值。 此将代码添加到你`Main`方法若要查看这些限制：
    
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

如果运算生成的值超过这些限值，则会出现下溢或溢出的情况。 答案似乎是从一个限值覆盖到另一个限值的范围。 添加到这两行你`Main`方法，以便查看示例：

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```
    
可以看到，答案非常接近最小（负）整数。 与 `min + 2` 相同。 加法运算会让整数溢出允许的值。
答案是一个非常大的负数，因为溢出从最大整数值覆盖回最小整数值。

如果 `int` 类型无法满足需求，还会用到限值和精度不同的其他数字类型。 接下来，将探索这些类型。

同样，让我们将移到单独的方法的此部分中编写的代码。 将其命名为 `TestLimits`。 

## <a name="work-with-the-double-type"></a>使用双精度类型

`double` 数字类型表示双精度浮点数。 这些词可能是第一次听说。 A**浮点数**数可用于表示可能会非常大或小在数量级上的非整型数字。 双精度意味着存储这些数字时使用的精度高于单精度。 在新式计算机上，使用双精度数字比使用单精度数字更为常见。
接下来，将探索双精度类型。 添加以下代码并查看结果：

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a  + b) / c;
Console.WriteLine(d);
```

可以看到，答案商包含小数部分。 试试对双精度类型使用更复杂一点的表达式：

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e  + f) / g;
Console.WriteLine(h);
```

双精度值的范围远大于整数值。 请尝试你到目前为止已编写下面的代码：

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

这些值输出科学记数法。 左侧的数字`E`是有效位数。 右侧为是 10 的 n 次幂。 

与数学上的十进制数字一样，C# 中的双精度值可能会有四舍五入误差。 试运行以下代码：

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

众所周知，`0.3` 循环小数与 `1/3` 并不完全相等。

***挑战***

尝试使用 `double` 类型执行其他的大小数、乘法和除法运算。  尝试执行更复杂的运算。

已花一些时间来使用质询后，需要你已经编写并将其放在一个新方法的代码。 将该新方法`WorkWithDoubles`。

## <a name="work-with-fixed-point-types"></a>使用固定点类型

大家已学习了 C# 中的基本数字类型，即整数和双精度。  下面将介绍另一种需要了解的类型，即 `decimal` 类型。 `decimal`类型具有更小的范围，但更高的精度比`double`。 “固定点”一词意味着，十进制小数点（或二进制小数点）不会移动。 让我们来实际操作一下：

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

可以看到，范围小于 `double` 类型。 通过试运行以下代码，可以看到十进制类型的精度更高：

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

数字中的 `M` 后缀指明了常数应如何使用 `decimal` 类型。

可以看到，使用十进制类型执行数学运算时，十进制小数点右侧的数字更多。 

***挑战***

至此，大家已了解不同的数字类型。请编写代码来计算圆面积（其中，半径为 2.50 英寸）。 请注意，圆面积是用半径的平方乘以 PI 进行计算。 一个提示： C# 包含常量 PI <xref:System.Math.PI?displayProperty=nameWithType> ，你可以使用为该值。 

你可以检查您的答案通过[在 GitHub 上查看已完成的示例代码](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)

如果你想要，尝试一些其他公式。 

您已完成"数字中 C#"快速入门。 您可以使用继续[分支和循环](branches-and-loops-local.md)开发环境中的快速入门。

可以参阅下面的主题，详细了解 C# 中的数字：

[整型类型表](../language-reference/keywords/integral-types-table.md)   
[浮点型表](../language-reference/keywords/floating-point-types-table.md)   
[内置类型表](../language-reference/keywords/built-in-types-table.md)   
[隐式数值转换表](../language-reference/keywords/implicit-numeric-conversions-table.md)   
[显式数值转换表](../language-reference/keywords/explicit-numeric-conversions-table.md)

