---
title: "泛型类型（泛型）概述"
description: "了解泛型如何充当代码模板，通过该模板可定义类型安全数据结构，无需处理实际数据类型。"
keywords: .NET, .NET Core
author: kuhlenh
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: a315b111-8e48-446c-ab19-acb6405894a7
ms.translationtype: HT
ms.sourcegitcommit: 75642ff3beb4462faa9068db76c89f3cb5f75ab8
ms.openlocfilehash: 08b8de2fe17a0032a1c1180667f39b1d6ce0feb6
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---

# <a name="generic-types-generics-overview"></a><span data-ttu-id="008a0-104">泛型类型（泛型）概述</span><span class="sxs-lookup"><span data-stu-id="008a0-104">Generic Types (Generics) Overview</span></span>

<span data-ttu-id="008a0-105">在 C# 中，我们随时会使用泛型，有时隐式使用，有时显式使用。</span><span class="sxs-lookup"><span data-stu-id="008a0-105">We use generics all the time in C#, whether implicitly or explicitly.</span></span> <span data-ttu-id="008a0-106">在 C# 中使用 LINQ 时，你是否曾经注意到，使用的正是 IEnumerable<T>？</span><span class="sxs-lookup"><span data-stu-id="008a0-106">When you use LINQ in C#, did you ever notice that you are working with IEnumerable<T>?</span></span> <span data-ttu-id="008a0-107">或者，你是否曾经看到过有关使用实体框架来与数据库通信的“泛型存储库”在线示例，其中的大多数方法返回 IQueryable<T>？</span><span class="sxs-lookup"><span data-stu-id="008a0-107">Or if you ever saw an online sample of a "generic repository" for talking to databases using Entity Framework, did you see that most methods return IQueryable<T>?</span></span> <span data-ttu-id="008a0-108">你可能很想知道，这些示例中的 **T** 是什么意思，为什么要使用它？</span><span class="sxs-lookup"><span data-stu-id="008a0-108">You may have wondered what the **T** is in these examples and why is it in there?</span></span>

<span data-ttu-id="008a0-109">泛型最初在 .NET Framework 2.0 中引入，涉及到对 C# 语言和公共语言运行时 (CLR) 的更改。</span><span class="sxs-lookup"><span data-stu-id="008a0-109">First introduced to the .NET Framework 2.0, generics involved changes to both the C# language and the Common Language Runtime (CLR).</span></span> <span data-ttu-id="008a0-110">泛型本质上是一个“代码模板”，可让开发人员定义[类型安全](https://msdn.microsoft.com/library/hbzz1a9a.aspx)数据结构，无需处理实际数据类型。</span><span class="sxs-lookup"><span data-stu-id="008a0-110">**Generics** are essentially a "code template" that allows developers to define [type-safe](https://msdn.microsoft.com/library/hbzz1a9a.aspx) data structures without committing to an actual data type.</span></span> <span data-ttu-id="008a0-111">例如，`List<T>` 是一个可以声明的[泛型集合](xref:System.Collections.Generic)，可与 `List<int>`、`List<string>`、`List<Person>` 等任何类型结合使用。</span><span class="sxs-lookup"><span data-stu-id="008a0-111">For example, `List<T>` is a [Generic Collection](xref:System.Collections.Generic) that can be declared and used with any type: `List<int>`, `List<string>`, `List<Person>`, etc.</span></span>

<span data-ttu-id="008a0-112">那么，泛型到底是什么？</span><span class="sxs-lookup"><span data-stu-id="008a0-112">So, what’s the point?</span></span> <span data-ttu-id="008a0-113">它又有什么作用？</span><span class="sxs-lookup"><span data-stu-id="008a0-113">Why are generics useful?</span></span> <span data-ttu-id="008a0-114">为方便理解，让我们看看添加泛型之前和之后的某个特定类。</span><span class="sxs-lookup"><span data-stu-id="008a0-114">In order to understand this, we need to take a look at a specific class before and after adding generics.</span></span> <span data-ttu-id="008a0-115">先看一下 `ArrayList`。</span><span class="sxs-lookup"><span data-stu-id="008a0-115">Let’s look at the `ArrayList`.</span></span> <span data-ttu-id="008a0-116">在 C# 1.0 中，`ArrayList` 元素的类型为 `object`。</span><span class="sxs-lookup"><span data-stu-id="008a0-116">In C# 1.0, the `ArrayList` elements were of type `object`.</span></span> <span data-ttu-id="008a0-117">这意味着，添加的任何元素都将以静默方式转换为 `object`；从列表中读取元素时也会发生相同的情况（此过程分别称为[装箱](https://msdn.microsoft.com/library/yz2be5wk.aspx)和取消装箱）。</span><span class="sxs-lookup"><span data-stu-id="008a0-117">This meant that any element that was added was silently converted into an `object`; same thing happens on reading the elements from the list (this process is known as [boxing](https://msdn.microsoft.com/library/yz2be5wk.aspx) and unboxing respectively).</span></span> <span data-ttu-id="008a0-118">装箱和取消装箱会给性能造成影响。</span><span class="sxs-lookup"><span data-stu-id="008a0-118">Boxing and unboxing have an impact of performance.</span></span> <span data-ttu-id="008a0-119">不仅如此，在编译时无法知道列表中的实际数据类型是什么。</span><span class="sxs-lookup"><span data-stu-id="008a0-119">More than that, however, there is no way to tell at compile time what is the actual type of the data in the list.</span></span> <span data-ttu-id="008a0-120">这就使得某些代码不太可靠。</span><span class="sxs-lookup"><span data-stu-id="008a0-120">This makes for some fragile code.</span></span> <span data-ttu-id="008a0-121">泛型解决了此问题，它可以提供有关每个列表实例将要包含的数据类型的附加信息。</span><span class="sxs-lookup"><span data-stu-id="008a0-121">Generics solve this problem by providing additional information the type of data each instance of list will contain.</span></span> <span data-ttu-id="008a0-122">简单而言，只能将整数添加到 `List<int>`，只能将人员添加到 `List<Person>`，等等。</span><span class="sxs-lookup"><span data-stu-id="008a0-122">Put simply, you can only add integers to `List<int>` and only add Persons to `List<Person>`, etc.</span></span>

<span data-ttu-id="008a0-123">泛型还可以在运行时使用，称为**具体化**。</span><span class="sxs-lookup"><span data-stu-id="008a0-123">Generics are also available at runtime, or **reified**.</span></span> <span data-ttu-id="008a0-124">这意味着，运行时知道你要使用的数据结构类型，并可以更高效地将数据结构存储在内存中。</span><span class="sxs-lookup"><span data-stu-id="008a0-124">This means the runtime knows what type of data structure you are using and can store it in memory more efficiently.</span></span>

<span data-ttu-id="008a0-125">下面这个小程序演示了在运行时如何有效地了解数据结构类型：</span><span class="sxs-lookup"><span data-stu-id="008a0-125">Here is a small program that illustrates the efficiency of knowing the data structure type at runtime:</span></span>

```csharp
  using System;
  using System.Collections;
  using System.Collections.Generic;
  using System.Diagnostics;

  namespace GenericsExample {
    class Program {
      static void Main(string[] args) {
        //generic list
        List<int> ListGeneric = new List<int> { 5, 9, 1, 4 };
        //non-generic list
        ArrayList ListNonGeneric = new ArrayList { 5, 9, 1, 4 };
        // timer for generic list sort
        Stopwatch s = Stopwatch.StartNew();
        ListGeneric.Sort();
        s.Stop();
        Console.WriteLine($"Generic Sort: {ListGeneric}  \n Time taken: {s.Elapsed.TotalMilliseconds}ms");

        //timer for non-generic list sort
        Stopwatch s2 = Stopwatch.StartNew();
        ListNonGeneric.Sort();
        s2.Stop();
        Console.WriteLine($"Non-Generic Sort: {ListNonGeneric}  \n Time taken: {s2.Elapsed.TotalMilliseconds}ms");
        Console.ReadLine();
      }
    }
  }
```

<span data-ttu-id="008a0-126">此程序生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="008a0-126">This program yields the following output:</span></span>

```console
Generic Sort: System.Collections.Generic.List\`1[System.Int32] Time taken: 0.0789ms
Non-Generic Sort: System.Collections.ArrayList Time taken: 2.4324ms
```

<span data-ttu-id="008a0-127">在此处可以看到的第一个优点是，泛型列表的排序比非泛型列表要快得多。</span><span class="sxs-lookup"><span data-stu-id="008a0-127">The first thing you notice here is that sorting the generic list is significantly faster than for the non-generic list.</span></span> <span data-ttu-id="008a0-128">还可以看到，泛型列表的类型是不同的 ([System.Int32])，而非泛型列表的类型已通用化。</span><span class="sxs-lookup"><span data-stu-id="008a0-128">You might also notice that the type for the generic list is distinct ([System.Int32]) whereas the type for the non-generic list is generalized.</span></span> <span data-ttu-id="008a0-129">由于运行时知道泛型 `List<int>` 的类型是 int，因此可以将列表元素存储在内存中的基础整数数组内；而非泛型 `ArrayList` 必须将每个列表元素强制转换为对象并将其存储在内存中的对象数组内。</span><span class="sxs-lookup"><span data-stu-id="008a0-129">Because the runtime knows the generic `List<int>` is of type int, it can store the list elements in an underlying integer array in memory while the non-generic `ArrayList` has to cast each list element as an object as stored in an object array in memory.</span></span> <span data-ttu-id="008a0-130">如本示例中所示，多余的强制转换会占用时间，降低列表排序的速度。</span><span class="sxs-lookup"><span data-stu-id="008a0-130">As shown through this example, the extra castings take up time and slow down the list sort.</span></span>

<span data-ttu-id="008a0-131">运行时知道泛型类型的最后一个优点是可以改善调试体验。</span><span class="sxs-lookup"><span data-stu-id="008a0-131">The last useful thing about the runtime knowing the type of your generic is a better debugging experience.</span></span> <span data-ttu-id="008a0-132">在 C# 中调试泛型时，可以知道数据结构中每个元素的类型。</span><span class="sxs-lookup"><span data-stu-id="008a0-132">When you are debugging a generic in C#, you know what type each element is in your data structure.</span></span> <span data-ttu-id="008a0-133">如果不使用泛型，则无从知道每个元素的类型是什么。</span><span class="sxs-lookup"><span data-stu-id="008a0-133">Without generics, you would have no idea what type each element was.</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="008a0-134">其他阅读材料和资源</span><span class="sxs-lookup"><span data-stu-id="008a0-134">Further reading and resources</span></span>

*   [<span data-ttu-id="008a0-135">C# 泛型简介</span><span class="sxs-lookup"><span data-stu-id="008a0-135">An Introduction to C# Generics</span></span>](https://msdn.microsoft.com/library/ms379564.aspx)
*   [<span data-ttu-id="008a0-136">C# 编程指南 - 泛型</span><span class="sxs-lookup"><span data-stu-id="008a0-136">C# Programming Guide - Generics</span></span>](https://msdn.microsoft.com/library/512aeb7t.aspx)

