---
title: 本地函数与 Lambda 表达式
description: 了解为什么选择本地函数比选择 Lambda 表达式更好。
ms.date: 06/27/2016
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.openlocfilehash: 7577950314f8c57fba635db8b2bcd69e8d427dc3
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611440"
---
# <a name="local-functions-compared-to-lambda-expressions"></a><span data-ttu-id="3f802-103">本地函数与 Lambda 表达式比较</span><span class="sxs-lookup"><span data-stu-id="3f802-103">Local functions compared to lambda expressions</span></span>

<span data-ttu-id="3f802-104">乍看之下，[本地函数](programming-guide/classes-and-structs/local-functions.md)和 [lambda 表达式](./programming-guide/statements-expressions-operators/lambda-expressions.md)非常相似。</span><span class="sxs-lookup"><span data-stu-id="3f802-104">At first glance, [local functions](programming-guide/classes-and-structs/local-functions.md) and [lambda expressions](./programming-guide/statements-expressions-operators/lambda-expressions.md) are very similar.</span></span> <span data-ttu-id="3f802-105">在许多情况下，选择使用 Lambda 表达式还是本地函数是风格和个人偏好的问题。</span><span class="sxs-lookup"><span data-stu-id="3f802-105">In many cases, the choice between using lambda expressions and local functions is a matter of style and personal preference.</span></span> <span data-ttu-id="3f802-106">但是，应该注意，从两者中选用一种的时机和条件其实是存在差别的。</span><span class="sxs-lookup"><span data-stu-id="3f802-106">However, there are real differences in where you can use one or the other that you should be aware of.</span></span>

<span data-ttu-id="3f802-107">让我们检查一下阶乘算法的本地函数实现和 lambda 表达式实现之间的差异。</span><span class="sxs-lookup"><span data-stu-id="3f802-107">Let's examine the differences between the local function and lambda expression implementations of the factorial algorithm.</span></span> <span data-ttu-id="3f802-108">首先使用本地函数的版本：</span><span class="sxs-lookup"><span data-stu-id="3f802-108">First the version using a local function:</span></span>

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

<span data-ttu-id="3f802-109">将该实现与使用 Lambda 表达式的版本对比：</span><span class="sxs-lookup"><span data-stu-id="3f802-109">Contrast that implementation with a version that uses lambda expressions:</span></span>

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

<span data-ttu-id="3f802-110">本地函数具有名称。</span><span class="sxs-lookup"><span data-stu-id="3f802-110">The local functions have names.</span></span> <span data-ttu-id="3f802-111">Lambda 表达式是赋给 `Func` 或 `Action` 类型变量的匿名方法。</span><span class="sxs-lookup"><span data-stu-id="3f802-111">The lambda expressions are anonymous methods that are assigned to variables that are `Func` or `Action` types.</span></span> <span data-ttu-id="3f802-112">在声明本地函数时，参数类型和返回类型是函数声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="3f802-112">When you declare a local function, the argument types and return type are part of the function declaration.</span></span> <span data-ttu-id="3f802-113">参数类型和返回类型不是 Lambda 表达式主体的一部分，而是 Lambda 表达式变量类型声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="3f802-113">Instead of being part of the body of the lambda expression, the argument types and return type are part of the lambda expression's variable type declaration.</span></span> <span data-ttu-id="3f802-114">这两种差别可以产生跟清楚的代码。</span><span class="sxs-lookup"><span data-stu-id="3f802-114">Those two differences may result in clearer code.</span></span>

<span data-ttu-id="3f802-115">本地函数的明确赋值规则与 Lambda 表达式的不同。</span><span class="sxs-lookup"><span data-stu-id="3f802-115">Local functions have different rules for definite assignment than lambda expressions.</span></span> <span data-ttu-id="3f802-116">从范围内的任意代码位置都可以引用本地函数声明。</span><span class="sxs-lookup"><span data-stu-id="3f802-116">A local function declaration can be referenced from any code location where it is in scope.</span></span> <span data-ttu-id="3f802-117">在可以访问（或通过引用 Lambda 表达式的委托调用）Lambda 表达式之前，必须先将 Lambda 表达式赋给委托变量。请注意，使用 lambda 表达式的版本必须先定义 lambda 表达式 `nthFactorial`，然后再对其进行声明并实例化。</span><span class="sxs-lookup"><span data-stu-id="3f802-117">A lambda expression must be assigned to a delegate variable before it can be accessed (or called through the delegate referencing the lambda expression.) Notice that the version using the lambda expression must declare and initialize the lambda expression, `nthFactorial` before defining it.</span></span> <span data-ttu-id="3f802-118">否则，会导致分配前引用 `nthFactorial` 时出现编译时错误。</span><span class="sxs-lookup"><span data-stu-id="3f802-118">Not doing so results in a compile time error for referencing `nthFactorial` before assigning it.</span></span>
<span data-ttu-id="3f802-119">这些区别意味着使用本地函数创建递归算法会更轻松。</span><span class="sxs-lookup"><span data-stu-id="3f802-119">These differences mean that recursive algorithms are easier to create using local functions.</span></span> <span data-ttu-id="3f802-120">你可以声明和定义一个调用自身的本地函数。</span><span class="sxs-lookup"><span data-stu-id="3f802-120">You can declare and define a local function that calls itself.</span></span> <span data-ttu-id="3f802-121">必须声明 Lambda 表达式，赋给默认值，然后才能将其重新赋给引用相同 Lambda 表达式的主体。</span><span class="sxs-lookup"><span data-stu-id="3f802-121">Lambda expressions must be declared, and assigned a default value before they can be re-assigned to a body that references the same lambda expression.</span></span>

<span data-ttu-id="3f802-122">明确分配规则也会影响本地函数或 Lambda 表达式捕获的任何变量。</span><span class="sxs-lookup"><span data-stu-id="3f802-122">Definite assignment rules also affect any variables that are captured by the local function or lambda expression.</span></span> <span data-ttu-id="3f802-123">本地函数和 Lambda 表达式规则都要求在将本地函数或 Lambda 表达式转换为委托时，明确分配任何捕获的变量。</span><span class="sxs-lookup"><span data-stu-id="3f802-123">Both local functions and lambda expression rules demand that any captured variables are definitely assigned at the point when the local function or lambda expression is converted to a delegate.</span></span> <span data-ttu-id="3f802-124">区别在于 Lambda 表达式在声明时转换为委托。</span><span class="sxs-lookup"><span data-stu-id="3f802-124">The difference is that lambda expressions are converted to delegates when they are declared.</span></span> <span data-ttu-id="3f802-125">只有在用作委托时，本地函数才转换为委托。</span><span class="sxs-lookup"><span data-stu-id="3f802-125">Local functions are converted to delegates only when used as a delegate.</span></span> <span data-ttu-id="3f802-126">如果声明了本地函数，但只是通过像调用方法一样调用该函数来引用该函数，它将不会转换成委托。</span><span class="sxs-lookup"><span data-stu-id="3f802-126">If you declare a local function and only reference it by calling it like a method, it will not be converted to a delegate.</span></span> <span data-ttu-id="3f802-127">使用该规则可在封闭范围内的任何方便的位置声明本地函数。</span><span class="sxs-lookup"><span data-stu-id="3f802-127">That rule enables you to declare a local function at any convenient location in its enclosing scope.</span></span> <span data-ttu-id="3f802-128">声明本地函数的位置常见于父方法的末尾和返回任何语句后方。</span><span class="sxs-lookup"><span data-stu-id="3f802-128">It's common to declare local functions at the end of the parent method, after any return statements.</span></span>

<span data-ttu-id="3f802-129">第三，编译器可以执行静态分析，因此本地函数能够在封闭范围内明确分配捕获的变量。</span><span class="sxs-lookup"><span data-stu-id="3f802-129">Third, the compiler can perform static analysis that enables local functions to definitely assign captured variables in the enclosing scope.</span></span> <span data-ttu-id="3f802-130">请看以下示例：</span><span class="sxs-lookup"><span data-stu-id="3f802-130">Consider this example:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="3f802-131">编译器可以确定 `LocalFunction` 在调用时明确分配 `y`。</span><span class="sxs-lookup"><span data-stu-id="3f802-131">The compiler can determine that `LocalFunction` definitely assigns `y` when called.</span></span> <span data-ttu-id="3f802-132">因为在 `return` 语句之前调用了 `LocalFunction`，所以在 `return` 语句中明确分配了 `y`。</span><span class="sxs-lookup"><span data-stu-id="3f802-132">Because `LocalFunction` is called before the `return` statement, `y` is definitely assigned at the `return` statement.</span></span>

<span data-ttu-id="3f802-133">可实现示例分析的分析允许第四个差异。</span><span class="sxs-lookup"><span data-stu-id="3f802-133">The analysis that enables the example analysis enables the fourth difference.</span></span>
<span data-ttu-id="3f802-134">根据它们的用途，本地函数可以避免 Lambda 表达式始终需要的堆分配。</span><span class="sxs-lookup"><span data-stu-id="3f802-134">Depending on their use, local functions can avoid heap allocations that are always necessary for lambda expressions.</span></span> <span data-ttu-id="3f802-135">如果本地函数永远不会转换为委托，并且本地函数捕获的变量都不会被其他转换为委托的 lambda 或本地函数捕获，则编译器可以避免堆分配。</span><span class="sxs-lookup"><span data-stu-id="3f802-135">If a local function is never converted to a delegate, and none of the variables captured by the local function is captured by other lambdas or local functions that are converted to delegates, the compiler can avoid heap allocations.</span></span> 

<span data-ttu-id="3f802-136">请看以下异步示例：</span><span class="sxs-lookup"><span data-stu-id="3f802-136">Consider this async example:</span></span>

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

<span data-ttu-id="3f802-137">该 lambda 表达式的闭包包含 `address`、`index` 和 `name` 变量。</span><span class="sxs-lookup"><span data-stu-id="3f802-137">The closure for this lambda expression contains the `address`, `index` and `name` variables.</span></span> <span data-ttu-id="3f802-138">就本地函数而言，实现闭包的对象可能为 `struct` 类型。</span><span class="sxs-lookup"><span data-stu-id="3f802-138">In the case of local functions, the object that implements the closure may be a `struct` type.</span></span> <span data-ttu-id="3f802-139">该结构类型将通过引用传递给本地函数。</span><span class="sxs-lookup"><span data-stu-id="3f802-139">That struct type would be passed by reference to the local function.</span></span> <span data-ttu-id="3f802-140">实现中的这个差异将保存在分配上。</span><span class="sxs-lookup"><span data-stu-id="3f802-140">This difference in implementation would save on an allocation.</span></span>

<span data-ttu-id="3f802-141">Lambda 表达式所需的实例化意味着额外的内存分配，后者可能是时间关键代码路径中的性能因素。</span><span class="sxs-lookup"><span data-stu-id="3f802-141">The instantiation necessary for lambda expressions means extra memory allocations, which may be a performance factor in time-critical code paths.</span></span>
<span data-ttu-id="3f802-142">本地函数不会产生这种开销。</span><span class="sxs-lookup"><span data-stu-id="3f802-142">Local functions do not incur this overhead.</span></span> <span data-ttu-id="3f802-143">在以上示例中，本地函数版本具有的分配比 lambda 表达式版本少 2 个。</span><span class="sxs-lookup"><span data-stu-id="3f802-143">In the example above, the local functions version has 2 fewer allocations than the lambda expression version.</span></span>

> [!NOTE]
> <span data-ttu-id="3f802-144">等效于此方法的本地函数还将类用于闭包。</span><span class="sxs-lookup"><span data-stu-id="3f802-144">The local function equivalent of this method also uses a class for the closure.</span></span> <span data-ttu-id="3f802-145">实现详细信息包括本地函数的闭包是作为 `class` 还是 `struct` 实现。</span><span class="sxs-lookup"><span data-stu-id="3f802-145">Whether the closure for a local function is implemented as a `class` or a `struct` is an implementation detail.</span></span> <span data-ttu-id="3f802-146">本地函数可能使用 `struct`，而 lambda 将始终使用 `class`。</span><span class="sxs-lookup"><span data-stu-id="3f802-146">A local function may use a `struct` whereas a lambda will always use a `class`.</span></span>

[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

<span data-ttu-id="3f802-147">在本示例中尚未演示的最后一个优点是，可将本地函数作为迭代器实现，使用 `yield return` 语法生成一系列值。</span><span class="sxs-lookup"><span data-stu-id="3f802-147">One final advantage not demonstrated in this sample is that local functions can be implemented as iterators, using the `yield return` syntax to produce a sequence of values.</span></span> <span data-ttu-id="3f802-148">Lambda 表达式中不允许使用 `yield return` 语句。</span><span class="sxs-lookup"><span data-stu-id="3f802-148">The `yield return` statement is not allowed in lambda expressions.</span></span>

<span data-ttu-id="3f802-149">虽然本地函数对 lambda 表达式可能有点冗余，但实际上它们的目的和用法都不一样。</span><span class="sxs-lookup"><span data-stu-id="3f802-149">While local functions may seem redundant to lambda expressions, they actually serve different purposes and have different uses.</span></span>
<span data-ttu-id="3f802-150">如果想要编写仅从上下文或其他方法中调用的函数，则使用本地函数更高效。</span><span class="sxs-lookup"><span data-stu-id="3f802-150">Local functions are more efficient for the case when you want to write a function that is called only from the context of another method.</span></span>
