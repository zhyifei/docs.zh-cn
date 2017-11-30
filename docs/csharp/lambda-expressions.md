---
title: "Lambda 表达式"
description: "了解如何使用 Lambda 表达式，它们是可作为参数传递的可执行代码块。"
keywords: ".NET, .NET Core, lambda 表达式, lambda, 委托"
ms-author: ronpet
author: rpetrusha
ms.date: 11/22/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: b6a0539a-8ce5-4da7-adcf-44be345a2714
ms.openlocfilehash: 1a97d830c675c8e3980eddae78f3face279ec6dc
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2017
---
# <a name="lambda-expressions"></a><span data-ttu-id="36baa-104">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="36baa-104">Lambda expressions</span></span> #

<span data-ttu-id="36baa-105">Lambda 表达式是作为对象处理的代码块（表达式或语句块）。</span><span class="sxs-lookup"><span data-stu-id="36baa-105">A *lambda expression* is a block of code (an expression or a statement block) that is treated as an object.</span></span> <span data-ttu-id="36baa-106">它可作为参数传递给方法，也可通过方法调用返回。</span><span class="sxs-lookup"><span data-stu-id="36baa-106">It can be passed as an argument to methods, and it can also be returned by method calls.</span></span> <span data-ttu-id="36baa-107">Lambda 表达式广泛用于：</span><span class="sxs-lookup"><span data-stu-id="36baa-107">Lambda expressions are used extensively for:</span></span>

- <span data-ttu-id="36baa-108">传递代码是要执行到异步方法，如<xref:System.Threading.Tasks.Task.Run(System.Action)>。</span><span class="sxs-lookup"><span data-stu-id="36baa-108">Passing the code that is to be executed to asynchronous methods, such as <xref:System.Threading.Tasks.Task.Run(System.Action)>.</span></span>

- <span data-ttu-id="36baa-109">编写 [LINQ 查询表达式](linq/index.md)。</span><span class="sxs-lookup"><span data-stu-id="36baa-109">Writing [LINQ query expressions](linq/index.md).</span></span>

- <span data-ttu-id="36baa-110">创建[表达式树](expression-trees-building.md)。</span><span class="sxs-lookup"><span data-stu-id="36baa-110">Creating [expression trees](expression-trees-building.md).</span></span>

<span data-ttu-id="36baa-111">Lambda 表达式是可以表示为委托的代码，或者表示为表达式树的代码，它所表示的表达式树可以编译为委托。</span><span class="sxs-lookup"><span data-stu-id="36baa-111">Lambda expressions are code that can be represented either as a delegate, or as an expression tree that compiles to a delegate.</span></span> <span data-ttu-id="36baa-112">Lambda 表达式的特定委托类型取决于其参数和返回值。</span><span class="sxs-lookup"><span data-stu-id="36baa-112">The specific delegate type of a lambda expression depends on its parameters and return value.</span></span> <span data-ttu-id="36baa-113">不返回值的 Lambda 表达式对应于 `Action` 委托，具体取决于其参数数量。</span><span class="sxs-lookup"><span data-stu-id="36baa-113">Lambda expressions that don't return a value correspond to a specific `Action` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="36baa-114">返回值的 Lambda 表达式对应于 `Func` 委托，具体取决于其参数数量。</span><span class="sxs-lookup"><span data-stu-id="36baa-114">Lambda expressions that return a value correspond to a specific `Func` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="36baa-115">例如，具有两个参数，但不返回值的 lambda 表达式对应于<xref:System.Action%602>委托。</span><span class="sxs-lookup"><span data-stu-id="36baa-115">For example, a lambda expression that has two parameters but returns no value corresponds to an <xref:System.Action%602> delegate.</span></span> <span data-ttu-id="36baa-116">Lambda 表达式，它具有一个参数并返回一个值对应于<xref:System.Func%602>委托。</span><span class="sxs-lookup"><span data-stu-id="36baa-116">A lambda expression that has one parameter and returns a value corresponds to <xref:System.Func%602> delegate.</span></span>

<span data-ttu-id="36baa-117">Lambda 表达式使用 [lambda 声明运算符](language-reference/operators/lambda-operator.md) `=>` 从其可执行代码中分离 lambda 参数列表。</span><span class="sxs-lookup"><span data-stu-id="36baa-117">A lambda expression uses `=>`, the [lambda declaration operator](language-reference/operators/lambda-operator.md), to separate the lambda's parameter list from its executable code.</span></span> <span data-ttu-id="36baa-118">若要创建 Lambda 表达式，需要在 lambda 运算符左侧指定输入参数（如果有），然后在另一侧输入表达式或语句块。</span><span class="sxs-lookup"><span data-stu-id="36baa-118">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator, and you put the expression or statement block on the other side.</span></span> <span data-ttu-id="36baa-119">例如，单行 Lambda 表达式 `x => x * x` 指定名为 `x` 的参数并返回 `x` 的平方值。</span><span class="sxs-lookup"><span data-stu-id="36baa-119">For example, the single-line lambda expression `x => x * x` specifies a parameter that’s named `x` and returns the value of `x` squared.</span></span> <span data-ttu-id="36baa-120">如下面的示例所示，你可以将此表达式分配给委托类型：</span><span class="sxs-lookup"><span data-stu-id="36baa-120">You can assign this expression to a delegate type, as the following example shows:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/lambda1.cs#1)]

<span data-ttu-id="36baa-121">或者，可以将其直接作为方法参数传递：</span><span class="sxs-lookup"><span data-stu-id="36baa-121">Or you can pass it directly as a method argument:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/lambda2.cs#2)]

## <a name="expression-lambdas"></a><span data-ttu-id="36baa-122">表达式 lambda</span><span class="sxs-lookup"><span data-stu-id="36baa-122">Expression lambdas</span></span> ##

 <span data-ttu-id="36baa-123">表达式位于 => 运算符右侧的 Lambda 表达式称为“表达式 lambda”。</span><span class="sxs-lookup"><span data-stu-id="36baa-123">A lambda expression with an expression on the right side of the => operator is called an *expression lambda*.</span></span> <span data-ttu-id="36baa-124">表达式 lambda 广泛用于[表达式树](expression-trees.md)的构造。</span><span class="sxs-lookup"><span data-stu-id="36baa-124">Expression lambdas are used extensively in the construction of [expression trees](expression-trees.md).</span></span> <span data-ttu-id="36baa-125">表达式 lambda 会返回表达式的结果，并采用以下基本形式：</span><span class="sxs-lookup"><span data-stu-id="36baa-125">An expression lambda returns the result of the expression and takes the following basic form:</span></span>

```csharp
(input parameters) => expression
```

<span data-ttu-id="36baa-126">仅当 lambda 只有一个输入参数时，括号才是可选的；否则括号是必需的。</span><span class="sxs-lookup"><span data-stu-id="36baa-126">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span> <span data-ttu-id="36baa-127">使用空括号指定零个输入参数：</span><span class="sxs-lookup"><span data-stu-id="36baa-127">Specify zero input parameters with empty parentheses:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/expression3.cs#1)]

<span data-ttu-id="36baa-128">括号内的两个或更多输入参数使用逗号加以分隔：</span><span class="sxs-lookup"><span data-stu-id="36baa-128">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/expression3.cs#2)]

<span data-ttu-id="36baa-129">通常，编译器在确定参数类型时使用类型推理。</span><span class="sxs-lookup"><span data-stu-id="36baa-129">Ordinarily, the compiler uses type inference in determining parameter types.</span></span> <span data-ttu-id="36baa-130">但是，编译器有时难以或无法推断输入类型。</span><span class="sxs-lookup"><span data-stu-id="36baa-130">However, sometimes it is difficult or impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="36baa-131">如果出现这种情况，可显式指定类型，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="36baa-131">When this occurs, you can specify the types explicitly, as in the following example:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/expression3.cs#3)]

<span data-ttu-id="36baa-132">在上一个示例中，请注意表达式 Lambda 的主体可以包含一个方法调用。</span><span class="sxs-lookup"><span data-stu-id="36baa-132">Note in the previous example that the body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="36baa-133">但是，如果要创建在 .NET Framework 外部（例如 SQL Server 或实体框架 (EF)）计算的表达式树，则应避免在 Lambda 表达式中使用方法调用，因为这些方法在 .NET 实现的上下文之外可能没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="36baa-133">However, if you are creating expression trees that are evaluated outside of the .NET Framework, such as in SQL Server or Entity Framework (EF), you should refrain from using method calls in lambda expressions, since the methods may have no meaning outside the context of the .NET implementation.</span></span> <span data-ttu-id="36baa-134">在这种情况下，如果选择使用方法调用，请务必对其进行全面测试，确保可成功解析此方法调用。</span><span class="sxs-lookup"><span data-stu-id="36baa-134">If you do choose to use method calls in this case, be sure to test them thoroughly to ensure that the method calls can be successfuly resolved.</span></span>

## <a name="statement-lambdas"></a><span data-ttu-id="36baa-135">语句 lambda</span><span class="sxs-lookup"><span data-stu-id="36baa-135">Statement lambdas</span></span> ##

<span data-ttu-id="36baa-136">语句 lambda 与表达式 lambda 表达式类似，只是语句括在大括号中：</span><span class="sxs-lookup"><span data-stu-id="36baa-136">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>

```csharp
(input parameters) => { statement; }
```

<span data-ttu-id="36baa-137">语句 lambda 的主体可以包含任意数量的语句；但是，实际上通常不会多于两个或三个。</span><span class="sxs-lookup"><span data-stu-id="36baa-137">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/statement1.cs#1)]

<span data-ttu-id="36baa-138">像匿名方法一样，语句 lambda 也不能用于创建表达式目录树。</span><span class="sxs-lookup"><span data-stu-id="36baa-138">Statement lambdas, like anonymous methods, cannot be used to create expression trees.</span></span>

## <a name="async-lambdas"></a><span data-ttu-id="36baa-139">异步 lambda</span><span class="sxs-lookup"><span data-stu-id="36baa-139">Async lambdas</span></span> ##

<span data-ttu-id="36baa-140">通过使用 [async](language-reference/keywords/async.md) 和 [await](language-reference/keywords/await.md) 关键字，可以轻松创建包含异步处理的 Lambda 表达式和语句。</span><span class="sxs-lookup"><span data-stu-id="36baa-140">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](language-reference/keywords/async.md) and [await](language-reference/keywords/await.md) keywords.</span></span> <span data-ttu-id="36baa-141">例如，本示例调用异步执行的 `ShowSquares` 方法。</span><span class="sxs-lookup"><span data-stu-id="36baa-141">For example, the example calls a `ShowSquares` method that executes asynchronously.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/async1.cs#1)]

<span data-ttu-id="36baa-142">有关如何创建和使用异步方法的详细信息，请参阅[使用 Async 和 Await 的异步编程](programming-guide/concepts/async/index.md)。</span><span class="sxs-lookup"><span data-stu-id="36baa-142">For more information about how to create and use async methods, see [Asynchronous programming with async and await](programming-guide/concepts/async/index.md).</span></span>

## <a name="lambda-expressions-and-tuples"></a><span data-ttu-id="36baa-143">Lambda 表达式和元祖</span><span class="sxs-lookup"><span data-stu-id="36baa-143">Lambda expressions and tuples</span></span> ##

<span data-ttu-id="36baa-144">从 C# 7.0 开始，C# 语言为元组提供内置支持。</span><span class="sxs-lookup"><span data-stu-id="36baa-144">Starting with C# 7.0, the C# language provides built-in support for tuples.</span></span> <span data-ttu-id="36baa-145">可以提供一个元组作为 Lambda 表达式的参数，同时 Lambda 表达式也可以返回元组。</span><span class="sxs-lookup"><span data-stu-id="36baa-145">You can provide a tuple as an argument to a lambda expression, and your lambda expression can also return a tuple.</span></span> <span data-ttu-id="36baa-146">在某些情况下，C# 编译器使用类型推理来确定元组组件的类型。</span><span class="sxs-lookup"><span data-stu-id="36baa-146">In some cases, the C# compiler uses type inference to determine the types of tuple components.</span></span> 

<span data-ttu-id="36baa-147">可通过用括号括住用逗号分隔的组件列表来定义元组。</span><span class="sxs-lookup"><span data-stu-id="36baa-147">You define a tuple by enclosing a comma-delimited list of its components in parentheses.</span></span> <span data-ttu-id="36baa-148">以下示例使用包含 5 个组件的元组将一系列数字传递给 Lambda 表达式，此 Lambda 表达式将每个值加倍，然后返回包含乘法运算结果的 5 个组件的元组。</span><span class="sxs-lookup"><span data-stu-id="36baa-148">The following example uses tuple with 5 components to pass a sequence of numbers to a lambda expression, which doubles each value and returns a tuple with 5 components that contains the result of the multiplications.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/tuples1.cs#1)]

<span data-ttu-id="36baa-149">通常，元组字段命名为 `Item1`、`Item2` 等等。但是，可以使用命名组件定义元组，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="36baa-149">Ordinarily, the fields of a tuple are named `Item1`, `Item2`, etc. You can, however, define a tuple with named components, as the following example does.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/tuples2.cs#1)]

<span data-ttu-id="36baa-150">有关对 C# 中元祖的支持的详细信息，请参阅 [C# 元祖类型](tuples.md)。</span><span class="sxs-lookup"><span data-stu-id="36baa-150">For more information on support for tuples in C#, see [C# Tuple types](tuples.md).</span></span>

## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="36baa-151">含标准查询运算符的 lambda</span><span class="sxs-lookup"><span data-stu-id="36baa-151">Lambdas with the standard query operators</span></span> ##

<span data-ttu-id="36baa-152">LINQ 到对象以及其他实现中，都具有其类型是一个输入的参数的<xref:System.Func%601>泛型委托系列。</span><span class="sxs-lookup"><span data-stu-id="36baa-152">LINQ to Objects, among other implementations, have an input parameter whose type is one of the <xref:System.Func%601> family of generic delegates.</span></span> <span data-ttu-id="36baa-153">这些委托使用类型参数来定义输入参数的数量和类型，以及委托的返回类型。</span><span class="sxs-lookup"><span data-stu-id="36baa-153">These delegates use type parameters to define the number and type of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="36baa-154">`Func` 委托对于封装用户定义的表达式非常有用，这些表达式将应用于一组源数据中的每个元素。</span><span class="sxs-lookup"><span data-stu-id="36baa-154">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="36baa-155">例如，考虑<xref:System.Func%601>委托，其语法是：</span><span class="sxs-lookup"><span data-stu-id="36baa-155">For example, consider the <xref:System.Func%601> delegate, whose syntax is:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#1)]

<span data-ttu-id="36baa-156">可使用如下代码实例化委托</span><span class="sxs-lookup"><span data-stu-id="36baa-156">The delegate can be instantiated with code like the following</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#2)]

<span data-ttu-id="36baa-157">其中，`int` 是一个输入参数，`bool` 是返回值。</span><span class="sxs-lookup"><span data-stu-id="36baa-157">where `int` is an input parameter, and `bool` is the return value.</span></span> <span data-ttu-id="36baa-158">返回值始终在最后一个类型参数中指定。</span><span class="sxs-lookup"><span data-stu-id="36baa-158">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="36baa-159">调用以下 `Func` 委托时，该委托将返回 true 或 false 以指示输入参数是否等于 5：</span><span class="sxs-lookup"><span data-stu-id="36baa-159">When the following `Func` delegate is invoked, it returns true or false to indicate whether the input parameter is equal to 5:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#3)]

<span data-ttu-id="36baa-160">你也可以提供 lambda 表达式，当自变量类型为<xref:System.Linq.Expressions.Expression%601>，例如在中定义的标准查询运算符<xref:System.Linq.Queryable>类型。</span><span class="sxs-lookup"><span data-stu-id="36baa-160">You can also supply a lambda expression when the argument type is an <xref:System.Linq.Expressions.Expression%601>, for example in the standard query operators that are defined in the <xref:System.Linq.Queryable> type.</span></span> <span data-ttu-id="36baa-161">当指定<xref:System.Linq.Expressions.Expression%601>自变量，lambda 将编译为表达式树。</span><span class="sxs-lookup"><span data-stu-id="36baa-161">When you specify an <xref:System.Linq.Expressions.Expression%601> argument, the lambda is compiled to an expression tree.</span></span> <span data-ttu-id="36baa-162">以下示例使用 [System.Linq.Enumerable.Count](xref:System.Linq.Enumerable.Count%60%601(System.Collections.Generic.IEnumerable{%60%600})) 标准查询运算符。</span><span class="sxs-lookup"><span data-stu-id="36baa-162">The following example uses the [System.Linq.Enumerable.Count](xref:System.Linq.Enumerable.Count%60%601(System.Collections.Generic.IEnumerable{%60%600})) standard query operator.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#4)]

<span data-ttu-id="36baa-163">编译器可以推断输入参数的类型，或者你也可以显式指定该类型。</span><span class="sxs-lookup"><span data-stu-id="36baa-163">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="36baa-164">这个特殊 Lambda 表达式可计算那些除以 2 时余数为 1 的整数的数量 (`n`)。</span><span class="sxs-lookup"><span data-stu-id="36baa-164">This particular lambda expression counts those integers (`n`) that, when divided by two, have a remainder of 1.</span></span>

<span data-ttu-id="36baa-165">以下示例生成一个序列，其中包含 `numbers` 数组中 位于 9 之前的所有元素，因为这是序列中第一个不满足条件的数字。</span><span class="sxs-lookup"><span data-stu-id="36baa-165">The following example produces a sequence that contains all elements in the `numbers` array that precede the 9, because that's the first number in the sequence that doesn't meet the condition.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#5)]

<span data-ttu-id="36baa-166">以下示例通过将输入参数括在括号中来指定多个输入参数。</span><span class="sxs-lookup"><span data-stu-id="36baa-166">The following example specifies multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="36baa-167">该方法返回数字数组中的所有元素，直至遇到一个值小于数组中其序号位置的数字为止。</span><span class="sxs-lookup"><span data-stu-id="36baa-167">The method returns all the elements in the numbers array until it encounters a number whose value is less than its ordinal position in the array.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#6)]

## <a name="type-inference-in-lambda-expressions"></a><span data-ttu-id="36baa-168">Lambda 表达式中的类型推理</span><span class="sxs-lookup"><span data-stu-id="36baa-168">Type inference in lambda expressions</span></span> ##

<span data-ttu-id="36baa-169">编写 lambda 时，通常不必为输入参数指定类型，因为编译器可以根据 lambda 主体、参数类型以及 C# 语言规范中描述的其他因素来推断类型。</span><span class="sxs-lookup"><span data-stu-id="36baa-169">When writing lambdas, you often do not have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter types, and other factors, as described in the C# Language Specification.</span></span> <span data-ttu-id="36baa-170">对于大多数标准查询运算符，第一个输入是源序列中的元素类型。</span><span class="sxs-lookup"><span data-stu-id="36baa-170">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="36baa-171">如果要查询 `IEnumerable<Customer>`，则输入变量将被推断为 `Customer` 对象，这意味着你可以访问其方法和属性：</span><span class="sxs-lookup"><span data-stu-id="36baa-171">If you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/infer1.cs#1)]

<span data-ttu-id="36baa-172">Lambda 类型推理的一般规则如下：</span><span class="sxs-lookup"><span data-stu-id="36baa-172">The general rules for type inference for lambdas are:</span></span>

- <span data-ttu-id="36baa-173">Lambda 包含的参数数量必须与委托类型包含的参数数量相同。</span><span class="sxs-lookup"><span data-stu-id="36baa-173">The lambda must contain the same number of parameters as the delegate type.</span></span>

- <span data-ttu-id="36baa-174">Lambda 中的每个输入参数必须都能够隐式转换为其对应的委托参数。</span><span class="sxs-lookup"><span data-stu-id="36baa-174">Each input argument in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>

- <span data-ttu-id="36baa-175">Lambda 的返回值（如果有）必须能够隐式转换为委托的返回类型。</span><span class="sxs-lookup"><span data-stu-id="36baa-175">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>

<span data-ttu-id="36baa-176">请注意，lambda 表达式本身没有类型，因为常规类型系统没有“Lambda 表达式”这一内部概念。</span><span class="sxs-lookup"><span data-stu-id="36baa-176">Note that lambda expressions in themselves do not have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="36baa-177">但是，有时以一种非正式的方式谈论 lambda 表达式的“类型”会很方便。</span><span class="sxs-lookup"><span data-stu-id="36baa-177">However, it is sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="36baa-178">在这些情况下，类型是指委托类型或 lambda 表达式所转换到的 <xref:System.Linq.Expressions.Expression> 类型。</span><span class="sxs-lookup"><span data-stu-id="36baa-178">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>

## <a name="variable-scope-in-lambda-expressions"></a><span data-ttu-id="36baa-179">Lambda 表达式中的变量范围</span><span class="sxs-lookup"><span data-stu-id="36baa-179">Variable Scope in Lambda Expressions</span></span> ##

<span data-ttu-id="36baa-180">在定义 lambda 函数的方法内或包含 Lambda 表达式的类型内，Lambda 可以引用范围内的外部变量（请参阅[匿名方法](programming-guide/statements-expressions-operators/anonymous-methods.md)）。</span><span class="sxs-lookup"><span data-stu-id="36baa-180">Lambdas can refer to *outer variables* (see [Anonymous methods](programming-guide/statements-expressions-operators/anonymous-methods.md)) that are in scope in the method that defines the lambda function, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="36baa-181">以这种方式捕获的变量将进行存储以备在 lambda 表达式中使用，即使在其他情况下，这些变量将超出范围并进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="36baa-181">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="36baa-182">必须明确地分配外部变量，然后才能在 lambda 表达式中使用该变量。</span><span class="sxs-lookup"><span data-stu-id="36baa-182">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="36baa-183">以下示例演示了这些规则。</span><span class="sxs-lookup"><span data-stu-id="36baa-183">The following example demonstrates these rules.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/scope.cs#1)]

 <span data-ttu-id="36baa-184">下列规则适用于 lambda 表达式中的变量范围：</span><span class="sxs-lookup"><span data-stu-id="36baa-184">The following rules apply to variable scope in lambda expressions:</span></span>

- <span data-ttu-id="36baa-185">捕获的变量将不会被作为垃圾回收，直至引用变量的委托符合垃圾回收的条件。</span><span class="sxs-lookup"><span data-stu-id="36baa-185">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>

- <span data-ttu-id="36baa-186">在外部方法中看不到 lambda 表达式内引入的变量。</span><span class="sxs-lookup"><span data-stu-id="36baa-186">Variables introduced within a lambda expression are not visible in the outer method.</span></span>

- <span data-ttu-id="36baa-187">Lambda 表达式无法从封闭方法中直接捕获 `ref` 或 `out` 参数。</span><span class="sxs-lookup"><span data-stu-id="36baa-187">A lambda expression cannot directly capture a `ref` or `out` parameter from an enclosing method.</span></span>

- <span data-ttu-id="36baa-188">Lambda 表达式中的返回语句不会导致封闭方法返回。</span><span class="sxs-lookup"><span data-stu-id="36baa-188">A return statement in a lambda expression does not cause the enclosing method to return.</span></span>

- <span data-ttu-id="36baa-189">如果跳转语句的目标在块外部，则 lambda 表达式不能包含位于 lambda 函数内部的 `goto` 语句、 `break` 语句或 `continue` 语句。</span><span class="sxs-lookup"><span data-stu-id="36baa-189">A lambda expression cannot contain a `goto` statement, `break` statement, or `continue` statement that is inside the lambda function if the jump statement’s target is outside the block.</span></span> <span data-ttu-id="36baa-190">同样，如果目标在块内部，则在 lambda 函数块外部使用跳转语句也是错误的。</span><span class="sxs-lookup"><span data-stu-id="36baa-190">It is also an error to have a jump statement outside the lambda function block if the target is inside the block.</span></span>

## <a name="see-also"></a><span data-ttu-id="36baa-191">请参阅</span><span class="sxs-lookup"><span data-stu-id="36baa-191">See also</span></span> ##

<span data-ttu-id="36baa-192">[LINQ（语言集成查询）](../standard/using-linq.md) </span><span class="sxs-lookup"><span data-stu-id="36baa-192">[LINQ (Language-Integrated Query)](../standard/using-linq.md) </span></span>  
<span data-ttu-id="36baa-193">[匿名方法](programming-guide/statements-expressions-operators/anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="36baa-193">[Anonymous methods](programming-guide/statements-expressions-operators/anonymous-methods.md) </span></span>  
[<span data-ttu-id="36baa-194">表达式树</span><span class="sxs-lookup"><span data-stu-id="36baa-194">Expression trees</span></span>](expression-trees.md)
