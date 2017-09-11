---
title: "执行表达式树"
description: "介绍通过将表达式树转换为可执行的中间语言 (IL) 指令，执行表达式树。"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 109e0ac5-2a9c-48b4-ac68-9b6219cdbccf
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4ca87c8410a04e9198e9dd6c379760e7b6596585
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="executing-expression-trees"></a><span data-ttu-id="38a39-104">执行表达式树</span><span class="sxs-lookup"><span data-stu-id="38a39-104">Executing Expression Trees</span></span>

[<span data-ttu-id="38a39-105">上一部分 -- 支持表达式树的框架类型</span><span class="sxs-lookup"><span data-stu-id="38a39-105">Previous -- Framework Types Supporting Expression Trees</span></span>](expression-classes.md)

<span data-ttu-id="38a39-106">*表达式树*是表示一些代码的数据结构。</span><span class="sxs-lookup"><span data-stu-id="38a39-106">An *expression tree* is a data structure that represents some code.</span></span>
<span data-ttu-id="38a39-107">它不是已编译且可执行的代码。</span><span class="sxs-lookup"><span data-stu-id="38a39-107">It is not compiled and executable code.</span></span> <span data-ttu-id="38a39-108">如果想要执行由表达式树表示的 .NET 代码，则必须将其转换为可执行的 IL 指令。</span><span class="sxs-lookup"><span data-stu-id="38a39-108">If you want to execute the .NET code that is represented by an expression tree, you must convert it into executable IL instructions.</span></span> 
## <a name="lambda-expressions-to-functions"></a><span data-ttu-id="38a39-109">Lambda 表达式到函数</span><span class="sxs-lookup"><span data-stu-id="38a39-109">Lambda Expressions to Functions</span></span>
<span data-ttu-id="38a39-110">可以将任何 LambdaExpression 或派生自 LambdaExpression 的任何类型转换为可执行的 IL。</span><span class="sxs-lookup"><span data-stu-id="38a39-110">You can convert any LambdaExpression, or any type derived from LambdaExpression into executable IL.</span></span> <span data-ttu-id="38a39-111">其他表达式类型不能直接转换为代码。</span><span class="sxs-lookup"><span data-stu-id="38a39-111">Other expression types cannot be directly converted into code.</span></span> <span data-ttu-id="38a39-112">此限制在实践中影响不大。</span><span class="sxs-lookup"><span data-stu-id="38a39-112">This restriction has little effect in practice.</span></span> <span data-ttu-id="38a39-113">Lambda 表达式是你可通过转换为可执行的中间语言 (IL) 来执行的唯一表达式类型。</span><span class="sxs-lookup"><span data-stu-id="38a39-113">Lambda expressions are the only types of expressions that you would want to execute by converting to executable intermediate language (IL).</span></span> <span data-ttu-id="38a39-114">（思考直接执行 `ConstantExpression` 意味着什么。</span><span class="sxs-lookup"><span data-stu-id="38a39-114">(Think about what it would mean to directly execute a `ConstantExpression`.</span></span> <span data-ttu-id="38a39-115">这是否意味着任何用处？）`LamdbaExpression` 或派生自 `LambdaExpression` 的类型的任何表达式树均可转换为 IL。</span><span class="sxs-lookup"><span data-stu-id="38a39-115">Would it mean anything useful?) Any expression tree that is a `LamdbaExpression`, or a type derived from `LambdaExpression` can be converted to IL.</span></span>
<span data-ttu-id="38a39-116">表达式类型 `Expression<TDelegate>` 是 .NET Core 库中的唯一具体示例。</span><span class="sxs-lookup"><span data-stu-id="38a39-116">The expression type `Expression<TDelegate>` is the only concrete example in the .NET Core libraries.</span></span> <span data-ttu-id="38a39-117">它用于表示映射到任何委托类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="38a39-117">It's used to represent an expression that maps to any delegate type.</span></span> <span data-ttu-id="38a39-118">由于此类型映射到一个委托类型，因此 .NET 可以检查表达式，并为匹配 lambda 表达式签名的适当委托生成 IL。</span><span class="sxs-lookup"><span data-stu-id="38a39-118">Because this type maps to a delegate type, .NET can examine the expression, and generate IL for an appropriate delegate that matches the signature of the lambda expression.</span></span> 

<span data-ttu-id="38a39-119">在大多数情况下，这将在表达式和其对应的委托之间创建简单映射。</span><span class="sxs-lookup"><span data-stu-id="38a39-119">In most cases, this creates a simple mapping between an expression, and its corresponding delegate.</span></span> <span data-ttu-id="38a39-120">例如，由 `Expression<Func<int>>` 表示的表达式树将被转换为 `Func<int>` 类型的委托。</span><span class="sxs-lookup"><span data-stu-id="38a39-120">For example, an expression tree that is represented by `Expression<Func<int>>` would be converted to a delegate of the type `Func<int>`.</span></span> <span data-ttu-id="38a39-121">对于具有任何返回类型和参数列表的 lambda 表达式，存在这样的委托类型：该类型是由该 lamdba 表达式表示的可执行代码的目标类型。</span><span class="sxs-lookup"><span data-stu-id="38a39-121">For a lambda expression with any return type and argument list, there exists a delegate type that is the target type for the executable code represented by that lamdba expression.</span></span>

<span data-ttu-id="38a39-122">`LamdbaExpression` 类型包含用于将表达式树转换为可执行代码的 `Compile` 和 `CompileToMethod` 成员。</span><span class="sxs-lookup"><span data-stu-id="38a39-122">The `LamdbaExpression` type contains `Compile` and `CompileToMethod` members that you would use to convert an expression tree to executable code.</span></span> <span data-ttu-id="38a39-123">`Compile` 方法创建委托。</span><span class="sxs-lookup"><span data-stu-id="38a39-123">The `Compile` method creates a delegate.</span></span> <span data-ttu-id="38a39-124">`ConmpileToMethod` 方法通过表示表达式树的已编译输出的 IL 更新 `MethodBuilder` 对象。</span><span class="sxs-lookup"><span data-stu-id="38a39-124">The `ConmpileToMethod` method updates a `MethodBuilder` object with the IL that represents the compiled output of the expression tree.</span></span> <span data-ttu-id="38a39-125">请注意，`CompileToMethod` 仅在完整的桌面框架上可用，不能用于 .NET Core 框架。</span><span class="sxs-lookup"><span data-stu-id="38a39-125">Note that `CompileToMethod` is only available on the full desktop framework, not on the .NET Core framework.</span></span>

<span data-ttu-id="38a39-126">还可以选择性地提供 `DebugInfoGenerator`，它将接收生成的委托对象的符号调试信息。</span><span class="sxs-lookup"><span data-stu-id="38a39-126">Optionally, you can also provide a `DebugInfoGenerator` that will receive the symbol debugging information for the generated delegate object.</span></span> <span data-ttu-id="38a39-127">这让你可以将表达式树转换为委托对象，并拥有生成的委托的完整调试信息。</span><span class="sxs-lookup"><span data-stu-id="38a39-127">This enables you to convert the expression tree into a delegate object, and have full debugging information about the generated delegate.</span></span>

<span data-ttu-id="38a39-128">使用下面的代码将表达式转换为委托：</span><span class="sxs-lookup"><span data-stu-id="38a39-128">You would convert an expression into a delegate using the following code:</span></span>

```csharp
Expression<Func<int>> add = () => 1 + 2;
var func = add.Compile(); // Create Delegate
var answer = func(); // Invoke Delegate
Console.WriteLine(answer);
```

<span data-ttu-id="38a39-129">请注意，该委托类型基于表达式类型。</span><span class="sxs-lookup"><span data-stu-id="38a39-129">Notice that the delegate type is based on the expression type.</span></span> <span data-ttu-id="38a39-130">如果想要以强类型的方式使用委托对象，则必须知道返回类型和参数列表。</span><span class="sxs-lookup"><span data-stu-id="38a39-130">You must know the return type and the argument list if you want to use the delegate object in a strongly typed manner.</span></span> <span data-ttu-id="38a39-131">`LambdaExpression.Compile()` 方法返回 `Delegate` 类型。</span><span class="sxs-lookup"><span data-stu-id="38a39-131">The `LambdaExpression.Compile()` method returns the `Delegate` type.</span></span> <span data-ttu-id="38a39-132">必须将其转换为正确的委托类型，以便使任何编译时工具检查返回类型的参数列表。</span><span class="sxs-lookup"><span data-stu-id="38a39-132">You will have to cast it to the correct delegate type to have any compile-time tools check the argument list of return type.</span></span>

## <a name="execution-and-lifetimes"></a><span data-ttu-id="38a39-133">执行和生存期</span><span class="sxs-lookup"><span data-stu-id="38a39-133">Execution and Lifetimes</span></span>

<span data-ttu-id="38a39-134">通过调用在调用 `LamdbaExpression.Compile()` 时创建的委托来执行代码。</span><span class="sxs-lookup"><span data-stu-id="38a39-134">You execute the code by invoking the delegate created when you called `LamdbaExpression.Compile()`.</span></span> <span data-ttu-id="38a39-135">可以在上面进行查看，其中 `add.Compile()` 返回了一个委托。</span><span class="sxs-lookup"><span data-stu-id="38a39-135">You can see this above where `add.Compile()` returns a delegate.</span></span> <span data-ttu-id="38a39-136">通过调用 `func()` 调用该委托将执行代码。</span><span class="sxs-lookup"><span data-stu-id="38a39-136">Invoking that delegate, by calling `func()` executes the code.</span></span>

<span data-ttu-id="38a39-137">该委托表示表达式树中的代码。</span><span class="sxs-lookup"><span data-stu-id="38a39-137">That delegate represents the code in the expression tree.</span></span> <span data-ttu-id="38a39-138">可以保留该委托的句柄并在稍后调用它。</span><span class="sxs-lookup"><span data-stu-id="38a39-138">You can retain the handle to that delegate and invoke it later.</span></span> <span data-ttu-id="38a39-139">不需要在每次想要执行表达式树所表示的代码时编译表达式树。</span><span class="sxs-lookup"><span data-stu-id="38a39-139">You don't need to compile the expression tree each time you want to execute the code it represents.</span></span> <span data-ttu-id="38a39-140">（请记住，表达式树是不可变的，且在之后编译同一表达式树将创建执行相同代码的委托。）</span><span class="sxs-lookup"><span data-stu-id="38a39-140">(Remember that expression trees are immutable, and compiling the same expression tree later will create a delegate that executes the same code.)</span></span>

<span data-ttu-id="38a39-141">在此提醒你不要通过避免不必要的编译调用尝试创建用于提高性能的任何更复杂的缓存机制。</span><span class="sxs-lookup"><span data-stu-id="38a39-141">I will caution you against trying to create any more sophisticated caching mechanisms to increase performance by avoiding unnecessary compile calls.</span></span> <span data-ttu-id="38a39-142">比较两个任意的表达式树，以确定如果它们表示相同的算法，是否也会花费很长的时间来执行。</span><span class="sxs-lookup"><span data-stu-id="38a39-142">Comparing two arbitrary expression trees to determine if they represent the same algorithm will also be time consuming to execute.</span></span> <span data-ttu-id="38a39-143">你可能会发现，通过避免对 `LambdaExpression.Compile()` 的任何额外调用所节省的计算时间将多于执行代码（该代码确定可导致相同可执行代码的两个不同表达式树）所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="38a39-143">You'll likely find that the compute time you save avoiding any extra calls to `LambdaExpression.Compile()` will be more than consumed by the time executing code that determines of two different expression trees result in the same executable code.</span></span>

## <a name="caveats"></a><span data-ttu-id="38a39-144">注意事项</span><span class="sxs-lookup"><span data-stu-id="38a39-144">Caveats</span></span>

<span data-ttu-id="38a39-145">将 lambda 表达式编译为委托并调用该委托是可对表达式树执行的最简单的操作之一。</span><span class="sxs-lookup"><span data-stu-id="38a39-145">Compiling a lambda expression to a delegate and invoking that delegate is one of the simplest operations you can perform with an expression tree.</span></span> <span data-ttu-id="38a39-146">但是，即使是执行这个简单的操作，也存在一些必须注意的事项。</span><span class="sxs-lookup"><span data-stu-id="38a39-146">However, even with this simple operation, there are caveats you must be aware of.</span></span> 

<span data-ttu-id="38a39-147">Lambda 表达式将对表达式中引用的任何局部变量创建闭包。</span><span class="sxs-lookup"><span data-stu-id="38a39-147">Lambda Expressions create closures over any local variables that are referenced in the expression.</span></span> <span data-ttu-id="38a39-148">必须保证作为委托的一部分的任何变量在调用 `Compile` 的位置处和执行结果委托时可用。</span><span class="sxs-lookup"><span data-stu-id="38a39-148">You must guarantee that any variables that would be part of the delegate are usable at the location where you call `Compile`, and when you execute the resulting delegate.</span></span>

<span data-ttu-id="38a39-149">一般情况下，编译器会确保这一点。</span><span class="sxs-lookup"><span data-stu-id="38a39-149">In general, the compiler will ensure that this is true.</span></span> <span data-ttu-id="38a39-150">但是，如果表达式访问实现 `IDisposable` 的变量，则代码可能在表达式树仍保留有对象时释放该对象。</span><span class="sxs-lookup"><span data-stu-id="38a39-150">However, if your expression accesses a variable that implements `IDisposable`, it's possible that your code might dispose of the object while it is still held by the expression tree.</span></span>

<span data-ttu-id="38a39-151">例如，此代码工作正常，因为 `int` 不实现 `IDisposable`：</span><span class="sxs-lookup"><span data-stu-id="38a39-151">For example, this code works fine, because `int` does not implement `IDisposable`:</span></span>

```csharp
private static Func<int, int> CreateBoundFunc()
{
    var constant = 5; // constant is captured by the expression tree
    Expression<Func<int, int>> expression = (b) => constant + b;
    var rVal = expression.Compile();
    return rVal;
}
```

<span data-ttu-id="38a39-152">委托已捕获对局部变量 `constant` 的引用。</span><span class="sxs-lookup"><span data-stu-id="38a39-152">The delegate has captured a reference to the local variable `constant`.</span></span>
<span data-ttu-id="38a39-153">在稍后执行 `CreateBoundFunc` 返回的函数之后，可随时访问该变量。</span><span class="sxs-lookup"><span data-stu-id="38a39-153">That variable is accessed at any time later, when the function returned by `CreateBoundFunc` executes.</span></span>

<span data-ttu-id="38a39-154">但是，请考虑实现 `IDisposable` 的此（人为设计的）类：</span><span class="sxs-lookup"><span data-stu-id="38a39-154">However, consider this (rather contrived) class that implements `IDisposable`:</span></span>

```csharp
public class Resource : IDisposable
{
    private bool isDisposed = false;
    public int Argument
    {
        get
        {
            if (!isDisposed)
                return 5;
            else throw new ObjectDisposedException("Resource");
        }
    }

    public void Dispose()
    {
        isDisposed = true;
    }
}
```

<span data-ttu-id="38a39-155">如果将其用于如下所示的表达式中，则在执行 `Resource.Argument` 属性引用的代码时将出现 `ObjectDisposedException`：</span><span class="sxs-lookup"><span data-stu-id="38a39-155">If you use it in an expression as shown below, you'll get an `ObjectDisposedException` when you execute the code referenced by the `Resource.Argument` property:</span></span>

```csharp
private static Func<int, int> CreateBoundResource()
{
    using (var constant = new Resource()) // constant is captured by the expression tree
    {
        Expression<Func<int, int>> expression = (b) => constant.Argument + b;
        var rVal = expression.Compile();
        return rVal;
    }
}
```

<span data-ttu-id="38a39-156">从此方法返回的委托已对释放了的 `constant` 对象闭包。</span><span class="sxs-lookup"><span data-stu-id="38a39-156">The delegate returned from this method has closed over the `constant` object, which has been disposed of.</span></span> <span data-ttu-id="38a39-157">（它已被释放，因为它已在 `using` 语句中进行声明。）</span><span class="sxs-lookup"><span data-stu-id="38a39-157">(It's been disposed, because it was declared in a `using` statement.)</span></span> 

<span data-ttu-id="38a39-158">现在，在执行从此方法返回的委托时，将在执行时引发 `ObjecctDisposedException`。</span><span class="sxs-lookup"><span data-stu-id="38a39-158">Now, when you execute the delegate returned from this method, you'll have a `ObjecctDisposedException` thrown at the point of execution.</span></span>

<span data-ttu-id="38a39-159">出现表示编译时构造的运行时错误确实很奇怪，但这是使用表达式树时的正常现象。</span><span class="sxs-lookup"><span data-stu-id="38a39-159">It does seem strange to have a runtime error representing a compile-time construct, but that's the world we enter when we work with expression trees.</span></span>

<span data-ttu-id="38a39-160">此问题存在大量的排列，因此很难提供用于避免此问题的一般性指导。</span><span class="sxs-lookup"><span data-stu-id="38a39-160">There are a lot of permutations of this problem, so it's hard to offer general guidance to avoid it.</span></span> <span data-ttu-id="38a39-161">定义表达式时，请谨慎访问局部变量，且在创建可由公共 API 返回的表达式树时，谨慎访问当前对象（由 `this` 表示）中的状态。</span><span class="sxs-lookup"><span data-stu-id="38a39-161">Be careful about accessing local variables when defining expressions, and be careful about accessing state in the current object (represented by `this`) when creating an expression tree that can be returned by a public API.</span></span>

<span data-ttu-id="38a39-162">表达式中的代码可能引用其他程序集中的方法或属性。</span><span class="sxs-lookup"><span data-stu-id="38a39-162">The code in your expression may reference methods or properties in other assemblies.</span></span> <span data-ttu-id="38a39-163">对表达式进行定义、编译或在调用结果委托时，该程序集必须可访问。</span><span class="sxs-lookup"><span data-stu-id="38a39-163">That assembly must be accessible when the expression is defined, and when it is compiled, and when the resulting delegate is invoked.</span></span> <span data-ttu-id="38a39-164">在它不存在的情况下，将遇到 `ReferencedAssemblyNotFoundException`。</span><span class="sxs-lookup"><span data-stu-id="38a39-164">You'll be met with a `ReferencedAssemblyNotFoundException` in cases where it is not present.</span></span>

## <a name="summary"></a><span data-ttu-id="38a39-165">摘要</span><span class="sxs-lookup"><span data-stu-id="38a39-165">Summary</span></span>

<span data-ttu-id="38a39-166">可以编译表示 lambda 表达式的表达式树，以创建可执行的委托。</span><span class="sxs-lookup"><span data-stu-id="38a39-166">Expression Trees that represent lambda expressions can be compiled to create a delegate that you can execute.</span></span> <span data-ttu-id="38a39-167">这提供了一种机制，用于执行表达式树所表示的代码。</span><span class="sxs-lookup"><span data-stu-id="38a39-167">This provides one mechanism to execute the code represented by an expression tree.</span></span>

<span data-ttu-id="38a39-168">表达式树表示会为创建的任意给定构造执行的代码。</span><span class="sxs-lookup"><span data-stu-id="38a39-168">The Expression Tree does represent the code that would execute for any given construct you create.</span></span> <span data-ttu-id="38a39-169">只要编译和执行代码的环境匹配创建表达式的环境，则一切将按预期进行。</span><span class="sxs-lookup"><span data-stu-id="38a39-169">As long as the environment where you compile and execute the code matches the environment where you create the expression, everything works as expected.</span></span> <span data-ttu-id="38a39-170">如果未按预期进行，那么错误也是很容易预知的，并且将在使用表达式树的任何代码的第一个测试中捕获这些错误。</span><span class="sxs-lookup"><span data-stu-id="38a39-170">When that doesn't happen, the errors are very predictable, and they will be caught in your first tests of any code using the expression trees.</span></span>

[<span data-ttu-id="38a39-171">下一部分 -- 解释表达式</span><span class="sxs-lookup"><span data-stu-id="38a39-171">Next -- Interpreting Expressions</span></span>](expression-trees-interpreting.md)

