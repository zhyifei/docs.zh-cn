---
title: .NET 教程
description: .NET 的一些重要功能指导教程。
author: cartermp
ms.author: wiwagn
ms.date: 05/22/2017
ms.technology: dotnet-standard
ms.assetid: bbfe6465-329d-4982-869d-472e7ef85d93
ms.openlocfilehash: b1925397fb7cad5e55f992feaa5be2e2d837aac8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33592257"
---
# <a name="tour-of-net"></a><span data-ttu-id="cc425-103">.NET 教程</span><span class="sxs-lookup"><span data-stu-id="cc425-103">Tour of .NET</span></span>

<span data-ttu-id="cc425-104">.NET 是一个通用开发平台。</span><span class="sxs-lookup"><span data-stu-id="cc425-104">.NET is a general purpose development platform.</span></span> <span data-ttu-id="cc425-105">它具有几项关键功能，例如支持多种编程语言、异步和并发编程模型以及本机互操作性，可以支持跨多个平台的各种方案。</span><span class="sxs-lookup"><span data-stu-id="cc425-105">It has several key features, such as support for multiple programming languages, asynchronous and concurrent programming models, and native interoperability, which enable a wide range of scenarios across multiple platforms.</span></span>

<span data-ttu-id="cc425-106">本文还提供了 .NET 的一些关键功能的指导教程。</span><span class="sxs-lookup"><span data-stu-id="cc425-106">This article offers a guided tour through some of the key features of the .NET.</span></span> <span data-ttu-id="cc425-107">请参阅 [.NET 体系结构组件](components.md)主题，了解 .NET 的各体系结构部分及其用途。</span><span class="sxs-lookup"><span data-stu-id="cc425-107">See the [.NET Architectural Components](components.md) topic to learn about the architectural pieces of .NET and what they're used for.</span></span>

## <a name="how-to-run-the-code-samples"></a><span data-ttu-id="cc425-108">如何运行代码示例</span><span class="sxs-lookup"><span data-stu-id="cc425-108">How to run the code samples</span></span>

<span data-ttu-id="cc425-109">要了解如何设置开发环境以运行代码示例，请参阅[入门](get-started.md)主题。</span><span class="sxs-lookup"><span data-stu-id="cc425-109">To learn how to set up a development environment to run the code samples, see the [Getting Started](get-started.md) topic.</span></span> <span data-ttu-id="cc425-110">将代码示例从此页复制并粘贴到你的环境中以执行它们。</span><span class="sxs-lookup"><span data-stu-id="cc425-110">Copy and paste code samples from this page into your environment to execute them.</span></span> 

## <a name="programming-languages"></a><span data-ttu-id="cc425-111">编程语言</span><span class="sxs-lookup"><span data-stu-id="cc425-111">Programming languages</span></span>

<span data-ttu-id="cc425-112">.NET 支持多种编程语言。</span><span class="sxs-lookup"><span data-stu-id="cc425-112">.NET supports multiple programming languages.</span></span> <span data-ttu-id="cc425-113">.NET 实现可实现[公共语言基础结构 (CLI)](https://www.visualstudio.com/license-terms/ecma-c-common-language-infrastructure-standards/)，除其他事项外，它指定与语言无关的运行时和语言互操作性。</span><span class="sxs-lookup"><span data-stu-id="cc425-113">The .NET implementations implement the [Common Language Infrastructure (CLI)](https://www.visualstudio.com/license-terms/ecma-c-common-language-infrastructure-standards/), which among other things specifies a language-independent runtime and language interoperability.</span></span> <span data-ttu-id="cc425-114">这意味着可选择任意 .NET 语言在 .NET 上生成应用和服务。</span><span class="sxs-lookup"><span data-stu-id="cc425-114">This means that you choose any .NET language to build apps and services on .NET.</span></span>

<span data-ttu-id="cc425-115">Microsoft 积极开发和支持三种 .NET 语言：C#、F# 和 Visual Basic (VB)。</span><span class="sxs-lookup"><span data-stu-id="cc425-115">Microsoft actively develops and supports three .NET languages: C#, F#, and Visual Basic (VB).</span></span> 

* <span data-ttu-id="cc425-116">C# 是一种简单、强大、类型安全、面向对象的语言，同时保留了 C 语言的表达力度和简洁性。</span><span class="sxs-lookup"><span data-stu-id="cc425-116">C# is simple, powerful, type-safe, and object-oriented, while retaining the expressiveness and elegance of C-style languages.</span></span> <span data-ttu-id="cc425-117">熟悉 C 和类似语言的任何人在适应 C# 的过程中几乎不会遇到什么问题。</span><span class="sxs-lookup"><span data-stu-id="cc425-117">Anyone familiar with C and similar languages finds few problems in adapting to C#.</span></span> <span data-ttu-id="cc425-118">请查看 [C# 指南](../csharp/index.md)，了解有关 C# 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cc425-118">Check out the [C# Guide](../csharp/index.md) to learn more about C#.</span></span>

* <span data-ttu-id="cc425-119">F# 是一种跨平台、功能优先的编程语言，它也支持传统的面向对象的编程和命令式编程。</span><span class="sxs-lookup"><span data-stu-id="cc425-119">F# is a cross-platform, functional-first programming language that also supports traditional object-oriented and imperative programming.</span></span> <span data-ttu-id="cc425-120">请查看 [F# 指南](../fsharp/index.md)，了解有关 F# 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cc425-120">Check out the [F# Guide](../fsharp/index.md) to learn more about F#.</span></span>

* <span data-ttu-id="cc425-121">Visual Basic 是一种简单易学的语言，用于生成在 .NET 上运行的各种应用。</span><span class="sxs-lookup"><span data-stu-id="cc425-121">Visual Basic is an easy language to learn that you use to build a variety of apps that run on .NET.</span></span> <span data-ttu-id="cc425-122">在 .NET 语言中，VB 的语法最接近于人类的普通用语，通常使软件开发新手更容易上手。</span><span class="sxs-lookup"><span data-stu-id="cc425-122">Among the .NET languages, the syntax of VB is the closest to ordinary human language, often making it easier for people new to software development.</span></span>

## <a name="automatic-memory-management"></a><span data-ttu-id="cc425-123">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="cc425-123">Automatic memory management</span></span>

<span data-ttu-id="cc425-124">.NET 使用[垃圾回收 (GC)](garbagecollection/index.md) 为程序提供自动内存管理。</span><span class="sxs-lookup"><span data-stu-id="cc425-124">.NET uses [garbage collection (GC)](garbagecollection/index.md) to provide automatic memory management for programs.</span></span> <span data-ttu-id="cc425-125">GC 以一种“懒散”的方式进行内存管理，它优先考虑应用吞吐量，而不是立即回收内存。</span><span class="sxs-lookup"><span data-stu-id="cc425-125">The GC operates on a lazy approach to memory management, preferring app throughput to the immediate collection of memory.</span></span> <span data-ttu-id="cc425-126">要了解有关 .NET GC 的详细信息，请查看[垃圾回收 (GC) 的基础](garbagecollection/fundamentals.md)。</span><span class="sxs-lookup"><span data-stu-id="cc425-126">To learn more about the .NET GC, check out [Fundamentals of garbage collection (GC)](garbagecollection/fundamentals.md).</span></span>

<span data-ttu-id="cc425-127">以下两行代码都会分配内存：</span><span class="sxs-lookup"><span data-stu-id="cc425-127">The following two lines both allocate memory:</span></span>

[!code-csharp[MemoryManagement](../../samples/csharp/snippets/tour/MemoryManagement.csx#L1-L2)]

<span data-ttu-id="cc425-128">无法使用任何类似的关键字来取消分配内存，因为当垃圾回收器通过其计划的运行规则回收内存时，会自动取消分配。</span><span class="sxs-lookup"><span data-stu-id="cc425-128">There's no analogous keyword to de-allocate memory, as de-allocation happens automatically when the garbage collector reclaims the memory through its scheduled run.</span></span>

<span data-ttu-id="cc425-129">垃圾回收站是一种帮助确保内存安全的服务。</span><span class="sxs-lookup"><span data-stu-id="cc425-129">The garbage collector is one of the services that help ensure *memory safety*.</span></span> <span data-ttu-id="cc425-130">如果某个程序仅访问分配的内存，则该程序就是内存安全的。</span><span class="sxs-lookup"><span data-stu-id="cc425-130">A program is memory safe if it accesses only allocated memory.</span></span> <span data-ttu-id="cc425-131">例如，运行时可确保应用不会访问超过数组边界的未分配内存。</span><span class="sxs-lookup"><span data-stu-id="cc425-131">For instance, the runtime ensures that an app doesn't access unallocated memory beyond the bounds of an array.</span></span>

<span data-ttu-id="cc425-132">下例中，运行时引发 `InvalidIndexException` 异常，强制实现内存安全：</span><span class="sxs-lookup"><span data-stu-id="cc425-132">In the following example, the runtime throws an `InvalidIndexException` exception to enforce memory safety:</span></span>

[!code-csharp[MemoryManagement](../../samples/csharp/snippets/tour/MemoryManagement.csx#L4-L5)]

## <a name="working-with-unmanaged-resources"></a><span data-ttu-id="cc425-133">处理未托管的资源</span><span class="sxs-lookup"><span data-stu-id="cc425-133">Working with unmanaged resources</span></span>

<span data-ttu-id="cc425-134">部分对象会引用*未托管的资源*。</span><span class="sxs-lookup"><span data-stu-id="cc425-134">Some objects reference *unmanaged resources*.</span></span> <span data-ttu-id="cc425-135">未托管的资源是指不由 .NET 运行时自动维护的资源。</span><span class="sxs-lookup"><span data-stu-id="cc425-135">Unmanaged resources are resources that aren't automatically maintained by the .NET runtime.</span></span> <span data-ttu-id="cc425-136">例如，文件句柄就是未托管的资源。</span><span class="sxs-lookup"><span data-stu-id="cc425-136">For example, a file handle is an unmanaged resource.</span></span> <span data-ttu-id="cc425-137"><xref:System.IO.FileStream> 对象是一个托管对象，但它引用未托管的文件句柄。</span><span class="sxs-lookup"><span data-stu-id="cc425-137">A <xref:System.IO.FileStream> object is a managed object, but it references a file handle, which is unmanaged.</span></span> <span data-ttu-id="cc425-138">用完 <xref:System.IO.FileStream> 之后，需要释放文件句柄。</span><span class="sxs-lookup"><span data-stu-id="cc425-138">When you're done using the <xref:System.IO.FileStream>, you need to release the file handle.</span></span>

<span data-ttu-id="cc425-139">在 .NET 中，引用未托管资源的对象会实现 <xref:System.IDisposable> 接口。</span><span class="sxs-lookup"><span data-stu-id="cc425-139">In .NET, objects that reference unmanaged resources implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="cc425-140">用完对象后，需调用此对象的 <xref:System.IDisposable.Dispose> 方法，该方法会释放所有托管资源。</span><span class="sxs-lookup"><span data-stu-id="cc425-140">When you're done using the object, you call the object's <xref:System.IDisposable.Dispose> method, which is responsible for releasing any unmanaged resources.</span></span> <span data-ttu-id="cc425-141">.NET 语言为此类对象提供了一种便捷的 `using` 语法，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="cc425-141">.NET languages provide a convenient `using` syntax for such objects, as shown in the following example:</span></span>

[!code-csharp[UnmanagedResources](../../samples/csharp/snippets/tour/UnmanagedResources.csx#L1-L6)]

<span data-ttu-id="cc425-142">`using` 块完成后，.NET 运行时会自动调用 `stream` 对象的 <xref:System.IDisposable.Dispose> 方法，该方法会释放文件句柄。</span><span class="sxs-lookup"><span data-stu-id="cc425-142">Once the `using` block completes, the .NET runtime automatically calls the `stream` object's <xref:System.IDisposable.Dispose> method, which releases the file handle.</span></span> <span data-ttu-id="cc425-143">如果某异常造成控件退出块，则运行时也会执行此操作。</span><span class="sxs-lookup"><span data-stu-id="cc425-143">The runtime also does this if an exception causes control to leave the block.</span></span>

<span data-ttu-id="cc425-144">有关更多详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="cc425-144">For more details, see the following topics:</span></span>

* <span data-ttu-id="cc425-145">对于 C#，请参阅 [using 语句（C# 参考）](../csharp/language-reference/keywords/using-statement.md)主题。</span><span class="sxs-lookup"><span data-stu-id="cc425-145">For C#, see the [using Statement (C# Reference)](../csharp/language-reference/keywords/using-statement.md) topic.</span></span>
* <span data-ttu-id="cc425-146">对于 F#，请参阅[资源管理：use 关键字](../fsharp/language-reference/resource-management-the-use-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="cc425-146">For F#, see [Resource Management: The use Keyword](../fsharp/language-reference/resource-management-the-use-keyword.md).</span></span>
* <span data-ttu-id="cc425-147">对于 VB，请参阅 [Using 语句 (Visual Basic)](../visual-basic/language-reference/statements/using-statement.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="cc425-147">For VB, see the [Using Statement (Visual Basic)](../visual-basic/language-reference/statements/using-statement.md) topic.</span></span>

## <a name="type-safety"></a><span data-ttu-id="cc425-148">类型安全</span><span class="sxs-lookup"><span data-stu-id="cc425-148">Type safety</span></span>

<span data-ttu-id="cc425-149">对象是特定类型的实例。</span><span class="sxs-lookup"><span data-stu-id="cc425-149">An object is an instance of a specific type.</span></span> <span data-ttu-id="cc425-150">给定对象允许的唯一操作属于特定的类型。</span><span class="sxs-lookup"><span data-stu-id="cc425-150">The only operations allowed for a given object are those of its type.</span></span> <span data-ttu-id="cc425-151">`Dog` 类型可能具有 `Jump` 和 `WagTail` 方法，但没有 `SumTotal` 方法。</span><span class="sxs-lookup"><span data-stu-id="cc425-151">A `Dog` type may have `Jump` and `WagTail` methods but not a `SumTotal` method.</span></span> <span data-ttu-id="cc425-152">程序只调用属于给定类型的方法。</span><span class="sxs-lookup"><span data-stu-id="cc425-152">A program only calls the methods belonging to a given type.</span></span> <span data-ttu-id="cc425-153">所有其他调用会导致编译时错误或运行时异常（如果使用动态功能或 `object`）。</span><span class="sxs-lookup"><span data-stu-id="cc425-153">All other calls result in either a compile-time error or a run-time exception (in case of using dynamic features or `object`).</span></span>

<span data-ttu-id="cc425-154">.NET 语言面向对象，包含基类和派生类的层次结构。</span><span class="sxs-lookup"><span data-stu-id="cc425-154">.NET languages are object-oriented with hierarchies of base and derived classes.</span></span> <span data-ttu-id="cc425-155">.NET 运行时仅允许与对象层次结构相符的对象强制转换和调用。</span><span class="sxs-lookup"><span data-stu-id="cc425-155">The .NET runtime only allows object casts and calls that align with the object hierarchy.</span></span> <span data-ttu-id="cc425-156">请记住，任何 .NET 语言中定义的每个类型都派生自 <xref:System.Object> 基类型。</span><span class="sxs-lookup"><span data-stu-id="cc425-156">Remember that every type defined in any .NET language derives from the base <xref:System.Object> type.</span></span>

[!code-csharp[TypeSafety](../../samples/csharp/snippets/tour/TypeSafety.csx#L19-L23)]

<span data-ttu-id="cc425-157">使用类型安全还有助于强制实施封装，因为它可以保证访问器关键字的保真度。</span><span class="sxs-lookup"><span data-stu-id="cc425-157">Type safety is also used to help enforce encapsulation by guaranteeing the fidelity of the accessor keywords.</span></span> <span data-ttu-id="cc425-158">访问器关键字是控制其他代码访问给定类型的成员的项目。</span><span class="sxs-lookup"><span data-stu-id="cc425-158">Accessor keywords are artifacts which control access to members of a given type by other code.</span></span> <span data-ttu-id="cc425-159">这些关键字通常用于某个类型中用来管理类型行为的各种数据。</span><span class="sxs-lookup"><span data-stu-id="cc425-159">These are usually used for various kinds of data within a type that are used to manage its behavior.</span></span>

[!code-csharp[TypeSafety](../../samples/csharp/snippets/tour/TypeSafety.csx#L3-L3)]

<span data-ttu-id="cc425-160">C#、VB 和 F# 支持本地类型推理。</span><span class="sxs-lookup"><span data-stu-id="cc425-160">C#, VB, and F# support local *type inference*.</span></span> <span data-ttu-id="cc425-161">类型推理是指编译器根据右侧的表达式推断左侧表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="cc425-161">Type inference means that the compiler deduces the type of the expression on the left-hand side from the expression on the right-hand side.</span></span> <span data-ttu-id="cc425-162">这并不意味着类型安全遭到破坏或规避。</span><span class="sxs-lookup"><span data-stu-id="cc425-162">This doesn't mean that the type safety is broken or avoided.</span></span> <span data-ttu-id="cc425-163">生成的类型具有一个隐含所有信息的强类型。</span><span class="sxs-lookup"><span data-stu-id="cc425-163">The resulting type does have a strong type with everything that implies.</span></span> <span data-ttu-id="cc425-164">在上例中，重写了 `dog` 和 `cat` 以介绍类型推理，示例的其余部分保持不变：</span><span class="sxs-lookup"><span data-stu-id="cc425-164">From the previous example, `dog` and `cat` are rewritten to introduce type inference, and the remainder of the example is unchanged:</span></span>

[!code-csharp[TypeSafety](../../samples/csharp/snippets/tour/TypeSafety.csx#L28-L34)]

<span data-ttu-id="cc425-165">与在 C# 和 VB 中找到的方法本地类型推理相比，F# 的类型推理能力更强。</span><span class="sxs-lookup"><span data-stu-id="cc425-165">F# has even further type inference capabilities than the method-local type inference found in C# and VB.</span></span> <span data-ttu-id="cc425-166">若要了解详细信息，请参阅[类型推理](../fsharp/language-reference/type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="cc425-166">To learn more, see [Type Inference](../fsharp/language-reference/type-inference.md).</span></span>

## <a name="delegates-and-lambdas"></a><span data-ttu-id="cc425-167">委托和 lambda</span><span class="sxs-lookup"><span data-stu-id="cc425-167">Delegates and lambdas</span></span>

<span data-ttu-id="cc425-168">委托用方法签名表示。</span><span class="sxs-lookup"><span data-stu-id="cc425-168">A delegate is represented by a method signature.</span></span> <span data-ttu-id="cc425-169">可将任何使用该签名的方法分配给该委托，调用该委托时会执行这些方法。</span><span class="sxs-lookup"><span data-stu-id="cc425-169">Any method with that signature can be assigned to the delegate and is executed when the delegate is invoked.</span></span>

<span data-ttu-id="cc425-170">委托类似于 C++ 函数指针，只是它们是类型安全的。</span><span class="sxs-lookup"><span data-stu-id="cc425-170">Delegates are like C++ function pointers except that they're type safe.</span></span> <span data-ttu-id="cc425-171">它们是 CLR 类型系统中某种断开连接的方法。</span><span class="sxs-lookup"><span data-stu-id="cc425-171">They're a kind of disconnected method within the CLR type system.</span></span> <span data-ttu-id="cc425-172">正则方法已连接到某个类，只能通过静态或实例调用约定来直接调用。</span><span class="sxs-lookup"><span data-stu-id="cc425-172">Regular methods are attached to a class and are only directly callable through static or instance calling conventions.</span></span>

<span data-ttu-id="cc425-173">在 .NET 中，委托通常用于事件处理程序、定义异步操作以及 lambda 表达式，它们是 LINQ 的基础。</span><span class="sxs-lookup"><span data-stu-id="cc425-173">In .NET, delegates are commonly used in event handlers, in defining asynchronous operations, and in lambda expressions, which are a cornerstone of LINQ.</span></span> <span data-ttu-id="cc425-174">有关详细信息，请参见[委托和 lambda](delegates-lambdas.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="cc425-174">Learn more in the [Delegates and lambdas](delegates-lambdas.md) topic.</span></span>

## <a name="generics"></a><span data-ttu-id="cc425-175">泛型</span><span class="sxs-lookup"><span data-stu-id="cc425-175">Generics</span></span>

<span data-ttu-id="cc425-176">泛型可让程序员在设计类时引入一个“类型参数”，这样，客户端代码（类型的用户）便可指定要使用哪个确切的类型来取代类型参数。</span><span class="sxs-lookup"><span data-stu-id="cc425-176">Generics allow the programmer to introduce a *type parameter* when designing their classes that allows the client code (the users of the type) to specify the exact type to use in place of the type parameter.</span></span>

<span data-ttu-id="cc425-177">添加泛型的目的是帮助程序员实现通用数据结构。</span><span class="sxs-lookup"><span data-stu-id="cc425-177">Generics were added to help programmers implement generic data structures.</span></span> <span data-ttu-id="cc425-178">在泛型问世之前，要将 `List` 等类型用作泛型，必须处理 `object` 类型的元素。</span><span class="sxs-lookup"><span data-stu-id="cc425-178">Before their arrival in order for a type such as the `List` type to be generic, it would have to work with elements that were of type `object`.</span></span> <span data-ttu-id="cc425-179">这会造成各种性能和语义问题，甚至造成微妙的运行时错误。</span><span class="sxs-lookup"><span data-stu-id="cc425-179">This had various performance and semantic problems, along with possible subtle runtime errors.</span></span> <span data-ttu-id="cc425-180">例如，当数据结构包含整数和字符串时，如果在处理列表的成员时引发 `InvalidCastException`，则就会出现运行时错误这种非常棘手的问题。</span><span class="sxs-lookup"><span data-stu-id="cc425-180">The most notorious of the latter is when a data structure contains, for instance, both integers and strings, and an `InvalidCastException` is thrown on working with the list's members.</span></span>

<span data-ttu-id="cc425-181">以下示例显示了使用 <xref:System.Collections.Generic.List%601> 类型实例运行的基本程序：</span><span class="sxs-lookup"><span data-stu-id="cc425-181">The following sample shows a basic program running using an instance of <xref:System.Collections.Generic.List%601> types:</span></span>

[!code-csharp[GenericsShort](../../samples/csharp/snippets/tour/GenericsShort.csx)]

<span data-ttu-id="cc425-182">有关详细信息，请参阅[泛型类型（泛型）概述](generics.md)主题。</span><span class="sxs-lookup"><span data-stu-id="cc425-182">For more information, see the [Generic types (Generics) overview](generics.md) topic.</span></span>

## <a name="async-programming"></a><span data-ttu-id="cc425-183">异步编程</span><span class="sxs-lookup"><span data-stu-id="cc425-183">Async programming</span></span>

<span data-ttu-id="cc425-184">异步编程是 .NET 中的一个先进概念，它在运行时、框架库和 .NET 语言构造中提供异步支持。</span><span class="sxs-lookup"><span data-stu-id="cc425-184">Async programming is a first-class concept within .NET with async support in the runtime, framework libraries, and .NET language constructs.</span></span> <span data-ttu-id="cc425-185">在内部，异步编程基于利用操作系统尽可能高效地执行 I/O 绑定型作业的对象（例如 `Task`）。</span><span class="sxs-lookup"><span data-stu-id="cc425-185">Internally, they're based on objects (such as `Task`), which take advantage of the operating system to perform I/O-bound jobs as efficiently as possible.</span></span>

<span data-ttu-id="cc425-186">若要了解有关 .NET 中异步编程的详细信息，请先阅读[异步概述](async.md)主题。</span><span class="sxs-lookup"><span data-stu-id="cc425-186">To learn more about async programming in .NET, start with the [Async overview](async.md) topic.</span></span>

## <a name="language-integrated-query-linq"></a><span data-ttu-id="cc425-187">语言集成查询 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="cc425-187">Language Integrated Query (LINQ)</span></span>

<span data-ttu-id="cc425-188">LINQ 是适用于 C# 和 VB 的强大功能集，可用于编写简单的声明性代码来处理数据。</span><span class="sxs-lookup"><span data-stu-id="cc425-188">LINQ is a powerful set of features for C# and VB that allow you to write simple, declarative code for operating on data.</span></span> <span data-ttu-id="cc425-189">数据可采用多种形式（例如，内存中对象、SQL 数据库或 XML 文档），但针对每个数据源编写的 LINQ 代码往往没有差别。</span><span class="sxs-lookup"><span data-stu-id="cc425-189">The data can be in many forms (such as in-memory objects, a SQL database, or an XML document), but the LINQ code you write typically doesn't differ by data source.</span></span>

<span data-ttu-id="cc425-190">若要了解详细信息并查看某部分示例，请参阅 [LINQ（语言集成查询）](using-linq.md)主题。</span><span class="sxs-lookup"><span data-stu-id="cc425-190">To learn more and see some samples, see the [LINQ (Language Integrated Query)](using-linq.md) topic.</span></span>

## <a name="native-interoperability"></a><span data-ttu-id="cc425-191">本机互操作性</span><span class="sxs-lookup"><span data-stu-id="cc425-191">Native interoperability</span></span>

<span data-ttu-id="cc425-192">每个操作系统都有一个应用程序编程接口 (API)，用于提供系统服务。</span><span class="sxs-lookup"><span data-stu-id="cc425-192">Every operating system includes an application programming interface (API) that provides system services.</span></span> <span data-ttu-id="cc425-193">.NET 提供多种方式来调用这些 API。</span><span class="sxs-lookup"><span data-stu-id="cc425-193">.NET provides several ways to call those APIs.</span></span>

<span data-ttu-id="cc425-194">实现本机互操作性的主要方式是通过“平台调用”（简称 P/Invoke），Linux 和 Windows 平台均支持这种方式。</span><span class="sxs-lookup"><span data-stu-id="cc425-194">The main way to do native interoperability is via "platform invoke" or P/Invoke for short, which is supported across Linux and Windows platforms.</span></span> <span data-ttu-id="cc425-195">实现本机互操作性的另一种方式称为“COM 互操作”（仅限 Windows），用于在托管代码中操作 [COM 组件](/cpp/atl/introduction-to-com)。</span><span class="sxs-lookup"><span data-stu-id="cc425-195">A Windows-only way of doing native interoperability is known as "COM interop," which is used to work with [COM components](/cpp/atl/introduction-to-com) in managed code.</span></span> <span data-ttu-id="cc425-196">这种方式建立在 P/Invoke 基础结构之上，但工作原理略有不同。</span><span class="sxs-lookup"><span data-stu-id="cc425-196">It's built on top of the P/Invoke infrastructure, but it works in subtly different ways.</span></span>

<span data-ttu-id="cc425-197">针对 Java 和 Objective-C 的 Mono（以及 Xamarin）互操作性支持基本上以类似的方式构建，也就是说，它们运用相同的原理。</span><span class="sxs-lookup"><span data-stu-id="cc425-197">Most of Mono's (and thus Xamarin's) interoperability support for Java and Objective-C are built similarly, that is, they use the same principles.</span></span>

<span data-ttu-id="cc425-198">有关本机互操作性的的详细信息，请参阅[本机互操作性](native-interop.md)主题。</span><span class="sxs-lookup"><span data-stu-id="cc425-198">Read more about it native interoperability in the [Native interoperability](native-interop.md) topic.</span></span>

## <a name="unsafe-code"></a><span data-ttu-id="cc425-199">不安全代码</span><span class="sxs-lookup"><span data-stu-id="cc425-199">Unsafe code</span></span>

<span data-ttu-id="cc425-200">根据语言支持，CLR 可通过 `unsafe` 代码访问本机内存和执行指针算术运算。</span><span class="sxs-lookup"><span data-stu-id="cc425-200">Depending on language support, the CLR lets you access native memory and do pointer arithmetic via `unsafe` code.</span></span> <span data-ttu-id="cc425-201">某些算法和系统互操作性需要这些操作。</span><span class="sxs-lookup"><span data-stu-id="cc425-201">These operations are needed for certain algorithms and system interoperability.</span></span> <span data-ttu-id="cc425-202">尽管不安全代码的功能强大，但除非有必要与系统 API 互操作或实现最高效的算法，否则不建议使用。</span><span class="sxs-lookup"><span data-stu-id="cc425-202">Although powerful, use of unsafe code is discouraged unless it's necessary to interop with system APIs or implement the most efficient algorithm.</span></span> <span data-ttu-id="cc425-203">在不同的环境中，不安全代码的执行方式可能不同，使用它还会丧失垃圾回收器和类型安全带来的好处。</span><span class="sxs-lookup"><span data-stu-id="cc425-203">Unsafe code may not execute the same way in different environments and also loses the benefits of a garbage collector and type safety.</span></span> <span data-ttu-id="cc425-204">建议尽可能地限制和集中化使用不安全代码，并全面测试该代码。</span><span class="sxs-lookup"><span data-stu-id="cc425-204">It's recommended to confine and centralize unsafe code as much as possible and test that code thoroughly.</span></span>

<span data-ttu-id="cc425-205">以下示例是 `StringBuilder` 类中 `ToString()` 方法的修改版本。</span><span class="sxs-lookup"><span data-stu-id="cc425-205">The following example is a modified version of the `ToString()` method from the `StringBuilder` class.</span></span> <span data-ttu-id="cc425-206">它演示了如何使用 `unsafe` 代码直接移动内存区块，从而有效实现某种算法：</span><span class="sxs-lookup"><span data-stu-id="cc425-206">It illustrates how using `unsafe` code can efficiently implement an algorithm by moving around chunks of memory directly:</span></span>

[!code-csharp[Unsafe](../../samples/csharp/snippets/tour/Unsafe.csx)]

## <a name="next-steps"></a><span data-ttu-id="cc425-207">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cc425-207">Next steps</span></span>

<span data-ttu-id="cc425-208">如果对 C# 功能的教程感兴趣，请参阅 [C# 教程](../csharp/tour-of-csharp/index.md)。</span><span class="sxs-lookup"><span data-stu-id="cc425-208">If you're interested in a tour of C# features, check out [Tour of C#](../csharp/tour-of-csharp/index.md).</span></span>

<span data-ttu-id="cc425-209">如果对 F# 功能的教程感兴趣，请参阅 [F# 教程](../fsharp/tour.md)。</span><span class="sxs-lookup"><span data-stu-id="cc425-209">If you're interested in a tour of F# features, see [Tour of F#](../fsharp/tour.md).</span></span>

<span data-ttu-id="cc425-210">如果想开始自己编写代码，请访问[入门](get-started.md)。</span><span class="sxs-lookup"><span data-stu-id="cc425-210">If you want to get started with writing code of your own, visit [Getting Started](get-started.md).</span></span>

<span data-ttu-id="cc425-211">要了解 .NET 的重要组件，请参阅 [.NET 体系结构组件](components.md)。</span><span class="sxs-lookup"><span data-stu-id="cc425-211">To learn about important components of .NET, check out [.NET Architectural Components](components.md).</span></span>
