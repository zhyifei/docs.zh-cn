---
title: "本地函数与 Lambda 表达式"
description: "了解为什么选择本地函数比选择 Lambda 表达式更好。"
keywords: "C#, .NET, .NET Core, 最新功能, 新增功能, 本地函数, Lambda 表达式"
author: BillWagner
ms.author: wiwagn
ms.date: 06/27/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.translationtype: HT
ms.sourcegitcommit: 9bb17207ba72bb22f5d6db55e9d1bd77e3013445
ms.openlocfilehash: 0730e7b7d6e3ef7b5c534d16baacde6a7dafacfc
ms.contentlocale: zh-cn
ms.lasthandoff: 08/25/2017

---
# <a name="local-functions-compared-to-lambda-expressions"></a><span data-ttu-id="4eb22-104">本地函数与 Lambda 表达式比较</span><span class="sxs-lookup"><span data-stu-id="4eb22-104">Local functions compared to Lambda expressions</span></span>

<span data-ttu-id="4eb22-105">乍看之下，[本地函数](programming-guide/classes-and-structs/local-functions.md)和 [lambda 表达式](lambda-expressions.md)非常相似。</span><span class="sxs-lookup"><span data-stu-id="4eb22-105">At first glance, [local functions](programming-guide/classes-and-structs/local-functions.md) and [lambda expressions](lambda-expressions.md) are very similar.</span></span>
<span data-ttu-id="4eb22-106">根据需要，本地函数可能是更好、更简单的解决方案。</span><span class="sxs-lookup"><span data-stu-id="4eb22-106">Depending on your needs, local functions may be a much better and simpler solution.</span></span>

<span data-ttu-id="4eb22-107">让我们检查一下阶乘算法的本地函数实现和 lambda 表达式实现之间的差异。</span><span class="sxs-lookup"><span data-stu-id="4eb22-107">Let's examine the differences between the local function and lambda expression implementations of the factorial algorithm.</span></span> <span data-ttu-id="4eb22-108">首先使用本地函数的版本：</span><span class="sxs-lookup"><span data-stu-id="4eb22-108">First the version using a local function:</span></span>

<span data-ttu-id="4eb22-109">[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "使用本地函数实现阶乘递归")]</span><span class="sxs-lookup"><span data-stu-id="4eb22-109">[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]</span></span>

<span data-ttu-id="4eb22-110">将该实现与使用 Lambda 表达式的版本对比：</span><span class="sxs-lookup"><span data-stu-id="4eb22-110">Contrast that implementation with a version that uses lambda expressions:</span></span>

<span data-ttu-id="4eb22-111">[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "使用 lambda 表达式实现阶乘递归")]</span><span class="sxs-lookup"><span data-stu-id="4eb22-111">[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]</span></span>

<span data-ttu-id="4eb22-112">首先，lambda 表达式是通过实例化委托并调用该委托来实现的。</span><span class="sxs-lookup"><span data-stu-id="4eb22-112">First, lambda expressions are implemented by instantiating a delegate and invoking that delegate.</span></span> <span data-ttu-id="4eb22-113">而本地函数是作为方法调用来实现的。</span><span class="sxs-lookup"><span data-stu-id="4eb22-113">Local functions are implemented as method calls.</span></span>
<span data-ttu-id="4eb22-114">Lambda 表达式所需的实例化意味着额外的内存分配，后者可能是时间关键代码路径中的性能因素。</span><span class="sxs-lookup"><span data-stu-id="4eb22-114">The instantiation necessary for lambda expressions means extra memory allocations, which may be a performance factor in time critical code paths.</span></span>
<span data-ttu-id="4eb22-115">本地函数不会产生这种开销。</span><span class="sxs-lookup"><span data-stu-id="4eb22-115">Local functions do not incur this overhead.</span></span> <span data-ttu-id="4eb22-116">在以上示例中，本地函数版本具有的分配比 lambda 表达式版本少 2 个。</span><span class="sxs-lookup"><span data-stu-id="4eb22-116">In the example above, the local functions version has 2 fewer allocations than the lambda expression version.</span></span>

<span data-ttu-id="4eb22-117">此递归方法非常简单，可以将本地函数作为具有编译器生成名称的私有方法实现。</span><span class="sxs-lookup"><span data-stu-id="4eb22-117">This recursive method is simple enough that the local function is implemented as a private method with a compiler generated name.</span></span> <span data-ttu-id="4eb22-118">它与其它私有方法唯一的不同是，它在语义上作用于外部函数。</span><span class="sxs-lookup"><span data-stu-id="4eb22-118">Its only difference from other private methods is that it is semantically scoped inside the outer function.</span></span>

<span data-ttu-id="4eb22-119">第二，本地函数可以在定义前进行调用。</span><span class="sxs-lookup"><span data-stu-id="4eb22-119">Second, local functions can be called before they are defined.</span></span> <span data-ttu-id="4eb22-120">必须先声明 Lambda 表达式，然后再进行定义。</span><span class="sxs-lookup"><span data-stu-id="4eb22-120">Lambda expressions must be declared before they are defined.</span></span> <span data-ttu-id="4eb22-121">这意味着本地函数在递归算法中更易于使用，如上所示。</span><span class="sxs-lookup"><span data-stu-id="4eb22-121">This means local functions are easier to use in recursive algorithms, as shown above.</span></span>

<span data-ttu-id="4eb22-122">请注意，使用 lambda 表达式的版本必须先定义 lambda 表达式 `nthFactorial`，然后再对其进行声明并实例化。</span><span class="sxs-lookup"><span data-stu-id="4eb22-122">Notice that the version using the lambda expression must declare and initialize the lambda expression, `nthFactorial` before defining it.</span></span> <span data-ttu-id="4eb22-123">否则，会导致分配前引用 `nthFactorial` 时出现编译时错误。</span><span class="sxs-lookup"><span data-stu-id="4eb22-123">Not doing so results in a compile time error for referencing `nthFactorial` before assigning it.</span></span>
<span data-ttu-id="4eb22-124">使用本地函数创建递归算法更轻松。</span><span class="sxs-lookup"><span data-stu-id="4eb22-124">Recursive algorithms are easier to create using local functions.</span></span>

<span data-ttu-id="4eb22-125">第三，对于 lambda 表达式，编译器必须始终创建匿名类和该类的实例以存储任何由闭包捕获的变量。</span><span class="sxs-lookup"><span data-stu-id="4eb22-125">Third, for lambda expressions, the compiler must always create an anonymous class and an instance of that class to store any variables captured by the closure.</span></span> <span data-ttu-id="4eb22-126">请看以下异步示例：</span><span class="sxs-lookup"><span data-stu-id="4eb22-126">Consider this async example:</span></span>

<span data-ttu-id="4eb22-127">[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "使用 lambda 表达式返回方法的任务")]</span><span class="sxs-lookup"><span data-stu-id="4eb22-127">[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]</span></span>

<span data-ttu-id="4eb22-128">该 lambda 表达式的闭包包含 `address`、`index` 和 `name` 变量。</span><span class="sxs-lookup"><span data-stu-id="4eb22-128">The closure for this lambda expression contains the `address`, `index` and `name` variables.</span></span> <span data-ttu-id="4eb22-129">就本地函数而言，实现闭包的对象可能为 `struct` 类型。</span><span class="sxs-lookup"><span data-stu-id="4eb22-129">In the case of local functions, the object that implements the closure may be a `struct` type.</span></span> <span data-ttu-id="4eb22-130">这将保存在分配上。</span><span class="sxs-lookup"><span data-stu-id="4eb22-130">That would save on an allocation.</span></span>

> [!NOTE]
> <span data-ttu-id="4eb22-131">等效于此方法的本地函数还将类用于闭包。</span><span class="sxs-lookup"><span data-stu-id="4eb22-131">The local function equivalent of this method also uses a class for the closure.</span></span> <span data-ttu-id="4eb22-132">实现详细信息包括本地函数的闭包是作为 `class` 还是 `struct` 实现。</span><span class="sxs-lookup"><span data-stu-id="4eb22-132">Whether the closure for a local function is implemented as a `class` or a `struct` is an implementation detail.</span></span> <span data-ttu-id="4eb22-133">本地函数可能使用 `struct`，而 lambda 将始终使用 `class`。</span><span class="sxs-lookup"><span data-stu-id="4eb22-133">A local function may use a `struct` whereas a lambda will always use a `class`.</span></span>

<span data-ttu-id="4eb22-134">[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "使用本地函数的 Task 返回方法")]</span><span class="sxs-lookup"><span data-stu-id="4eb22-134">[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]</span></span>

<span data-ttu-id="4eb22-135">在本示例中尚未演示的最后一个优点是，可将本地函数作为迭代器实现，使用 `yield return` 语法生成一系列值。</span><span class="sxs-lookup"><span data-stu-id="4eb22-135">One final advantage not demonstrated in this sample is that local functions can be implemented as iterators, using the `yield return` syntax to produce a sequence of values.</span></span>

<span data-ttu-id="4eb22-136">虽然本地函数对 lambda 表达式可能有点冗余，但实际上它们的目的和用法都不一样。</span><span class="sxs-lookup"><span data-stu-id="4eb22-136">While local functions may seem redundant to lambda expressions, they actually serve different purposes and have different uses.</span></span>
<span data-ttu-id="4eb22-137">如果想要编写仅从上下文或其他方法中调用的函数，则使用本地函数更高效。</span><span class="sxs-lookup"><span data-stu-id="4eb22-137">Local functions are more efficient for the case when you want to write a function that is called only from the context of another method.</span></span>

