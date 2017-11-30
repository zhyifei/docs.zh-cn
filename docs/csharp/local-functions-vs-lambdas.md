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
ms.openlocfilehash: 20312b58a24dc991791edad4bb92d3a8ca6d501a
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2017
---
# <a name="local-functions-compared-to-lambda-expressions"></a><span data-ttu-id="2d990-104">相比于 lambda 表达式的本地函数</span><span class="sxs-lookup"><span data-stu-id="2d990-104">Local functions compared to lambda expressions</span></span>

<span data-ttu-id="2d990-105">乍看之下，[本地函数](programming-guide/classes-and-structs/local-functions.md)和 [lambda 表达式](lambda-expressions.md)非常相似。</span><span class="sxs-lookup"><span data-stu-id="2d990-105">At first glance, [local functions](programming-guide/classes-and-structs/local-functions.md) and [lambda expressions](lambda-expressions.md) are very similar.</span></span> <span data-ttu-id="2d990-106">在许多情况下，使用 lambda 表达式和本地函数之间的选择是一种样式和个人首选项。</span><span class="sxs-lookup"><span data-stu-id="2d990-106">In many cases, the choice between using lambda expressions and local functions is a matter of style and personal preference.</span></span> <span data-ttu-id="2d990-107">但是，有在其中你可以使用一个或其他你应注意的实际差异。</span><span class="sxs-lookup"><span data-stu-id="2d990-107">However, there are real differences in where you can use one or the other that you should be aware of.</span></span>

<span data-ttu-id="2d990-108">让我们检查一下阶乘算法的本地函数实现和 lambda 表达式实现之间的差异。</span><span class="sxs-lookup"><span data-stu-id="2d990-108">Let's examine the differences between the local function and lambda expression implementations of the factorial algorithm.</span></span> <span data-ttu-id="2d990-109">首先使用本地函数的版本：</span><span class="sxs-lookup"><span data-stu-id="2d990-109">First the version using a local function:</span></span>

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

<span data-ttu-id="2d990-110">将该实现与使用 Lambda 表达式的版本对比：</span><span class="sxs-lookup"><span data-stu-id="2d990-110">Contrast that implementation with a version that uses lambda expressions:</span></span>

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

<span data-ttu-id="2d990-111">本地函数具有名称。</span><span class="sxs-lookup"><span data-stu-id="2d990-111">The local functions have names.</span></span> <span data-ttu-id="2d990-112">Lambda 表达式是分配给变量的匿名方法`Func`或`Action`类型。</span><span class="sxs-lookup"><span data-stu-id="2d990-112">The lambda expressions are anonymous methods that are assigned to variables that are `Func` or `Action` types.</span></span> <span data-ttu-id="2d990-113">在声明局部函数时，自变量类型和返回类型是函数声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="2d990-113">When you declare a local function, the argument types and return type are part of the function declaration.</span></span> <span data-ttu-id="2d990-114">而不是主体的 lambda 的一部分表达式、 参数类型和返回类型是主体的 lambda 表达式的变量类型声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="2d990-114">Instead of being part of the body of the lambda expression, the argument types and return type are part of the lambda expression's variable type declaration.</span></span> <span data-ttu-id="2d990-115">这些两个差异可能会导致更清晰的代码。</span><span class="sxs-lookup"><span data-stu-id="2d990-115">Those two differences may result in clearer code.</span></span>

<span data-ttu-id="2d990-116">本地函数具有比 lambda 表达式的明确赋值的不同规则。</span><span class="sxs-lookup"><span data-stu-id="2d990-116">Local functions have different rules for definite assignment than lambda expressions.</span></span> <span data-ttu-id="2d990-117">可以从任何位置处于范围内的代码位置引用本地函数声明。</span><span class="sxs-lookup"><span data-stu-id="2d990-117">A local function declaration can be referenced from any code location where it is in scope.</span></span> <span data-ttu-id="2d990-118">必须将 lambda 表达式分配给一个委托变量，然后它才能访问 （或通过引用 lambda 表达式 delgate 调用。）请注意，使用 lambda 表达式的版本必须先定义 lambda 表达式 `nthFactorial`，然后再对其进行声明并实例化。</span><span class="sxs-lookup"><span data-stu-id="2d990-118">A lambda expression must be assigned to a delegate variable before it can be accessed (or called through the delgate referencing the lambda expression.) Notice that the version using the lambda expression must declare and initialize the lambda expression, `nthFactorial` before defining it.</span></span> <span data-ttu-id="2d990-119">否则，会导致分配前引用 `nthFactorial` 时出现编译时错误。</span><span class="sxs-lookup"><span data-stu-id="2d990-119">Not doing so results in a compile time error for referencing `nthFactorial` before assigning it.</span></span>
<span data-ttu-id="2d990-120">这些差异意味着递归算法是更轻松地创建使用本地函数。</span><span class="sxs-lookup"><span data-stu-id="2d990-120">These differences mean that recursive algorithms are easier to create using local functions.</span></span> <span data-ttu-id="2d990-121">你可以声明并定义调用其自身的本地函数。</span><span class="sxs-lookup"><span data-stu-id="2d990-121">You can declare and define a local function that calls itself.</span></span> <span data-ttu-id="2d990-122">Lambda 表达式必须是声明，并且它们可以是重新分配给引用的相同的 lambda 表达式的主体之前分配默认值。</span><span class="sxs-lookup"><span data-stu-id="2d990-122">Lambda expressions must be declared, and assigned a default value before they can be re-assigned to a body that references the same lambda expression.</span></span>

<span data-ttu-id="2d990-123">明确赋值规则也会影响任何通过本地的函数或 lamdba epression 捕获的变量。</span><span class="sxs-lookup"><span data-stu-id="2d990-123">Definite assignment rules also affect any variables that are captured by the local function or lamdba epression.</span></span> <span data-ttu-id="2d990-124">本地函数和 lambda 表达式规则要求，任何捕获的变量，则肯定分配的点处时本地的函数或 lambda 表达式转换为的委托。</span><span class="sxs-lookup"><span data-stu-id="2d990-124">Both local functions and lambda expression rules demand that any captured variables are definitely assigned at the point when the local function or lambda expression is converted to a delegate.</span></span> <span data-ttu-id="2d990-125">不同之处在于，进行声明时，将 lambda 表达式转换为委托。</span><span class="sxs-lookup"><span data-stu-id="2d990-125">The difference is that lambda expressions are converted to delegates when they are declared.</span></span> <span data-ttu-id="2d990-126">本地函数将转换为委托仅当使用作为代理。</span><span class="sxs-lookup"><span data-stu-id="2d990-126">Local functions are converted to delegates only when used as a delegate.</span></span> <span data-ttu-id="2d990-127">如果声明了局部函数只能引用它通过调用方法一样，它将转换为的委托。</span><span class="sxs-lookup"><span data-stu-id="2d990-127">If you declare a local function and only reference it by calling it like a method, it will not be converted to a delegate.</span></span> <span data-ttu-id="2d990-128">该规则，可声明在其封闭范围中的任何方便的位置的本地函数。</span><span class="sxs-lookup"><span data-stu-id="2d990-128">That rule enables you to declare a local function at any convenient location in its enclosing scope.</span></span> <span data-ttu-id="2d990-129">很普遍后返回的任何语句声明在父方法的末尾的本地函数。</span><span class="sxs-lookup"><span data-stu-id="2d990-129">It's common to declare local functions at the end of the parent method, after any return statements.</span></span>

<span data-ttu-id="2d990-130">第三，编译器可以执行静态分析，使本地函数，以明确分配封闭范围中捕获的变量。</span><span class="sxs-lookup"><span data-stu-id="2d990-130">Third, the compiler can perform static analysis that enables local functions to definitely assign captured variables in the enclosing scope.</span></span> <span data-ttu-id="2d990-131">请看以下示例：</span><span class="sxs-lookup"><span data-stu-id="2d990-131">Consider this example:</span></span>

```csharp
bool M()
{
    int y;
    Local();
    return y;

    void Local() => y = 0;
}
```

<span data-ttu-id="2d990-132">编译器可以确定`Local`明确分配`y`时调用。</span><span class="sxs-lookup"><span data-stu-id="2d990-132">The compiler can determine that `Local` definitely assigns `y` when called.</span></span> <span data-ttu-id="2d990-133">因为`Local`之前调用`return`语句， `y` definitiely 分配在`return`语句。</span><span class="sxs-lookup"><span data-stu-id="2d990-133">Because `Local` is called before the `return` statement, `y` is definitiely assigned at the `return` statement.</span></span>

<span data-ttu-id="2d990-134">启用分析允许的第四个差异分析。</span><span class="sxs-lookup"><span data-stu-id="2d990-134">The analysis that enables that analysis enables the fourth difference.</span></span>
<span data-ttu-id="2d990-135">具体取决于其使用本地函数可以避免始终所需的 lambda 表达式的堆分配。</span><span class="sxs-lookup"><span data-stu-id="2d990-135">Depending on their use, local functions can avoid heap allocations that are always necessary for lambda expressions.</span></span> <span data-ttu-id="2d990-136">如果本地函数永远不会转换为的委托，并且无本地函数捕获的变量捕获由其他 lambda 或转换为委托的本地函数，编译器可以避免堆分配。</span><span class="sxs-lookup"><span data-stu-id="2d990-136">If a local function is never converted to a delegate, and none of the variables captured by the local function is captured by other lambdas or local functions that are converted to delegates, the compiler can avoid heap allocations.</span></span> 

<span data-ttu-id="2d990-137">请看以下异步示例：</span><span class="sxs-lookup"><span data-stu-id="2d990-137">Consider this async example:</span></span>

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

<span data-ttu-id="2d990-138">该 lambda 表达式的闭包包含 `address`、`index` 和 `name` 变量。</span><span class="sxs-lookup"><span data-stu-id="2d990-138">The closure for this lambda expression contains the `address`, `index` and `name` variables.</span></span> <span data-ttu-id="2d990-139">就本地函数而言，实现闭包的对象可能为 `struct` 类型。</span><span class="sxs-lookup"><span data-stu-id="2d990-139">In the case of local functions, the object that implements the closure may be a `struct` type.</span></span> <span data-ttu-id="2d990-140">将通过对本地函数的引用传递该结构类型。</span><span class="sxs-lookup"><span data-stu-id="2d990-140">That struct type would be passed by reference to the local function.</span></span> <span data-ttu-id="2d990-141">实现这种差异将保存在分配上。</span><span class="sxs-lookup"><span data-stu-id="2d990-141">This difference in implementation would save on an allocation.</span></span>

<span data-ttu-id="2d990-142">Lambda 表达式所需实例化意味着额外的内存分配，可能是在时间关键代码路径中的一个性能因素。</span><span class="sxs-lookup"><span data-stu-id="2d990-142">The instantiation necessary for lambda expressions means extra memory allocations, which may be a performance factor in time-critical code paths.</span></span>
<span data-ttu-id="2d990-143">本地函数不会产生这种开销。</span><span class="sxs-lookup"><span data-stu-id="2d990-143">Local functions do not incur this overhead.</span></span> <span data-ttu-id="2d990-144">在以上示例中，本地函数版本具有的分配比 lambda 表达式版本少 2 个。</span><span class="sxs-lookup"><span data-stu-id="2d990-144">In the example above, the local functions version has 2 fewer allocations than the lambda expression version.</span></span>

> [!NOTE]
> <span data-ttu-id="2d990-145">等效于此方法的本地函数还将类用于闭包。</span><span class="sxs-lookup"><span data-stu-id="2d990-145">The local function equivalent of this method also uses a class for the closure.</span></span> <span data-ttu-id="2d990-146">实现详细信息包括本地函数的闭包是作为 `class` 还是 `struct` 实现。</span><span class="sxs-lookup"><span data-stu-id="2d990-146">Whether the closure for a local function is implemented as a `class` or a `struct` is an implementation detail.</span></span> <span data-ttu-id="2d990-147">本地函数可能使用 `struct`，而 lambda 将始终使用 `class`。</span><span class="sxs-lookup"><span data-stu-id="2d990-147">A local function may use a `struct` whereas a lambda will always use a `class`.</span></span>

[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]

<span data-ttu-id="2d990-148">在本示例中尚未演示的最后一个优点是，可将本地函数作为迭代器实现，使用 `yield return` 语法生成一系列值。</span><span class="sxs-lookup"><span data-stu-id="2d990-148">One final advantage not demonstrated in this sample is that local functions can be implemented as iterators, using the `yield return` syntax to produce a sequence of values.</span></span> <span data-ttu-id="2d990-149">`yield return`语句不允许在 lambda 表达式中。</span><span class="sxs-lookup"><span data-stu-id="2d990-149">The `yield return` statement is not allowed in lambda expressions.</span></span>

<span data-ttu-id="2d990-150">虽然本地函数对 lambda 表达式可能有点冗余，但实际上它们的目的和用法都不一样。</span><span class="sxs-lookup"><span data-stu-id="2d990-150">While local functions may seem redundant to lambda expressions, they actually serve different purposes and have different uses.</span></span>
<span data-ttu-id="2d990-151">如果想要编写仅从上下文或其他方法中调用的函数，则使用本地函数更高效。</span><span class="sxs-lookup"><span data-stu-id="2d990-151">Local functions are more efficient for the case when you want to write a function that is called only from the context of another method.</span></span>
