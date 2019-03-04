---
title: Lambda 表达式 - C# 编程指南
ms.custom: seodec18
ms.date: 03/03/2017
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: 77701653abacbe6d876c0890a11586f0840bad5d
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200892"
---
# <a name="lambda-expressions-c-programming-guide"></a><span data-ttu-id="46012-102">Lambda 表达式（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="46012-102">Lambda expressions (C# Programming Guide)</span></span>

<span data-ttu-id="46012-103">Lambda 表达式是一种可用于创建 [委托](anonymous-methods.md) 或 [表达式目录树](../delegates/using-delegates.md) 类型的 [匿名函数](../concepts/expression-trees/index.md) 。</span><span class="sxs-lookup"><span data-stu-id="46012-103">A lambda expression is an [anonymous function](anonymous-methods.md) that you can use to create [delegates](../delegates/using-delegates.md) or [expression tree](../concepts/expression-trees/index.md) types.</span></span> <span data-ttu-id="46012-104">通过使用 lambda 表达式，可以写入可作为参数传递或作为函数调用值返回的本地函数。</span><span class="sxs-lookup"><span data-stu-id="46012-104">By using lambda expressions, you can write local functions that can be passed as arguments or returned as the value of function calls.</span></span> <span data-ttu-id="46012-105">Lambda 表达式对于编写 LINQ 查询表达式特别有用。</span><span class="sxs-lookup"><span data-stu-id="46012-105">Lambda expressions are particularly helpful for writing LINQ query expressions.</span></span>
  
<span data-ttu-id="46012-106">若要创建 Lambda 表达式，需要在 Lambda 运算符 [=>](../../../csharp/language-reference/operators/lambda-operator.md)左侧指定输入参数（如果有），然后在另一侧输入表达式或语句块。</span><span class="sxs-lookup"><span data-stu-id="46012-106">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator [=>](../../../csharp/language-reference/operators/lambda-operator.md), and you put the expression or statement block on the other side.</span></span> <span data-ttu-id="46012-107">例如，lambda 表达式 `x => x * x` 指定名为 `x` 的参数并返回 `x` 的平方值。</span><span class="sxs-lookup"><span data-stu-id="46012-107">For example, the lambda expression `x => x * x` specifies a parameter that’s named `x` and returns the value of `x` squared.</span></span> <span data-ttu-id="46012-108">如下面的示例所示，你可以将此表达式分配给委托类型：</span><span class="sxs-lookup"><span data-stu-id="46012-108">You can assign this expression to a delegate type, as the following example shows:</span></span>  
  
```csharp  
delegate int del(int i);  
static void Main(string[] args)  
{  
    del myDelegate = x => x * x;  
    int j = myDelegate(5); //j = 25  
}  
```  
  
 <span data-ttu-id="46012-109">若要创建表达式目录树类型：</span><span class="sxs-lookup"><span data-stu-id="46012-109">To create an expression tree type:</span></span>  
  
```csharp  
using System.Linq.Expressions;  
  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Expression<del> myET = x => x * x;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="46012-110">`=>` 运算符具有与赋值运算符 (`=`) 相同的优先级并且是[右结合运算](../../../csharp/programming-guide/statements-expressions-operators/operators.md)（参见“运算符”文章的“结合性”部分）。</span><span class="sxs-lookup"><span data-stu-id="46012-110">The `=>` operator has the same precedence as assignment (`=`) and is [right associative](../../../csharp/programming-guide/statements-expressions-operators/operators.md) (see "Associativity" section of the Operators article).</span></span>  
  
 <span data-ttu-id="46012-111">Lambda 在基于方法的 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 查询中用作标准查询运算符方法（如 <xref:System.Linq.Enumerable.Where%2A>）的参数。</span><span class="sxs-lookup"><span data-stu-id="46012-111">Lambdas are used in method-based [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries as arguments to standard query operator methods such as <xref:System.Linq.Enumerable.Where%2A>.</span></span>  
  
 <span data-ttu-id="46012-112">使用基于方法的语法在 <xref:System.Linq.Enumerable.Where%2A> 类中调用 <xref:System.Linq.Enumerable> 方法时（如在 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to Objects 和 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]中一样），参数是委托类型 <xref:System.Func%602?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="46012-112">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Where%2A> method in the <xref:System.Linq.Enumerable> class (as you do in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to Objects and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]) the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="46012-113">使用 Lambda 表达式创建该委托最为方便。</span><span class="sxs-lookup"><span data-stu-id="46012-113">A lambda expression is the most convenient way to create that delegate.</span></span> <span data-ttu-id="46012-114">例如，在 <xref:System.Linq.Queryable?displayProperty=nameWithType> 类中调用相同的方法时（如在 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 中一样），参数类型为 <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType><Func\>，其中 Func 是最多具有十六个输入参数的任何一个 Func 委托。</span><span class="sxs-lookup"><span data-stu-id="46012-114">When you call the same method in, for example, the <xref:System.Linq.Queryable?displayProperty=nameWithType> class (as you do in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]) then the parameter type is an <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType><Func\> where Func is any of the Func delegates with up to sixteen input parameters.</span></span> <span data-ttu-id="46012-115">同样，Lambda 表达式只是一种非常简洁的构造该表达式目录树的方式。</span><span class="sxs-lookup"><span data-stu-id="46012-115">Again, a lambda expression is just a very concise way to construct that expression tree.</span></span> <span data-ttu-id="46012-116">尽管事实上通过 Lambda 创建的对象具有不同的类型，但 Lambda 使得 `Where` 调用看起来类似。</span><span class="sxs-lookup"><span data-stu-id="46012-116">The lambdas allow the `Where` calls to look similar although in fact the type of object created from the lambda is different.</span></span>  
  
 <span data-ttu-id="46012-117">在上一个示例中，请注意委托签名具有一个 `int`类型的隐式类型输入参数，并返回 `int`。</span><span class="sxs-lookup"><span data-stu-id="46012-117">In the previous example, notice that the delegate signature has one implicitly-typed input parameter of type `int`, and returns an `int`.</span></span> <span data-ttu-id="46012-118">可以将 Lambda 表达式转换为该类型的委托，因为该表达式也具有一个输入参数 (`x`)，以及一个编译器可隐式转换为 `int` 类型的返回值。</span><span class="sxs-lookup"><span data-stu-id="46012-118">The lambda expression can be converted to a delegate of that type because it also has one input parameter (`x`) and a return value that the compiler can implicitly convert to type `int`.</span></span> <span data-ttu-id="46012-119">（以下几节中将对类型推理进行详细讨论。）使用输入参数 5 调用委托时，它将返回结果 25。</span><span class="sxs-lookup"><span data-stu-id="46012-119">(Type inference is discussed in more detail in the following sections.) When the delegate is invoked by using an input parameter of 5, it returns a result of 25.</span></span>  
  
 <span data-ttu-id="46012-120">在 [is](../../../csharp/language-reference/keywords/is.md) 或 [as](../../../csharp/language-reference/keywords/as.md) 运算符的左侧不允许使用 Lambda。</span><span class="sxs-lookup"><span data-stu-id="46012-120">Lambdas are not allowed on the left side of the [is](../../../csharp/language-reference/keywords/is.md) or [as](../../../csharp/language-reference/keywords/as.md) operator.</span></span>  
  
 <span data-ttu-id="46012-121">适用于匿名方法的所有限制也适用于 Lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="46012-121">All restrictions that apply to anonymous methods also apply to lambda expressions.</span></span> <span data-ttu-id="46012-122">有关详细信息，请参阅[匿名方法](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="46012-122">For more information, see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
## <a name="expression-lambdas"></a><span data-ttu-id="46012-123">表达式 lambda</span><span class="sxs-lookup"><span data-stu-id="46012-123">Expression lambdas</span></span>

 <span data-ttu-id="46012-124">表达式位于 => 运算符右侧的 Lambda 表达式称为“表达式 lambda”。</span><span class="sxs-lookup"><span data-stu-id="46012-124">A lambda expression with an expression on the right side of the => operator is called an *expression lambda*.</span></span> <span data-ttu-id="46012-125">表达式 lambda 广泛用于[表达式树](../concepts/expression-trees/index.md)的构造。</span><span class="sxs-lookup"><span data-stu-id="46012-125">Expression lambdas are used extensively in the construction of [Expression Trees](../concepts/expression-trees/index.md).</span></span> <span data-ttu-id="46012-126">表达式 lambda 会返回表达式的结果，并采用以下基本形式：</span><span class="sxs-lookup"><span data-stu-id="46012-126">An expression lambda returns the result of the expression and takes the following basic form:</span></span>
  
```csharp
(input-parameters) => expression
```

 <span data-ttu-id="46012-127">仅当 lambda 只有一个输入参数时，括号才是可选的；否则括号是必需的。</span><span class="sxs-lookup"><span data-stu-id="46012-127">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span> <span data-ttu-id="46012-128">括号内的两个或更多输入参数使用逗号加以分隔：</span><span class="sxs-lookup"><span data-stu-id="46012-128">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>  
  
```csharp
(x, y) => x == y
```

 <span data-ttu-id="46012-129">有时，编译器难以或无法推断输入类型。</span><span class="sxs-lookup"><span data-stu-id="46012-129">Sometimes it is difficult or impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="46012-130">如果出现这种情况，你可以按以下示例中所示方式显式指定类型：</span><span class="sxs-lookup"><span data-stu-id="46012-130">When this occurs, you can specify the types explicitly as shown in the following example:</span></span>  
  
```csharp
(int x, string s) => s.Length > x
```
 <span data-ttu-id="46012-131">输入参数类型必须全部为显式或全部为隐式；否则，C# 将生成 [CS0748](../../misc/cs0748.md) 编译器错误。</span><span class="sxs-lookup"><span data-stu-id="46012-131">Input parameter types must be all explicit or all implicit; otherwise, C# generates a [CS0748](../../misc/cs0748.md) compiler error.</span></span>

 <span data-ttu-id="46012-132">使用空括号指定零个输入参数：</span><span class="sxs-lookup"><span data-stu-id="46012-132">Specify zero input parameters with empty parentheses:</span></span>  
  
```csharp
() => SomeMethod()
```

 <span data-ttu-id="46012-133">在上一个示例中，请注意表达式 Lambda 的主体可以包含一个方法调用。</span><span class="sxs-lookup"><span data-stu-id="46012-133">Note in the previous example that the body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="46012-134">但是，如果要创建在 .NET Framework 之外计算的表达式目录树（例如，在 SQL Server 中），则不应在 lambda 表达式中使用方法调用。</span><span class="sxs-lookup"><span data-stu-id="46012-134">However, if you are creating expression trees that are evaluated outside of the .NET Framework, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="46012-135">在 .NET 公共语言运行时上下文之外，方法将没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="46012-135">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>  
  
## <a name="statement-lambdas"></a><span data-ttu-id="46012-136">语句 lambda</span><span class="sxs-lookup"><span data-stu-id="46012-136">Statement lambdas</span></span>

 <span data-ttu-id="46012-137">语句 lambda 与表达式 lambda 表达式类似，只是语句括在大括号中：</span><span class="sxs-lookup"><span data-stu-id="46012-137">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>  
  
<span data-ttu-id="46012-138">(input-parameters) => { statement; }</span><span class="sxs-lookup"><span data-stu-id="46012-138">(input-parameters) => { statement; }</span></span>

 <span data-ttu-id="46012-139">语句 lambda 的主体可以包含任意数量的语句；但是，实际上通常不会多于两个或三个。</span><span class="sxs-lookup"><span data-stu-id="46012-139">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>  
  
[!code-csharp[StatementLambda#1](~/samples/snippets/csharp/programming-guide/lambda-expressions/statements.cs#1)]

[!code-csharp[StatementLambda#2](~/samples/snippets/csharp/programming-guide/lambda-expressions/statements.cs#2)]

 <span data-ttu-id="46012-140">像匿名方法一样，语句 lambda 也不能用于创建表达式目录树。</span><span class="sxs-lookup"><span data-stu-id="46012-140">Statement lambdas, like anonymous methods, cannot be used to create expression trees.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="46012-141">异步 lambda</span><span class="sxs-lookup"><span data-stu-id="46012-141">Async lambdas</span></span>

 <span data-ttu-id="46012-142">通过使用 [async](../../../csharp/language-reference/keywords/async.md) 和 [await](../../../csharp/language-reference/keywords/await.md) 关键字，你可以轻松创建包含异步处理的 lambda 表达式和语句。</span><span class="sxs-lookup"><span data-stu-id="46012-142">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../../../csharp/language-reference/keywords/async.md) and [await](../../../csharp/language-reference/keywords/await.md) keywords.</span></span> <span data-ttu-id="46012-143">例如，下面的 Windows 窗体示例包含一个调用和等待异步方法 `ExampleMethodAsync`的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="46012-143">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
```csharp
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
    }  
  
    private async void button1_Click(object sender, EventArgs e)  
    {  
        // ExampleMethodAsync returns a Task.  
        await ExampleMethodAsync();  
        textBox1.Text += "\r\nControl returned to Click event handler.\n";  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```

 <span data-ttu-id="46012-144">你可以使用异步 lambda 添加同一事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="46012-144">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="46012-145">若要添加此处理程序，请在 lambda 参数列表前添加一个 `async` 修饰符，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="46012-145">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
```csharp  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        button1.Click += async (sender, e) =>  
        {  
            // ExampleMethodAsync returns a Task.  
            await ExampleMethodAsync();  
            textBox1.Text += "\nControl returned to Click event handler.\n";  
        };  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```  

 <span data-ttu-id="46012-146">有关如何创建和使用异步方法的详细信息，请参阅[使用 Async 和 Await 的异步编程](../../../csharp/programming-guide/concepts/async/index.md)。</span><span class="sxs-lookup"><span data-stu-id="46012-146">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md).</span></span>  
  
## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="46012-147">含标准查询运算符的 lambda</span><span class="sxs-lookup"><span data-stu-id="46012-147">Lambdas with the standard query operators</span></span>

 <span data-ttu-id="46012-148">许多标准查询运算符都具有输入参数，其类型是泛型委托系列 <xref:System.Func%602> 中的一种。</span><span class="sxs-lookup"><span data-stu-id="46012-148">Many standard query operators have an input parameter whose type is one of the <xref:System.Func%602> family of generic delegates.</span></span> <span data-ttu-id="46012-149">这些委托使用类型参数来定义输入参数的数量和类型，以及委托的返回类型。</span><span class="sxs-lookup"><span data-stu-id="46012-149">These delegates use type parameters to define the number and types of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="46012-150">`Func` 委托对于封装用户定义的表达式非常有用，这些表达式将应用于一组源数据中的每个元素。</span><span class="sxs-lookup"><span data-stu-id="46012-150">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="46012-151">例如，请考虑以下委托类型：</span><span class="sxs-lookup"><span data-stu-id="46012-151">For example, consider the following delegate type:</span></span>  
  
```csharp  
public delegate TResult Func<TArg0, TResult>(TArg0 arg0)  
```  
  
 <span data-ttu-id="46012-152">可以将委托实例化为 `Func<int,bool> myFunc` ，其中 `int` 是输入参数， `bool` 是返回值。</span><span class="sxs-lookup"><span data-stu-id="46012-152">The delegate can be instantiated as `Func<int,bool> myFunc` where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="46012-153">返回值始终在最后一个类型参数中指定。</span><span class="sxs-lookup"><span data-stu-id="46012-153">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="46012-154">`Func<int, string, bool>` 定义包含两个输入参数（ `int` 和 `string`）且返回类型为 `bool`的委托。</span><span class="sxs-lookup"><span data-stu-id="46012-154">`Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="46012-155">当调用下面的 `Func` 委托时，该委托将返回 true 或 false 以指示输入参数是否等于 5：</span><span class="sxs-lookup"><span data-stu-id="46012-155">The following `Func` delegate, when it is invoked, will return true or false to indicate whether the input parameter is equal to 5:</span></span>  
  
```csharp  
Func<int, bool> myFunc = x => x == 5;  
bool result = myFunc(4); // returns false of course  
```  
  
 <span data-ttu-id="46012-156">当参数类型为 `Expression<Func>`时，你也可以提供 Lambda 表达式，例如在 System.Linq.Queryable 内定义的标准查询运算符中。</span><span class="sxs-lookup"><span data-stu-id="46012-156">You can also supply a lambda expression when the argument type is an `Expression<Func>`, for example in the standard query operators that are defined in System.Linq.Queryable.</span></span> <span data-ttu-id="46012-157">如果指定 `Expression<Func>` 参数，lambda 将编译为表达式目录树。</span><span class="sxs-lookup"><span data-stu-id="46012-157">When you specify an `Expression<Func>` argument, the lambda will be compiled to an expression tree.</span></span>  
  
 <span data-ttu-id="46012-158">此处显示了一个标准查询运算符， <xref:System.Linq.Enumerable.Count%2A> 方法：</span><span class="sxs-lookup"><span data-stu-id="46012-158">A standard query operator, the <xref:System.Linq.Enumerable.Count%2A> method, is shown here:</span></span>  
  
```csharp  
int[] numbers = { 5, 4, 1, 3, 9, 8, 6, 7, 2, 0 };  
int oddNumbers = numbers.Count(n => n % 2 == 1);  
```  
  
 <span data-ttu-id="46012-159">编译器可以推断输入参数的类型，或者你也可以显式指定该类型。</span><span class="sxs-lookup"><span data-stu-id="46012-159">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="46012-160">这个特殊 lambda 表达式将计算那些除以 2 时余数为 1 的整数的数量 (`n`)。</span><span class="sxs-lookup"><span data-stu-id="46012-160">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>  
  
 <span data-ttu-id="46012-161">下面一行代码将生成一个序列，其中包含 `numbers` 数组中在 9 左侧的所有元素，因为它是序列中第一个不满足条件的数字：</span><span class="sxs-lookup"><span data-stu-id="46012-161">The following line of code produces a sequence that contains all elements in the `numbers` array that are to the left side of the 9 because that's the first number in the sequence that doesn't meet the condition:</span></span>  
  
```csharp  
var firstNumbersLessThan6 = numbers.TakeWhile(n => n < 6);  
```  
  
 <span data-ttu-id="46012-162">此示例展示了如何通过将输入参数括在括号中来指定多个输入参数。</span><span class="sxs-lookup"><span data-stu-id="46012-162">This example shows how to specify multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="46012-163">该方法将返回数字数组中的所有元素，直至遇到一个值小于其位置的数字为止。</span><span class="sxs-lookup"><span data-stu-id="46012-163">The method returns all the elements in the numbers array until a number is encountered whose value is less than its position.</span></span> <span data-ttu-id="46012-164">不要将 lambda 运算符 (`=>`) 与大于等于运算符 (`>=`) 混淆。</span><span class="sxs-lookup"><span data-stu-id="46012-164">Do not confuse the lambda operator (`=>`) with the greater than or equal operator (`>=`).</span></span>  
  
```csharp  
var firstSmallNumbers = numbers.TakeWhile((n, index) => n >= index);  
```  
  
## <a name="type-inference-in-lambdas"></a><span data-ttu-id="46012-165">lambda 中的类型推理</span><span class="sxs-lookup"><span data-stu-id="46012-165">Type inference in lambdas</span></span>

 <span data-ttu-id="46012-166">在编写 lambda 时，通常不必为输入参数指定类型，因为编译器可以根据 lambda 主体、参数的委托类型以及 C# 语言规范中描述的其他因素来推断类型。</span><span class="sxs-lookup"><span data-stu-id="46012-166">When writing lambdas, you often do not have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter’s delegate type, and other factors as described in the C# Language Specification.</span></span> <span data-ttu-id="46012-167">对于大多数标准查询运算符，第一个输入是源序列中的元素类型。</span><span class="sxs-lookup"><span data-stu-id="46012-167">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="46012-168">因此，如果要查询 `IEnumerable<Customer>`，则输入变量将被推断为 `Customer` 对象，这意味着你可以访问其方法和属性：</span><span class="sxs-lookup"><span data-stu-id="46012-168">So if you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  
  
```csharp  
customers.Where(c => c.City == "London");  
```  
  
 <span data-ttu-id="46012-169">Lambda 的一般规则如下：</span><span class="sxs-lookup"><span data-stu-id="46012-169">The general rules for lambdas are as follows:</span></span>  
  
-   <span data-ttu-id="46012-170">Lambda 包含的参数数量必须与委托类型包含的参数数量相同。</span><span class="sxs-lookup"><span data-stu-id="46012-170">The lambda must contain the same number of parameters as the delegate type.</span></span>  
  
-   <span data-ttu-id="46012-171">Lambda 中的每个输入参数必须都能够隐式转换为其对应的委托参数。</span><span class="sxs-lookup"><span data-stu-id="46012-171">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>  
  
-   <span data-ttu-id="46012-172">Lambda 的返回值（如果有）必须能够隐式转换为委托的返回类型。</span><span class="sxs-lookup"><span data-stu-id="46012-172">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>  
  
 <span data-ttu-id="46012-173">请注意，lambda 表达式本身没有类型，因为常规类型系统没有“Lambda 表达式”这一内部概念。</span><span class="sxs-lookup"><span data-stu-id="46012-173">Note that lambda expressions in themselves do not have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="46012-174">但是，有时以一种非正式的方式谈论 lambda 表达式的“类型”会很方便。</span><span class="sxs-lookup"><span data-stu-id="46012-174">However, it is sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="46012-175">在这些情况下，类型是指委托类型或 lambda 表达式所转换到的 <xref:System.Linq.Expressions.Expression> 类型。</span><span class="sxs-lookup"><span data-stu-id="46012-175">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>  
  
## <a name="variable-scope-in-lambda-expressions"></a><span data-ttu-id="46012-176">lambda 表达式中的变量范围</span><span class="sxs-lookup"><span data-stu-id="46012-176">Variable scope in lambda expressions</span></span>

 <span data-ttu-id="46012-177">在定义 lambda 函数的方法内或包含 Lambda 表达式的类型内，Lambda 可以引用范围内的外部变量（请参阅[匿名方法](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)）。</span><span class="sxs-lookup"><span data-stu-id="46012-177">Lambdas can refer to *outer variables* (see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)) that are in scope in the method that defines the lambda function, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="46012-178">以这种方式捕获的变量将进行存储以备在 lambda 表达式中使用，即使在其他情况下，这些变量将超出范围并进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="46012-178">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="46012-179">必须明确地分配外部变量，然后才能在 lambda 表达式中使用该变量。</span><span class="sxs-lookup"><span data-stu-id="46012-179">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="46012-180">下面的示例演示这些规则：</span><span class="sxs-lookup"><span data-stu-id="46012-180">The following example demonstrates these rules:</span></span>  
  
```csharp  
delegate bool D();  
delegate bool D2(int i);  
  
class Test  
{  
    D del;  
    D2 del2;  
    public void TestMethod(int input)  
    {  
        int j = 0;  
        // Initialize the delegates with lambda expressions.  
        // Note access to 2 outer variables.  
        // del will be invoked within this method.  
        del = () => { j = 10;  return j > input; };  
  
        // del2 will be invoked after TestMethod goes out of scope.  
        del2 = (x) => {return x == j; };  
  
        // Demonstrate value of j:  
        // Output: j = 0   
        // The delegate has not been invoked yet.  
        Console.WriteLine("j = {0}", j);        // Invoke the delegate.  
        bool boolResult = del();  
  
        // Output: j = 10 b = True  
        Console.WriteLine("j = {0}. b = {1}", j, boolResult);  
    }  
  
    static void Main()  
    {  
        Test test = new Test();  
        test.TestMethod(5);  
  
        // Prove that del2 still has a copy of  
        // local variable j from TestMethod.  
        bool result = test.del2(10);  
  
        // Output: True  
        Console.WriteLine(result);  
  
        Console.ReadKey();  
    }  
}  
```  
  
 <span data-ttu-id="46012-181">下列规则适用于 lambda 表达式中的变量范围：</span><span class="sxs-lookup"><span data-stu-id="46012-181">The following rules apply to variable scope in lambda expressions:</span></span>  
  
-   <span data-ttu-id="46012-182">捕获的变量将不会被作为垃圾回收，直至引用变量的委托符合垃圾回收的条件。</span><span class="sxs-lookup"><span data-stu-id="46012-182">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>  
  
-   <span data-ttu-id="46012-183">在外部方法中看不到 lambda 表达式内引入的变量。</span><span class="sxs-lookup"><span data-stu-id="46012-183">Variables introduced within a lambda expression are not visible in the outer method.</span></span>  
  
-   <span data-ttu-id="46012-184">Lambda 表达式无法从封闭方法中直接捕获 `in`、`ref` 或 `out` 参数。</span><span class="sxs-lookup"><span data-stu-id="46012-184">A lambda expression cannot directly capture an `in`, `ref`, or `out` parameter from an enclosing method.</span></span>  
  
-   <span data-ttu-id="46012-185">Lambda 表达式中的返回语句不会导致封闭方法返回。</span><span class="sxs-lookup"><span data-stu-id="46012-185">A return statement in a lambda expression does not cause the enclosing method to return.</span></span>  
  
-   <span data-ttu-id="46012-186">如果跳转语句的目标在块外部，则 lambda 表达式不能包含位于 lambda 函数内部的 `goto` 语句、 `break` 语句或 `continue` 语句。</span><span class="sxs-lookup"><span data-stu-id="46012-186">A lambda expression cannot contain a `goto` statement, `break` statement, or `continue` statement that is inside the lambda function if the jump statement’s target is outside the block.</span></span> <span data-ttu-id="46012-187">同样，如果目标在块内部，则在 lambda 函数块外部使用跳转语句也是错误的。</span><span class="sxs-lookup"><span data-stu-id="46012-187">It is also an error to have a jump statement outside the lambda function block if the target is inside the block.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="46012-188">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="46012-188">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapter"></a><span data-ttu-id="46012-189">特别推荐书籍章节</span><span class="sxs-lookup"><span data-stu-id="46012-189">Featured book chapter</span></span>

 <span data-ttu-id="46012-190">[C# 3.0 手册（第三版）：面向 C# 3.0 程序员的超过 250 个解决方案](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)中的[委托、事件和 Lambda 表达式](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="46012-190">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46012-191">请参阅</span><span class="sxs-lookup"><span data-stu-id="46012-191">See also</span></span>

- [<span data-ttu-id="46012-192">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="46012-192">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="46012-193">LINQ（语言集成查询）</span><span class="sxs-lookup"><span data-stu-id="46012-193">LINQ (Language-Integrated Query)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="46012-194">匿名方法</span><span class="sxs-lookup"><span data-stu-id="46012-194">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
- [<span data-ttu-id="46012-195">is</span><span class="sxs-lookup"><span data-stu-id="46012-195">is</span></span>](../../../csharp/language-reference/keywords/is.md)
- [<span data-ttu-id="46012-196">表达式树</span><span class="sxs-lookup"><span data-stu-id="46012-196">Expression Trees</span></span>](../../../csharp/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="46012-197">Visual Studio 2008 C# 示例（请参阅 LINQ 示例查询文件和 XQuery 程序）</span><span class="sxs-lookup"><span data-stu-id="46012-197">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
- [<span data-ttu-id="46012-198">递归 lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="46012-198">Recursive lambda expressions</span></span>](https://blogs.msdn.microsoft.com/madst/2007/05/11/recursive-lambda-expressions/)
