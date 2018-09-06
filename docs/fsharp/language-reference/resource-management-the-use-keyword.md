---
title: 资源管理：use 关键字 (F#)
description: '了解有关 F # 关键字 use 和 using 函数，可以控制的初始化和释放资源。'
ms.date: 05/16/2016
ms.openlocfilehash: ffa1cb515139a3705920d9d9f79be1a69602f7d8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43878383"
---
# <a name="resource-management-the-use-keyword"></a><span data-ttu-id="a0c88-103">资源管理：use 关键字</span><span class="sxs-lookup"><span data-stu-id="a0c88-103">Resource Management: The use Keyword</span></span>

<span data-ttu-id="a0c88-104">本主题介绍了关键字`use`和`using`函数，可以控制的初始化和释放资源。</span><span class="sxs-lookup"><span data-stu-id="a0c88-104">This topic describes the keyword `use` and the `using` function, which can control the initialization and release of resources.</span></span>

## <a name="resources"></a><span data-ttu-id="a0c88-105">资源</span><span class="sxs-lookup"><span data-stu-id="a0c88-105">Resources</span></span>

<span data-ttu-id="a0c88-106">术语*资源*以多种方式使用。</span><span class="sxs-lookup"><span data-stu-id="a0c88-106">The term *resource* is used in more than one way.</span></span> <span data-ttu-id="a0c88-107">是的资源可以是应用程序使用，如字符串、 图形和类似的内容，但在此上下文中的数据*资源*指的是软件或操作系统资源，例如图形设备上下文、 文件句柄、 网络和数据库连接，如等待句柄等并发对象。</span><span class="sxs-lookup"><span data-stu-id="a0c88-107">Yes, resources can be data that an application uses, such as strings, graphics, and the like, but in this context, *resources* refers to software or operating system resources, such as graphics device contexts, file handles, network and database connections, concurrency objects such as wait handles, and so on.</span></span> <span data-ttu-id="a0c88-108">由应用程序的这些资源的使用涉及到操作系统或其他资源提供程序后, 跟资源的更高版本到池，以便它可以提供给另一个应用程序的资源的获取。</span><span class="sxs-lookup"><span data-stu-id="a0c88-108">The use of these resources by applications involves the acquisition of the resource from the operating system or other resource provider, followed by the later release of the resource to the pool so that it can be provided to another application.</span></span> <span data-ttu-id="a0c88-109">当应用程序不会释放资源恢复到公共池时，会出现问题。</span><span class="sxs-lookup"><span data-stu-id="a0c88-109">Problems occur when applications do not release resources back to the common pool.</span></span>

## <a name="managing-resources"></a><span data-ttu-id="a0c88-110">管理资源</span><span class="sxs-lookup"><span data-stu-id="a0c88-110">Managing Resources</span></span>

<span data-ttu-id="a0c88-111">若要有效地和负责任地管理应用程序中的资源，你必须立即和可预测的方式释放资源。</span><span class="sxs-lookup"><span data-stu-id="a0c88-111">To efficiently and responsibly manage resources in an application, you must release resources promptly and in a predictable manner.</span></span> <span data-ttu-id="a0c88-112">.NET Framework 可帮助你执行此操作，从而`System.IDisposable`接口。</span><span class="sxs-lookup"><span data-stu-id="a0c88-112">The .NET Framework helps you do this by providing the `System.IDisposable` interface.</span></span> <span data-ttu-id="a0c88-113">实现的类型`System.IDisposable`具有`System.IDisposable.Dispose`方法，可正确地释放资源。</span><span class="sxs-lookup"><span data-stu-id="a0c88-113">A type that implements `System.IDisposable` has the `System.IDisposable.Dispose` method, which correctly frees resources.</span></span> <span data-ttu-id="a0c88-114">编写良好的应用程序保证`System.IDisposable.Dispose`时不再需要保留有限的资源的任何对象，立即调用。</span><span class="sxs-lookup"><span data-stu-id="a0c88-114">Well-written applications guarantee that `System.IDisposable.Dispose` is called promptly when any object that holds a limited resource is no longer needed.</span></span> <span data-ttu-id="a0c88-115">幸运的是，大多数.NET 语言提供支持，以简化此过程，和 F # 也不例外。</span><span class="sxs-lookup"><span data-stu-id="a0c88-115">Fortunately, most .NET languages provide support to make this easier, and F# is no exception.</span></span> <span data-ttu-id="a0c88-116">有两个有用的语言结构支持的释放模式：`use`绑定和`using`函数。</span><span class="sxs-lookup"><span data-stu-id="a0c88-116">There are two useful language constructs that support the dispose pattern: the `use` binding and the `using` function.</span></span>

## <a name="use-binding"></a><span data-ttu-id="a0c88-117">使用绑定</span><span class="sxs-lookup"><span data-stu-id="a0c88-117">use Binding</span></span>

<span data-ttu-id="a0c88-118">`use`关键字具有类似的窗体`let`绑定：</span><span class="sxs-lookup"><span data-stu-id="a0c88-118">The `use` keyword has a form that resembles that of the `let` binding:</span></span>

<span data-ttu-id="a0c88-119">使用*值* = *表达式*</span><span class="sxs-lookup"><span data-stu-id="a0c88-119">use *value* = *expression*</span></span>

<span data-ttu-id="a0c88-120">它提供了相同的功能`let`绑定，但添加到调用`Dispose`值超出范围时的值。</span><span class="sxs-lookup"><span data-stu-id="a0c88-120">It provides the same functionality as a `let` binding but adds a call to `Dispose` on the value when the value goes out of scope.</span></span> <span data-ttu-id="a0c88-121">请注意，编译器将插入 null 值，检查，因此，如果值为`null`，在调用`Dispose`未尝试。</span><span class="sxs-lookup"><span data-stu-id="a0c88-121">Note that the compiler inserts a null check on the value, so that if the value is `null`, the call to `Dispose` is not attempted.</span></span>

<span data-ttu-id="a0c88-122">下面的示例演示如何通过使用自动关闭文件`use`关键字。</span><span class="sxs-lookup"><span data-stu-id="a0c88-122">The following example shows how to close a file automatically by using the `use` keyword.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

>[!NOTE]
<span data-ttu-id="a0c88-123">可以使用`use`在计算表达式中，在这种情况下的自定义的版本`use`使用表达式。</span><span class="sxs-lookup"><span data-stu-id="a0c88-123">You can use `use` in computation expressions, in which case a customized version of the `use` expression is used.</span></span> <span data-ttu-id="a0c88-124">有关详细信息，请参阅[序列](sequences.md)，[异步工作流](asynchronous-workflows.md)，并[计算表达式](computation-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="a0c88-124">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="using-function"></a><span data-ttu-id="a0c88-125">使用函数</span><span class="sxs-lookup"><span data-stu-id="a0c88-125">using Function</span></span>

<span data-ttu-id="a0c88-126">`using`函数具有以下形式：</span><span class="sxs-lookup"><span data-stu-id="a0c88-126">The `using` function has the following form:</span></span>

<span data-ttu-id="a0c88-127">`using` (*expression1*)*函数或 lambda*</span><span class="sxs-lookup"><span data-stu-id="a0c88-127">`using` (*expression1*) *function-or-lambda*</span></span>

<span data-ttu-id="a0c88-128">在中`using`表达式中， *expression1*创建必须释放的对象。</span><span class="sxs-lookup"><span data-stu-id="a0c88-128">In a `using` expression, *expression1* creates the object that must be disposed.</span></span> <span data-ttu-id="a0c88-129">结果*expression1* （必须释放的对象） 将成为自变量，*值*到*函数或 lambda*，它是需要将单个的任一函数剩余值相匹配的类型参数由*expression1*，或需要一个该类型的参数的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="a0c88-129">The result of *expression1* (the object that must be disposed) becomes an argument, *value*, to *function-or-lambda*, which is either a function that expects a single remaining argument of a type that matches the value produced by *expression1*, or a lambda expression that expects an argument of that type.</span></span> <span data-ttu-id="a0c88-130">在函数的执行结束时，运行时调用`Dispose`，并释放资源 (除非的值为`null`，在这种情况下不尝试对 Dispose 的调用)。</span><span class="sxs-lookup"><span data-stu-id="a0c88-130">At the end of the execution of the function, the runtime calls `Dispose` and frees the resources (unless the value is `null`, in which case the call to Dispose is not attempted).</span></span>

<span data-ttu-id="a0c88-131">下面的示例演示`using`使用 lambda 表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="a0c88-131">The following example demonstrates the `using` expression with a lambda expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

<span data-ttu-id="a0c88-132">下面的示例说明`using`的函数的表达式。</span><span class="sxs-lookup"><span data-stu-id="a0c88-132">The next example shows the `using` expression with a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

<span data-ttu-id="a0c88-133">请注意，该函数可以是具有已应用某些参数的函数。</span><span class="sxs-lookup"><span data-stu-id="a0c88-133">Note that the function could be a function that has some arguments applied already.</span></span> <span data-ttu-id="a0c88-134">下面的代码示例展示了此操作。</span><span class="sxs-lookup"><span data-stu-id="a0c88-134">The following code example demonstrates this.</span></span> <span data-ttu-id="a0c88-135">它将创建包含字符串的文件`XYZ`。</span><span class="sxs-lookup"><span data-stu-id="a0c88-135">It creates a file that contains the string `XYZ`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

<span data-ttu-id="a0c88-136">`using`函数和`use`绑定是几乎等效方法来完成同样的操作。</span><span class="sxs-lookup"><span data-stu-id="a0c88-136">The `using` function and the `use` binding are nearly equivalent ways to accomplish the same thing.</span></span> <span data-ttu-id="a0c88-137">`using`关键字提供了更好地控制何时`Dispose`调用。</span><span class="sxs-lookup"><span data-stu-id="a0c88-137">The `using` keyword provides more control over when `Dispose` is called.</span></span> <span data-ttu-id="a0c88-138">当你使用`using`，`Dispose`在使用时调用的函数或 lambda 表达式，则末尾`use`关键字，`Dispose`包含代码块的结束时调用。</span><span class="sxs-lookup"><span data-stu-id="a0c88-138">When you use `using`, `Dispose` is called at the end of the function or lambda expression; when you use the `use` keyword, `Dispose` is called at the end of the containing code block.</span></span> <span data-ttu-id="a0c88-139">一般情况下，应优先使用`use`而不是`using`函数。</span><span class="sxs-lookup"><span data-stu-id="a0c88-139">In general, you should prefer to use `use` instead of the `using` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0c88-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0c88-140">See also</span></span>

- [<span data-ttu-id="a0c88-141">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="a0c88-141">F# Language Reference</span></span>](index.md)
