---
title: 泛型类型（泛型）概述
description: 了解泛型如何充当代码模板，通过该模板可定义类型安全数据结构，无需处理实际数据类型。
author: kuhlenh
ms.author: wiwagn
ms.date: 10/09/2018
ms.openlocfilehash: 3c1181f5be717f328ae906c6009fc8a34b904c89
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2019
ms.locfileid: "58465420"
---
# <a name="generic-types-overview"></a><span data-ttu-id="4e39a-103">泛型类型概述</span><span class="sxs-lookup"><span data-stu-id="4e39a-103">Generic types overview</span></span>

<span data-ttu-id="4e39a-104">在 .NET 中，开发人员随时会使用泛型，有时隐式使用，有时显式使用。</span><span class="sxs-lookup"><span data-stu-id="4e39a-104">Developers use generics all the time in .NET, whether implicitly or explicitly.</span></span> <span data-ttu-id="4e39a-105">在 .NET 中使用 LINQ 时，你是否曾经注意到，使用的正是 <xref:System.Collections.Generic.IEnumerable%601>？</span><span class="sxs-lookup"><span data-stu-id="4e39a-105">When you use LINQ in .NET, did you ever notice that you're working with <xref:System.Collections.Generic.IEnumerable%601>?</span></span> <span data-ttu-id="4e39a-106">或者，你是否曾经看到过有关使用实体框架来与数据库通信的“泛型存储库”在线示例，其中的大多数方法返回 IQueryable\<T>？</span><span class="sxs-lookup"><span data-stu-id="4e39a-106">Or if you ever saw an online sample of a "generic repository" for talking to databases using Entity Framework, did you see that most methods return IQueryable\<T>?</span></span> <span data-ttu-id="4e39a-107">你可能很想知道，这些示例中的 T 是什么意思，为什么要使用它？</span><span class="sxs-lookup"><span data-stu-id="4e39a-107">You may have wondered what the **T** is in these examples and why it's in there.</span></span>

<span data-ttu-id="4e39a-108">泛型在 .NET Framework 2.0 中首次引入，它本质上是一个“代码模板”，可让开发人员定义[类型安全](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100))数据结构，无需处理实际数据类型。</span><span class="sxs-lookup"><span data-stu-id="4e39a-108">First introduced in the .NET Framework 2.0, **generics** are essentially a "code template" that allows developers to define [type-safe](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) data structures without committing to an actual data type.</span></span> <span data-ttu-id="4e39a-109">例如，<xref:System.Collections.Generic.List%601> 是一个可以声明的[泛型集合](xref:System.Collections.Generic)，可与 `List<int>`、`List<string>` 或 `List<Person>` 等任何类型结合使用。</span><span class="sxs-lookup"><span data-stu-id="4e39a-109">For example, <xref:System.Collections.Generic.List%601> is a [generic collection](xref:System.Collections.Generic) that can be declared and used with any type, such as `List<int>`, `List<string>`, or `List<Person>`.</span></span>

<span data-ttu-id="4e39a-110">为方便理解泛型的作用，让我们看看添加泛型之前和之后的一个特定类：<xref:System.Collections.ArrayList>。</span><span class="sxs-lookup"><span data-stu-id="4e39a-110">To understand why generics are useful, let's take a look at a specific class before and after adding generics: <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="4e39a-111">在 .NET Framework 1.0 中，`ArrayList` 元素属于 <xref:System.Object> 类型。</span><span class="sxs-lookup"><span data-stu-id="4e39a-111">In .NET Framework 1.0, the `ArrayList` elements were of type <xref:System.Object>.</span></span> <span data-ttu-id="4e39a-112">这意味着添加的任何元素都会以静默方式转换为 `Object`。</span><span class="sxs-lookup"><span data-stu-id="4e39a-112">This meant that any element added was silently converted into an `Object`.</span></span> <span data-ttu-id="4e39a-113">从列表读取元素时，会发生相同的情况。</span><span class="sxs-lookup"><span data-stu-id="4e39a-113">The same would happen when reading the elements from the list.</span></span> <span data-ttu-id="4e39a-114">此过程称为[装箱和取消装箱](../csharp/programming-guide/types/boxing-and-unboxing.md)，它会影响性能。</span><span class="sxs-lookup"><span data-stu-id="4e39a-114">This process is known as [boxing and unboxing](../csharp/programming-guide/types/boxing-and-unboxing.md), and it impacts performance.</span></span> <span data-ttu-id="4e39a-115">但更重要的是，在编译时无法确定列表中的数据类型。</span><span class="sxs-lookup"><span data-stu-id="4e39a-115">More than that, however, there's no way to determine the type of data in the list at compile time.</span></span> <span data-ttu-id="4e39a-116">这就使得某些代码不太可靠。</span><span class="sxs-lookup"><span data-stu-id="4e39a-116">This makes for some fragile code.</span></span> <span data-ttu-id="4e39a-117">泛型解决了此问题，它可以定义每个列表实例将要包含的数据类型。</span><span class="sxs-lookup"><span data-stu-id="4e39a-117">Generics solve this problem by defining the type of data each instance of list will contain.</span></span> <span data-ttu-id="4e39a-118">例如，只能将整数添加到 `List<int>`，只能将人员添加到 `List<Person>`。</span><span class="sxs-lookup"><span data-stu-id="4e39a-118">For example, you can only add integers to `List<int>` and only add Persons to `List<Person>`.</span></span>

<span data-ttu-id="4e39a-119">泛型还可以在运行时使用。</span><span class="sxs-lookup"><span data-stu-id="4e39a-119">Generics are also available at runtime.</span></span> <span data-ttu-id="4e39a-120">这意味着，运行时知道你要使用的数据结构类型，并可以更高效地将数据结构存储在内存中。</span><span class="sxs-lookup"><span data-stu-id="4e39a-120">This means the runtime knows what type of data structure you're using and can store it in memory more efficiently.</span></span>

<span data-ttu-id="4e39a-121">下面的示例是一个小程序，演示了在运行时如何有效地了解数据结构类型：</span><span class="sxs-lookup"><span data-stu-id="4e39a-121">The following example is a small program that illustrates the efficiency of knowing the data structure type at runtime:</span></span>

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

<span data-ttu-id="4e39a-122">此程序将生成类似下面的输出：</span><span class="sxs-lookup"><span data-stu-id="4e39a-122">This program produces output similar to the following:</span></span>

```console
Generic Sort: System.Collections.Generic.List`1[System.Int32]
 Time taken: 0.0034ms
Non-Generic Sort: System.Collections.ArrayList
 Time taken: 0.2592ms
```

<span data-ttu-id="4e39a-123">在此处可以看到的第一个优点是，泛型列表的排序比非泛型列表要快得多。</span><span class="sxs-lookup"><span data-stu-id="4e39a-123">The first thing you can notice here is that sorting the generic list is significantly faster than sorting the non-generic list.</span></span> <span data-ttu-id="4e39a-124">还可以看到，泛型列表的类型是不同的 ([System.Int32])，而非泛型列表的类型已通用化。</span><span class="sxs-lookup"><span data-stu-id="4e39a-124">You might also notice that the type for the generic list is distinct ([System.Int32]), whereas the type for the non-generic list is generalized.</span></span> <span data-ttu-id="4e39a-125">由于运行时知道泛型 `List<int>` 的类型是 <xref:System.Int32>，因此可以将列表元素存储在内存中的基础整数数组内；而非泛型 `ArrayList` 必须将每个列表元素强制转换为对象。</span><span class="sxs-lookup"><span data-stu-id="4e39a-125">Because the runtime knows the generic `List<int>` is of type <xref:System.Int32>, it can store the list elements in an underlying integer array in memory while the non-generic `ArrayList` has to cast each list element to an object.</span></span> <span data-ttu-id="4e39a-126">如本示例中所示，多余的强制转换会占用时间，降低列表排序的速度。</span><span class="sxs-lookup"><span data-stu-id="4e39a-126">As this example shows, the extra casts take up time and slow down the list sort.</span></span>

<span data-ttu-id="4e39a-127">运行时知道泛型类型的另一个优点是可以改善调试体验。</span><span class="sxs-lookup"><span data-stu-id="4e39a-127">An additional advantage of the runtime knowing the type of your generic is a better debugging experience.</span></span> <span data-ttu-id="4e39a-128">在 C# 中调试泛型时，可以知道数据结构中每个元素的类型。</span><span class="sxs-lookup"><span data-stu-id="4e39a-128">When you're debugging a generic in C#, you know what type each element is in your data structure.</span></span> <span data-ttu-id="4e39a-129">如果不使用泛型，则无从知道每个元素的类型是什么。</span><span class="sxs-lookup"><span data-stu-id="4e39a-129">Without generics, you would have no idea what type each element was.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e39a-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e39a-130">See also</span></span>

- [<span data-ttu-id="4e39a-131">C# 编程指南 - 泛型</span><span class="sxs-lookup"><span data-stu-id="4e39a-131">C# Programming Guide - Generics</span></span>](../../docs/csharp/programming-guide/generics/index.md)
