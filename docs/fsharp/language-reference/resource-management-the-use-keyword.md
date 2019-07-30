---
title: 资源管理:Use 关键字
description: 了解F#关键字 "use" 和 "using" 函数, 它可以控制资源的初始化和发布。
ms.date: 05/16/2016
ms.openlocfilehash: 5e0838401bee02050343b2f6dcc646a8dc8b4dc0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627259"
---
# <a name="resource-management-the-use-keyword"></a><span data-ttu-id="33441-103">资源管理:Use 关键字</span><span class="sxs-lookup"><span data-stu-id="33441-103">Resource Management: The use Keyword</span></span>

<span data-ttu-id="33441-104">本主题介绍关键字`use` `using`和函数, 它可以控制资源的初始化和发布。</span><span class="sxs-lookup"><span data-stu-id="33441-104">This topic describes the keyword `use` and the `using` function, which can control the initialization and release of resources.</span></span>

## <a name="resources"></a><span data-ttu-id="33441-105">资源</span><span class="sxs-lookup"><span data-stu-id="33441-105">Resources</span></span>

<span data-ttu-id="33441-106">术语 "*资源*" 使用多种方法。</span><span class="sxs-lookup"><span data-stu-id="33441-106">The term *resource* is used in more than one way.</span></span> <span data-ttu-id="33441-107">是的, 资源可以是应用程序使用的数据, 例如字符串、图形等, 但在此上下文中,*资源*是指软件或操作系统资源, 如图形设备上下文、文件句柄、网络和数据库连接、并发对象 (如等待句柄等)。</span><span class="sxs-lookup"><span data-stu-id="33441-107">Yes, resources can be data that an application uses, such as strings, graphics, and the like, but in this context, *resources* refers to software or operating system resources, such as graphics device contexts, file handles, network and database connections, concurrency objects such as wait handles, and so on.</span></span> <span data-ttu-id="33441-108">应用程序对这些资源的使用涉及到从操作系统或其他资源提供程序获取资源, 然后将该资源的更高版本发布到池中, 以便可以将其提供给其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="33441-108">The use of these resources by applications involves the acquisition of the resource from the operating system or other resource provider, followed by the later release of the resource to the pool so that it can be provided to another application.</span></span> <span data-ttu-id="33441-109">当应用程序不将资源释放回公用池时, 会出现问题。</span><span class="sxs-lookup"><span data-stu-id="33441-109">Problems occur when applications do not release resources back to the common pool.</span></span>

## <a name="managing-resources"></a><span data-ttu-id="33441-110">管理资源</span><span class="sxs-lookup"><span data-stu-id="33441-110">Managing Resources</span></span>

<span data-ttu-id="33441-111">若要有效地管理应用程序中的资源, 必须以可预测的方式立即释放资源。</span><span class="sxs-lookup"><span data-stu-id="33441-111">To efficiently and responsibly manage resources in an application, you must release resources promptly and in a predictable manner.</span></span> <span data-ttu-id="33441-112">.NET Framework 提供`System.IDisposable`接口, 有助于实现此目的。</span><span class="sxs-lookup"><span data-stu-id="33441-112">The .NET Framework helps you do this by providing the `System.IDisposable` interface.</span></span> <span data-ttu-id="33441-113">实现`System.IDisposable`的类型`System.IDisposable.Dispose`具有可正确释放资源的方法。</span><span class="sxs-lookup"><span data-stu-id="33441-113">A type that implements `System.IDisposable` has the `System.IDisposable.Dispose` method, which correctly frees resources.</span></span> <span data-ttu-id="33441-114">编写良好的应用程序可`System.IDisposable.Dispose`保证当不再需要任何持有有限资源的对象时, 会立即调用。</span><span class="sxs-lookup"><span data-stu-id="33441-114">Well-written applications guarantee that `System.IDisposable.Dispose` is called promptly when any object that holds a limited resource is no longer needed.</span></span> <span data-ttu-id="33441-115">幸运的是, 大多数 .NET 语言都提供支持来简化这F#一过程, 并且不会出现异常。</span><span class="sxs-lookup"><span data-stu-id="33441-115">Fortunately, most .NET languages provide support to make this easier, and F# is no exception.</span></span> <span data-ttu-id="33441-116">有两种支持 dispose 模式的有用语言构造: `use`绑定`using`和函数。</span><span class="sxs-lookup"><span data-stu-id="33441-116">There are two useful language constructs that support the dispose pattern: the `use` binding and the `using` function.</span></span>

## <a name="use-binding"></a><span data-ttu-id="33441-117">使用绑定</span><span class="sxs-lookup"><span data-stu-id="33441-117">use Binding</span></span>

<span data-ttu-id="33441-118">关键字的形式与`let`绑定类似: `use`</span><span class="sxs-lookup"><span data-stu-id="33441-118">The `use` keyword has a form that resembles that of the `let` binding:</span></span>

<span data-ttu-id="33441-119">使用*值* = *表达式*</span><span class="sxs-lookup"><span data-stu-id="33441-119">use *value* = *expression*</span></span>

<span data-ttu-id="33441-120">它提供与`let`绑定相同的功能, 但在值超出范围`Dispose`时对值添加对的调用。</span><span class="sxs-lookup"><span data-stu-id="33441-120">It provides the same functionality as a `let` binding but adds a call to `Dispose` on the value when the value goes out of scope.</span></span> <span data-ttu-id="33441-121">请注意, 编译器会对值插入 null 检查, 因此, 如果该值为`null`, 则不`Dispose`会尝试调用。</span><span class="sxs-lookup"><span data-stu-id="33441-121">Note that the compiler inserts a null check on the value, so that if the value is `null`, the call to `Dispose` is not attempted.</span></span>

<span data-ttu-id="33441-122">下面的示例演示如何使用`use`关键字自动关闭文件。</span><span class="sxs-lookup"><span data-stu-id="33441-122">The following example shows how to close a file automatically by using the `use` keyword.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

> [!NOTE]
> <span data-ttu-id="33441-123">可以在计算`use`表达式中使用, 在这种情况下, 将使用`use`自定义版本的表达式。</span><span class="sxs-lookup"><span data-stu-id="33441-123">You can use `use` in computation expressions, in which case a customized version of the `use` expression is used.</span></span> <span data-ttu-id="33441-124">有关详细信息, 请参阅[序列](sequences.md)、[异步工作流](asynchronous-workflows.md)和[计算表达式](computation-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="33441-124">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="using-function"></a><span data-ttu-id="33441-125">使用函数</span><span class="sxs-lookup"><span data-stu-id="33441-125">using Function</span></span>

<span data-ttu-id="33441-126">`using`函数具有以下格式:</span><span class="sxs-lookup"><span data-stu-id="33441-126">The `using` function has the following form:</span></span>

<span data-ttu-id="33441-127">`using`(*表达式*=)*函数或 lambda*</span><span class="sxs-lookup"><span data-stu-id="33441-127">`using` (*expression1*) *function-or-lambda*</span></span>

<span data-ttu-id="33441-128">在表达式*中, 表达式*= 创建必须释放的对象。 `using`</span><span class="sxs-lookup"><span data-stu-id="33441-128">In a `using` expression, *expression1* creates the object that must be disposed.</span></span> <span data-ttu-id="33441-129">*表达式*类型 (必须释放的对象) 的结果将成为*函数或 lambda*的参数 (*值*), 这是一个函数, 该函数需要类型的单个剩余参数与生成*的值相匹配*表达式类型或需要该类型的参数的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="33441-129">The result of *expression1* (the object that must be disposed) becomes an argument, *value*, to *function-or-lambda*, which is either a function that expects a single remaining argument of a type that matches the value produced by *expression1*, or a lambda expression that expects an argument of that type.</span></span> <span data-ttu-id="33441-130">在函数执行结束时, 运行时会调用`Dispose`并释放资源 (除非值为`null`, 在这种情况下, 不尝试调用 Dispose)。</span><span class="sxs-lookup"><span data-stu-id="33441-130">At the end of the execution of the function, the runtime calls `Dispose` and frees the resources (unless the value is `null`, in which case the call to Dispose is not attempted).</span></span>

<span data-ttu-id="33441-131">下面的示例演示带有`using` lambda 表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="33441-131">The following example demonstrates the `using` expression with a lambda expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

<span data-ttu-id="33441-132">下一个示例显示`using`带有函数的表达式。</span><span class="sxs-lookup"><span data-stu-id="33441-132">The next example shows the `using` expression with a function.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

<span data-ttu-id="33441-133">请注意, 该函数可能是已应用了某些参数的函数。</span><span class="sxs-lookup"><span data-stu-id="33441-133">Note that the function could be a function that has some arguments applied already.</span></span> <span data-ttu-id="33441-134">下面的代码示例展示了此操作。</span><span class="sxs-lookup"><span data-stu-id="33441-134">The following code example demonstrates this.</span></span> <span data-ttu-id="33441-135">它会创建一个包含字符串`XYZ`的文件。</span><span class="sxs-lookup"><span data-stu-id="33441-135">It creates a file that contains the string `XYZ`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

<span data-ttu-id="33441-136">`using` 函数`use`和绑定几乎等效于完成相同操作的方法。</span><span class="sxs-lookup"><span data-stu-id="33441-136">The `using` function and the `use` binding are nearly equivalent ways to accomplish the same thing.</span></span> <span data-ttu-id="33441-137">关键字可以更好地控制调用`Dispose`的时间。 `using`</span><span class="sxs-lookup"><span data-stu-id="33441-137">The `using` keyword provides more control over when `Dispose` is called.</span></span> <span data-ttu-id="33441-138">使用`using`时, `Dispose`在函数或 lambda 表达式的末尾调用`use` ; 当使用关键字时, `Dispose`将在包含代码块的末尾调用。</span><span class="sxs-lookup"><span data-stu-id="33441-138">When you use `using`, `Dispose` is called at the end of the function or lambda expression; when you use the `use` keyword, `Dispose` is called at the end of the containing code block.</span></span> <span data-ttu-id="33441-139">一般情况下, 您应该优先使用`use`而不是`using`函数。</span><span class="sxs-lookup"><span data-stu-id="33441-139">In general, you should prefer to use `use` instead of the `using` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="33441-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="33441-140">See also</span></span>

- [<span data-ttu-id="33441-141">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="33441-141">F# Language Reference</span></span>](index.md)
