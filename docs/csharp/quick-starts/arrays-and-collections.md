---
title: "快速入门 - 集合 - C# 指南"
description: "在本快速入门课程中通过探索列表集合了解 C#。"
keywords: "C#, 入门, 教程, 集合, 列表"
author: billwagner
ms.author: wiwagn
ms.date: 10/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 6f559c7a3290e7db2266e10ec792c283394fb904
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2017
---
# <a name="c-quick-start-collections"></a><span data-ttu-id="94ed1-104">C# 快速入门：集合</span><span class="sxs-lookup"><span data-stu-id="94ed1-104">C# Quick start: Collections</span></span> #

<span data-ttu-id="94ed1-105">本快速入门教程介绍了 C# 语言和 <xref:System.Collections.Generic.List%601> 类的基础知识。</span><span class="sxs-lookup"><span data-stu-id="94ed1-105">This quick start provides an introduction to the C# language and the basics of the <xref:System.Collections.Generic.List%601> class.</span></span>

<span data-ttu-id="94ed1-106">本快速入门教程要求你有一台可用于开发的计算机。</span><span class="sxs-lookup"><span data-stu-id="94ed1-106">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="94ed1-107">.NET 主题 [10 分钟入门](https://www.microsoft.com/net/core)介绍了如何在 Mac、PC 或 Linux 上设置本地开发环境。</span><span class="sxs-lookup"><span data-stu-id="94ed1-107">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="94ed1-108">[本地快速入门简介](local-environment.md)简要概述了你将用到的命令，还提供了详细信息链接。</span><span class="sxs-lookup"><span data-stu-id="94ed1-108">A quick overview of the commands you'll use is in the [introduction to the local quick starts](local-environment.md) with links to more details.</span></span>

## <a name="a-basic-list-example"></a><span data-ttu-id="94ed1-109">基本的列表示例。</span><span class="sxs-lookup"><span data-stu-id="94ed1-109">A basic list example.</span></span>

<span data-ttu-id="94ed1-110">创建名为 list-quickstart 的目录。</span><span class="sxs-lookup"><span data-stu-id="94ed1-110">Create a directory named **list-quickstart**.</span></span> <span data-ttu-id="94ed1-111">将新建的目录设为当前目录，并运行 `dotnet new console`。</span><span class="sxs-lookup"><span data-stu-id="94ed1-111">Make that the current directory and run `dotnet new console`.</span></span>

> [!NOTE]
> <span data-ttu-id="94ed1-112">如果你刚完成 [10 分钟 .NET 入门](https://www.microsoft.com/net)，则可以继续使用刚刚创建的 myApp 应用程序。</span><span class="sxs-lookup"><span data-stu-id="94ed1-112">If you just completed [Get started with .NET in 10 minutes](https://www.microsoft.com/net), you can keep using the myApp application that you just created.</span></span>
 
<span data-ttu-id="94ed1-113">在常用编辑器中，打开 Program.cs，并将现有代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="94ed1-113">Open **Program.cs** in your favorite editor, and replace the existing code with the following:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_quickstart
{
    class Program
    {
        static void Main(string[] args)
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

<span data-ttu-id="94ed1-114">将 `<name>` 替换为自己的名称。</span><span class="sxs-lookup"><span data-stu-id="94ed1-114">Replace `<name>` with your name.</span></span> <span data-ttu-id="94ed1-115">保存 Program.cs。</span><span class="sxs-lookup"><span data-stu-id="94ed1-115">Save **Program.cs**.</span></span> <span data-ttu-id="94ed1-116">在控制台窗口中键入 `dotnet run`，试运行看看。</span><span class="sxs-lookup"><span data-stu-id="94ed1-116">Type `dotnet run` in your console window to try it.</span></span>

<span data-ttu-id="94ed1-117">刚刚创建了一个字符串列表，并向其中添加了三个名称，再输出了全部大写的名称。</span><span class="sxs-lookup"><span data-stu-id="94ed1-117">You've just created a list of strings, added three names to that list, and printed out the names in all CAPS.</span></span> <span data-ttu-id="94ed1-118">循环读取整个列表需要用到在前面的快速入门课程中学到的概念。</span><span class="sxs-lookup"><span data-stu-id="94ed1-118">You're using concepts that you've learned in earlier quick starts to loop through the list.</span></span>

<span data-ttu-id="94ed1-119">用于显示名称的代码使用内插字符串。</span><span class="sxs-lookup"><span data-stu-id="94ed1-119">The code to display names makes use of **interpolated strings**.</span></span>  <span data-ttu-id="94ed1-120">如果 `$` 字符前面有 `string`，可以在字符串声明中嵌入 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="94ed1-120">When you precede a `string` with the `$` character, you can embed C# code in the string declaration.</span></span> <span data-ttu-id="94ed1-121">实际字符串使用自己生成的值替换该 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="94ed1-121">The actual string replaces that C# code with the value it generates.</span></span> <span data-ttu-id="94ed1-122">在此示例中，`{name.ToUpper()}` 被替换为各个转换为大写字母的名称，因为调用了 <xref:System.String.ToUpper%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="94ed1-122">In this example, it replaces the `{name.ToUpper()}` with each name, converted to capital letters, because you called the <xref:System.String.ToUpper%2A> method.</span></span>

<span data-ttu-id="94ed1-123">接下来将进一步探索。</span><span class="sxs-lookup"><span data-stu-id="94ed1-123">Let's keep exploring.</span></span>
    
## <a name="modify-list-contents"></a><span data-ttu-id="94ed1-124">修改列表内容</span><span class="sxs-lookup"><span data-stu-id="94ed1-124">Modify list contents</span></span>

<span data-ttu-id="94ed1-125">创建的集合使用 <xref:System.Collections.Generic.List%601> 类型。</span><span class="sxs-lookup"><span data-stu-id="94ed1-125">The collection you created uses the <xref:System.Collections.Generic.List%601> type.</span></span> <span data-ttu-id="94ed1-126">此类型存储一系列元素。</span><span class="sxs-lookup"><span data-stu-id="94ed1-126">This type stores sequences of elements.</span></span> <span data-ttu-id="94ed1-127">元素类型是在尖括号内指定。</span><span class="sxs-lookup"><span data-stu-id="94ed1-127">You specify the type of the elements between the angle brackets.</span></span>
    
<span data-ttu-id="94ed1-128"><xref:System.Collections.Generic.List%601> 类型的一个重要方面是，既可以扩大，也可以收缩，方便用户添加或删除元素。</span><span class="sxs-lookup"><span data-stu-id="94ed1-128">One important aspect of this <xref:System.Collections.Generic.List%601> type is that it can grow or shrink, enabling you to add or remove elements.</span></span> <span data-ttu-id="94ed1-129">在 `Main` 方法的右 `}` 前添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="94ed1-129">Add this code before the closing `}` in the `Main` method:</span></span>

```csharp
Console.WriteLine();
names.Add("Maria");
names.Add("Bill");
names.Remove("Ana");
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="94ed1-130">又向列表的末尾添加了两个名称。</span><span class="sxs-lookup"><span data-stu-id="94ed1-130">You've added two more names to the end of the list.</span></span> <span data-ttu-id="94ed1-131">同时，也删除了一个名称。</span><span class="sxs-lookup"><span data-stu-id="94ed1-131">You've also removed one as well.</span></span> <span data-ttu-id="94ed1-132">保存此文件，并键入 `dotnet run`，试运行看看。</span><span class="sxs-lookup"><span data-stu-id="94ed1-132">Save the file, and type `dotnet run` to try it.</span></span>
    
<span data-ttu-id="94ed1-133">借助 <xref:System.Collections.Generic.List%601>，还可以按索引引用各项。</span><span class="sxs-lookup"><span data-stu-id="94ed1-133">The <xref:System.Collections.Generic.List%601> enables you to reference individual items by **index** as well.</span></span> <span data-ttu-id="94ed1-134">索引位于列表名称后面的 `[` 和 `]` 令牌之间。</span><span class="sxs-lookup"><span data-stu-id="94ed1-134">You place the index between `[` and `]` tokens following the list name.</span></span> <span data-ttu-id="94ed1-135">C# 对第一个索引使用 0。</span><span class="sxs-lookup"><span data-stu-id="94ed1-135">C# uses 0 for the first index.</span></span> <span data-ttu-id="94ed1-136">将以下代码添加到刚才添加的代码的正下方，并试运行看看：</span><span class="sxs-lookup"><span data-stu-id="94ed1-136">Add this code directly below the code you just added and try it:</span></span>

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

<span data-ttu-id="94ed1-137">不得访问超出列表末尾的索引。</span><span class="sxs-lookup"><span data-stu-id="94ed1-137">You cannot access an index beyond the end of the list.</span></span> <span data-ttu-id="94ed1-138">请注意，索引是从 0 开始编制，因此最大有效索引是用列表项数减 1 计算得出。</span><span class="sxs-lookup"><span data-stu-id="94ed1-138">Remember that indices start at 0, so the largest valid index is one less than the number of items in the list.</span></span> <span data-ttu-id="94ed1-139">可以使用 <xref:System.Collections.Generic.List%601.Count%2A> 属性确定列表长度。</span><span class="sxs-lookup"><span data-stu-id="94ed1-139">You can check how long the list is using the <xref:System.Collections.Generic.List%601.Count%2A> property.</span></span> <span data-ttu-id="94ed1-140">在 Main 方法的末尾，添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="94ed1-140">Add the following code at the end of the Main method:</span></span>

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

<span data-ttu-id="94ed1-141">保存此文件，并再次键入 `dotnet run` 看看结果如何。</span><span class="sxs-lookup"><span data-stu-id="94ed1-141">Save the file, and type `dotnet run` again to see the results.</span></span>    

## <a name="search-and-sort-lists"></a><span data-ttu-id="94ed1-142">搜索列表并进行排序</span><span class="sxs-lookup"><span data-stu-id="94ed1-142">Search and sort lists</span></span>
<span data-ttu-id="94ed1-143">我们的示例使用的列表较小，但大家的应用程序创建的列表通常可能会包含更多元素，有时可能会包含数以千计的元素。</span><span class="sxs-lookup"><span data-stu-id="94ed1-143">Our samples use relatively small lists, but your applications may often create lists with many more elements, sometimes numbering in the thousands.</span></span> <span data-ttu-id="94ed1-144">若要在更大的集合中查找元素，需要在列表中搜索不同的项。</span><span class="sxs-lookup"><span data-stu-id="94ed1-144">To find elements in these larger collections, you need to search the list for different items.</span></span> <span data-ttu-id="94ed1-145"><xref:System.Collections.Generic.List%601.IndexOf%2A> 方法可搜索项，并返回此项的索引。</span><span class="sxs-lookup"><span data-stu-id="94ed1-145">The <xref:System.Collections.Generic.List%601.IndexOf%2A> method searches for an item and returns the index of the item.</span></span> <span data-ttu-id="94ed1-146">将以下代码添加到 `Main` 方法的底部：</span><span class="sxs-lookup"><span data-stu-id="94ed1-146">Add this code to the bottom of your `Main` method:</span></span>

```csharp
var index = names.IndexOf("Felipe");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
    
}
```

<span data-ttu-id="94ed1-147">还可以对列表中的项进行排序。</span><span class="sxs-lookup"><span data-stu-id="94ed1-147">The items in your list can be sorted as well.</span></span> <span data-ttu-id="94ed1-148"><xref:System.Collections.Generic.List%601.Sort%2A> 方法按正常顺序（按字母顺序，如果是字符串的话）对列表中的所有项进行排序。</span><span class="sxs-lookup"><span data-stu-id="94ed1-148">The <xref:System.Collections.Generic.List%601.Sort%2A> method sorts all the items in the list in their normal order (alphabetically in the case of strings).</span></span> <span data-ttu-id="94ed1-149">将以下代码添加到 `Main` 方法的底部：</span><span class="sxs-lookup"><span data-stu-id="94ed1-149">Add this code to the bottom of our `Main` method:</span></span>

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="94ed1-150">保存此文件，并键入 `dotnet run`，试运行此最新版程序。</span><span class="sxs-lookup"><span data-stu-id="94ed1-150">Save the file and type `dotnet run` to try this latest version.</span></span>

<span data-ttu-id="94ed1-151">开始进入下一部分前，先将当前代码移到单独的方法中。</span><span class="sxs-lookup"><span data-stu-id="94ed1-151">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="94ed1-152">这样一来，可以更轻松地开始处理新示例。</span><span class="sxs-lookup"><span data-stu-id="94ed1-152">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="94ed1-153">将 `Main` 方法重命名为 `WorkingWithStrings`，并编写调用 `WorkingWithStrings` 的新 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="94ed1-153">Rename your `Main` method to `WorkingWithStrings` and write a new `Main` method that calls `WorkingWithStrings`.</span></span> <span data-ttu-id="94ed1-154">完成后，代码应如下所示：</span><span class="sxs-lookup"><span data-stu-id="94ed1-154">When you have finished, your code should look like this:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_quickstart
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        public static void WorkingWithStrings()
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine();
            names.Add("Maria");
            names.Add("Bill");
            names.Remove("Ana");
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine($"My name is {names[0]}");
            Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");

            Console.WriteLine($"The list has {names.Count} people in it");

            var index = names.IndexOf("Felipe");
            Console.WriteLine($"The name {names[index]} is at index {index}");

            var notFound = names.IndexOf("Not Found");
            Console.WriteLine($"When an item is not found, IndexOf returns {notFound}");

            names.Sort();
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

## <a name="lists-of-other-types"></a><span data-ttu-id="94ed1-155">其他类型的列表</span><span class="sxs-lookup"><span data-stu-id="94ed1-155">Lists of other types</span></span>

<span data-ttu-id="94ed1-156">到目前为止，大家一直在列表中使用 `string` 类型。</span><span class="sxs-lookup"><span data-stu-id="94ed1-156">You've been using the `string` type in lists so far.</span></span> <span data-ttu-id="94ed1-157">接下来，将让 <xref:System.Collections.Generic.List%601> 使用其他类型。</span><span class="sxs-lookup"><span data-stu-id="94ed1-157">Let's make a <xref:System.Collections.Generic.List%601> using a different type.</span></span> <span data-ttu-id="94ed1-158">那就生成一组数字吧。</span><span class="sxs-lookup"><span data-stu-id="94ed1-158">Let's build a set of numbers.</span></span> 

<span data-ttu-id="94ed1-159">将以下代码添加到新 `Main` 方法的底部：</span><span class="sxs-lookup"><span data-stu-id="94ed1-159">Add the following to the bottom of your new `Main` method:</span></span>

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

<span data-ttu-id="94ed1-160">这会创建一个整数列表，并将头两个整数设置为值 1。</span><span class="sxs-lookup"><span data-stu-id="94ed1-160">That creates a list of integers, and sets the first two integers to the value 1.</span></span> <span data-ttu-id="94ed1-161">这些是斐波那契数列（一系列数字）的头两个值。</span><span class="sxs-lookup"><span data-stu-id="94ed1-161">These are the first two values of a *Fibonacci Sequence*, a sequence of numbers.</span></span> <span data-ttu-id="94ed1-162">斐波那契数列中的每个数字都是前两个数字之和。</span><span class="sxs-lookup"><span data-stu-id="94ed1-162">Each next Fibonacci number is found by taking the sum of the previous two numbers.</span></span> <span data-ttu-id="94ed1-163">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="94ed1-163">Add this code:</span></span>

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach(var item in fibonacciNumbers)
    Console.WriteLine(item);
```

<span data-ttu-id="94ed1-164">保存此文件，并键入 `dotnet run` 看看结果如何。</span><span class="sxs-lookup"><span data-stu-id="94ed1-164">Save the file and type `dotnet run` to see the results.</span></span> 

> [!TIP]
> <span data-ttu-id="94ed1-165">为了能够集中精力探究此部分，可以注释掉调用 `WorkingWithStrings();` 的代码。</span><span class="sxs-lookup"><span data-stu-id="94ed1-165">To concentrate on just this section, you can comment out the code that calls `WorkingWithStrings();`.</span></span> <span data-ttu-id="94ed1-166">只需在此调用前添加两个 `/` 字符即可，如 `// WorkingWithStrings();`。</span><span class="sxs-lookup"><span data-stu-id="94ed1-166">Just put two `/` characters in front of the call like this:  `// WorkingWithStrings();`.</span></span> 

## <a name="challenge"></a><span data-ttu-id="94ed1-167">挑战</span><span class="sxs-lookup"><span data-stu-id="94ed1-167">Challenge</span></span>
<span data-ttu-id="94ed1-168">看看能不能将本课程中的一些概念与前面的课程融会贯通。</span><span class="sxs-lookup"><span data-stu-id="94ed1-168">See if you can put together some of the concepts from this and earlier lessons.</span></span> <span data-ttu-id="94ed1-169">使用斐波那契数列，扩展当前生成的程序。</span><span class="sxs-lookup"><span data-stu-id="94ed1-169">Expand on what you've built so far with Fibonacci Numbers.</span></span> <span data-ttu-id="94ed1-170">试着编写代码，生成此序列中的前 20 个数字。</span><span class="sxs-lookup"><span data-stu-id="94ed1-170">Try to write the code to generate the first 20 numbers in the sequence.</span></span> <span data-ttu-id="94ed1-171">（作为提示，第 20 个斐波纳契数是 6765。）</span><span class="sxs-lookup"><span data-stu-id="94ed1-171">(As a hint, the 20th Fibonacci number is 6765.)</span></span>

## <a name="complete-challenge"></a><span data-ttu-id="94ed1-172">完成挑战</span><span class="sxs-lookup"><span data-stu-id="94ed1-172">Complete challenge</span></span>

<span data-ttu-id="94ed1-173">可以[查看 GitHub 上的完成示例代码](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs#L13-L23)，了解示例解决方案</span><span class="sxs-lookup"><span data-stu-id="94ed1-173">You can see an example solution by [looking at the finished sample code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs#L13-L23)</span></span>

<span data-ttu-id="94ed1-174">在循环的每次迭代中，取此列表中的最后两个整数进行求和，并将计算出的总和值添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="94ed1-174">With each iteration of the loop, you're taking the last two integers in the list, summing them, and adding that value to the list.</span></span> <span data-ttu-id="94ed1-175">循环会一直重复运行到列表中有 20 个项为止。</span><span class="sxs-lookup"><span data-stu-id="94ed1-175">The loop repeats until you've added 20 items to the list.</span></span>

<span data-ttu-id="94ed1-176">恭喜！你已完成列表快速入门教程。</span><span class="sxs-lookup"><span data-stu-id="94ed1-176">Congratulations, you've completed the list quick start.</span></span> <span data-ttu-id="94ed1-177">可以继续在你自己的开发环境中学习[类简介](introduction-to-classes.md)快速入门教程。</span><span class="sxs-lookup"><span data-stu-id="94ed1-177">You can continue with the [Introduction to classes](introduction-to-classes.md) quick start in your own development environment.</span></span>

<span data-ttu-id="94ed1-178">若要详细了解如何使用 `List` 类型，可以参阅有关[集合](../../standard/collections/index.md)的 [.NET 指南](../../standard/index.md)主题。</span><span class="sxs-lookup"><span data-stu-id="94ed1-178">You can learn more about working with the `List` type in the [.NET Guide](../../standard/index.md) topic on [collections](../../standard/collections/index.md).</span></span> <span data-ttu-id="94ed1-179">还可以了解其他许多集合类型。</span><span class="sxs-lookup"><span data-stu-id="94ed1-179">You'll also learn about many other collection types.</span></span>
