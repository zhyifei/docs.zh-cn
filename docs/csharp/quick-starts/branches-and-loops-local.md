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
# <a name="branches-and-loops"></a><span data-ttu-id="74e1a-103">分支和循环</span><span class="sxs-lookup"><span data-stu-id="74e1a-103">Branches and loops</span></span>

<span data-ttu-id="74e1a-104">本快速入门介绍了如何编写代码来检查变量并更改基于这些变量的执行路径。</span><span class="sxs-lookup"><span data-stu-id="74e1a-104">This quick start teaches you how to write code that examines variables and changes the execution path based on those variables.</span></span> <span data-ttu-id="74e1a-105">编写 C# 代码，并请参阅编译和运行它的结果。</span><span class="sxs-lookup"><span data-stu-id="74e1a-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="74e1a-106">快速入门包含一系列的浏览分支和循环构造在 C# 中的课程。</span><span class="sxs-lookup"><span data-stu-id="74e1a-106">The quick start contains a series of lessons that explore branching and looping constructs in C#.</span></span> <span data-ttu-id="74e1a-107">这些课程介绍了 C# 语言的基础知识。</span><span class="sxs-lookup"><span data-stu-id="74e1a-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="74e1a-108">本快速入门希望有一台计算机可用于开发。</span><span class="sxs-lookup"><span data-stu-id="74e1a-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="74e1a-109">.NET 主题[开始在 10 分钟后](https://www.microsoft.com/net/core)已设置你在 Mac、 PC 或 Linux 上的本地开发环境的说明。</span><span class="sxs-lookup"><span data-stu-id="74e1a-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

## <a name="make-decisions-using-the-if-statement"></a><span data-ttu-id="74e1a-110">使用做出决策`if`语句</span><span class="sxs-lookup"><span data-stu-id="74e1a-110">Make decisions using the `if` statement</span></span>

<span data-ttu-id="74e1a-111">创建一个名为目录**分支快速入门**。</span><span class="sxs-lookup"><span data-stu-id="74e1a-111">Create a directory named **branches-quickstart**.</span></span> <span data-ttu-id="74e1a-112">将新建的目录设为当前目录，并运行 `dotnet new console -n BranchesAndLoops -o .`。</span><span class="sxs-lookup"><span data-stu-id="74e1a-112">Make that the current directory and run `dotnet new console -n BranchesAndLoops -o .`.</span></span> <span data-ttu-id="74e1a-113">此命令在当前目录中创建一个新的.NET Core 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="74e1a-113">This command creates a new .NET Core console application in the current directory.</span></span> 

<span data-ttu-id="74e1a-114">打开**Program.cs**行替换你喜爱的编辑器中`Console.Writeline("Hello World!");`替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="74e1a-114">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following code:</span></span>

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

<span data-ttu-id="74e1a-115">请尝试此代码，通过键入`dotnet run`在控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="74e1a-115">Try this code by typing `dotnet run` in the your console window.</span></span> <span data-ttu-id="74e1a-116">你应看到消息"答案大于 10。"</span><span class="sxs-lookup"><span data-stu-id="74e1a-116">You should see the message "The answer is greater than 10."</span></span> <span data-ttu-id="74e1a-117">打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="74e1a-117">printed to your console.</span></span>

<span data-ttu-id="74e1a-118">修改 `b` 的声明，让总和小于 10：</span><span class="sxs-lookup"><span data-stu-id="74e1a-118">Modify the declaration of `b` so that the sum is less than 10:</span></span> 

```csharp
int b = 3;
```

<span data-ttu-id="74e1a-119">类型`dotnet run`试。</span><span class="sxs-lookup"><span data-stu-id="74e1a-119">Type `dotnet run` again.</span></span> <span data-ttu-id="74e1a-120">由于答案小于 10，因此什么也没有打印出来。</span><span class="sxs-lookup"><span data-stu-id="74e1a-120">Because the answer is less than 10, nothing is printed.</span></span> <span data-ttu-id="74e1a-121">要测试的条件为 false。</span><span class="sxs-lookup"><span data-stu-id="74e1a-121">The **condition** you're testing is false.</span></span> <span data-ttu-id="74e1a-122">没有任何可供执行的代码，因为仅为 `if` 语句编写了一个可能分支，即 true 分支。</span><span class="sxs-lookup"><span data-stu-id="74e1a-122">You don't have any code to execute because you've only written one of the possible branches for an `if` statement: the true branch.</span></span>

> [!TIP]
> <span data-ttu-id="74e1a-123">在探索 C#（或任何编程语言）的过程中，可能会在编写代码时犯错。</span><span class="sxs-lookup"><span data-stu-id="74e1a-123">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="74e1a-124">编译器将找出并报告错误。</span><span class="sxs-lookup"><span data-stu-id="74e1a-124">The compiler will find and report the errors.</span></span> <span data-ttu-id="74e1a-125">仔细查看的错误输出，并生成错误的代码。</span><span class="sxs-lookup"><span data-stu-id="74e1a-125">Look closely the the error output and the code that generated the error.</span></span> <span data-ttu-id="74e1a-126">Compler 错误通常可帮助你找出问题。</span><span class="sxs-lookup"><span data-stu-id="74e1a-126">The compler error can usually help you find the problem.</span></span> 

<span data-ttu-id="74e1a-127">此第一个示例显示的电源`if`和布尔值类型。</span><span class="sxs-lookup"><span data-stu-id="74e1a-127">This first sample shows the power of `if` and Boolean types.</span></span> <span data-ttu-id="74e1a-128">A*布尔*是一个变量，可以具有两个值之一：`true`或`false`。</span><span class="sxs-lookup"><span data-stu-id="74e1a-128">A *Boolean* is a variable that can have one of two values: `true` or `false`.</span></span> <span data-ttu-id="74e1a-129">C# 定义一种特殊类型，`bool`布尔变量。</span><span class="sxs-lookup"><span data-stu-id="74e1a-129">C# defines a special type, `bool` for Boolean variables.</span></span> <span data-ttu-id="74e1a-130">`if` 语句检查 `bool` 的值。</span><span class="sxs-lookup"><span data-stu-id="74e1a-130">The `if` statement checks the value of a `bool`.</span></span> <span data-ttu-id="74e1a-131">如果值为 `true`，执行 `if` 后面的语句。</span><span class="sxs-lookup"><span data-stu-id="74e1a-131">When the value is `true`, the statement following the `if` executes.</span></span> <span data-ttu-id="74e1a-132">否则，跳过上述语句。</span><span class="sxs-lookup"><span data-stu-id="74e1a-132">Otherwise, it is skipped.</span></span> 

<span data-ttu-id="74e1a-133">这种检查条件并根据条件执行语句的过程非常强大。</span><span class="sxs-lookup"><span data-stu-id="74e1a-133">This process of checking conditions and executing statements based on those conditions is very powerful.</span></span>


## <a name="make-if-and-else-work-together"></a><span data-ttu-id="74e1a-134">让 if 和 else 完美配合</span><span class="sxs-lookup"><span data-stu-id="74e1a-134">Make if and else work together</span></span>

<span data-ttu-id="74e1a-135">若要执行 true 和 false 分支中的不同代码，请创建在条件为 false 时执行的 `else` 分支。</span><span class="sxs-lookup"><span data-stu-id="74e1a-135">To execute different code in both the true and false branches, you create an `else` branch that executes when the condition is false.</span></span> <span data-ttu-id="74e1a-136">尝试此操作。</span><span class="sxs-lookup"><span data-stu-id="74e1a-136">Try this.</span></span> <span data-ttu-id="74e1a-137">在下面的代码以便中添加的最后两行你`Main`（你应该已前四个） 的方法：</span><span class="sxs-lookup"><span data-stu-id="74e1a-137">Add the last two lines in the code below to your `Main` method (you should already have the first four):</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

<span data-ttu-id="74e1a-138">只有当条件的测试结果为 `false` 时，才执行 `else` 关键字后面的语句。</span><span class="sxs-lookup"><span data-stu-id="74e1a-138">The statement following the `else` keyword executes only when the condition being tested is `false`.</span></span> <span data-ttu-id="74e1a-139">组合`if`和`else`使用布尔值条件提供你需要同时处理的所有 power`true`和`false`条件。</span><span class="sxs-lookup"><span data-stu-id="74e1a-139">Combining `if` and `else` with Boolean conditions provides all the power you need to handle both a `true` and a `false` condition.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74e1a-140">`if` 和 `else` 语句下的缩进是为了方便读者阅读。</span><span class="sxs-lookup"><span data-stu-id="74e1a-140">The indentation under the `if` and `else` statements is for human readers.</span></span>
> <span data-ttu-id="74e1a-141">C# 语言忽略缩进或空格。</span><span class="sxs-lookup"><span data-stu-id="74e1a-141">The C# language doesn't treat indentation or whitespace as significant.</span></span> <span data-ttu-id="74e1a-142">`if` 或 `else` 关键字后面的语句根据条件决定是否执行。</span><span class="sxs-lookup"><span data-stu-id="74e1a-142">The statement following the `if` or `else` keyword will be executed based on the condition.</span></span> <span data-ttu-id="74e1a-143">本快速入门中的所有示例都按照常见的做法，缩进基于语句的控制流的行。</span><span class="sxs-lookup"><span data-stu-id="74e1a-143">All the samples in this quick start follow a common practice to indent lines based on the control flow of statements.</span></span>

<span data-ttu-id="74e1a-144">由于缩进会被忽略，因此需要使用 `{` 和 `}`，指明要在根据条件决定是否执行的代码块中添加多个语句。</span><span class="sxs-lookup"><span data-stu-id="74e1a-144">Because indentation is not significant, you need to use `{` and `}` to indicate when you want more than one statement to be part of the block that executes conditionally.</span></span> <span data-ttu-id="74e1a-145">C# 程序员通常会对所有 `if` 和 `else` 子句使用这些大括号。</span><span class="sxs-lookup"><span data-stu-id="74e1a-145">C# programmers typically use those braces on all `if` and `else` clauses.</span></span> <span data-ttu-id="74e1a-146">下面的示例是与你刚刚创建的一个相同。</span><span class="sxs-lookup"><span data-stu-id="74e1a-146">The following example is the same as the one you just created.</span></span> <span data-ttu-id="74e1a-147">修改代码更高版本以匹配下面的代码：</span><span class="sxs-lookup"><span data-stu-id="74e1a-147">Modify your code above to match the following code:</span></span>

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
> <span data-ttu-id="74e1a-148">完成本快速入门的其余部分，所有的代码示例包括大括号，以下接受做法。</span><span class="sxs-lookup"><span data-stu-id="74e1a-148">Through the rest of this quick start, the code samples all include the braces, following accepted practices.</span></span>

<span data-ttu-id="74e1a-149">你可以测试更复杂的条件。</span><span class="sxs-lookup"><span data-stu-id="74e1a-149">You can test more complicated conditions.</span></span> <span data-ttu-id="74e1a-150">添加以下代码中的你`Main`方法之后你到目前为止已编写的代码：</span><span class="sxs-lookup"><span data-stu-id="74e1a-150">Add the following code in your `Main` method after the code you've written so far:</span></span>

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

<span data-ttu-id="74e1a-151">`&&` 表示“且”。</span><span class="sxs-lookup"><span data-stu-id="74e1a-151">The `&&` represents "and".</span></span> <span data-ttu-id="74e1a-152">也就是说，两个条件必须都为 true，才能执行 true 分支中的语句。</span><span class="sxs-lookup"><span data-stu-id="74e1a-152">It means both conditions must be true to execute the statement in the true branch.</span></span>  <span data-ttu-id="74e1a-153">这些示例还表明，可以在每个条件分支中添加多个语句，前提是将它们用 `{` 和 `}` 括住。</span><span class="sxs-lookup"><span data-stu-id="74e1a-153">These examples also show that you can have multiple statements in each conditional branch, provided you enclose them in `{` and `}`.</span></span>

<span data-ttu-id="74e1a-154">你还可以使用`||`来表示"。</span><span class="sxs-lookup"><span data-stu-id="74e1a-154">You can also use  `||` to represent "or".</span></span> <span data-ttu-id="74e1a-155">你到目前为止已编写之后添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="74e1a-155">Add the following code after what you've written so far:</span></span>

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

<span data-ttu-id="74e1a-156">你已完成的第一步。</span><span class="sxs-lookup"><span data-stu-id="74e1a-156">You've finished the first step.</span></span> <span data-ttu-id="74e1a-157">开始进入下一部分前，先将当前代码移到单独的方法中。</span><span class="sxs-lookup"><span data-stu-id="74e1a-157">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="74e1a-158">这样一来，可以更轻松地开始处理新示例。</span><span class="sxs-lookup"><span data-stu-id="74e1a-158">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="74e1a-159">将 `Main` 方法重命名为 `ExploreIf`，并编写调用 `ExploreIf` 的新 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="74e1a-159">Rename your `Main` method to `ExploreIf` and write a new `Main` method that calls `ExploreIf`.</span></span> <span data-ttu-id="74e1a-160">完成后，代码应如下所示：</span><span class="sxs-lookup"><span data-stu-id="74e1a-160">When you have finished, your code should look like this:</span></span>

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

<span data-ttu-id="74e1a-161">注释掉对的调用`ExploreIf()`。</span><span class="sxs-lookup"><span data-stu-id="74e1a-161">Comment out the call to `ExploreIf()`.</span></span> <span data-ttu-id="74e1a-162">它将使整洁的当您在本部分工作的输出：</span><span class="sxs-lookup"><span data-stu-id="74e1a-162">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//ExploreIf();
```

<span data-ttu-id="74e1a-163">`//`启动**注释**C# 中。</span><span class="sxs-lookup"><span data-stu-id="74e1a-163">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="74e1a-164">注释是你想要保留在源代码中，但不是能作为代码执行的任何文本。</span><span class="sxs-lookup"><span data-stu-id="74e1a-164">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="74e1a-165">从注释，编译器不生成任何可执行代码。</span><span class="sxs-lookup"><span data-stu-id="74e1a-165">The compiler does not generate any executable code from comments.</span></span>

## <a name="use-loops-to-repeat-operations"></a><span data-ttu-id="74e1a-166">使用循环重复执行运算</span><span class="sxs-lookup"><span data-stu-id="74e1a-166">Use loops to repeat operations</span></span>

<span data-ttu-id="74e1a-167">在本部分中使用**循环**重复语句。</span><span class="sxs-lookup"><span data-stu-id="74e1a-167">In this section you use **loops** to repeat statements.</span></span> <span data-ttu-id="74e1a-168">请尝试此代码中的你`Main`方法：</span><span class="sxs-lookup"><span data-stu-id="74e1a-168">Try this code in your `Main` method:</span></span>

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

<span data-ttu-id="74e1a-169">`while`语句检查的条件，并执行的语句或后面的语句块`while`。</span><span class="sxs-lookup"><span data-stu-id="74e1a-169">The `while` statement checks a condition and executes the statement or statement block following the `while`.</span></span> <span data-ttu-id="74e1a-170">它会重复检查的条件和执行这些语句，直到条件为 false。</span><span class="sxs-lookup"><span data-stu-id="74e1a-170">It repeatedly checks the condition and executing those statements until the condition is false.</span></span>

<span data-ttu-id="74e1a-171">此示例新引入了另外一个运算符。</span><span class="sxs-lookup"><span data-stu-id="74e1a-171">There's one other new operator in this example.</span></span> <span data-ttu-id="74e1a-172">`counter` 变量后面的 `++` 是增量运算符。</span><span class="sxs-lookup"><span data-stu-id="74e1a-172">The `++` after the `counter` variable is the **increment** operator.</span></span> <span data-ttu-id="74e1a-173">它将 1 添加到的值`counter`，并将存储中的该值`counter`变量。</span><span class="sxs-lookup"><span data-stu-id="74e1a-173">It adds 1 to the value of `counter` and stores that value in the `counter` variable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74e1a-174">请确保`while`循环条件更改为 false，如执行代码。</span><span class="sxs-lookup"><span data-stu-id="74e1a-174">Make sure that the `while` loop condition changes to false as you execute the code.</span></span> <span data-ttu-id="74e1a-175">否则，创建的就是无限循环，即程序永不结束。</span><span class="sxs-lookup"><span data-stu-id="74e1a-175">Otherwise, you create an **infinite loop** where your program never ends.</span></span> <span data-ttu-id="74e1a-176">程序不演示此示例中，因为你必须以强制程序若要停止使用**CTRL-C**或其他方法。</span><span class="sxs-lookup"><span data-stu-id="74e1a-176">That is not demonstrated in this sample, because you have to force your program to quit using **CTRL-C** or other means.</span></span>

<span data-ttu-id="74e1a-177">`while` 循环先测试条件，然后再执行 `while` 后面的代码。</span><span class="sxs-lookup"><span data-stu-id="74e1a-177">The `while` loop tests the condition before executing the code following the `while`.</span></span> <span data-ttu-id="74e1a-178">`do` ... `while` 循环先执行代码，然后再检查条件。</span><span class="sxs-lookup"><span data-stu-id="74e1a-178">The `do` ... `while` loop executes the code first, and then checks the condition.</span></span> <span data-ttu-id="74e1a-179">以下代码所示循环时执行：</span><span class="sxs-lookup"><span data-stu-id="74e1a-179">The do while loop is shown in the following code:</span></span>

```csharp
counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

<span data-ttu-id="74e1a-180">这`do`循环及更早版本`while`循环生成相同的输出。</span><span class="sxs-lookup"><span data-stu-id="74e1a-180">This `do` loop and the earlier `while` loop produce the same output.</span></span>

## <a name="work-with-the-for-loop"></a><span data-ttu-id="74e1a-181">使用 for 循环</span><span class="sxs-lookup"><span data-stu-id="74e1a-181">Work with the for loop</span></span>

<span data-ttu-id="74e1a-182">**为**循环通常用在 C#。</span><span class="sxs-lookup"><span data-stu-id="74e1a-182">The **for** loop is commonly used in C#.</span></span> <span data-ttu-id="74e1a-183">请尝试此代码在 main （） 方法中：</span><span class="sxs-lookup"><span data-stu-id="74e1a-183">Try this code in your Main() method:</span></span>

```csharp
for(int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
} 
```

<span data-ttu-id="74e1a-184">此循环的工作原理与已用过的 `while` 循环和 `do` 循环相同。</span><span class="sxs-lookup"><span data-stu-id="74e1a-184">This does the same work as the `while` loop and the `do` loop you've already used.</span></span> <span data-ttu-id="74e1a-185">`for` 语句包含三个控制具体工作方式的部分。</span><span class="sxs-lookup"><span data-stu-id="74e1a-185">The `for` statement has three parts that control how it works.</span></span> 

<span data-ttu-id="74e1a-186">第一部分是 for 初始值设定项：`for index = 0;` 声明 `index` 是循环变量，并将它的初始值设置为 `0`。</span><span class="sxs-lookup"><span data-stu-id="74e1a-186">The first part is the **for initializer**: `for index = 0;` declares that `index` is the loop variable, and sets its initial value to `0`.</span></span>

<span data-ttu-id="74e1a-187">中间部分是 for 条件：`index < 10` 声明只要计数器值小于 10，此 `for` 循环就会继续执行。</span><span class="sxs-lookup"><span data-stu-id="74e1a-187">The middle part is the **for condition**: `index < 10` declares that this `for` loop continues to execute as long as the value of counter is less than 10.</span></span>

<span data-ttu-id="74e1a-188">最后一部分是 for 迭代器：`index++` 指定在执行 `for` 语句后面的代码块后，如何修改循环变量。</span><span class="sxs-lookup"><span data-stu-id="74e1a-188">The final part is the **for iterator**: `index++` specifies how to modify the loop variable after executing the block following the `for` statement.</span></span> <span data-ttu-id="74e1a-189">在此示例中，它指定 `index` 应在代码块每次执行时递增 1。</span><span class="sxs-lookup"><span data-stu-id="74e1a-189">Here, it specifies that `index` should be incremented by 1 each time the block executes.</span></span>

<span data-ttu-id="74e1a-190">亲自试运行这些部分的代码。</span><span class="sxs-lookup"><span data-stu-id="74e1a-190">Experiment with these yourself.</span></span> <span data-ttu-id="74e1a-191">试着执行下列两项操作：</span><span class="sxs-lookup"><span data-stu-id="74e1a-191">Try each of the following:</span></span>

- <span data-ttu-id="74e1a-192">将初始值设定项更改为其他初始值。</span><span class="sxs-lookup"><span data-stu-id="74e1a-192">Change the initializer to start at a different value.</span></span>
- <span data-ttu-id="74e1a-193">将结束条件设定项更改为其他值。</span><span class="sxs-lookup"><span data-stu-id="74e1a-193">Change the condition to stop at a different value.</span></span>

<span data-ttu-id="74e1a-194">完成后，继续利用所学知识，试着自己编写一些代码。</span><span class="sxs-lookup"><span data-stu-id="74e1a-194">When you're done, let's move on to write some code yourself to use what you've learned.</span></span>

## <a name="combine-branches-and-loops"></a><span data-ttu-id="74e1a-195">将分支和循环结合起来</span><span class="sxs-lookup"><span data-stu-id="74e1a-195">Combine branches and loops</span></span>

<span data-ttu-id="74e1a-196">支持，大家已了解 C# 语言中的 `if` 语句和循环构造。看看能否编写 C# 代码，计算 1 到 20 中所有可被 3 整除的整数的总和。</span><span class="sxs-lookup"><span data-stu-id="74e1a-196">Now that you've seen the `if` statement and the looping constructs in the C# language, see if you can write C# code to find the sum of all integers 1 through 20 that are divisible by 3.</span></span>  <span data-ttu-id="74e1a-197">下面提供了一些提示：</span><span class="sxs-lookup"><span data-stu-id="74e1a-197">Here are a few hints:</span></span>

- <span data-ttu-id="74e1a-198">`%` 运算符可用于获取除法运算的余数。</span><span class="sxs-lookup"><span data-stu-id="74e1a-198">The `%` operator gives you the remainder of a division operation.</span></span>
- <span data-ttu-id="74e1a-199">`if`语句，为你提供的条件，以查看是否数应为之和的一部分。</span><span class="sxs-lookup"><span data-stu-id="74e1a-199">The `if` statement gives you the condition to see if a number should be part of the sum.</span></span>
- <span data-ttu-id="74e1a-200">`for` 循环有助于对 1 到 20 中的所有数字重复执行一系列步骤。</span><span class="sxs-lookup"><span data-stu-id="74e1a-200">The `for` loop can help you repeat a series of steps for all the numbers 1 through 20.</span></span>

<span data-ttu-id="74e1a-201">亲自试一试吧。</span><span class="sxs-lookup"><span data-stu-id="74e1a-201">Try it yourself.</span></span> <span data-ttu-id="74e1a-202">然后，看看自己是怎么做到的。</span><span class="sxs-lookup"><span data-stu-id="74e1a-202">Then check how you did.</span></span> <span data-ttu-id="74e1a-203">你可以看到由一个可能的答案[GitHub 上查看代码的已完成的](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54)。</span><span class="sxs-lookup"><span data-stu-id="74e1a-203">You can see one possible answer by [viewing the completed code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).</span></span>

<span data-ttu-id="74e1a-204">您已完成"分支和循环"快速入门。</span><span class="sxs-lookup"><span data-stu-id="74e1a-204">You've completed the "branches and loops" quick start.</span></span>

<span data-ttu-id="74e1a-205">您可以使用继续[数组和集合](arrays-and-collections.md)开发环境中的快速入门。</span><span class="sxs-lookup"><span data-stu-id="74e1a-205">You can continue with the [Arrays and collections](arrays-and-collections.md) quick start in your own development environment.</span></span>

<span data-ttu-id="74e1a-206">若要详细了解这些概念，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="74e1a-206">You can learn more about these concepts in these topics:</span></span>

<span data-ttu-id="74e1a-207">[If 和 else 语句](../language-reference/keywords/if-else.md) </span><span class="sxs-lookup"><span data-stu-id="74e1a-207">[If and else statement](../language-reference/keywords/if-else.md) </span></span>  
<span data-ttu-id="74e1a-208">[While 语句](../language-reference/keywords/while.md) </span><span class="sxs-lookup"><span data-stu-id="74e1a-208">[While statement](../language-reference/keywords/while.md) </span></span>  
<span data-ttu-id="74e1a-209">[Do 语句](../language-reference/keywords/do.md) </span><span class="sxs-lookup"><span data-stu-id="74e1a-209">[Do statement](../language-reference/keywords/do.md) </span></span>  
[<span data-ttu-id="74e1a-210">For 语句</span><span class="sxs-lookup"><span data-stu-id="74e1a-210">For statement</span></span>](../language-reference/keywords/for.md)   
