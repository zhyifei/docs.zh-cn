---
title: "“C# 中的数字”教程 - C# 本地快速入门"
description: "通过浏览数字类型、其属性和方法了解 C#。"
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 9a8b28d840d3c8ef63611e9f584e5984e1dcb1a3
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="numbers-in-c-quickstart"></a><span data-ttu-id="39991-103">“C# 中的数字”快速入门</span><span class="sxs-lookup"><span data-stu-id="39991-103">Numbers in C# quickstart</span></span>

<span data-ttu-id="39991-104">本快速入门教程以交互方式介绍了 C# 中的数字类型。</span><span class="sxs-lookup"><span data-stu-id="39991-104">This quickstart teaches you about the number types in C# interactively.</span></span> <span data-ttu-id="39991-105">你将编写少量的代码，然后编译并运行这些代码。</span><span class="sxs-lookup"><span data-stu-id="39991-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="39991-106">本快速入门教程包含一系列课程，介绍了 C# 中的数字和数学操作。</span><span class="sxs-lookup"><span data-stu-id="39991-106">The quickstart contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="39991-107">这些课程介绍了 C# 语言的基础知识。</span><span class="sxs-lookup"><span data-stu-id="39991-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="39991-108">若要学习本快速入门教程，必须有开发计算机。</span><span class="sxs-lookup"><span data-stu-id="39991-108">This quickstart expects you to have a machine you can use for development.</span></span> <span data-ttu-id="39991-109">.NET 主题 [10 分钟入门](https://www.microsoft.com/net/core)介绍了如何在 Mac、PC 或 Linux 上设置本地开发环境。</span><span class="sxs-lookup"><span data-stu-id="39991-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="39991-110">[本地快速入门教程简介](local-environment.md)不仅简要概述了将用到的命令，还收录了详细信息链接。</span><span class="sxs-lookup"><span data-stu-id="39991-110">A quick overview of the commands you'll use is in the [introduction to the local quickstarts](local-environment.md) with links to more details.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="39991-111">探索整数数学运算</span><span class="sxs-lookup"><span data-stu-id="39991-111">Explore integer math</span></span>

<span data-ttu-id="39991-112">创建名为 numbers-quickstart 的目录。</span><span class="sxs-lookup"><span data-stu-id="39991-112">Create a directory named **numbers-quickstart**.</span></span> <span data-ttu-id="39991-113">将新建的目录设为当前目录，并运行 `dotnet new console -n NumbersInCSharp -o .`。</span><span class="sxs-lookup"><span data-stu-id="39991-113">Make that the current directory and run `dotnet new console -n NumbersInCSharp -o .`.</span></span>

<span data-ttu-id="39991-114">在常用编辑器中，打开 Program.cs，并将行 `Console.Writeline("Hello World!");` 替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="39991-114">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="39991-115">通过在命令窗口中键入 `dotnet run` 运行此代码。</span><span class="sxs-lookup"><span data-stu-id="39991-115">Run this code by typing `dotnet run` in your command window.</span></span> 

<span data-ttu-id="39991-116">刚刚看到的是一种基本的整数数学运算。</span><span class="sxs-lookup"><span data-stu-id="39991-116">You've just seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="39991-117">`int` 类型表示整数（正整数或负整数）。</span><span class="sxs-lookup"><span data-stu-id="39991-117">The `int` type represents an **integer**, a positive or negative whole number.</span></span> <span data-ttu-id="39991-118">使用 `+` 符号执行加法运算。</span><span class="sxs-lookup"><span data-stu-id="39991-118">You use the `+` symbol for addition.</span></span> <span data-ttu-id="39991-119">其他常见的整数数学运算包括：</span><span class="sxs-lookup"><span data-stu-id="39991-119">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="39991-120">`-`：减法运算</span><span class="sxs-lookup"><span data-stu-id="39991-120">`-` for subtraction</span></span>
- <span data-ttu-id="39991-121">`*`：乘法运算</span><span class="sxs-lookup"><span data-stu-id="39991-121">`*` for multiplication</span></span>
- <span data-ttu-id="39991-122">`/`：除法运算</span><span class="sxs-lookup"><span data-stu-id="39991-122">`/` for division</span></span>

<span data-ttu-id="39991-123">首先，探索这些不同类型的运算。</span><span class="sxs-lookup"><span data-stu-id="39991-123">Start by exploring those different operations.</span></span> <span data-ttu-id="39991-124">在写入 `c` 值的行之后添加以下行：</span><span class="sxs-lookup"><span data-stu-id="39991-124">Add these lines after the line that writes the value of `c`:</span></span>

```csharp
c = a - b;
Console.WriteLine(c);
c = a * b;
Console.WriteLine(c);
c = a / b;
Console.WriteLine(c);
```

<span data-ttu-id="39991-125">通过在命令窗口中键入 `dotnet run` 运行此代码。</span><span class="sxs-lookup"><span data-stu-id="39991-125">Run this code by typing `dotnet run` in your command window.</span></span> 
    
<span data-ttu-id="39991-126">如果愿意，也可以尝试在同一行中执行多个数学运算。</span><span class="sxs-lookup"><span data-stu-id="39991-126">You can also experiment by performing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="39991-127">例如，请尝试 `c = a + b - 12 * 17;`。</span><span class="sxs-lookup"><span data-stu-id="39991-127">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="39991-128">允许混合使用变量和常数。</span><span class="sxs-lookup"><span data-stu-id="39991-128">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="39991-129">在探索 C#（或任何编程语言）的过程中，可能会在编写代码时犯错。</span><span class="sxs-lookup"><span data-stu-id="39991-129">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="39991-130">编译器会发现并报告这些错误。</span><span class="sxs-lookup"><span data-stu-id="39991-130">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="39991-131">如果输出中包含错误消息，请仔细比对示例代码和你的窗口中的代码，看看哪些需要纠正。</span><span class="sxs-lookup"><span data-stu-id="39991-131">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="39991-132">这样做有助于了解 C# 代码结构。</span><span class="sxs-lookup"><span data-stu-id="39991-132">That exercise will help you learn the structure of C# code.</span></span>     

<span data-ttu-id="39991-133">你已完成第一步。</span><span class="sxs-lookup"><span data-stu-id="39991-133">You've finished the first step.</span></span> <span data-ttu-id="39991-134">开始进入下一部分前，先将当前代码移到单独的方法中。</span><span class="sxs-lookup"><span data-stu-id="39991-134">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="39991-135">这样一来，可以更轻松地开始处理新示例。</span><span class="sxs-lookup"><span data-stu-id="39991-135">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="39991-136">将 `Main` 方法重命名为 `WorkingWithIntegers`，并编写调用 `WorkingWithIntegers` 的新 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="39991-136">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="39991-137">完成后，代码应如下所示：</span><span class="sxs-lookup"><span data-stu-id="39991-137">When you have finished, your code should look like this:</span></span>

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

## <a name="explore-order-of-operations"></a><span data-ttu-id="39991-138">探索运算顺序</span><span class="sxs-lookup"><span data-stu-id="39991-138">Explore order of operations</span></span>

<span data-ttu-id="39991-139">注释掉对 `WorkingWithIntegers()` 的调用。</span><span class="sxs-lookup"><span data-stu-id="39991-139">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="39991-140">在本节中，它会在你工作时使输出变得不那么杂乱：</span><span class="sxs-lookup"><span data-stu-id="39991-140">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="39991-141">`//` 在 C# 中启动 注释。</span><span class="sxs-lookup"><span data-stu-id="39991-141">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="39991-142">注释是你想要保留在源代码中但不能作为代码执行的任何文本。</span><span class="sxs-lookup"><span data-stu-id="39991-142">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="39991-143">编译器不会从注释中生成任何可执行代码。</span><span class="sxs-lookup"><span data-stu-id="39991-143">The compiler does not generate any executable code from comments.</span></span>

<span data-ttu-id="39991-144">C# 语言使用与数学运算规则一致的规则，定义不同数学运算的优先级。</span><span class="sxs-lookup"><span data-stu-id="39991-144">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="39991-145">乘法和除法的优先级高于加法和减法。</span><span class="sxs-lookup"><span data-stu-id="39991-145">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="39991-146">将以下代码添加到 `Main` 方法，然后执行 `dotnet run` 进行探索：</span><span class="sxs-lookup"><span data-stu-id="39991-146">Explore that by adding the following code to your `Main` method, and execuing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="39991-147">输出结果表明，乘法先于加法执行。</span><span class="sxs-lookup"><span data-stu-id="39991-147">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="39991-148">可以在要优先执行的一个或多个运算前后添加括号，从而强制改变运算顺序。</span><span class="sxs-lookup"><span data-stu-id="39991-148">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="39991-149">添加以下行并再次运行：</span><span class="sxs-lookup"><span data-stu-id="39991-149">Add the following lines and run again:</span></span>

```csharp
d = (a  + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="39991-150">通过组合多个不同的运算，进一步探索运算顺序。</span><span class="sxs-lookup"><span data-stu-id="39991-150">Explore more by combining many different operations.</span></span> <span data-ttu-id="39991-151">在 `Main` 方法底部添加类似以下行的内容。</span><span class="sxs-lookup"><span data-stu-id="39991-151">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="39991-152">重试 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="39991-152">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="39991-153">可能已注意到，整数有一个非常有趣的行为。</span><span class="sxs-lookup"><span data-stu-id="39991-153">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="39991-154">整数除法始终生成整数结果，即使预期结果有小数或分数部分也是如此。</span><span class="sxs-lookup"><span data-stu-id="39991-154">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="39991-155">如果你没有注意到此行为，请在 `Main` 方法结束时试运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="39991-155">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="39991-156">再次键入 `dotnet run`，看看结果如何。</span><span class="sxs-lookup"><span data-stu-id="39991-156">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="39991-157">继续之前，让我们获取你在本节编写的所有代码并放在新的方法中。</span><span class="sxs-lookup"><span data-stu-id="39991-157">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="39991-158">调用新方法 `OrderPrecedence`。</span><span class="sxs-lookup"><span data-stu-id="39991-158">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="39991-159">最后应以与下面类似的代码结束：</span><span class="sxs-lookup"><span data-stu-id="39991-159">You should end up with something like this:</span></span>

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

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="39991-160">探索整数运算精度和限值</span><span class="sxs-lookup"><span data-stu-id="39991-160">Explore integer precision and limits</span></span>
<span data-ttu-id="39991-161">在上一个示例中，整数除法截断了结果。</span><span class="sxs-lookup"><span data-stu-id="39991-161">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="39991-162">可以使用取模运算符（即 `%` 字符）计算余数。</span><span class="sxs-lookup"><span data-stu-id="39991-162">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="39991-163">在 `Main` 方法中试用以下代码：</span><span class="sxs-lookup"><span data-stu-id="39991-163">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a  + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="39991-164">C# 整数类型不同于数学上的整数的另一点是，`int` 类型有最小限值和最大限值。</span><span class="sxs-lookup"><span data-stu-id="39991-164">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="39991-165">将此代码添加到 `Main` 方法，看看这些限制的运行机制：</span><span class="sxs-lookup"><span data-stu-id="39991-165">Add this code to your `Main` method to see those limits:</span></span>
    
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="39991-166">如果运算生成的值超过这些限值，则会出现下溢或溢出的情况。</span><span class="sxs-lookup"><span data-stu-id="39991-166">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="39991-167">答案似乎是从一个限值覆盖到另一个限值的范围。</span><span class="sxs-lookup"><span data-stu-id="39991-167">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="39991-168">例如，将以下两行添加到 `Main` 方法：</span><span class="sxs-lookup"><span data-stu-id="39991-168">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```
    
<span data-ttu-id="39991-169">可以看到，答案非常接近最小（负）整数。</span><span class="sxs-lookup"><span data-stu-id="39991-169">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="39991-170">与 `min + 2` 相同。</span><span class="sxs-lookup"><span data-stu-id="39991-170">It's the same as `min + 2`.</span></span> <span data-ttu-id="39991-171">加法运算会让整数溢出允许的值。</span><span class="sxs-lookup"><span data-stu-id="39991-171">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="39991-172">答案是一个非常大的负数，因为溢出从最大整数值覆盖回最小整数值。</span><span class="sxs-lookup"><span data-stu-id="39991-172">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="39991-173">如果 `int` 类型无法满足需求，还会用到限值和精度不同的其他数字类型。</span><span class="sxs-lookup"><span data-stu-id="39991-173">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="39991-174">接下来，将探索这些类型。</span><span class="sxs-lookup"><span data-stu-id="39991-174">Let's explore those next.</span></span>

<span data-ttu-id="39991-175">让我们再一次将你在本节编写的代码移到一个单独的方法中。</span><span class="sxs-lookup"><span data-stu-id="39991-175">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="39991-176">将其命名为 `TestLimits`。</span><span class="sxs-lookup"><span data-stu-id="39991-176">Name it `TestLimits`.</span></span> 

## <a name="work-with-the-double-type"></a><span data-ttu-id="39991-177">使用双精度类型</span><span class="sxs-lookup"><span data-stu-id="39991-177">Work with the double type</span></span>

<span data-ttu-id="39991-178">`double` 数字类型表示双精度浮点数。</span><span class="sxs-lookup"><span data-stu-id="39991-178">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="39991-179">这些词可能是第一次听说。</span><span class="sxs-lookup"><span data-stu-id="39991-179">Those terms may be new to you.</span></span> <span data-ttu-id="39991-180">浮点数可用于表示数量级可能非常大或非常小的非整数。</span><span class="sxs-lookup"><span data-stu-id="39991-180">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="39991-181">双精度意味着存储这些数字时使用的精度高于单精度。</span><span class="sxs-lookup"><span data-stu-id="39991-181">**Double-precision** means that these numbers are stored using greater precision than **single-precision**.</span></span> <span data-ttu-id="39991-182">在新式计算机上，使用双精度数字比使用单精度数字更为常见。</span><span class="sxs-lookup"><span data-stu-id="39991-182">On modern computers, it is more common to use double precision than single precision numbers.</span></span>
<span data-ttu-id="39991-183">接下来，将探索双精度类型。</span><span class="sxs-lookup"><span data-stu-id="39991-183">Let's explore.</span></span> <span data-ttu-id="39991-184">添加以下代码并查看结果：</span><span class="sxs-lookup"><span data-stu-id="39991-184">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a  + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="39991-185">可以看到，答案商包含小数部分。</span><span class="sxs-lookup"><span data-stu-id="39991-185">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="39991-186">试试对双精度类型使用更复杂一点的表达式：</span><span class="sxs-lookup"><span data-stu-id="39991-186">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="39991-187">双精度值的范围远大于整数值。</span><span class="sxs-lookup"><span data-stu-id="39991-187">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="39991-188">在当前已编写的代码下方试运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="39991-188">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="39991-189">打印出来的这些值用科学记数法表示。</span><span class="sxs-lookup"><span data-stu-id="39991-189">These values are printed out in scientific notation.</span></span> <span data-ttu-id="39991-190">`E` 左侧为有效数字。</span><span class="sxs-lookup"><span data-stu-id="39991-190">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="39991-191">右侧为是 10 的 n 次幂。</span><span class="sxs-lookup"><span data-stu-id="39991-191">The number to the right is the exponent, as a power of 10.</span></span> 

<span data-ttu-id="39991-192">与数学上的十进制数字一样，C# 中的双精度值可能会有四舍五入误差。</span><span class="sxs-lookup"><span data-stu-id="39991-192">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="39991-193">试运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="39991-193">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="39991-194">众所周知，`0.3` 循环小数与 `1/3` 并不完全相等。</span><span class="sxs-lookup"><span data-stu-id="39991-194">You know that `0.3` repeating is not exactly the same as `1/3`.</span></span>

<span data-ttu-id="39991-195">***挑战***</span><span class="sxs-lookup"><span data-stu-id="39991-195">***Challenge***</span></span>

<span data-ttu-id="39991-196">尝试使用 `double` 类型执行其他的大小数、乘法和除法运算。</span><span class="sxs-lookup"><span data-stu-id="39991-196">Try other calculations with large numbers, small numbers, multiplication and division using the `double` type.</span></span>  <span data-ttu-id="39991-197">尝试执行更复杂的运算。</span><span class="sxs-lookup"><span data-stu-id="39991-197">Try more complicated calculations.</span></span>

<span data-ttu-id="39991-198">花了一些时间应对挑战之后，获取已编写的代码并放在一个新方法中。</span><span class="sxs-lookup"><span data-stu-id="39991-198">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="39991-199">将新方法命名为 `WorkWithDoubles`。</span><span class="sxs-lookup"><span data-stu-id="39991-199">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-fixed-point-types"></a><span data-ttu-id="39991-200">使用固定点类型</span><span class="sxs-lookup"><span data-stu-id="39991-200">Work with fixed point types</span></span>

<span data-ttu-id="39991-201">大家已学习了 C# 中的基本数字类型，即整数和双精度。</span><span class="sxs-lookup"><span data-stu-id="39991-201">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="39991-202">下面将介绍另一种需要了解的类型，即 `decimal` 类型。</span><span class="sxs-lookup"><span data-stu-id="39991-202">There is one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="39991-203">`decimal` 类型的范围较小，但精度高于 `double`。</span><span class="sxs-lookup"><span data-stu-id="39991-203">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="39991-204">“固定点”一词意味着，十进制小数点（或二进制小数点）不会移动。</span><span class="sxs-lookup"><span data-stu-id="39991-204">The term **fixed point** means that the decimal point (or binary point) doesn't move.</span></span> <span data-ttu-id="39991-205">让我们来实际操作一下：</span><span class="sxs-lookup"><span data-stu-id="39991-205">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="39991-206">可以看到，范围小于 `double` 类型。</span><span class="sxs-lookup"><span data-stu-id="39991-206">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="39991-207">通过试运行以下代码，可以看到十进制类型的精度更高：</span><span class="sxs-lookup"><span data-stu-id="39991-207">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="39991-208">数字中的 `M` 后缀指明了常数应如何使用 `decimal` 类型。</span><span class="sxs-lookup"><span data-stu-id="39991-208">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span>

<span data-ttu-id="39991-209">可以看到，使用十进制类型执行数学运算时，十进制小数点右侧的数字更多。</span><span class="sxs-lookup"><span data-stu-id="39991-209">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span> 

<span data-ttu-id="39991-210">***挑战***</span><span class="sxs-lookup"><span data-stu-id="39991-210">***Challenge***</span></span>

<span data-ttu-id="39991-211">至此，大家已了解不同的数字类型。请编写代码来计算圆面积（其中，半径为 2.50 英寸）。</span><span class="sxs-lookup"><span data-stu-id="39991-211">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 inches.</span></span> <span data-ttu-id="39991-212">请注意，圆面积是用半径的平方乘以 PI 进行计算。</span><span class="sxs-lookup"><span data-stu-id="39991-212">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="39991-213">小提示：.NET 包含 PI 常数 <xref:System.Math.PI?displayProperty=nameWithType>，可用于相应的值计算。</span><span class="sxs-lookup"><span data-stu-id="39991-213">One hint: .NET contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> 

<span data-ttu-id="39991-214">你应获得 19 和 20 之间的答案。</span><span class="sxs-lookup"><span data-stu-id="39991-214">You should get an answer between 19 and 20.</span></span>
<span data-ttu-id="39991-215">要查看你的答案，可以[查看 GitHub 上的完成示例代码](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)</span><span class="sxs-lookup"><span data-stu-id="39991-215">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)</span></span>

<span data-ttu-id="39991-216">如果需要，可以试用一些其他公式。</span><span class="sxs-lookup"><span data-stu-id="39991-216">Try some other formulas if you'd like.</span></span> 

<span data-ttu-id="39991-217">已完成“C# 中的数字”快速入门教程。</span><span class="sxs-lookup"><span data-stu-id="39991-217">You've completed the "Numbers in C#" quickstart.</span></span> <span data-ttu-id="39991-218">可以在自己的开发环境中继续学习[分支和循环](branches-and-loops-local.md)快速入门教程。</span><span class="sxs-lookup"><span data-stu-id="39991-218">You can continue with the [Branches and loops](branches-and-loops-local.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="39991-219">可以参阅下面的主题，详细了解 C# 中的数字：</span><span class="sxs-lookup"><span data-stu-id="39991-219">You can learn more about numbers in C# in the following topics:</span></span>

<span data-ttu-id="39991-220">[整型类型表](../language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="39991-220">[Integral Types Table](../language-reference/keywords/integral-types-table.md) </span></span>  
<span data-ttu-id="39991-221">[浮点型表](../language-reference/keywords/floating-point-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="39991-221">[Floating-Point Types Table](../language-reference/keywords/floating-point-types-table.md) </span></span>  
<span data-ttu-id="39991-222">[内置类型表](../language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="39991-222">[Built-In Types Table](../language-reference/keywords/built-in-types-table.md) </span></span>  
<span data-ttu-id="39991-223">[隐式数值转换表](../language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="39991-223">[Implicit Numeric Conversions Table](../language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
[<span data-ttu-id="39991-224">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="39991-224">Explicit Numeric Conversions Table</span></span>](../language-reference/keywords/explicit-numeric-conversions-table.md)

