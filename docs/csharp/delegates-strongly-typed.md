---
title: 强类型委托
description: 了解创建需要委托的功能时，如何使用泛型委托类型声明自定义类型。
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 564a683d-352b-4e57-8bac-b466529daf6b
ms.openlocfilehash: efdbef39d0e6bf2f07cde2c9621cec173e921752
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73037358"
---
# <a name="strongly-typed-delegates"></a><span data-ttu-id="00b85-103">强类型委托</span><span class="sxs-lookup"><span data-stu-id="00b85-103">Strongly Typed Delegates</span></span>

[<span data-ttu-id="00b85-104">上一篇</span><span class="sxs-lookup"><span data-stu-id="00b85-104">Previous</span></span>](delegate-class.md)

<span data-ttu-id="00b85-105">在上一篇文章中，使用 `delegate` 关键字创建了特定委托类型。</span><span class="sxs-lookup"><span data-stu-id="00b85-105">In the previous article, you saw that you create specific delegate types using the `delegate` keyword.</span></span> 

<span data-ttu-id="00b85-106">抽象的 Delegate 类为松散耦合和调用提供基础结构。</span><span class="sxs-lookup"><span data-stu-id="00b85-106">The abstract Delegate class provide the infrastructure for loose coupling and invocation.</span></span> <span data-ttu-id="00b85-107">通过包含和实施添加到委托对象的调用列表的方法的类型安全性，具体的委托类型将变得更加有用。</span><span class="sxs-lookup"><span data-stu-id="00b85-107">Concrete Delegate types become much more useful by embracing and enforcing type safety for the methods that are added to the invocation list for a delegate object.</span></span> <span data-ttu-id="00b85-108">使用 `delegate` 关键字并定义具体的委托类型时，编译器将生成这些方法。</span><span class="sxs-lookup"><span data-stu-id="00b85-108">When you use the `delegate` keyword and define a concrete delegate type, the compiler generates those methods.</span></span>

<span data-ttu-id="00b85-109">实际上，无论何时需要不同的方法签名，这都会创建新的委托类型。</span><span class="sxs-lookup"><span data-stu-id="00b85-109">In practice, this would lead to creating new delegate types whenever you need a different method signature.</span></span> <span data-ttu-id="00b85-110">一段时间后此操作可能变得繁琐。</span><span class="sxs-lookup"><span data-stu-id="00b85-110">This work could get tedious after a time.</span></span> <span data-ttu-id="00b85-111">每个新功能都需要新的委托类型。</span><span class="sxs-lookup"><span data-stu-id="00b85-111">Every new feature requires new delegate types.</span></span>

<span data-ttu-id="00b85-112">幸运的是，没有必要这样做。</span><span class="sxs-lookup"><span data-stu-id="00b85-112">Thankfully, this isn't necessary.</span></span> <span data-ttu-id="00b85-113">.NET Core 框架包含几个在需要委托类型时可重用的类型。</span><span class="sxs-lookup"><span data-stu-id="00b85-113">The .NET Core framework contains several types that you can reuse whenever you need delegate types.</span></span> <span data-ttu-id="00b85-114">这些是[泛型](programming-guide/generics/index.md)定义，因此需要新的方法声明时可以声明自定义。</span><span class="sxs-lookup"><span data-stu-id="00b85-114">These are [generic](programming-guide/generics/index.md) definitions so you can declare customizations when you need new method declarations.</span></span> 

<span data-ttu-id="00b85-115">第一个类型是 <xref:System.Action> 类型和一些变体：</span><span class="sxs-lookup"><span data-stu-id="00b85-115">The first of these types is the <xref:System.Action> type, and several variations:</span></span>

```csharp
public delegate void Action();
public delegate void Action<in T>(T arg);
public delegate void Action<in T1, in T2>(T1 arg1, T2 arg2);
// Other variations removed for brevity.
```

<span data-ttu-id="00b85-116">有关协方差的文章中介绍了泛型类型参数的 `in` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="00b85-116">The `in` modifier on the generic type argument is covered in the article on covariance.</span></span>

<span data-ttu-id="00b85-117">`Action` 委托的变体可包含多达 16 个参数，如 <xref:System.Action%6016>。</span><span class="sxs-lookup"><span data-stu-id="00b85-117">There are variations of the `Action` delegate that contain up to 16 arguments such as <xref:System.Action%6016>.</span></span>
<span data-ttu-id="00b85-118">重要的是，这些定义对每个委托参数将使用不同的泛型参数：这样可以提供最大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="00b85-118">It's important that these definitions use different generic arguments for each of the delegate arguments: That gives you maximum flexibility.</span></span> <span data-ttu-id="00b85-119">方法参数不需要但可能是相同的类型。</span><span class="sxs-lookup"><span data-stu-id="00b85-119">The method arguments need not be, but may be, the same type.</span></span>

<span data-ttu-id="00b85-120">对任何具有 void 返回类型的委托类型使用一种 `Action` 类型。</span><span class="sxs-lookup"><span data-stu-id="00b85-120">Use one of the `Action` types for any delegate type that has a void return type.</span></span>

<span data-ttu-id="00b85-121">此框架还包括几种可用于返回值的委托类型的泛型委托类型：</span><span class="sxs-lookup"><span data-stu-id="00b85-121">The framework also includes several generic delegate types that you can use for delegate types that return values:</span></span>

```csharp
public delegate TResult Func<out TResult>();
public delegate TResult Func<in T1, out TResult>(T1 arg);
public delegate TResult Func<in T1, in T2, out TResult>(T1 arg1, T2 arg2);
// Other variations removed for brevity
```

<span data-ttu-id="00b85-122">有关协方差的文章中介绍了所产生的泛型类型参数的 `out` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="00b85-122">The `out` modifier on the result generic type argument is covered in the article on covariance.</span></span>

<span data-ttu-id="00b85-123">`Func` 委托的变体可包含多达 16 个输入参数，如 <xref:System.Func%6017>。</span><span class="sxs-lookup"><span data-stu-id="00b85-123">There are variations of the `Func` delegate with up to 16 input arguments such as <xref:System.Func%6017>.</span></span>
<span data-ttu-id="00b85-124">按照约定，结果的类型始终是所有 `Func` 声明中的最后一个类型参数。</span><span class="sxs-lookup"><span data-stu-id="00b85-124">The type of the result is always the last type parameter in all the `Func` declarations, by convention.</span></span>

<span data-ttu-id="00b85-125">对任何返回值的委托类型使用一种 `Func` 类型。</span><span class="sxs-lookup"><span data-stu-id="00b85-125">Use one of the `Func` types for any delegate type that returns a value.</span></span>

<span data-ttu-id="00b85-126">还有一种专门的 <xref:System.Predicate%601></span><span class="sxs-lookup"><span data-stu-id="00b85-126">There's also a specialized <xref:System.Predicate%601></span></span> 
<span data-ttu-id="00b85-127">委托类型，可返回单个值的测试结果：</span><span class="sxs-lookup"><span data-stu-id="00b85-127">type for a delegate that returns a test on a single value:</span></span>

```csharp
public delegate bool Predicate<in T>(T obj);
```

<span data-ttu-id="00b85-128">你可能会注意到对于任何 `Predicate` 类型，均存在一个在结构上等效的 `Func` 类型，例如：</span><span class="sxs-lookup"><span data-stu-id="00b85-128">You may notice that for any `Predicate` type, a structurally equivalent `Func` type exists For example:</span></span>

```csharp
Func<string, bool> TestForString;
Predicate<string> AnotherTestForString;
```

<span data-ttu-id="00b85-129">你可能认为这两种类型是等效的。</span><span class="sxs-lookup"><span data-stu-id="00b85-129">You might think these two types are equivalent.</span></span> <span data-ttu-id="00b85-130">它们不是。</span><span class="sxs-lookup"><span data-stu-id="00b85-130">They are not.</span></span>
<span data-ttu-id="00b85-131">这两个变量不能互换使用。</span><span class="sxs-lookup"><span data-stu-id="00b85-131">These two variables cannot be used interchangeably.</span></span> <span data-ttu-id="00b85-132">一种类型的变量无法赋予另一种类型。</span><span class="sxs-lookup"><span data-stu-id="00b85-132">A variable of one type cannot be assigned the other type.</span></span> <span data-ttu-id="00b85-133">C# 类型系统使用的是已定义类型的名称，而不是其结构。</span><span class="sxs-lookup"><span data-stu-id="00b85-133">The C# type system uses the names of the defined types, not the structure.</span></span>

<span data-ttu-id="00b85-134">.NET Core 库中的所有这些委托类型定义意味着你不需要为创建的任何需要委托的新功能定义新的委托类型。</span><span class="sxs-lookup"><span data-stu-id="00b85-134">All these delegate type definitions in the .NET Core Library should mean that you do not need to define a new delegate type for any new feature you create that requires delegates.</span></span> <span data-ttu-id="00b85-135">这些泛型定义应已提供大多数情况下所需要的所有委托类型。</span><span class="sxs-lookup"><span data-stu-id="00b85-135">These generic definitions should provide all the delegate types you need under most situations.</span></span> <span data-ttu-id="00b85-136">只需使用所需的类型参数实例化其中一个类型。</span><span class="sxs-lookup"><span data-stu-id="00b85-136">You can simply instantiate one of these types with the required type parameters.</span></span> <span data-ttu-id="00b85-137">对于可成为泛型算法的算法，这些委托可以用作泛型类型。</span><span class="sxs-lookup"><span data-stu-id="00b85-137">In the case of algorithms that can be made generic, these delegates can be used as generic types.</span></span> 

<span data-ttu-id="00b85-138">这样可以节省时间，并尽量减少为了使用委托而需要创建的新类型的数目。</span><span class="sxs-lookup"><span data-stu-id="00b85-138">This should save time, and minimize the number of new types that you need to create in order to work with delegates.</span></span>

<span data-ttu-id="00b85-139">在下一篇文章中，你将看到在实践中使用委托的几种通用模式。</span><span class="sxs-lookup"><span data-stu-id="00b85-139">In the next article, you'll see several common patterns for working with delegates in practice.</span></span>

[<span data-ttu-id="00b85-140">下一篇</span><span class="sxs-lookup"><span data-stu-id="00b85-140">Next</span></span>](delegates-patterns.md)
