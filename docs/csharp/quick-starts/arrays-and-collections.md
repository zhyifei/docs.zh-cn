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
ms.openlocfilehash: 51b190fba32186cb4c52ccd773274d9ae22c8efb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="c-quick-start-collections"></a><span data-ttu-id="cf774-104">C# 快速入门：集合</span><span class="sxs-lookup"><span data-stu-id="cf774-104">C# Quick start: Collections</span></span> #

<span data-ttu-id="cf774-105">本教程介绍了 C# 语言和 <xref:System.Collections.Generic.List%601> 类的基础知识。</span><span class="sxs-lookup"><span data-stu-id="cf774-105">This tutorial provides an introduction to the C# language and the basics of the <xref:System.Collections.Generic.List%601> class.</span></span>

## <a name="a-simple-list-example"></a><span data-ttu-id="cf774-106">简单的列表示例。</span><span class="sxs-lookup"><span data-stu-id="cf774-106">A simple list example.</span></span>

> [!NOTE]
> <span data-ttu-id="cf774-107">如果一开始就有使用 [dot.net](https://dot.net/) 编写的代码，表明已拥有此部分中编写的代码。</span><span class="sxs-lookup"><span data-stu-id="cf774-107">If you're starting from the code you wrote in [dot.net](https://dot.net/), you already have the code written in this section.</span></span> <span data-ttu-id="cf774-108">请跳转到[修改列表内容](#modify-list-contents)。</span><span class="sxs-lookup"><span data-stu-id="cf774-108">Jump to [Modify list contents](#modify-list-contents).</span></span>

<span data-ttu-id="cf774-109">若要更好地学习本课程，需要已完成联机快速入门课程，并已安装 [.NET Core SDK](http://dot.net/core) 和 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="cf774-109">This lesson assumes you've finished the online quick starts, and you've installed the [.NET Core SDK](http://dot.net/core) and [Visual Studio Code](https://code.visualstudio.com/).</span></span> 

<span data-ttu-id="cf774-110">创建名为 list-quickstart 的目录。</span><span class="sxs-lookup"><span data-stu-id="cf774-110">Create a directory named **list-quickstart**.</span></span> <span data-ttu-id="cf774-111">将新建的目录设为当前目录，并运行 `dotnet new console`。</span><span class="sxs-lookup"><span data-stu-id="cf774-111">Make that the current directory and run `dotnet new console`.</span></span>

<span data-ttu-id="cf774-112">在常用编辑器中，打开 Program.cs，并将现有代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="cf774-112">Open **Program.cs** in your favorite editor, and replace the existing code with the following:</span></span>

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

<span data-ttu-id="cf774-113">将 `<name>` 替换为自己的名称。</span><span class="sxs-lookup"><span data-stu-id="cf774-113">Replace `<name>` with your name.</span></span> <span data-ttu-id="cf774-114">保存 Program.cs。</span><span class="sxs-lookup"><span data-stu-id="cf774-114">Save **Program.cs**.</span></span> <span data-ttu-id="cf774-115">在控制台窗口中键入 `dotnet run`，试运行看看。</span><span class="sxs-lookup"><span data-stu-id="cf774-115">Type `dotnet run` in your console window to try it.</span></span>

<span data-ttu-id="cf774-116">刚刚创建了一个字符串列表，并向其中添加了三个名称，再输出了全部大写的名称。</span><span class="sxs-lookup"><span data-stu-id="cf774-116">You've just created a list of strings, added three names to that list, and printed out the names in all CAPS.</span></span> <span data-ttu-id="cf774-117">循环读取整个列表需要用到在前面的快速入门课程中学到的概念。</span><span class="sxs-lookup"><span data-stu-id="cf774-117">You're using concepts that you've learned in earlier quick starts to loop through the list.</span></span>

<span data-ttu-id="cf774-118">用于显示名称的代码使用内插字符串。</span><span class="sxs-lookup"><span data-stu-id="cf774-118">The code to display names makes use of **interpolated strings**.</span></span>  <span data-ttu-id="cf774-119">如果 `$` 字符前面有 `string`，可以在字符串声明中嵌入 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="cf774-119">When you precede a `string` with the `$` character, you can embed C# code in the string declaration.</span></span> <span data-ttu-id="cf774-120">实际字符串使用自己生成的值替换相应 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="cf774-120">The actual string replaces that C# code with the value it generates.</span></span> <span data-ttu-id="cf774-121">在此示例中，`{name.ToUpper()}` 被替换为各个转换为大写字母的名称，因为调用了 <xref:System.String.ToUpper%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="cf774-121">In this example, it replaces the `{name.ToUpper()}` with each name, converted to capital letters, because you called the <xref:System.String.ToUpper%2A> method.</span></span>

<span data-ttu-id="cf774-122">接下来将进一步探索。</span><span class="sxs-lookup"><span data-stu-id="cf774-122">Let's keep exploring.</span></span>
    
## <a name="modify-list-contents"></a><span data-ttu-id="cf774-123">修改列表内容</span><span class="sxs-lookup"><span data-stu-id="cf774-123">Modify list contents</span></span>

<span data-ttu-id="cf774-124">创建的集合使用 <xref:System.Collections.Generic.List%601> 类型。</span><span class="sxs-lookup"><span data-stu-id="cf774-124">The collection you created uses the <xref:System.Collections.Generic.List%601> type.</span></span> <span data-ttu-id="cf774-125">此类型存储一系列元素。</span><span class="sxs-lookup"><span data-stu-id="cf774-125">This type stores sequences of elements.</span></span> <span data-ttu-id="cf774-126">元素类型是在尖括号内指定。</span><span class="sxs-lookup"><span data-stu-id="cf774-126">You specify the type of the elements between the angle brackets.</span></span>
    
<span data-ttu-id="cf774-127"><xref:System.Collections.Generic.List%601> 类型的一个重要方面是，既可以扩大，也可以收缩，方便用户添加或删除元素。</span><span class="sxs-lookup"><span data-stu-id="cf774-127">One important aspect of this <xref:System.Collections.Generic.List%601> type is that it can grow or shrink, enabling you to add or remove elements.</span></span> <span data-ttu-id="cf774-128">在 `Main` 方法的右 `}` 前添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="cf774-128">Add this code before the closing `}` in the `Main` method:</span></span>

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

<span data-ttu-id="cf774-129">又向列表的末尾添加了两个名称。</span><span class="sxs-lookup"><span data-stu-id="cf774-129">You've added two more names to the end of the list.</span></span> <span data-ttu-id="cf774-130">同时，也删除了一个名称。</span><span class="sxs-lookup"><span data-stu-id="cf774-130">You've also removed one as well.</span></span> <span data-ttu-id="cf774-131">保存此文件，并键入 `dotnet run`，试运行看看。</span><span class="sxs-lookup"><span data-stu-id="cf774-131">Save the file, and type `dotnet run` to try it.</span></span>
    
<span data-ttu-id="cf774-132">借助 <xref:System.Collections.Generic.List%601>，还可以按索引引用各项。</span><span class="sxs-lookup"><span data-stu-id="cf774-132">The <xref:System.Collections.Generic.List%601> enables you to reference individual items by **index** as well.</span></span> <span data-ttu-id="cf774-133">索引位于列表名称后面的 `[` 和 `]` 令牌之间。</span><span class="sxs-lookup"><span data-stu-id="cf774-133">You place the index between `[` and `]` tokens following the list name.</span></span> <span data-ttu-id="cf774-134">C# 对第一个索引使用 0。</span><span class="sxs-lookup"><span data-stu-id="cf774-134">C# uses 0 for the first index.</span></span> <span data-ttu-id="cf774-135">将以下代码添加到刚才添加的代码的正下方，并试运行看看：</span><span class="sxs-lookup"><span data-stu-id="cf774-135">Add this code directly below the code you just added and try it:</span></span>

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

<span data-ttu-id="cf774-136">不得访问超出列表末尾的索引。</span><span class="sxs-lookup"><span data-stu-id="cf774-136">You cannot access an index beyond the end of the list.</span></span> <span data-ttu-id="cf774-137">请注意，索引是从 0 开始编制，因此最大有效索引是用列表项数减 1 计算得出。</span><span class="sxs-lookup"><span data-stu-id="cf774-137">Remember that indices start at 0, so the largest valid index is one less than the number of items in the list.</span></span> <span data-ttu-id="cf774-138">可以使用 <xref:System.Collections.Generic.List%601.Count%2A> 属性确定列表长度。</span><span class="sxs-lookup"><span data-stu-id="cf774-138">You can check how long the list is using the <xref:System.Collections.Generic.List%601.Count%2A> property.</span></span> <span data-ttu-id="cf774-139">在 Main 方法的末尾，添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="cf774-139">Add the following code at the end of the Main method:</span></span>

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

<span data-ttu-id="cf774-140">保存此文件，并再次键入 `dotnet run` 看看结果如何。</span><span class="sxs-lookup"><span data-stu-id="cf774-140">Save the file, and type `dotnet run` again to see the results.</span></span>    

## <a name="search-and-sort-lists"></a><span data-ttu-id="cf774-141">搜索列表并进行排序</span><span class="sxs-lookup"><span data-stu-id="cf774-141">Search and sort lists</span></span>
<span data-ttu-id="cf774-142">我们的示例使用的列表较小，但大家的应用程序创建的列表通常可能会包含更多元素，有时可能会包含数以千计的元素。</span><span class="sxs-lookup"><span data-stu-id="cf774-142">Our samples use relatively small lists, but your applications may often create lists with many more elements, sometimes numbering in the thousands.</span></span> <span data-ttu-id="cf774-143">若要在更大的集合中查找元素，需要在列表中搜索不同的项。</span><span class="sxs-lookup"><span data-stu-id="cf774-143">To find elements in these larger collections, you need to search the list for different items.</span></span> <span data-ttu-id="cf774-144"><xref:System.Collections.Generic.List%601.IndexOf%2A> 方法可搜索项，并返回此项的索引。</span><span class="sxs-lookup"><span data-stu-id="cf774-144">The <xref:System.Collections.Generic.List%601.IndexOf%2A> method searches for an item and returns the index of the item.</span></span> <span data-ttu-id="cf774-145">将以下代码添加到 `Main` 方法的底部：</span><span class="sxs-lookup"><span data-stu-id="cf774-145">Add this code to the bottom of your `Main` method:</span></span>

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

<span data-ttu-id="cf774-146">还可以对列表中的项进行排序。</span><span class="sxs-lookup"><span data-stu-id="cf774-146">The items in your list can be sorted as well.</span></span> <span data-ttu-id="cf774-147"><xref:System.Collections.Generic.List%601.Sort%2A> 方法按正常顺序（按字母顺序，如果是字符串的话）对列表中的所有项进行排序。</span><span class="sxs-lookup"><span data-stu-id="cf774-147">The <xref:System.Collections.Generic.List%601.Sort%2A> method sorts all the items in the list in their normal order (alphabetically in the case of strings).</span></span> <span data-ttu-id="cf774-148">将以下代码添加到 `Main` 方法的底部：</span><span class="sxs-lookup"><span data-stu-id="cf774-148">Add this code to the bottom of our `Main` method:</span></span>

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="cf774-149">保存此文件，并键入 `dotnet run`，试运行此最新版程序。</span><span class="sxs-lookup"><span data-stu-id="cf774-149">Save the file and type `dotnet run` to try this latest version.</span></span>

<span data-ttu-id="cf774-150">开始进入下一部分前，先将当前代码移到单独的方法中。</span><span class="sxs-lookup"><span data-stu-id="cf774-150">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="cf774-151">这样一来，可以更轻松地开始处理新示例。</span><span class="sxs-lookup"><span data-stu-id="cf774-151">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="cf774-152">将 `Main` 方法重命名为 `WorkingWithStrings`，并编写调用 `WorkingWithStrings` 的新 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="cf774-152">Rename your `Main` method to `WorkingWithStrings` and write a new `Main` method that calls `WorkingWithStrings`.</span></span> <span data-ttu-id="cf774-153">完成后，代码应如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf774-153">When you have finished, your code should look like this:</span></span>

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

## <a name="lists-of-other-types"></a><span data-ttu-id="cf774-154">其他类型的列表</span><span class="sxs-lookup"><span data-stu-id="cf774-154">Lists of other types</span></span>

<span data-ttu-id="cf774-155">到目前为止，大家一直在列表中使用 `string` 类型。</span><span class="sxs-lookup"><span data-stu-id="cf774-155">You've been using the `string` type in lists so far.</span></span> <span data-ttu-id="cf774-156">接下来，将让 <xref:System.Collections.Generic.List%601> 使用其他类型。</span><span class="sxs-lookup"><span data-stu-id="cf774-156">Let's make a <xref:System.Collections.Generic.List%601> using a different type.</span></span> <span data-ttu-id="cf774-157">那就生成一组数字吧。</span><span class="sxs-lookup"><span data-stu-id="cf774-157">Let's build a set of numbers.</span></span> 

<span data-ttu-id="cf774-158">将以下代码添加到新 `Main` 方法的底部：</span><span class="sxs-lookup"><span data-stu-id="cf774-158">Add the following to the bottom of your new `Main` method:</span></span>

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

<span data-ttu-id="cf774-159">这会创建一个整数列表，并将头两个整数设置为值 1。</span><span class="sxs-lookup"><span data-stu-id="cf774-159">That creates a list of integers, and sets the first two integers to the value 1.</span></span> <span data-ttu-id="cf774-160">这些是斐波那契数列（一系列数字）的头两个值。</span><span class="sxs-lookup"><span data-stu-id="cf774-160">These are the first two values of a *Fibonacci Sequence*, a sequence of numbers.</span></span> <span data-ttu-id="cf774-161">斐波那契数列中的每个数字都是前两个数字之和。</span><span class="sxs-lookup"><span data-stu-id="cf774-161">Each next Fibonacci number is found by taking the sum of the previous two numbers.</span></span> <span data-ttu-id="cf774-162">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="cf774-162">Add this code:</span></span>

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach(var item in fibonacciNumbers)
    Console.WriteLine(item);
```

<span data-ttu-id="cf774-163">保存此文件，并键入 `dotnet run` 看看结果如何。</span><span class="sxs-lookup"><span data-stu-id="cf774-163">Save the file and type `dotnet run` to see the results.</span></span> 

> [!TIP]
> <span data-ttu-id="cf774-164">为了能够集中精力探究此部分，可以注释掉调用 `WorkingWithStrings();` 的代码。</span><span class="sxs-lookup"><span data-stu-id="cf774-164">To concentrate on just this section, you can comment out the code that calls `WorkingWithStrings();`.</span></span> <span data-ttu-id="cf774-165">只需在此调用前添加两个 `/` 字符即可，如 `// WorkingWithStrings();`。</span><span class="sxs-lookup"><span data-stu-id="cf774-165">Just put two `/` characters in front of the call like this:  `// WorkingWithStrings();`.</span></span> 

## <a name="challenge"></a><span data-ttu-id="cf774-166">挑战</span><span class="sxs-lookup"><span data-stu-id="cf774-166">Challenge</span></span>
<span data-ttu-id="cf774-167">看看能不能将本课程中的一些内容与前面的课程融会贯通。</span><span class="sxs-lookup"><span data-stu-id="cf774-167">See if you can put together some of the lessons from this and earlier lessons.</span></span> <span data-ttu-id="cf774-168">使用斐波那契数列，扩展当前生成的程序。</span><span class="sxs-lookup"><span data-stu-id="cf774-168">Expand on what you've built so far with Fibonacci Numbers.</span></span> <span data-ttu-id="cf774-169">试着编写代码，生成此序列中的前 20 个数字。</span><span class="sxs-lookup"><span data-stu-id="cf774-169">Try and write the code to generate the first 20 numbers in the sequence.</span></span>

## <a name="complete-challenge"></a><span data-ttu-id="cf774-170">完成挑战</span><span class="sxs-lookup"><span data-stu-id="cf774-170">Complete challenge</span></span>

<span data-ttu-id="cf774-171">可以[查看 GitHub 上的完成示例代码](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs)，了解示例解决方案</span><span class="sxs-lookup"><span data-stu-id="cf774-171">You can see an example solution by [looking at the finished sample code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs)</span></span>

<span data-ttu-id="cf774-172">在循环的每次迭代中，取此列表中的最后两个整数进行求和，并将计算出的总和值添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="cf774-172">With each iteration of the loop, you're taking the last two integers in the list, summing them, and adding that value to the list.</span></span> <span data-ttu-id="cf774-173">循环会一直重复运行到列表中有 20 个项为止。</span><span class="sxs-lookup"><span data-stu-id="cf774-173">The loop repeats until you've added 20 items to the list.</span></span>

<span data-ttu-id="cf774-174">恭喜！已完成“列表集合”教程。</span><span class="sxs-lookup"><span data-stu-id="cf774-174">Congratulations, you've completed the list tutorial.</span></span>

<span data-ttu-id="cf774-175">若要详细了解如何使用 `List` 类型，可以参阅有关[集合](../../standard/collections/index.md)的 [.NET 指南](../../standard/index.md)主题。</span><span class="sxs-lookup"><span data-stu-id="cf774-175">You can learn more about working with the `List` type in the [.NET Guide](../../standard/index.md) topic on [collections](../../standard/collections/index.md).</span></span> <span data-ttu-id="cf774-176">还可以了解其他许多集合类型。</span><span class="sxs-lookup"><span data-stu-id="cf774-176">You'll also learn about many other collection types.</span></span>
