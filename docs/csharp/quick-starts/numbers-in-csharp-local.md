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
# <a name="numbers-in-c-quick-start"></a><span data-ttu-id="01c9e-103">C# 快速入门中的数字</span><span class="sxs-lookup"><span data-stu-id="01c9e-103">Numbers in C# quick start</span></span> #

<span data-ttu-id="01c9e-104">本快速入门介绍了有关在 C# 中的数字类型以交互方式。</span><span class="sxs-lookup"><span data-stu-id="01c9e-104">This quick start teaches you about the number types in C# interactively.</span></span> <span data-ttu-id="01c9e-105">你将在其中编写少量的代码，然后将编译并运行该代码。</span><span class="sxs-lookup"><span data-stu-id="01c9e-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="01c9e-106">快速入门包含一系列的浏览数字和 C# 中的数学运算的课程。</span><span class="sxs-lookup"><span data-stu-id="01c9e-106">The quick start contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="01c9e-107">这些课程介绍了 C# 语言的基础知识。</span><span class="sxs-lookup"><span data-stu-id="01c9e-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="01c9e-108">本快速入门希望有一台计算机可用于开发。</span><span class="sxs-lookup"><span data-stu-id="01c9e-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="01c9e-109">.NET 主题[开始在 10 分钟后](https://www.microsoft.com/net/core)已设置你在 Mac、 PC 或 Linux 上的本地开发环境的说明。</span><span class="sxs-lookup"><span data-stu-id="01c9e-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="01c9e-110">探索整数数学运算</span><span class="sxs-lookup"><span data-stu-id="01c9e-110">Explore integer math</span></span>

<span data-ttu-id="01c9e-111">创建一个名为目录**数字快速入门**。</span><span class="sxs-lookup"><span data-stu-id="01c9e-111">Create a directory named **numbers-quickstart**.</span></span> <span data-ttu-id="01c9e-112">将新建的目录设为当前目录，并运行 `dotnet new console -n NumbersInCSharp -o .`。</span><span class="sxs-lookup"><span data-stu-id="01c9e-112">Make that the current directory and run `dotnet new console -n NumbersInCSharp -o .`.</span></span>

<span data-ttu-id="01c9e-113">打开**Program.cs**行替换你喜爱的编辑器中`Console.Writeline("Hello World!");`替换为以下：</span><span class="sxs-lookup"><span data-stu-id="01c9e-113">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="01c9e-114">通过键入运行此代码`dotnet run`命令窗口中。</span><span class="sxs-lookup"><span data-stu-id="01c9e-114">Run this code by typing `dotnet run` in your command window.</span></span> 

<span data-ttu-id="01c9e-115">刚刚看到的是一种基本的整数数学运算。</span><span class="sxs-lookup"><span data-stu-id="01c9e-115">You've just seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="01c9e-116">`int` 类型表示整数（正整数或负整数）。</span><span class="sxs-lookup"><span data-stu-id="01c9e-116">The `int` type represents an **integer**, a positive or negative whole number.</span></span> <span data-ttu-id="01c9e-117">使用 `+` 符号执行加法运算。</span><span class="sxs-lookup"><span data-stu-id="01c9e-117">You use the `+` symbol for addition.</span></span> <span data-ttu-id="01c9e-118">其他常见的整数数学运算包括：</span><span class="sxs-lookup"><span data-stu-id="01c9e-118">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="01c9e-119">`-`：减法运算</span><span class="sxs-lookup"><span data-stu-id="01c9e-119">`-` for subtraction</span></span>
- <span data-ttu-id="01c9e-120">`*`：乘法运算</span><span class="sxs-lookup"><span data-stu-id="01c9e-120">`*` for multiplication</span></span>
- <span data-ttu-id="01c9e-121">`/`：除法运算</span><span class="sxs-lookup"><span data-stu-id="01c9e-121">`/` for division</span></span>

<span data-ttu-id="01c9e-122">首先，探索这些不同类型的运算。</span><span class="sxs-lookup"><span data-stu-id="01c9e-122">Start by exploring those different operations.</span></span> <span data-ttu-id="01c9e-123">值写入行后添加以下行`c`:</span><span class="sxs-lookup"><span data-stu-id="01c9e-123">Add these lines after the line that writes the value of `c`:</span></span>

```csharp
c = a - b;
Console.WriteLine(c);
c = a * b;
Console.WriteLine(c);
c = a / b;
Console.WriteLine(c);
```

<span data-ttu-id="01c9e-124">通过键入运行此代码`dotnet run`命令窗口中。</span><span class="sxs-lookup"><span data-stu-id="01c9e-124">Run this code by typing `dotnet run` in your command window.</span></span> 
    
<span data-ttu-id="01c9e-125">如果愿意，也可以尝试在同一行中执行多个数学运算。</span><span class="sxs-lookup"><span data-stu-id="01c9e-125">You can also experiment by performing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="01c9e-126">请尝试`c = a + b - 12 * 17;`例如。</span><span class="sxs-lookup"><span data-stu-id="01c9e-126">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="01c9e-127">允许混合使用变量和常量的数字。</span><span class="sxs-lookup"><span data-stu-id="01c9e-127">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="01c9e-128">在探索 C#（或任何编程语言）的过程中，可能会在编写代码时犯错。</span><span class="sxs-lookup"><span data-stu-id="01c9e-128">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="01c9e-129">编译器会发现并报告这些错误。</span><span class="sxs-lookup"><span data-stu-id="01c9e-129">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="01c9e-130">当输出中包含错误消息时，仔细查看此代码示例和你的窗口以查看要修复的内容中的代码。</span><span class="sxs-lookup"><span data-stu-id="01c9e-130">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="01c9e-131">这样做有助于了解 C# 代码结构。</span><span class="sxs-lookup"><span data-stu-id="01c9e-131">That exercise will help you learn the structure of C# code.</span></span>     

<span data-ttu-id="01c9e-132">你已完成的第一步。</span><span class="sxs-lookup"><span data-stu-id="01c9e-132">You've finished the first step.</span></span> <span data-ttu-id="01c9e-133">开始进入下一部分前，先将当前代码移到单独的方法中。</span><span class="sxs-lookup"><span data-stu-id="01c9e-133">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="01c9e-134">这样一来，可以更轻松地开始处理新示例。</span><span class="sxs-lookup"><span data-stu-id="01c9e-134">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="01c9e-135">将 `Main` 方法重命名为 `WorkingWithIntegers`，并编写调用 `WorkingWithIntegers` 的新 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="01c9e-135">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="01c9e-136">完成后，代码应如下所示：</span><span class="sxs-lookup"><span data-stu-id="01c9e-136">When you have finished, your code should look like this:</span></span>

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

## <a name="explore-order-of-operations"></a><span data-ttu-id="01c9e-137">探索运算顺序</span><span class="sxs-lookup"><span data-stu-id="01c9e-137">Explore order of operations</span></span>

<span data-ttu-id="01c9e-138">注释掉对的调用`WorkingWithIntegers()`。</span><span class="sxs-lookup"><span data-stu-id="01c9e-138">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="01c9e-139">它将使整洁的当您在本部分工作的输出：</span><span class="sxs-lookup"><span data-stu-id="01c9e-139">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="01c9e-140">`//`启动**注释**C# 中。</span><span class="sxs-lookup"><span data-stu-id="01c9e-140">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="01c9e-141">注释是你想要保留在源代码中，但不是能作为代码执行的任何文本。</span><span class="sxs-lookup"><span data-stu-id="01c9e-141">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="01c9e-142">从注释，编译器不生成任何可执行代码。</span><span class="sxs-lookup"><span data-stu-id="01c9e-142">The compiler does not generate any executable code from comments.</span></span>

<span data-ttu-id="01c9e-143">C# 语言使用与数学运算规则一致的规则，定义不同数学运算的优先级。</span><span class="sxs-lookup"><span data-stu-id="01c9e-143">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="01c9e-144">乘法和除法的优先级高于加法和减法。</span><span class="sxs-lookup"><span data-stu-id="01c9e-144">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="01c9e-145">通过添加以下代码中浏览，你`Main`方法，并 execuing `dotnet run`:</span><span class="sxs-lookup"><span data-stu-id="01c9e-145">Explore that by adding the following code to your `Main` method, and execuing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="01c9e-146">输出结果表明，乘法先于加法执行。</span><span class="sxs-lookup"><span data-stu-id="01c9e-146">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="01c9e-147">你可以通过添加圆括号操作强制操作的不同的顺序或第一次执行所需的操作。</span><span class="sxs-lookup"><span data-stu-id="01c9e-147">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="01c9e-148">添加以下行，重新运行：</span><span class="sxs-lookup"><span data-stu-id="01c9e-148">Add the following lines and run again:</span></span>

```csharp
d = (a  + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="01c9e-149">通过组合多个不同的运算，进一步探索运算顺序。</span><span class="sxs-lookup"><span data-stu-id="01c9e-149">Explore more by combining many different operations.</span></span> <span data-ttu-id="01c9e-150">在底部添加以下行类似你`Main`方法。</span><span class="sxs-lookup"><span data-stu-id="01c9e-150">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="01c9e-151">请尝试`dotnet run`试。</span><span class="sxs-lookup"><span data-stu-id="01c9e-151">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="01c9e-152">可能已注意到，整数有一个非常有趣的行为。</span><span class="sxs-lookup"><span data-stu-id="01c9e-152">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="01c9e-153">整数除法始终生成整数结果，即使你预期的结果包含小数或分数部分。</span><span class="sxs-lookup"><span data-stu-id="01c9e-153">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="01c9e-154">如果尚未看到此行为，请尝试下面的代码的末尾你`Main`方法：</span><span class="sxs-lookup"><span data-stu-id="01c9e-154">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="01c9e-155">类型`dotnet run`试以查看结果。</span><span class="sxs-lookup"><span data-stu-id="01c9e-155">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="01c9e-156">继续之前，让我们需要你编写在本部分并将其放入新的方法的所有代码。</span><span class="sxs-lookup"><span data-stu-id="01c9e-156">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="01c9e-157">可以调用该新方法`OrderPrecedence`。</span><span class="sxs-lookup"><span data-stu-id="01c9e-157">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="01c9e-158">你应会得到类似如下内容：</span><span class="sxs-lookup"><span data-stu-id="01c9e-158">You should end up with something like this:</span></span>

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

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="01c9e-159">探索整数运算精度和限值</span><span class="sxs-lookup"><span data-stu-id="01c9e-159">Explore integer precision and limits</span></span>
<span data-ttu-id="01c9e-160">在上一个示例中，整数除法截断了结果。</span><span class="sxs-lookup"><span data-stu-id="01c9e-160">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="01c9e-161">你可以获取**余数**使用**取模**运算符，`%`字符。</span><span class="sxs-lookup"><span data-stu-id="01c9e-161">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="01c9e-162">尝试使用以下代码中的你`Main`方法：</span><span class="sxs-lookup"><span data-stu-id="01c9e-162">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a  + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="01c9e-163">C# 整数类型不同于数学上的整数的另一点是，`int` 类型有最小限值和最大限值。</span><span class="sxs-lookup"><span data-stu-id="01c9e-163">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="01c9e-164">此将代码添加到你`Main`方法若要查看这些限制：</span><span class="sxs-lookup"><span data-stu-id="01c9e-164">Add this code to your `Main` method to see those limits:</span></span>
    
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="01c9e-165">如果运算生成的值超过这些限值，则会出现下溢或溢出的情况。</span><span class="sxs-lookup"><span data-stu-id="01c9e-165">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="01c9e-166">答案似乎是从一个限值覆盖到另一个限值的范围。</span><span class="sxs-lookup"><span data-stu-id="01c9e-166">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="01c9e-167">添加到这两行你`Main`方法，以便查看示例：</span><span class="sxs-lookup"><span data-stu-id="01c9e-167">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```
    
<span data-ttu-id="01c9e-168">可以看到，答案非常接近最小（负）整数。</span><span class="sxs-lookup"><span data-stu-id="01c9e-168">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="01c9e-169">与 `min + 2` 相同。</span><span class="sxs-lookup"><span data-stu-id="01c9e-169">It's the same as `min + 2`.</span></span> <span data-ttu-id="01c9e-170">加法运算会让整数溢出允许的值。</span><span class="sxs-lookup"><span data-stu-id="01c9e-170">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="01c9e-171">答案是一个非常大的负数，因为溢出从最大整数值覆盖回最小整数值。</span><span class="sxs-lookup"><span data-stu-id="01c9e-171">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="01c9e-172">如果 `int` 类型无法满足需求，还会用到限值和精度不同的其他数字类型。</span><span class="sxs-lookup"><span data-stu-id="01c9e-172">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="01c9e-173">接下来，将探索这些类型。</span><span class="sxs-lookup"><span data-stu-id="01c9e-173">Let's explore those next.</span></span>

<span data-ttu-id="01c9e-174">同样，让我们将移到单独的方法的此部分中编写的代码。</span><span class="sxs-lookup"><span data-stu-id="01c9e-174">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="01c9e-175">将其命名为 `TestLimits`。</span><span class="sxs-lookup"><span data-stu-id="01c9e-175">Name it `TestLimits`.</span></span> 

## <a name="work-with-the-double-type"></a><span data-ttu-id="01c9e-176">使用双精度类型</span><span class="sxs-lookup"><span data-stu-id="01c9e-176">Work with the double type</span></span>

<span data-ttu-id="01c9e-177">`double` 数字类型表示双精度浮点数。</span><span class="sxs-lookup"><span data-stu-id="01c9e-177">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="01c9e-178">这些词可能是第一次听说。</span><span class="sxs-lookup"><span data-stu-id="01c9e-178">Those terms may be new to you.</span></span> <span data-ttu-id="01c9e-179">A**浮点数**数可用于表示可能会非常大或小在数量级上的非整型数字。</span><span class="sxs-lookup"><span data-stu-id="01c9e-179">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="01c9e-180">双精度意味着存储这些数字时使用的精度高于单精度。</span><span class="sxs-lookup"><span data-stu-id="01c9e-180">**Double-precision** means that these numbers are stored using greater precision than **single-precision**.</span></span> <span data-ttu-id="01c9e-181">在新式计算机上，使用双精度数字比使用单精度数字更为常见。</span><span class="sxs-lookup"><span data-stu-id="01c9e-181">On modern computers, it is more common to use double precision than single precision numbers.</span></span>
<span data-ttu-id="01c9e-182">接下来，将探索双精度类型。</span><span class="sxs-lookup"><span data-stu-id="01c9e-182">Let's explore.</span></span> <span data-ttu-id="01c9e-183">添加以下代码并查看结果：</span><span class="sxs-lookup"><span data-stu-id="01c9e-183">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a  + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="01c9e-184">可以看到，答案商包含小数部分。</span><span class="sxs-lookup"><span data-stu-id="01c9e-184">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="01c9e-185">试试对双精度类型使用更复杂一点的表达式：</span><span class="sxs-lookup"><span data-stu-id="01c9e-185">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="01c9e-186">双精度值的范围远大于整数值。</span><span class="sxs-lookup"><span data-stu-id="01c9e-186">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="01c9e-187">请尝试你到目前为止已编写下面的代码：</span><span class="sxs-lookup"><span data-stu-id="01c9e-187">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="01c9e-188">这些值输出科学记数法。</span><span class="sxs-lookup"><span data-stu-id="01c9e-188">These values are printed out in scientific notation.</span></span> <span data-ttu-id="01c9e-189">左侧的数字`E`是有效位数。</span><span class="sxs-lookup"><span data-stu-id="01c9e-189">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="01c9e-190">右侧为是 10 的 n 次幂。</span><span class="sxs-lookup"><span data-stu-id="01c9e-190">The number to the right is the exponent, as a power of 10.</span></span> 

<span data-ttu-id="01c9e-191">与数学上的十进制数字一样，C# 中的双精度值可能会有四舍五入误差。</span><span class="sxs-lookup"><span data-stu-id="01c9e-191">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="01c9e-192">试运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="01c9e-192">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="01c9e-193">众所周知，`0.3` 循环小数与 `1/3` 并不完全相等。</span><span class="sxs-lookup"><span data-stu-id="01c9e-193">You know that `0.3` repeating is not exactly the same as `1/3`.</span></span>

<span data-ttu-id="01c9e-194">***挑战***</span><span class="sxs-lookup"><span data-stu-id="01c9e-194">***Challenge***</span></span>

<span data-ttu-id="01c9e-195">尝试使用 `double` 类型执行其他的大小数、乘法和除法运算。</span><span class="sxs-lookup"><span data-stu-id="01c9e-195">Try other calculations with large numbers, small numbers, multiplication and division using the `double` type.</span></span>  <span data-ttu-id="01c9e-196">尝试执行更复杂的运算。</span><span class="sxs-lookup"><span data-stu-id="01c9e-196">Try more complicated calculations.</span></span>

<span data-ttu-id="01c9e-197">已花一些时间来使用质询后，需要你已经编写并将其放在一个新方法的代码。</span><span class="sxs-lookup"><span data-stu-id="01c9e-197">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="01c9e-198">将该新方法`WorkWithDoubles`。</span><span class="sxs-lookup"><span data-stu-id="01c9e-198">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-fixed-point-types"></a><span data-ttu-id="01c9e-199">使用固定点类型</span><span class="sxs-lookup"><span data-stu-id="01c9e-199">Work with fixed point types</span></span>

<span data-ttu-id="01c9e-200">大家已学习了 C# 中的基本数字类型，即整数和双精度。</span><span class="sxs-lookup"><span data-stu-id="01c9e-200">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="01c9e-201">下面将介绍另一种需要了解的类型，即 `decimal` 类型。</span><span class="sxs-lookup"><span data-stu-id="01c9e-201">There is one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="01c9e-202">`decimal`类型具有更小的范围，但更高的精度比`double`。</span><span class="sxs-lookup"><span data-stu-id="01c9e-202">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="01c9e-203">“固定点”一词意味着，十进制小数点（或二进制小数点）不会移动。</span><span class="sxs-lookup"><span data-stu-id="01c9e-203">The term **fixed point** means that the decimal point (or binary point) doesn't move.</span></span> <span data-ttu-id="01c9e-204">让我们来实际操作一下：</span><span class="sxs-lookup"><span data-stu-id="01c9e-204">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="01c9e-205">可以看到，范围小于 `double` 类型。</span><span class="sxs-lookup"><span data-stu-id="01c9e-205">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="01c9e-206">通过试运行以下代码，可以看到十进制类型的精度更高：</span><span class="sxs-lookup"><span data-stu-id="01c9e-206">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="01c9e-207">数字中的 `M` 后缀指明了常数应如何使用 `decimal` 类型。</span><span class="sxs-lookup"><span data-stu-id="01c9e-207">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span>

<span data-ttu-id="01c9e-208">可以看到，使用十进制类型执行数学运算时，十进制小数点右侧的数字更多。</span><span class="sxs-lookup"><span data-stu-id="01c9e-208">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span> 

<span data-ttu-id="01c9e-209">***挑战***</span><span class="sxs-lookup"><span data-stu-id="01c9e-209">***Challenge***</span></span>

<span data-ttu-id="01c9e-210">至此，大家已了解不同的数字类型。请编写代码来计算圆面积（其中，半径为 2.50 英寸）。</span><span class="sxs-lookup"><span data-stu-id="01c9e-210">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 inches.</span></span> <span data-ttu-id="01c9e-211">请注意，圆面积是用半径的平方乘以 PI 进行计算。</span><span class="sxs-lookup"><span data-stu-id="01c9e-211">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="01c9e-212">一个提示： C# 包含常量 PI <xref:System.Math.PI?displayProperty=nameWithType> ，你可以使用为该值。</span><span class="sxs-lookup"><span data-stu-id="01c9e-212">One hint: C# contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> 

<span data-ttu-id="01c9e-213">你可以检查您的答案通过[在 GitHub 上查看已完成的示例代码](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)</span><span class="sxs-lookup"><span data-stu-id="01c9e-213">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)</span></span>

<span data-ttu-id="01c9e-214">如果你想要，尝试一些其他公式。</span><span class="sxs-lookup"><span data-stu-id="01c9e-214">Try some other formulas if you'd like.</span></span> 

<span data-ttu-id="01c9e-215">您已完成"数字中 C#"快速入门。</span><span class="sxs-lookup"><span data-stu-id="01c9e-215">You've completed the "Numbers in C#" quick start.</span></span> <span data-ttu-id="01c9e-216">您可以使用继续[分支和循环](branches-and-loops-local.md)开发环境中的快速入门。</span><span class="sxs-lookup"><span data-stu-id="01c9e-216">You can continue with the [Branches and loops](branches-and-loops-local.md) quick start in your own development environment.</span></span>

<span data-ttu-id="01c9e-217">可以参阅下面的主题，详细了解 C# 中的数字：</span><span class="sxs-lookup"><span data-stu-id="01c9e-217">You can learn more about numbers in C# in the following topics:</span></span>

<span data-ttu-id="01c9e-218">[整型类型表](../language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="01c9e-218">[Integral Types Table](../language-reference/keywords/integral-types-table.md) </span></span>  
<span data-ttu-id="01c9e-219">[浮点型表](../language-reference/keywords/floating-point-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="01c9e-219">[Floating-Point Types Table](../language-reference/keywords/floating-point-types-table.md) </span></span>  
<span data-ttu-id="01c9e-220">[内置类型表](../language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="01c9e-220">[Built-In Types Table](../language-reference/keywords/built-in-types-table.md) </span></span>  
<span data-ttu-id="01c9e-221">[隐式数值转换表](../language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="01c9e-221">[Implicit Numeric Conversions Table](../language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
[<span data-ttu-id="01c9e-222">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="01c9e-222">Explicit Numeric Conversions Table</span></span>](../language-reference/keywords/explicit-numeric-conversions-table.md)

