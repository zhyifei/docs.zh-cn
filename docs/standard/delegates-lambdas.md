---
title: 委托和 lambda
description: 了解委托定义某种类型的方式，该类型可指定特定的方法签名，而后者又可直接调用或传递到另一种方法进行调用。
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: 3fb926683de90516bcf67d99026a0134d82cb683
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152192"
---
# <a name="delegates-and-lambdas"></a><span data-ttu-id="94518-103">委托和 lambda</span><span class="sxs-lookup"><span data-stu-id="94518-103">Delegates and lambdas</span></span>

<span data-ttu-id="94518-104">委托定义类型，类型指定特定方法签名。</span><span class="sxs-lookup"><span data-stu-id="94518-104">Delegates define a type, which specify a particular method signature.</span></span> <span data-ttu-id="94518-105">可将满足此签名的方法（静态或实例）分配给该类型的变量，然后（使用适当参数）直接调用该方法，或将其作为参数本身传递给另一方法再进行调用。</span><span class="sxs-lookup"><span data-stu-id="94518-105">A method (static or instance) that satisfies this signature can be assigned to a variable of that type, then called directly (with the appropriate arguments) or passed as an argument itself to another method and then called.</span></span> <span data-ttu-id="94518-106">以下示例演示了委托的用法。</span><span class="sxs-lookup"><span data-stu-id="94518-106">The following example demonstrates delegate use.</span></span>

```csharp
using System;
using System.Linq;

public class Program
{
    public delegate string Reverse(string s);

    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Reverse rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

* <span data-ttu-id="94518-107">`public delegate string Reverse(string s);` 行创建特定签名的委托类型，在本例中即接受字符串参数并返回字符串参数的方法。</span><span class="sxs-lookup"><span data-stu-id="94518-107">The `public delegate string Reverse(string s);` line creates a delegate type of a certain signature, in this case a method that takes a string parameter and then returns a string parameter.</span></span>
* <span data-ttu-id="94518-108">`static string ReverseString(string s)` 方法与定义的委托类型具有完全相同的签名，用于实现委托。</span><span class="sxs-lookup"><span data-stu-id="94518-108">The `static string ReverseString(string s)` method, which has the exact same signature as the defined delegate type, implements the delegate.</span></span>
* <span data-ttu-id="94518-109">`Reverse rev = ReverseString;` 行显示可将方法分配给相应委托类型的变量。</span><span class="sxs-lookup"><span data-stu-id="94518-109">The `Reverse rev = ReverseString;` line shows that you can assign a method to a variable of the corresponding delegate type.</span></span>
* <span data-ttu-id="94518-110">`Console.WriteLine(rev("a string"));` 行演示如何使用委托类型的变量来调用委托。</span><span class="sxs-lookup"><span data-stu-id="94518-110">The `Console.WriteLine(rev("a string"));` line demonstrates how to use a variable of a delegate type to invoke the delegate.</span></span>

<span data-ttu-id="94518-111">为简化开发过程，.NET 包含一组委托类型，程序员可重用这些类型而无需创建新类型。</span><span class="sxs-lookup"><span data-stu-id="94518-111">In order to streamline the development process, .NET includes a set of delegate types that programmers can reuse and not have to create new types.</span></span> <span data-ttu-id="94518-112">其中包括 `Func<>`、`Action<>` 和 `Predicate<>`，可用于 .NET API 的各个位置，无需定义新委托类型。</span><span class="sxs-lookup"><span data-stu-id="94518-112">These are `Func<>`, `Action<>` and `Predicate<>`, and they can be used in various places throughout the .NET APIs without the need to define new delegate types.</span></span> <span data-ttu-id="94518-113">当然，从这三者的签名可以看出它们之间存在某些差异，主要影响其既定用途：</span><span class="sxs-lookup"><span data-stu-id="94518-113">Of course, there are some differences between the three as you will see in their signatures which mostly have to do with the way they were meant to be used:</span></span>

*   <span data-ttu-id="94518-114">`Action<>` 用于需要使用委托参数执行操作的情况。</span><span class="sxs-lookup"><span data-stu-id="94518-114">`Action<>` is used when there is a need to perform an action using the arguments of the delegate.</span></span>
*   <span data-ttu-id="94518-115">`Func<>` 通常用于现有转换的情况，也就是说需要将委托参数转换为其他结果时。</span><span class="sxs-lookup"><span data-stu-id="94518-115">`Func<>` is used usually when you have a transformation on hand, that is, you need to transform the arguments of the delegate into a different result.</span></span> <span data-ttu-id="94518-116">最好的示例就是投影。</span><span class="sxs-lookup"><span data-stu-id="94518-116">Projections are a prime example of this.</span></span>
*   <span data-ttu-id="94518-117">`Predicate<>` 用于需要确定参数是否满足委托条件的情况。</span><span class="sxs-lookup"><span data-stu-id="94518-117">`Predicate<>` is used when you need to determine if the argument satisfies the condition of the delegate.</span></span> <span data-ttu-id="94518-118">也可将其写作 `Func<T, bool>`。</span><span class="sxs-lookup"><span data-stu-id="94518-118">It can also be written as a `Func<T, bool>`.</span></span>

<span data-ttu-id="94518-119">现在可使用 `Func<>` 委托而非自定义类型重新编写上述示例。</span><span class="sxs-lookup"><span data-stu-id="94518-119">We can now take our example above and rewrite it using the `Func<>` delegate instead of a custom type.</span></span> <span data-ttu-id="94518-120">程序将照旧继续运行。</span><span class="sxs-lookup"><span data-stu-id="94518-120">The program will continue running exactly the same.</span></span>

```csharp
using System;
using System.Linq;

public class Program
{
    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Func<string, string> rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

<span data-ttu-id="94518-121">对于此简单示例而言，在 `Main` 方法之外定义方法似乎有些多余。</span><span class="sxs-lookup"><span data-stu-id="94518-121">For this simple example, having a method defined outside of the `Main` method seems a bit superfluous.</span></span> <span data-ttu-id="94518-122">因此 .NET Framework 2.0 引入了**匿名委托**的概念。</span><span class="sxs-lookup"><span data-stu-id="94518-122">It is because of this that .NET Framework 2.0 introduced the concept of **anonymous delegates**.</span></span> <span data-ttu-id="94518-123">在其支持下，可创建“内联”委托，而无需指定任何其他类型或方法。</span><span class="sxs-lookup"><span data-stu-id="94518-123">With their support you are able to create "inline" delegates without having to specify any additional type or method.</span></span> <span data-ttu-id="94518-124">只需在所需位置内联委托的定义即可。</span><span class="sxs-lookup"><span data-stu-id="94518-124">You simply inline the definition of the delegate where you need it.</span></span>

<span data-ttu-id="94518-125">例如，要进行切换并使用匿名委托筛选出只有偶数的列表，然后将其打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="94518-125">For an example, we are going to switch it up and use our anonymous delegate to filter out a list of only even numbers and then print them to the console.</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(
          delegate (int no)
          {
              return (no % 2 == 0);
          }
        );

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

<span data-ttu-id="94518-126">如你所见，该委托的正文只是一组表达式，其他所有委托也是如此。</span><span class="sxs-lookup"><span data-stu-id="94518-126">As you can see, the body of the delegate is just a set of expressions, as any other delegate.</span></span> <span data-ttu-id="94518-127">但它并非单独定义，而是在调用 <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> 方法时临时引入。</span><span class="sxs-lookup"><span data-stu-id="94518-127">But instead of it being a separate definition, we’ve introduced it _ad hoc_ in our call to the <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="94518-128">但是，即使使用此方法，仍有许多可以丢弃的代码。</span><span class="sxs-lookup"><span data-stu-id="94518-128">However, even with this approach, there is still much code that we can throw away.</span></span> <span data-ttu-id="94518-129">此时就需要使用 **lambda 表达式**。</span><span class="sxs-lookup"><span data-stu-id="94518-129">This is where **lambda expressions** come into play.</span></span>

<span data-ttu-id="94518-130">lambda 表达式（或简称“lambda”）在 C# 3.0 中作为语言集成查询的 (LINQ) 核心构建基块被首次引入。</span><span class="sxs-lookup"><span data-stu-id="94518-130">Lambda expressions, or just "lambdas" for short, were introduced first in C# 3.0, as one of the core building blocks of Language Integrated Query (LINQ).</span></span> <span data-ttu-id="94518-131">这种表达式只是使用委托的更方便的语法。</span><span class="sxs-lookup"><span data-stu-id="94518-131">They are just a more convenient syntax for using delegates.</span></span> <span data-ttu-id="94518-132">它们将声明签名和方法正文，但在分配到委托之前没有自己的正式标识。</span><span class="sxs-lookup"><span data-stu-id="94518-132">They declare a signature and a method body, but don’t have an formal identity of their own, unless they are assigned to a delegate.</span></span> <span data-ttu-id="94518-133">与委托不同，可将其作为事件注册的左侧内容或在各种 LINQ 子句和方法中直接分配。</span><span class="sxs-lookup"><span data-stu-id="94518-133">Unlike delegates, they can be directly assigned as the left-hand side of event registration or in various LINQ clauses and methods.</span></span>

<span data-ttu-id="94518-134">由于 lambda 表达式只是指定委托的另一种方式，因此应可重新编写上述示例，令其使用 lambda 表达式而不是匿名委托。</span><span class="sxs-lookup"><span data-stu-id="94518-134">Since a lambda expression is just another way of specifying a delegate, we should be able to rewrite the above sample to use a lambda expression instead of an anonymous delegate.</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(i => i % 2 == 0);

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

<span data-ttu-id="94518-135">在前面的示例中，所使用的 Lambda 表达式为 `i => i % 2 == 0`。</span><span class="sxs-lookup"><span data-stu-id="94518-135">In the preceding example, the lambda expression used is `i => i % 2 == 0`.</span></span> <span data-ttu-id="94518-136">再次强调，它只是使用委托的一种**非常**方便的语法，因此其实际行为与使用匿名委托时相同。</span><span class="sxs-lookup"><span data-stu-id="94518-136">Again, it is just a **very** convenient syntax for using delegates, so what happens under the covers is similar to what happens with the anonymous delegate.</span></span>

<span data-ttu-id="94518-137">再次强调，lambda 只是委托，这意味着可将其顺利用作事件处理程序，如以下代码片段所示。</span><span class="sxs-lookup"><span data-stu-id="94518-137">Again, lambdas are just delegates, which means that they can be used as an event handler without any problems, as the following code snippet illustrates.</span></span>

```csharp
public MainWindow()
{
    InitializeComponent();

    Loaded += (o, e) =>
    {
        this.Title = "Loaded";
    };
}
```

## <a name="further-reading-and-resources"></a><span data-ttu-id="94518-138">其他阅读材料和资源</span><span class="sxs-lookup"><span data-stu-id="94518-138">Further reading and resources</span></span>

*   [<span data-ttu-id="94518-139">委托</span><span class="sxs-lookup"><span data-stu-id="94518-139">Delegates</span></span>](../../docs/csharp/programming-guide/delegates/index.md)
*   [<span data-ttu-id="94518-140">匿名函数</span><span class="sxs-lookup"><span data-stu-id="94518-140">Anonymous Functions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
*   [<span data-ttu-id="94518-141">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="94518-141">Lambda expressions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
