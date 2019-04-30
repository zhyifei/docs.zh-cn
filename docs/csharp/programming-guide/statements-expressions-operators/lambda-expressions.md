---
title: Lambda 表达式 - C# 编程指南
ms.custom: seodec18
ms.date: 03/14/2019
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: dd9b77a90030a96d17104c8c0e48964b6a85d165
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2019
ms.locfileid: "58125728"
---
# <a name="lambda-expressions-c-programming-guide"></a><span data-ttu-id="4e19d-102">Lambda 表达式（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="4e19d-102">Lambda expressions (C# Programming Guide)</span></span>

<span data-ttu-id="4e19d-103">Lambda 表达式是作为对象处理的代码块（表达式或语句块）。</span><span class="sxs-lookup"><span data-stu-id="4e19d-103">A *lambda expression* is a block of code (an expression or a statement block) that is treated as an object.</span></span> <span data-ttu-id="4e19d-104">它可作为参数传递给方法，也可通过方法调用返回。</span><span class="sxs-lookup"><span data-stu-id="4e19d-104">It can be passed as an argument to methods, and it can also be returned by method calls.</span></span> <span data-ttu-id="4e19d-105">Lambda 表达式广泛用于：</span><span class="sxs-lookup"><span data-stu-id="4e19d-105">Lambda expressions are used extensively for:</span></span>

- <span data-ttu-id="4e19d-106">将要执行的代码传递给异步方法，例如 <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="4e19d-106">Passing the code that is to be executed to asynchronous methods, such as <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="4e19d-107">编写 [LINQ 查询表达式](../../linq/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4e19d-107">Writing [LINQ query expressions](../../linq/index.md).</span></span>

- <span data-ttu-id="4e19d-108">创建[表达式树](../concepts/expression-trees/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4e19d-108">Creating [expression trees](../concepts/expression-trees/index.md).</span></span>

<span data-ttu-id="4e19d-109">Lambda 表达式是可以表示为委托的代码，或者表示为表达式树的代码，它所表示的表达式树可以编译为委托。</span><span class="sxs-lookup"><span data-stu-id="4e19d-109">Lambda expressions are code that can be represented either as a delegate, or as an expression tree that compiles to a delegate.</span></span> <span data-ttu-id="4e19d-110">Lambda 表达式的特定委托类型取决于其参数和返回值。</span><span class="sxs-lookup"><span data-stu-id="4e19d-110">The specific delegate type of a lambda expression depends on its parameters and return value.</span></span> <span data-ttu-id="4e19d-111">不返回值的 Lambda 表达式对应于 `Action` 委托，具体取决于其参数数量。</span><span class="sxs-lookup"><span data-stu-id="4e19d-111">Lambda expressions that don't return a value correspond to a specific `Action` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="4e19d-112">返回值的 Lambda 表达式对应于 `Func` 委托，具体取决于其参数数量。</span><span class="sxs-lookup"><span data-stu-id="4e19d-112">Lambda expressions that return a value correspond to a specific `Func` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="4e19d-113">例如，有 2 个参数但不返回值的 Lambda 表达式对应于 <xref:System.Action%602> 委托。</span><span class="sxs-lookup"><span data-stu-id="4e19d-113">For example, a lambda expression that has two parameters but returns no value corresponds to an <xref:System.Action%602> delegate.</span></span> <span data-ttu-id="4e19d-114">有 1 个参数并返回值的 Lambda 表达式对应于 <xref:System.Func%602> 委托。</span><span class="sxs-lookup"><span data-stu-id="4e19d-114">A lambda expression that has one parameter and returns a value corresponds to <xref:System.Func%602> delegate.</span></span>

<span data-ttu-id="4e19d-115">Lambda 表达式使用 [lambda 声明运算符](../../language-reference/operators/lambda-operator.md) `=>` 从其可执行代码中分离 lambda 参数列表。</span><span class="sxs-lookup"><span data-stu-id="4e19d-115">A lambda expression uses `=>`, the [lambda declaration operator](../../language-reference/operators/lambda-operator.md), to separate the lambda's parameter list from its executable code.</span></span> <span data-ttu-id="4e19d-116">若要创建 Lambda 表达式，需要在 lambda 运算符左侧指定输入参数（如果有），然后在另一侧输入表达式或语句块。</span><span class="sxs-lookup"><span data-stu-id="4e19d-116">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator, and you put the expression or statement block on the other side.</span></span> <span data-ttu-id="4e19d-117">例如，单行 Lambda 表达式 `x => x * x` 指定名为 `x` 的参数并返回 `x` 的平方值。</span><span class="sxs-lookup"><span data-stu-id="4e19d-117">For example, the single-line lambda expression `x => x * x` specifies a parameter that’s named `x` and returns the value of `x` squared.</span></span> <span data-ttu-id="4e19d-118">如下面的示例所示，你可以将此表达式分配给委托类型：</span><span class="sxs-lookup"><span data-stu-id="4e19d-118">You can assign this expression to a delegate type, as the following example shows:</span></span>

[!code-csharp-interactive[lambda is delegate](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Delegate)]

<span data-ttu-id="4e19d-119">还可以将 lambda 表达式分配给表达式树类型：</span><span class="sxs-lookup"><span data-stu-id="4e19d-119">You also can assign a lambda expression to an expression tree type:</span></span>

[!code-csharp-interactive[lambda is expression tree](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#ExpressionTree)]

<span data-ttu-id="4e19d-120">或者，可以将其直接作为方法参数传递：</span><span class="sxs-lookup"><span data-stu-id="4e19d-120">Or you can pass it directly as a method argument:</span></span>

[!code-csharp-interactive[lambda is argument](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Argument)]

<span data-ttu-id="4e19d-121">如果使用基于方法的语法在 <xref:System.Linq.Enumerable?displayProperty=nameWithType> 类中调用 <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> 方法（就像在 LINQ to Objects 和 LINQ to XML 中一样），参数是委托类型 <xref:System.Func%602?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="4e19d-121">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Enumerable?displayProperty=nameWithType> class (as you do in LINQ to Objects and LINQ to XML) the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4e19d-122">使用 Lambda 表达式创建该委托最为方便。</span><span class="sxs-lookup"><span data-stu-id="4e19d-122">A lambda expression is the most convenient way to create that delegate.</span></span> <span data-ttu-id="4e19d-123">如果在 <xref:System.Linq.Queryable?displayProperty=nameWithType> 类中调用 <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> 方法（就像在 LINQ to SQL 中一样），参数类型是表达式树类型 [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>)。</span><span class="sxs-lookup"><span data-stu-id="4e19d-123">When you call the <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Queryable?displayProperty=nameWithType> class (as you do in LINQ to SQL) the parameter type is an expression tree type [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span></span> <span data-ttu-id="4e19d-124">同样，Lambda 表达式只是一种非常简洁的构造该表达式目录树的方式。</span><span class="sxs-lookup"><span data-stu-id="4e19d-124">Again, a lambda expression is just a very concise way to construct that expression tree.</span></span> <span data-ttu-id="4e19d-125">尽管事实上通过 Lambda 创建的对象具有不同的类型，但 Lambda 使得 `Select` 调用看起来类似。</span><span class="sxs-lookup"><span data-stu-id="4e19d-125">The lambdas allow the `Select` calls to look similar although in fact the type of object created from the lambda is different.</span></span>

<span data-ttu-id="4e19d-126">所有适用于[匿名方法](anonymous-methods.md)的限制也都适用于 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="4e19d-126">All restrictions that apply to [anonymous methods](anonymous-methods.md) also apply to lambda expressions.</span></span>
  
## <a name="expression-lambdas"></a><span data-ttu-id="4e19d-127">表达式 lambda</span><span class="sxs-lookup"><span data-stu-id="4e19d-127">Expression lambdas</span></span>

<span data-ttu-id="4e19d-128">表达式位于 `=>` 运算符右侧的 lambda 表达式称为“表达式 lambda”。</span><span class="sxs-lookup"><span data-stu-id="4e19d-128">A lambda expression with an expression on the right side of the `=>` operator is called an *expression lambda*.</span></span> <span data-ttu-id="4e19d-129">表达式 lambda 广泛用于[表达式树](../concepts/expression-trees/index.md)的构造。</span><span class="sxs-lookup"><span data-stu-id="4e19d-129">Expression lambdas are used extensively in the construction of [expression trees](../concepts/expression-trees/index.md).</span></span> <span data-ttu-id="4e19d-130">表达式 lambda 会返回表达式的结果，并采用以下基本形式：</span><span class="sxs-lookup"><span data-stu-id="4e19d-130">An expression lambda returns the result of the expression and takes the following basic form:</span></span>

```csharp
(input-parameters) => expression
```

<span data-ttu-id="4e19d-131">仅当 lambda 只有一个输入参数时，括号才是可选的；否则括号是必需的。</span><span class="sxs-lookup"><span data-stu-id="4e19d-131">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span>

<span data-ttu-id="4e19d-132">使用空括号指定零个输入参数：</span><span class="sxs-lookup"><span data-stu-id="4e19d-132">Specify zero input parameters with empty parentheses:</span></span>  

[!code-csharp[zero parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ZeroParameters)]

<span data-ttu-id="4e19d-133">括号内的两个或更多输入参数使用逗号加以分隔：</span><span class="sxs-lookup"><span data-stu-id="4e19d-133">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>

[!code-csharp[two parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#TwoParameters)]

<span data-ttu-id="4e19d-134">有时，编译器无法推断输入类型。</span><span class="sxs-lookup"><span data-stu-id="4e19d-134">Sometimes it's impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="4e19d-135">可以显式指定类型，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="4e19d-135">You can specify the types explicitly as shown in the following example:</span></span>

[!code-csharp[explicitly typed parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ExplicitlyTypedParameters)]

<span data-ttu-id="4e19d-136">输入参数类型必须全部为显式或全部为隐式；否则，便会生成 [CS0748](../../misc/cs0748.md) 编译器错误。</span><span class="sxs-lookup"><span data-stu-id="4e19d-136">Input parameter types must be all explicit or all implicit; otherwise, a [CS0748](../../misc/cs0748.md) compiler error occurs.</span></span>

<span data-ttu-id="4e19d-137">表达式 lambda 的主体可以包含方法调用。</span><span class="sxs-lookup"><span data-stu-id="4e19d-137">The body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="4e19d-138">不过，若要创建在 .NET 公共语言运行时的上下文之外（如在 SQL Server 中）计算的表达式树，不得在 lambda 表达式中使用方法调用。</span><span class="sxs-lookup"><span data-stu-id="4e19d-138">However, if you are creating expression trees that are evaluated outside the context of the .NET common language runtime, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="4e19d-139">在 .NET 公共语言运行时上下文之外，方法将没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="4e19d-139">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>

## <a name="statement-lambdas"></a><span data-ttu-id="4e19d-140">语句 lambda</span><span class="sxs-lookup"><span data-stu-id="4e19d-140">Statement lambdas</span></span>

<span data-ttu-id="4e19d-141">语句 lambda 与表达式 lambda 表达式类似，只是语句括在大括号中：</span><span class="sxs-lookup"><span data-stu-id="4e19d-141">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>

```csharp  
(input-parameters) => { statement; }
```

<span data-ttu-id="4e19d-142">语句 lambda 的主体可以包含任意数量的语句；但是，实际上通常不会多于两个或三个。</span><span class="sxs-lookup"><span data-stu-id="4e19d-142">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>

[!code-csharp-interactive[statement lambda](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#StatementLambda)]

<span data-ttu-id="4e19d-143">像匿名方法一样，语句 lambda 也不能用于创建表达式目录树。</span><span class="sxs-lookup"><span data-stu-id="4e19d-143">Statement lambdas, like anonymous methods, cannot be used to create expression trees.</span></span>
  
## <a name="async-lambdas"></a><span data-ttu-id="4e19d-144">异步 lambda</span><span class="sxs-lookup"><span data-stu-id="4e19d-144">Async lambdas</span></span>

<span data-ttu-id="4e19d-145">通过使用 [async](../../language-reference/keywords/async.md) 和 [await](../../language-reference/keywords/await.md) 关键字，你可以轻松创建包含异步处理的 lambda 表达式和语句。</span><span class="sxs-lookup"><span data-stu-id="4e19d-145">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../../language-reference/keywords/async.md) and [await](../../language-reference/keywords/await.md) keywords.</span></span> <span data-ttu-id="4e19d-146">例如，下面的 Windows 窗体示例包含一个调用和等待异步方法 `ExampleMethodAsync`的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4e19d-146">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += button1_Click;
    }

    private async void button1_Click(object sender, EventArgs e)
    {
        await ExampleMethodAsync();
        textBox1.Text += "\r\nControl returned to Click event handler.\n";
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="4e19d-147">你可以使用异步 lambda 添加同一事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4e19d-147">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="4e19d-148">若要添加此处理程序，请在 lambda 参数列表前添加 `async` 修饰符，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="4e19d-148">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows:</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += async (sender, e) =>
        {
            await ExampleMethodAsync();
            textBox1.Text += "\r\nControl returned to Click event handler.\n";
        };
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="4e19d-149">有关如何创建和使用异步方法的详细信息，请参阅[使用 Async 和 Await 的异步编程](../concepts/async/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4e19d-149">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../concepts/async/index.md).</span></span>

## <a name="lambda-expressions-and-tuples"></a><span data-ttu-id="4e19d-150">lambda 表达式和元组</span><span class="sxs-lookup"><span data-stu-id="4e19d-150">Lambda expressions and tuples</span></span>

<span data-ttu-id="4e19d-151">自 C# 7.0 起，C# 语言提供对[元组](../../tuples.md)的内置支持。</span><span class="sxs-lookup"><span data-stu-id="4e19d-151">Starting with C# 7.0, the C# language provides built-in support for [tuples](../../tuples.md).</span></span> <span data-ttu-id="4e19d-152">可以提供一个元组作为 Lambda 表达式的参数，同时 Lambda 表达式也可以返回元组。</span><span class="sxs-lookup"><span data-stu-id="4e19d-152">You can provide a tuple as an argument to a lambda expression, and your lambda expression can also return a tuple.</span></span> <span data-ttu-id="4e19d-153">在某些情况下，C# 编译器使用类型推理来确定元组组件的类型。</span><span class="sxs-lookup"><span data-stu-id="4e19d-153">In some cases, the C# compiler uses type inference to determine the types of tuple components.</span></span>

<span data-ttu-id="4e19d-154">可通过用括号括住用逗号分隔的组件列表来定义元组。</span><span class="sxs-lookup"><span data-stu-id="4e19d-154">You define a tuple by enclosing a comma-delimited list of its components in parentheses.</span></span> <span data-ttu-id="4e19d-155">下面的示例使用包含三个组件的元组，将一系列数字传递给 lambda 表达式，此表达式将每个值翻倍，然后返回包含乘法运算结果的元组（内含三个组件）。</span><span class="sxs-lookup"><span data-stu-id="4e19d-155">The following example uses tuple with three components to pass a sequence of numbers to a lambda expression, which doubles each value and returns a tuple with three components that contains the result of the multiplications.</span></span>

[!code-csharp-interactive[lambda and tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

<span data-ttu-id="4e19d-156">通常，元组字段命名为 `Item1`、`Item2` 等等。但是，可以使用命名组件定义元组，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="4e19d-156">Ordinarily, the fields of a tuple are named `Item1`, `Item2`, etc. You can, however, define a tuple with named components, as the following example does.</span></span>

[!code-csharp-interactive[lambda and named tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

<span data-ttu-id="4e19d-157">若要详细了解 C# 元组，请参阅 [C# 元组类型](../../tuples.md)。</span><span class="sxs-lookup"><span data-stu-id="4e19d-157">For more information about C# tuples, see [C# tuple types](../../tuples.md).</span></span>

## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="4e19d-158">含标准查询运算符的 lambda</span><span class="sxs-lookup"><span data-stu-id="4e19d-158">Lambdas with the standard query operators</span></span>

<span data-ttu-id="4e19d-159">在其他实现中，LINQ to Objects 有一个输入参数，其类型是泛型委托 <xref:System.Func%601> 系列中的一种。</span><span class="sxs-lookup"><span data-stu-id="4e19d-159">LINQ to Objects, among other implementations, have an input parameter whose type is one of the <xref:System.Func%601> family of generic delegates.</span></span> <span data-ttu-id="4e19d-160">这些委托使用类型参数来定义输入参数的数量和类型，以及委托的返回类型。</span><span class="sxs-lookup"><span data-stu-id="4e19d-160">These delegates use type parameters to define the number and type of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="4e19d-161">`Func` 委托对于封装用户定义的表达式非常有用，这些表达式将应用于一组源数据中的每个元素。</span><span class="sxs-lookup"><span data-stu-id="4e19d-161">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="4e19d-162">例如，假设为 <xref:System.Func%602> 委托类型：</span><span class="sxs-lookup"><span data-stu-id="4e19d-162">For example, consider the <xref:System.Func%602> delegate type:</span></span>  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

<span data-ttu-id="4e19d-163">可以将委托实例化为 `Func<int, bool>` 实例，其中 `int` 是输入参数，`bool` 是返回值。</span><span class="sxs-lookup"><span data-stu-id="4e19d-163">The delegate can be instantiated as a `Func<int, bool>` instance where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="4e19d-164">返回值始终在最后一个类型参数中指定。</span><span class="sxs-lookup"><span data-stu-id="4e19d-164">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="4e19d-165">例如，`Func<int, string, bool>` 定义包含两个输入参数（`int` 和 `string`）且返回类型为 `bool`的委托。</span><span class="sxs-lookup"><span data-stu-id="4e19d-165">For example, `Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="4e19d-166">下面的 `Func` 委托在调用后返回布尔值，以指明输入参数是否等于 5：</span><span class="sxs-lookup"><span data-stu-id="4e19d-166">The following `Func` delegate, when it's invoked, returns Boolean value that indicates whether the input parameter is equal to five:</span></span>

[!code-csharp-interactive[Func example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

<span data-ttu-id="4e19d-167">参数类型为 <xref:System.Linq.Expressions.Expression%601> 时，也可以提供 Lambda 表达式，例如在 <xref:System.Linq.Queryable> 类型内定义的标准查询运算符中提供。</span><span class="sxs-lookup"><span data-stu-id="4e19d-167">You can also supply a lambda expression when the argument type is an <xref:System.Linq.Expressions.Expression%601>, for example in the standard query operators that are defined in the <xref:System.Linq.Queryable> type.</span></span> <span data-ttu-id="4e19d-168">指定 <xref:System.Linq.Expressions.Expression%601> 参数时，lambda 编译为表达式树。</span><span class="sxs-lookup"><span data-stu-id="4e19d-168">When you specify an <xref:System.Linq.Expressions.Expression%601> argument, the lambda is compiled to an expression tree.</span></span>
  
<span data-ttu-id="4e19d-169">下面的示例使用 <xref:System.Linq.Enumerable.Count%2A> 标准查询运算符：</span><span class="sxs-lookup"><span data-stu-id="4e19d-169">The following example uses the <xref:System.Linq.Enumerable.Count%2A> standard query operator:</span></span>

[!code-csharp-interactive[Count example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

<span data-ttu-id="4e19d-170">编译器可以推断输入参数的类型，或者你也可以显式指定该类型。</span><span class="sxs-lookup"><span data-stu-id="4e19d-170">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="4e19d-171">这个特殊 lambda 表达式将计算那些除以 2 时余数为 1 的整数的数量 (`n`)。</span><span class="sxs-lookup"><span data-stu-id="4e19d-171">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>

<span data-ttu-id="4e19d-172">下面的示例生成一个序列，其中包含 `numbers` 数组中位于 9 之前的所有元素，因为这是序列中第一个不符合条件的数字：</span><span class="sxs-lookup"><span data-stu-id="4e19d-172">The following example produces a sequence that contains all elements in the `numbers` array that precede the 9, because that's the first number in the sequence that doesn't meet the condition:</span></span>

[!code-csharp-interactive[TakeWhile example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

<span data-ttu-id="4e19d-173">以下示例通过将输入参数括在括号中来指定多个输入参数。</span><span class="sxs-lookup"><span data-stu-id="4e19d-173">The following example specifies multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="4e19d-174">此方法返回 `numbers` 数组中的所有元素，直至遇到值小于其在数组中的序号位置的数字为止：</span><span class="sxs-lookup"><span data-stu-id="4e19d-174">The method returns all the elements in the `numbers` array until it encounters a number whose value is less than its ordinal position in the array:</span></span>

[!code-csharp-interactive[TakeWhile example 2](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a><span data-ttu-id="4e19d-175">Lambda 表达式中的类型推理</span><span class="sxs-lookup"><span data-stu-id="4e19d-175">Type inference in lambda expressions</span></span>

<span data-ttu-id="4e19d-176">编写 lambda 时，通常不必为输入参数指定类型，因为编译器可以根据 lambda 主体、参数类型以及 C# 语言规范中描述的其他因素来推断类型。</span><span class="sxs-lookup"><span data-stu-id="4e19d-176">When writing lambdas, you often don't have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter types, and other factors as described in the C# language specification.</span></span> <span data-ttu-id="4e19d-177">对于大多数标准查询运算符，第一个输入是源序列中的元素类型。</span><span class="sxs-lookup"><span data-stu-id="4e19d-177">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="4e19d-178">如果要查询 `IEnumerable<Customer>`，则输入变量将被推断为 `Customer` 对象，这意味着你可以访问其方法和属性：</span><span class="sxs-lookup"><span data-stu-id="4e19d-178">If you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  

```csharp
customers.Where(c => c.City == "London");
```

<span data-ttu-id="4e19d-179">lambda 类型推理的一般规则如下：</span><span class="sxs-lookup"><span data-stu-id="4e19d-179">The general rules for type inference for lambdas are as follows:</span></span>

- <span data-ttu-id="4e19d-180">Lambda 包含的参数数量必须与委托类型包含的参数数量相同。</span><span class="sxs-lookup"><span data-stu-id="4e19d-180">The lambda must contain the same number of parameters as the delegate type.</span></span>

- <span data-ttu-id="4e19d-181">Lambda 中的每个输入参数必须都能够隐式转换为其对应的委托参数。</span><span class="sxs-lookup"><span data-stu-id="4e19d-181">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>

- <span data-ttu-id="4e19d-182">Lambda 的返回值（如果有）必须能够隐式转换为委托的返回类型。</span><span class="sxs-lookup"><span data-stu-id="4e19d-182">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>
  
<span data-ttu-id="4e19d-183">请注意，lambda 表达式本身没有类型，因为通用类型系统没有“lambda 表达式”这一固有概念。</span><span class="sxs-lookup"><span data-stu-id="4e19d-183">Note that lambda expressions in themselves don't have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="4e19d-184">不过，有时以一种非正式的方式谈论 lambda 表达式的“类型”会很方便。</span><span class="sxs-lookup"><span data-stu-id="4e19d-184">However, it's sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="4e19d-185">在这些情况下，类型是指委托类型或 lambda 表达式所转换到的 <xref:System.Linq.Expressions.Expression> 类型。</span><span class="sxs-lookup"><span data-stu-id="4e19d-185">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>

## <a name="variable-scope-in-lambda-expressions"></a><span data-ttu-id="4e19d-186">lambda 表达式中的变量范围</span><span class="sxs-lookup"><span data-stu-id="4e19d-186">Variable scope in lambda expressions</span></span>

<span data-ttu-id="4e19d-187">在定义 lambda 表达式的方法内或包含 lambda 表达式的类型内，lambda 可以引用范围内的外部变量（请参阅[匿名方法](anonymous-methods.md)）。</span><span class="sxs-lookup"><span data-stu-id="4e19d-187">Lambdas can refer to *outer variables* (see [Anonymous methods](anonymous-methods.md)) that are in scope in the method that defines the lambda expression, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="4e19d-188">以这种方式捕获的变量将进行存储以备在 lambda 表达式中使用，即使在其他情况下，这些变量将超出范围并进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="4e19d-188">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="4e19d-189">必须明确地分配外部变量，然后才能在 lambda 表达式中使用该变量。</span><span class="sxs-lookup"><span data-stu-id="4e19d-189">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="4e19d-190">下面的示例演示这些规则：</span><span class="sxs-lookup"><span data-stu-id="4e19d-190">The following example demonstrates these rules:</span></span>

[!code-csharp[variable scope](~/samples/snippets/csharp/programming-guide/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

<span data-ttu-id="4e19d-191">下列规则适用于 lambda 表达式中的变量范围：</span><span class="sxs-lookup"><span data-stu-id="4e19d-191">The following rules apply to variable scope in lambda expressions:</span></span>  

- <span data-ttu-id="4e19d-192">捕获的变量将不会被作为垃圾回收，直至引用变量的委托符合垃圾回收的条件。</span><span class="sxs-lookup"><span data-stu-id="4e19d-192">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>

- <span data-ttu-id="4e19d-193">在封闭方法中看不到 lambda 表达式内引入的变量。</span><span class="sxs-lookup"><span data-stu-id="4e19d-193">Variables introduced within a lambda expression are not visible in the enclosing method.</span></span>

- <span data-ttu-id="4e19d-194">lambda 表达式无法从封闭方法中直接捕获 [in](../../language-reference/keywords/in-parameter-modifier.md)、[ref](../../language-reference/keywords/ref.md) 或 [out](../../language-reference/keywords/out-parameter-modifier.md) 参数。</span><span class="sxs-lookup"><span data-stu-id="4e19d-194">A lambda expression cannot directly capture an [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter from the enclosing method.</span></span>

- <span data-ttu-id="4e19d-195">lambda 表达式中的 [return](../../language-reference/keywords/return.md) 语句不会导致封闭方法返回。</span><span class="sxs-lookup"><span data-stu-id="4e19d-195">A [return](../../language-reference/keywords/return.md) statement in a lambda expression doesn't cause the enclosing method to return.</span></span>

- <span data-ttu-id="4e19d-196">如果相应跳转语句的目标位于 lambda 表达式块之外，lambda 表达式不得包含 [goto](../../language-reference/keywords/goto.md)、[break](../../language-reference/keywords/break.md) 或 [continue](../../language-reference/keywords/continue.md) 语句。</span><span class="sxs-lookup"><span data-stu-id="4e19d-196">A lambda expression cannot contain a [goto](../../language-reference/keywords/goto.md), [break](../../language-reference/keywords/break.md), or [continue](../../language-reference/keywords/continue.md) statement if the target of that jump statement is outside the lambda expression block.</span></span> <span data-ttu-id="4e19d-197">同样，如果目标在块内部，在 lambda 表达式块外部使用跳转语句也是错误的。</span><span class="sxs-lookup"><span data-stu-id="4e19d-197">It's also an error to have a jump statement outside the lambda expression block if the target is inside the block.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4e19d-198">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="4e19d-198">C# language specification</span></span>

<span data-ttu-id="4e19d-199">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的 [匿名函数表达式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)部分。</span><span class="sxs-lookup"><span data-stu-id="4e19d-199">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="featured-book-chapter"></a><span data-ttu-id="4e19d-200">特别推荐书籍章节</span><span class="sxs-lookup"><span data-stu-id="4e19d-200">Featured book chapter</span></span>

<span data-ttu-id="4e19d-201">[C# 3.0 手册（第三版）：面向 C# 3.0 程序员的超过 250 个解决方案](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)中的[委托、事件和 Lambda 表达式](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="4e19d-201">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e19d-202">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e19d-202">See also</span></span>

- [<span data-ttu-id="4e19d-203">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="4e19d-203">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4e19d-204">LINQ（语言集成查询）</span><span class="sxs-lookup"><span data-stu-id="4e19d-204">LINQ (Language-Integrated Query)</span></span>](../concepts/linq/index.md)
- [<span data-ttu-id="4e19d-205">匿名方法</span><span class="sxs-lookup"><span data-stu-id="4e19d-205">Anonymous Methods</span></span>](anonymous-methods.md)
- [<span data-ttu-id="4e19d-206">表达式树</span><span class="sxs-lookup"><span data-stu-id="4e19d-206">Expression Trees</span></span>](../concepts/expression-trees/index.md)
- [<span data-ttu-id="4e19d-207">本地函数与 lambda 表达式比较</span><span class="sxs-lookup"><span data-stu-id="4e19d-207">Local functions compared to lambda expressions</span></span>](../../local-functions-vs-lambdas.md)
- [<span data-ttu-id="4e19d-208">隐式类型化 lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="4e19d-208">Implicitly typed lambda expressions</span></span>](../../implicitly-typed-lambda-expressions.md)
- [<span data-ttu-id="4e19d-209">Visual Studio 2008 C# 示例（请参阅 LINQ 示例查询文件和 XQuery 程序）</span><span class="sxs-lookup"><span data-stu-id="4e19d-209">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
- [<span data-ttu-id="4e19d-210">递归 lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="4e19d-210">Recursive lambda expressions</span></span>](https://blogs.msdn.microsoft.com/madst/2007/05/11/recursive-lambda-expressions/)
