---
title: "处理和引发异常"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET Framework], exceptions
- exceptions [.NET Framework], throwing
- exceptions [.NET Framework]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
caps.latest.revision: 16
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5d44996042d167c029291f2b454dc1a22cfbcfb4
ms.contentlocale: zh-cn
ms.lasthandoff: 09/05/2017

---
# <a name="handling-and-throwing-exceptions-in-net"></a><span data-ttu-id="12aa7-102">在 .NET 中处理和引发异常</span><span class="sxs-lookup"><span data-stu-id="12aa7-102">Handling and throwing exceptions in .NET</span></span>

<span data-ttu-id="12aa7-103">应用程序必须能够以一致的方式处理执行期间发生的错误。</span><span class="sxs-lookup"><span data-stu-id="12aa7-103">Applications must be able to handle errors that occur during execution in a consistent manner.</span></span> <span data-ttu-id="12aa7-104">.NET 提供一种以统一方式向应用程序报错的模型：.NET 操作通过引发异常来指示故障。</span><span class="sxs-lookup"><span data-stu-id="12aa7-104">.NET provides a model for notifying applications of errors in a uniform way: .NET operations indicate failure by throwing exceptions.</span></span>

## <a name="exceptions"></a><span data-ttu-id="12aa7-105">异常</span><span class="sxs-lookup"><span data-stu-id="12aa7-105">Exceptions</span></span>

<span data-ttu-id="12aa7-106">异常是执行程序遇到的所有错误条件或意外行为。</span><span class="sxs-lookup"><span data-stu-id="12aa7-106">An exception is any error condition or unexpected behavior that is encountered by an executing program.</span></span> <span data-ttu-id="12aa7-107">异常可能由你的代码或调用的代码（如共享库）中的错误、不可用的操作系统资源、运行时遇到的意外情况（如无法验证的代码）等引发。</span><span class="sxs-lookup"><span data-stu-id="12aa7-107">Exceptions can be thrown because of a fault in your code or in code that you call (such as a shared library), unavailable operating system resources, unexpected conditions that the runtime encounters (such as code that cannot be verified), and so on.</span></span> <span data-ttu-id="12aa7-108">应用程序可从这些情况中的一些中恢复，但无法从其他情况中恢复。</span><span class="sxs-lookup"><span data-stu-id="12aa7-108">Your application can recover from some of these conditions, but not from others.</span></span> <span data-ttu-id="12aa7-109">尽管可以从大多数应用程序异常中恢复，但不能从大多数运行时异常中恢复。</span><span class="sxs-lookup"><span data-stu-id="12aa7-109">Although you can recover from most application exceptions, you cannot recover from most runtime exceptions.</span></span>

<span data-ttu-id="12aa7-110">在 .NET 中，异常是从 [System.Exception](xref:System.Exception) 类继承的对象。</span><span class="sxs-lookup"><span data-stu-id="12aa7-110">In .NET, an exception is an object that inherits from the [System.Exception](xref:System.Exception) class.</span></span> <span data-ttu-id="12aa7-111">异常引发自发生问题的代码区域。</span><span class="sxs-lookup"><span data-stu-id="12aa7-111">An exception is thrown from an area of code where a problem has occurred.</span></span> <span data-ttu-id="12aa7-112">异常在堆栈中向上传递，直到应用程序对其进行处理或者程序终止。</span><span class="sxs-lookup"><span data-stu-id="12aa7-112">The exception is passed up the stack until the application handles it or the program terminates.</span></span>

## <a name="exceptions-vs-traditional-error-handling-methods"></a><span data-ttu-id="12aa7-113">异常与传统的错误处理方法</span><span class="sxs-lookup"><span data-stu-id="12aa7-113">Exceptions vs. traditional error-handling methods</span></span>

<span data-ttu-id="12aa7-114">传统上，语言的错误处理模型依赖语言检测错误和针对错误查找其处理程序的独特方式，或者依赖操作系统提供的错误处理机制。</span><span class="sxs-lookup"><span data-stu-id="12aa7-114">Traditionally, a language's error-handling model relied on either the language's unique way of detecting errors and locating handlers for them, or on the error-handling mechanism provided by the operating system.</span></span> <span data-ttu-id="12aa7-115">.NET 实现异常处理的方式有以下优点：</span><span class="sxs-lookup"><span data-stu-id="12aa7-115">The way .NET implements exception handling provides the following advantages:</span></span>

- <span data-ttu-id="12aa7-116">引发和处理异常的方式与 .NET 编程语言的相同。</span><span class="sxs-lookup"><span data-stu-id="12aa7-116">Exception throwing and handling works the same for .NET programming languages.</span></span>

- <span data-ttu-id="12aa7-117">处理异常不需要任何特定的语言语法，但允许每种语言定义自己的语法。</span><span class="sxs-lookup"><span data-stu-id="12aa7-117">Does not require any particular language syntax for handling exceptions, but allows each language to define its own syntax.</span></span>

- <span data-ttu-id="12aa7-118">可跨进程，甚至跨计算机边界引发异常。</span><span class="sxs-lookup"><span data-stu-id="12aa7-118">Exceptions can be thrown across process and even machine boundaries.</span></span>

- <span data-ttu-id="12aa7-119">可向应用程序添加异常处理代码以提高程序的可靠性。</span><span class="sxs-lookup"><span data-stu-id="12aa7-119">Exception-handling code can be added to an application to increase program reliability.</span></span>

<span data-ttu-id="12aa7-120">异常相较于其他错误通知方法（如返回代码）具有多种优势。</span><span class="sxs-lookup"><span data-stu-id="12aa7-120">Exceptions offer advantages over other methods of error notification, such as return codes.</span></span> <span data-ttu-id="12aa7-121">故障不会被忽略掉，因为如果引发了异常且未得到解决，运行时会终止应用程序。</span><span class="sxs-lookup"><span data-stu-id="12aa7-121">Failures do not go unnoticed because if an exception is thrown and you don't handle it, the runtime terminates your application.</span></span> <span data-ttu-id="12aa7-122">因为代码未能检查出是否存在故障返回代码，所以无效值不会继续在系统中传播。</span><span class="sxs-lookup"><span data-stu-id="12aa7-122">Invalid values do not continue to propagate through the system as a result of code that fails to check for a failure return code.</span></span> 

## <a name="common-exceptions"></a><span data-ttu-id="12aa7-123">常见异常</span><span class="sxs-lookup"><span data-stu-id="12aa7-123">Common Exceptions</span></span>

<span data-ttu-id="12aa7-124">下表列出了一些常见的异常，以及会引发这些异常的原因的示例。</span><span class="sxs-lookup"><span data-stu-id="12aa7-124">The following table lists some common exceptions with examples of what can cause them.</span></span>

| <span data-ttu-id="12aa7-125">异常类型</span><span class="sxs-lookup"><span data-stu-id="12aa7-125">Exception type</span></span> | <span data-ttu-id="12aa7-126">基类型</span><span class="sxs-lookup"><span data-stu-id="12aa7-126">Base type</span></span> | <span data-ttu-id="12aa7-127">描述</span><span class="sxs-lookup"><span data-stu-id="12aa7-127">Description</span></span> | <span data-ttu-id="12aa7-128">示例</span><span class="sxs-lookup"><span data-stu-id="12aa7-128">Example</span></span> |
| -------------- | --------- | ----------- | ------- |
| @System.Exception | @System.Object | <span data-ttu-id="12aa7-129">所有异常的基类。</span><span class="sxs-lookup"><span data-stu-id="12aa7-129">Base class for all exceptions.</span></span> | <span data-ttu-id="12aa7-130">无（使用此异常的派生类）。</span><span class="sxs-lookup"><span data-stu-id="12aa7-130">None (use a derived class of this exception).</span></span> |
| @System.IndexOutOfRangeException | @System.Exception | <span data-ttu-id="12aa7-131">仅当错误地对数组进行索引时，才由运行时引发。</span><span class="sxs-lookup"><span data-stu-id="12aa7-131">Thrown by the runtime only when an array is indexed improperly.</span></span> | <span data-ttu-id="12aa7-132">在数组的有效范围外对数组进行索引：`arr[arr.Length+1]`</span><span class="sxs-lookup"><span data-stu-id="12aa7-132">Indexing an array outside its valid range: `arr[arr.Length+1]`</span></span> |
| @System.NullReferenceException | @System.Exception | <span data-ttu-id="12aa7-133">仅当引用 null 对象时，才由运行时引发。</span><span class="sxs-lookup"><span data-stu-id="12aa7-133">Thrown by the runtime only when a null object is referenced.</span></span> | `object o = null; o.ToString();` |
| @System.InvalidOperationException | @System.Exception | <span data-ttu-id="12aa7-134">当处于无效状态时，由方法引发。</span><span class="sxs-lookup"><span data-stu-id="12aa7-134">Thrown by methods when in an invalid state.</span></span> | <span data-ttu-id="12aa7-135">从基础集合删除项后调用 `Enumerator.GetNext()`。</span><span class="sxs-lookup"><span data-stu-id="12aa7-135">Calling `Enumerator.GetNext()` after removing an Item from the underlying collection.</span></span> |
| @System.ArgumentException | @System.Exception | <span data-ttu-id="12aa7-136">所有自变量异常的基类。</span><span class="sxs-lookup"><span data-stu-id="12aa7-136">Base class for all argument exceptions.</span></span> | <span data-ttu-id="12aa7-137">无（使用此异常的派生类）。</span><span class="sxs-lookup"><span data-stu-id="12aa7-137">None (use a derived class of this exception).</span></span> |
| @System.ArgumentNullException | @System.Exception | <span data-ttu-id="12aa7-138">由不允许参数为 null 的方法引发。</span><span class="sxs-lookup"><span data-stu-id="12aa7-138">Thrown by methods that do not allow an argument to be null.</span></span> | `String s = null; "Calculate".IndexOf (s);` |
| @System.ArgumentOutOfRangeException | @System.Exception | <span data-ttu-id="12aa7-139">由验证自变量是否位于给定范围内的方法引发。</span><span class="sxs-lookup"><span data-stu-id="12aa7-139">Thrown by methods that verify that arguments are in a given range.</span></span> | `String s = "string"; s.Substring(s.Length+1);` |

## <a name="see-also"></a><span data-ttu-id="12aa7-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12aa7-140">See Also</span></span>

* [<span data-ttu-id="12aa7-141">异常类和属性</span><span class="sxs-lookup"><span data-stu-id="12aa7-141">Exception Class and Properties</span></span>](exception-class-and-properties.md)
* [<span data-ttu-id="12aa7-142">如何：使用 Try-Catch 块捕捉异常</span><span class="sxs-lookup"><span data-stu-id="12aa7-142">How to: Use the Try-Catch Block to Catch Exceptions</span></span>](how-to-use-the-try-catch-block-to-catch-exceptions.md)
* [<span data-ttu-id="12aa7-143">如何：在 Catch 块中使用特定异常</span><span class="sxs-lookup"><span data-stu-id="12aa7-143">How to: Use Specific Exceptions in a Catch Block</span></span>](how-to-use-specific-exceptions-in-a-catch-block.md)
* [<span data-ttu-id="12aa7-144">如何：显式引发异常</span><span class="sxs-lookup"><span data-stu-id="12aa7-144">How to: Explicitly Throw Exceptions</span></span>](how-to-explicitly-throw-exceptions.md)
* [<span data-ttu-id="12aa7-145">如何：创建用户定义的异常</span><span class="sxs-lookup"><span data-stu-id="12aa7-145">How to: Create User-Defined Exceptions</span></span>](how-to-create-user-defined-exceptions.md)
* [<span data-ttu-id="12aa7-146">使用用户筛选的异常处理程序</span><span class="sxs-lookup"><span data-stu-id="12aa7-146">Using User-Filtered Exception Handlers</span></span>](using-user-filtered-exception-handlers.md)
* [<span data-ttu-id="12aa7-147">如何：使用 Finally 块</span><span class="sxs-lookup"><span data-stu-id="12aa7-147">How to: Use Finally Blocks</span></span>](how-to-use-finally-blocks.md)
* [<span data-ttu-id="12aa7-148">处理 COM 互操作异常</span><span class="sxs-lookup"><span data-stu-id="12aa7-148">Handling COM Interop Exceptions</span></span>](handling-com-interop-exceptions.md)
* [<span data-ttu-id="12aa7-149">与异常有关的最佳做法</span><span class="sxs-lookup"><span data-stu-id="12aa7-149">Best Practices for Exceptions</span></span>](best-practices-for-exceptions.md)

<span data-ttu-id="12aa7-150">若要了解有关 .NET 中异常的工作方式的详细信息，请参阅[运行时中每个开发人员都需要了解的有关异常的事项](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="12aa7-150">To learn more about how exceptions work in .NET, see [What Every Dev needs to Know About Exceptions in the Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md).</span></span>

