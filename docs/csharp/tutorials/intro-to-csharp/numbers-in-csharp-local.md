---
title: C# 中的数字 - C# 教程简介
description: 通过探索数字类型及其用途、属性和方法了解 C#。
ms.date: 10/31/2017
ms.custom: mvc
ms.openlocfilehash: 3dc2a5afc6321da45351525a632f586cb84bf7fe
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794606"
---
# <a name="manipulate-integral-and-floating-point-numbers-in-c"></a><span data-ttu-id="95827-103">处理 C\# 中的整数和浮点数</span><span class="sxs-lookup"><span data-stu-id="95827-103">Manipulate integral and floating point numbers in C\#</span></span>

<span data-ttu-id="95827-104">本教程以交互方式介绍了 C# 中的数字类型。</span><span class="sxs-lookup"><span data-stu-id="95827-104">This tutorial teaches you about the numeric types in C# interactively.</span></span> <span data-ttu-id="95827-105">你将编写少量的代码，然后编译并运行这些代码。</span><span class="sxs-lookup"><span data-stu-id="95827-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="95827-106">本教程包含一系列课程，介绍了 C# 中的数字和数学运算。</span><span class="sxs-lookup"><span data-stu-id="95827-106">The tutorial contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="95827-107">这些课程介绍了 C# 语言的基础知识。</span><span class="sxs-lookup"><span data-stu-id="95827-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="95827-108">本教程要求你有一台可用于开发的计算机。</span><span class="sxs-lookup"><span data-stu-id="95827-108">This tutorial expects you to have a machine you can use for development.</span></span> <span data-ttu-id="95827-109">.NET 教程 [Hello World 10 分钟入门](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro)介绍了如何在 Windows、Linux 或 macOS 上设置本地开发环境。</span><span class="sxs-lookup"><span data-stu-id="95827-109">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="95827-110">[熟悉开发工具](local-environment.md)不仅简要概述了将用到的命令，还收录了详细信息链接。</span><span class="sxs-lookup"><span data-stu-id="95827-110">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="95827-111">探索整数数学运算</span><span class="sxs-lookup"><span data-stu-id="95827-111">Explore integer math</span></span>

<span data-ttu-id="95827-112">创建名为 numbers-quickstart  的目录。</span><span class="sxs-lookup"><span data-stu-id="95827-112">Create a directory named *numbers-quickstart*.</span></span> <span data-ttu-id="95827-113">将其设为当前目录并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="95827-113">Make that the current directory and run the following command:</span></span>

```dotnetcli
dotnet new console -n NumbersInCSharp -o .
```

<span data-ttu-id="95827-114">在常用编辑器中，打开 Program.cs  ，并将行 `Console.WriteLine("Hello World!");` 替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="95827-114">Open *Program.cs* in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="95827-115">通过在命令窗口中键入 `dotnet run` 运行此代码。</span><span class="sxs-lookup"><span data-stu-id="95827-115">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="95827-116">上面是基本的整数数学运算之一。</span><span class="sxs-lookup"><span data-stu-id="95827-116">You've seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="95827-117">`int` 类型表示整数  （零、正整数或负整数）。</span><span class="sxs-lookup"><span data-stu-id="95827-117">The `int` type represents an **integer**, a zero, positive, or negative whole number.</span></span> <span data-ttu-id="95827-118">使用 `+` 符号执行加法运算。</span><span class="sxs-lookup"><span data-stu-id="95827-118">You use the `+` symbol for addition.</span></span> <span data-ttu-id="95827-119">其他常见的整数数学运算包括：</span><span class="sxs-lookup"><span data-stu-id="95827-119">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="95827-120">`-`：减法运算</span><span class="sxs-lookup"><span data-stu-id="95827-120">`-` for subtraction</span></span>
- <span data-ttu-id="95827-121">`*`：乘法运算</span><span class="sxs-lookup"><span data-stu-id="95827-121">`*` for multiplication</span></span>
- <span data-ttu-id="95827-122">`/`：除法运算</span><span class="sxs-lookup"><span data-stu-id="95827-122">`/` for division</span></span>

<span data-ttu-id="95827-123">首先，探索这些不同类型的运算。</span><span class="sxs-lookup"><span data-stu-id="95827-123">Start by exploring those different operations.</span></span> <span data-ttu-id="95827-124">在写入 `c` 值的行之后添加以下行：</span><span class="sxs-lookup"><span data-stu-id="95827-124">Add these lines after the line that writes the value of `c`:</span></span>

```csharp

// subtraction
c = a - b;
Console.WriteLine(c);

// multiplication
c = a * b;
Console.WriteLine(c);

// division
c = a / b;
Console.WriteLine(c);
```

<span data-ttu-id="95827-125">通过在命令窗口中键入 `dotnet run` 运行此代码。</span><span class="sxs-lookup"><span data-stu-id="95827-125">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="95827-126">如果愿意，还可以通过在同一行中编写多个数学运算来进行试验。</span><span class="sxs-lookup"><span data-stu-id="95827-126">You can also experiment by writing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="95827-127">例如，请尝试 `c = a + b - 12 * 17;`。</span><span class="sxs-lookup"><span data-stu-id="95827-127">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="95827-128">允许混合使用变量和常数。</span><span class="sxs-lookup"><span data-stu-id="95827-128">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="95827-129">在探索 C#（或任何编程语言）的过程中，可能会在编写代码时犯错。</span><span class="sxs-lookup"><span data-stu-id="95827-129">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="95827-130">编译器  会发现并报告这些错误。</span><span class="sxs-lookup"><span data-stu-id="95827-130">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="95827-131">如果输出中包含错误消息，请仔细比对示例代码和你的窗口中的代码，看看哪些需要纠正。</span><span class="sxs-lookup"><span data-stu-id="95827-131">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="95827-132">这样做有助于了解 C# 代码结构。</span><span class="sxs-lookup"><span data-stu-id="95827-132">That exercise will help you learn the structure of C# code.</span></span>

<span data-ttu-id="95827-133">你已完成第一步。</span><span class="sxs-lookup"><span data-stu-id="95827-133">You've finished the first step.</span></span> <span data-ttu-id="95827-134">开始进入下一部分前，先将当前代码移到单独的方法中。</span><span class="sxs-lookup"><span data-stu-id="95827-134">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="95827-135">这样一来，可以更轻松地开始处理新示例。</span><span class="sxs-lookup"><span data-stu-id="95827-135">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="95827-136">将 `Main` 方法重命名为 `WorkingWithIntegers`，并编写调用 `WorkingWithIntegers` 的新 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="95827-136">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="95827-137">完成后，代码应如下所示：</span><span class="sxs-lookup"><span data-stu-id="95827-137">When you finish, your code should look like this:</span></span>

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

            // addition
            int c = a + b;
            Console.WriteLine(c);

            // subtraction
            c = a - b;
            Console.WriteLine(c);

            // multiplication
            c = a * b;
            Console.WriteLine(c);

            // division
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

## <a name="explore-order-of-operations"></a><span data-ttu-id="95827-138">探索运算顺序</span><span class="sxs-lookup"><span data-stu-id="95827-138">Explore order of operations</span></span>

<span data-ttu-id="95827-139">注释掉对 `WorkingWithIntegers()` 的调用。</span><span class="sxs-lookup"><span data-stu-id="95827-139">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="95827-140">在本节中，它会在你工作时使输出变得不那么杂乱：</span><span class="sxs-lookup"><span data-stu-id="95827-140">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="95827-141">`//` 在 C# 中启动  注释。</span><span class="sxs-lookup"><span data-stu-id="95827-141">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="95827-142">注释是你想要保留在源代码中但不能作为代码执行的任何文本。</span><span class="sxs-lookup"><span data-stu-id="95827-142">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="95827-143">编译器不会从注释中生成任何可执行代码。</span><span class="sxs-lookup"><span data-stu-id="95827-143">The compiler doesn't generate any executable code from comments.</span></span>

<span data-ttu-id="95827-144">C# 语言使用与数学运算规则一致的规则，定义不同数学运算的优先级。</span><span class="sxs-lookup"><span data-stu-id="95827-144">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="95827-145">乘法和除法的优先级高于加法和减法。</span><span class="sxs-lookup"><span data-stu-id="95827-145">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="95827-146">将以下代码添加到 `Main` 方法，然后执行 `dotnet run` 进行探索：</span><span class="sxs-lookup"><span data-stu-id="95827-146">Explore that by adding the following code to your `Main` method, and executing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="95827-147">输出结果表明，乘法先于加法执行。</span><span class="sxs-lookup"><span data-stu-id="95827-147">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="95827-148">可以在要优先执行的一个或多个运算前后添加括号，从而强制改变运算顺序。</span><span class="sxs-lookup"><span data-stu-id="95827-148">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="95827-149">添加以下行并再次运行：</span><span class="sxs-lookup"><span data-stu-id="95827-149">Add the following lines and run again:</span></span>

```csharp
d = (a + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="95827-150">通过组合多个不同的运算，进一步探索运算顺序。</span><span class="sxs-lookup"><span data-stu-id="95827-150">Explore more by combining many different operations.</span></span> <span data-ttu-id="95827-151">在 `Main` 方法底部添加类似以下行的内容。</span><span class="sxs-lookup"><span data-stu-id="95827-151">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="95827-152">重试 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="95827-152">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="95827-153">可能已注意到，整数有一个非常有趣的行为。</span><span class="sxs-lookup"><span data-stu-id="95827-153">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="95827-154">整数除法始终生成整数结果，即使预期结果有小数或分数部分也是如此。</span><span class="sxs-lookup"><span data-stu-id="95827-154">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="95827-155">如果你没有注意到此行为，请在 `Main` 方法结束时试运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="95827-155">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="95827-156">再次键入 `dotnet run`，看看结果如何。</span><span class="sxs-lookup"><span data-stu-id="95827-156">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="95827-157">继续之前，让我们获取你在本节编写的所有代码并放在新的方法中。</span><span class="sxs-lookup"><span data-stu-id="95827-157">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="95827-158">调用新方法 `OrderPrecedence`。</span><span class="sxs-lookup"><span data-stu-id="95827-158">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="95827-159">应编写如下所示的内容：</span><span class="sxs-lookup"><span data-stu-id="95827-159">You should write something like this:</span></span>

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

            // addition
            int c = a + b;
            Console.WriteLine(c);

            // subtraction
            c = a - b;
            Console.WriteLine(c);

            // multiplication
            c = a * b;
            Console.WriteLine(c);

            // division
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

            d = (a + b) * c;
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

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="95827-160">探索整数运算精度和限值</span><span class="sxs-lookup"><span data-stu-id="95827-160">Explore integer precision and limits</span></span>

<span data-ttu-id="95827-161">在上一个示例中，整数除法截断了结果。</span><span class="sxs-lookup"><span data-stu-id="95827-161">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="95827-162">可以使用取模  运算符（即 `%` 字符）计算余数  。</span><span class="sxs-lookup"><span data-stu-id="95827-162">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="95827-163">在 `Main` 方法中试用以下代码：</span><span class="sxs-lookup"><span data-stu-id="95827-163">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="95827-164">C# 整数类型不同于数学上的整数的另一点是，`int` 类型有最小限值和最大限值。</span><span class="sxs-lookup"><span data-stu-id="95827-164">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="95827-165">将此代码添加到 `Main` 方法，看看这些限制的运行机制：</span><span class="sxs-lookup"><span data-stu-id="95827-165">Add this code to your `Main` method to see those limits:</span></span>

```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="95827-166">如果运算生成的值超过这些限值，则会出现下溢  或溢出  的情况。</span><span class="sxs-lookup"><span data-stu-id="95827-166">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="95827-167">答案似乎是从一个限值覆盖到另一个限值的范围。</span><span class="sxs-lookup"><span data-stu-id="95827-167">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="95827-168">例如，将以下两行添加到 `Main` 方法：</span><span class="sxs-lookup"><span data-stu-id="95827-168">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```

<span data-ttu-id="95827-169">可以看到，答案非常接近最小（负）整数。</span><span class="sxs-lookup"><span data-stu-id="95827-169">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="95827-170">与 `min + 2` 相同。</span><span class="sxs-lookup"><span data-stu-id="95827-170">It's the same as `min + 2`.</span></span>
<span data-ttu-id="95827-171">加法运算会让整数溢出  允许的值。</span><span class="sxs-lookup"><span data-stu-id="95827-171">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="95827-172">答案是一个非常大的负数，因为溢出从最大整数值覆盖回最小整数值。</span><span class="sxs-lookup"><span data-stu-id="95827-172">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="95827-173">如果 `int` 类型无法满足需求，还会用到限值和精度不同的其他数字类型。</span><span class="sxs-lookup"><span data-stu-id="95827-173">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="95827-174">接下来，让我们来研究一下其他类型。</span><span class="sxs-lookup"><span data-stu-id="95827-174">Let's explore those other types next.</span></span>

<span data-ttu-id="95827-175">让我们再一次将你在本节编写的代码移到一个单独的方法中。</span><span class="sxs-lookup"><span data-stu-id="95827-175">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="95827-176">将其命名为 `TestLimits`。</span><span class="sxs-lookup"><span data-stu-id="95827-176">Name it `TestLimits`.</span></span>

## <a name="work-with-the-double-type"></a><span data-ttu-id="95827-177">使用双精度类型</span><span class="sxs-lookup"><span data-stu-id="95827-177">Work with the double type</span></span>

<span data-ttu-id="95827-178">`double` 数字类型表示双精度浮点数。</span><span class="sxs-lookup"><span data-stu-id="95827-178">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="95827-179">这些词可能是第一次听说。</span><span class="sxs-lookup"><span data-stu-id="95827-179">Those terms may be new to you.</span></span> <span data-ttu-id="95827-180">浮点  数可用于表示数量级可能非常大或非常小的非整数。</span><span class="sxs-lookup"><span data-stu-id="95827-180">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="95827-181">双精度  是一个相对术语，描述用于存储值的二进制数位数。</span><span class="sxs-lookup"><span data-stu-id="95827-181">**Double-precision** is a relative term that describes the number of binary digits used to store the value.</span></span> <span data-ttu-id="95827-182">双精度  数字的二进制数位数是单精度  的两倍。</span><span class="sxs-lookup"><span data-stu-id="95827-182">**Double precision** numbers have twice the number of binary digits as **single-precision**.</span></span> <span data-ttu-id="95827-183">在新式计算机上，使用双精度数字比使用单精度数字更为常见。</span><span class="sxs-lookup"><span data-stu-id="95827-183">On modern computers, it's more common to use double precision than single precision numbers.</span></span> <span data-ttu-id="95827-184">单精度  数字是使用 `float` 关键字声明的。</span><span class="sxs-lookup"><span data-stu-id="95827-184">**Single precision** numbers are declared using the `float` keyword.</span></span>
<span data-ttu-id="95827-185">接下来，将探索双精度类型。</span><span class="sxs-lookup"><span data-stu-id="95827-185">Let's explore.</span></span> <span data-ttu-id="95827-186">添加以下代码并查看结果：</span><span class="sxs-lookup"><span data-stu-id="95827-186">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="95827-187">可以看到，答案商包含小数部分。</span><span class="sxs-lookup"><span data-stu-id="95827-187">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="95827-188">试试对双精度类型使用更复杂一点的表达式：</span><span class="sxs-lookup"><span data-stu-id="95827-188">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="95827-189">双精度值的范围远大于整数值。</span><span class="sxs-lookup"><span data-stu-id="95827-189">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="95827-190">在当前已编写的代码下方试运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="95827-190">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="95827-191">打印出来的这些值用科学记数法表示。</span><span class="sxs-lookup"><span data-stu-id="95827-191">These values are printed out in scientific notation.</span></span> <span data-ttu-id="95827-192">`E` 左侧为有效数字。</span><span class="sxs-lookup"><span data-stu-id="95827-192">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="95827-193">右侧为是 10 的 n 次幂。</span><span class="sxs-lookup"><span data-stu-id="95827-193">The number to the right is the exponent, as a power of 10.</span></span>

<span data-ttu-id="95827-194">与数学上的十进制数字一样，C# 中的双精度值可能会有四舍五入误差。</span><span class="sxs-lookup"><span data-stu-id="95827-194">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="95827-195">试运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="95827-195">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="95827-196">众所周知，`0.3` 循环小数与 `1/3` 并不完全相等。</span><span class="sxs-lookup"><span data-stu-id="95827-196">You know that `0.3` repeating isn't exactly the same as `1/3`.</span></span>

<span data-ttu-id="95827-197">***挑战***</span><span class="sxs-lookup"><span data-stu-id="95827-197">***Challenge***</span></span>

<span data-ttu-id="95827-198">尝试使用 `double` 类型执行其他的大小数、乘法和除法运算。</span><span class="sxs-lookup"><span data-stu-id="95827-198">Try other calculations with large numbers, small numbers, multiplication, and division using the `double` type.</span></span> <span data-ttu-id="95827-199">尝试执行更复杂的运算。</span><span class="sxs-lookup"><span data-stu-id="95827-199">Try more complicated calculations.</span></span>

<span data-ttu-id="95827-200">花了一些时间应对挑战之后，获取已编写的代码并放在一个新方法中。</span><span class="sxs-lookup"><span data-stu-id="95827-200">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="95827-201">将新方法命名为 `WorkWithDoubles`。</span><span class="sxs-lookup"><span data-stu-id="95827-201">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-decimal-types"></a><span data-ttu-id="95827-202">使用十进制类型</span><span class="sxs-lookup"><span data-stu-id="95827-202">Work with decimal types</span></span>

<span data-ttu-id="95827-203">大家已学习了 C# 中的基本数字类型，即整数和双精度。</span><span class="sxs-lookup"><span data-stu-id="95827-203">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="95827-204">还需要学习另一种类型，即 `decimal` 类型。</span><span class="sxs-lookup"><span data-stu-id="95827-204">There's one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="95827-205">`decimal` 类型的范围较小，但精度高于 `double`。</span><span class="sxs-lookup"><span data-stu-id="95827-205">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="95827-206">让我们来实际操作一下：</span><span class="sxs-lookup"><span data-stu-id="95827-206">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="95827-207">可以看到，范围小于 `double` 类型。</span><span class="sxs-lookup"><span data-stu-id="95827-207">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="95827-208">通过试运行以下代码，可以看到十进制类型的精度更高：</span><span class="sxs-lookup"><span data-stu-id="95827-208">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="95827-209">数字中的 `M` 后缀指明了常数应如何使用 `decimal` 类型。</span><span class="sxs-lookup"><span data-stu-id="95827-209">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span> <span data-ttu-id="95827-210">否则，编译器假定为 `double` 类型。</span><span class="sxs-lookup"><span data-stu-id="95827-210">Otherwise, the compiler assumes the `double` type.</span></span>

> [!NOTE]
> <span data-ttu-id="95827-211">字母 `M` 被选为 `double` 与 `decimal` 关键字之间最明显不同的字母。</span><span class="sxs-lookup"><span data-stu-id="95827-211">The letter `M` was chosen as the most visually distinct letter between the `double` and `decimal` keywords.</span></span>

<span data-ttu-id="95827-212">可以看到，使用十进制类型执行数学运算时，十进制小数点右侧的数字更多。</span><span class="sxs-lookup"><span data-stu-id="95827-212">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span>

<span data-ttu-id="95827-213">***挑战***</span><span class="sxs-lookup"><span data-stu-id="95827-213">***Challenge***</span></span>

<span data-ttu-id="95827-214">至此，大家已了解不同的数字类型。请编写代码来计算圆面积（其中，半径为 2.50 厘米）。</span><span class="sxs-lookup"><span data-stu-id="95827-214">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 centimeters.</span></span> <span data-ttu-id="95827-215">请注意，圆面积是用半径的平方乘以 PI 进行计算。</span><span class="sxs-lookup"><span data-stu-id="95827-215">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="95827-216">小提示：.NET 包含 PI 常数 <xref:System.Math.PI?displayProperty=nameWithType>，可用于相应的值计算。</span><span class="sxs-lookup"><span data-stu-id="95827-216">One hint: .NET contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> <span data-ttu-id="95827-217">与 `System.Math` 命名空间中声明的所有常量一样，<xref:System.Math.PI?displayProperty=nameWithType> 也是 `double` 值。</span><span class="sxs-lookup"><span data-stu-id="95827-217"><xref:System.Math.PI?displayProperty=nameWithType>, like all constants declared in the `System.Math` namespace, is a `double` value.</span></span> <span data-ttu-id="95827-218">因此，应使用 `double`（而不是 `decimal`）值来完成这项挑战。</span><span class="sxs-lookup"><span data-stu-id="95827-218">For that reason, you should use `double` instead of `decimal` values for this challenge.</span></span>

<span data-ttu-id="95827-219">你应获得 19 和 20 之间的答案。</span><span class="sxs-lookup"><span data-stu-id="95827-219">You should get an answer between 19 and 20.</span></span>
<span data-ttu-id="95827-220">要查看你的答案，可以[查看 GitHub 上的完成示例代码](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106)。</span><span class="sxs-lookup"><span data-stu-id="95827-220">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106).</span></span>

<span data-ttu-id="95827-221">如果需要，可以试用一些其他公式。</span><span class="sxs-lookup"><span data-stu-id="95827-221">Try some other formulas if you'd like.</span></span>

<span data-ttu-id="95827-222">已完成“C# 中的数字”快速入门教程。</span><span class="sxs-lookup"><span data-stu-id="95827-222">You've completed the "Numbers in C#" quickstart.</span></span> <span data-ttu-id="95827-223">可以在自己的开发环境中继续学习[分支和循环](branches-and-loops-local.md)快速入门教程。</span><span class="sxs-lookup"><span data-stu-id="95827-223">You can continue with the [Branches and loops](branches-and-loops-local.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="95827-224">若要详细了解 C# 中的数字，可以参阅下面的文章：</span><span class="sxs-lookup"><span data-stu-id="95827-224">You can learn more about numbers in C# in the following articles:</span></span>

- [<span data-ttu-id="95827-225">整型数值类型</span><span class="sxs-lookup"><span data-stu-id="95827-225">Integral numeric types</span></span>](../../language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="95827-226">浮点型数值类型</span><span class="sxs-lookup"><span data-stu-id="95827-226">Floating-point numeric types</span></span>](../../language-reference/builtin-types/floating-point-numeric-types.md)
- [<span data-ttu-id="95827-227">内置数值转换</span><span class="sxs-lookup"><span data-stu-id="95827-227">Built-in numeric conversions</span></span>](../../language-reference/builtin-types/numeric-conversions.md)
