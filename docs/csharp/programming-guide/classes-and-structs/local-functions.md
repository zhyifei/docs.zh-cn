---
title: 本地函数 - C# 编程指南
ms.custom: seodec18
ms.date: 06/14/2017
helpviewer_keywords:
- local functions [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e91069c25ebe6c2a22927391734e5030a908e4ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663922"
---
# <a name="local-functions-c-programming-guide"></a><span data-ttu-id="f6ba7-102">本地函数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="f6ba7-102">Local functions (C# Programming Guide)</span></span>

<span data-ttu-id="f6ba7-103">从 C# 7.0 开始，C# 支持本地函数。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-103">Starting with C# 7.0, C# supports *local functions*.</span></span> <span data-ttu-id="f6ba7-104">本地函数是一种嵌套在另一成员中的类型的私有方法。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-104">Local functions are private methods of a type that are nested in another member.</span></span> <span data-ttu-id="f6ba7-105">仅能从其包含成员中调用它们。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-105">They can only be called from their containing member.</span></span> <span data-ttu-id="f6ba7-106">可以在以下位置中声明和调用本地函数：</span><span class="sxs-lookup"><span data-stu-id="f6ba7-106">Local functions can be declared in and called from:</span></span>

- <span data-ttu-id="f6ba7-107">方法（尤其是迭代器方法和异步方法）</span><span class="sxs-lookup"><span data-stu-id="f6ba7-107">Methods, especially iterator methods and async methods</span></span>
- <span data-ttu-id="f6ba7-108">构造函数</span><span class="sxs-lookup"><span data-stu-id="f6ba7-108">Constructors</span></span>
- <span data-ttu-id="f6ba7-109">属性访问器</span><span class="sxs-lookup"><span data-stu-id="f6ba7-109">Property accessors</span></span>
- <span data-ttu-id="f6ba7-110">事件访问器</span><span class="sxs-lookup"><span data-stu-id="f6ba7-110">Event accessors</span></span>
- <span data-ttu-id="f6ba7-111">匿名方法</span><span class="sxs-lookup"><span data-stu-id="f6ba7-111">Anonymous methods</span></span>
- <span data-ttu-id="f6ba7-112">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="f6ba7-112">Lambda expressions</span></span>
- <span data-ttu-id="f6ba7-113">终结器</span><span class="sxs-lookup"><span data-stu-id="f6ba7-113">Finalizers</span></span>
- <span data-ttu-id="f6ba7-114">其他本地函数</span><span class="sxs-lookup"><span data-stu-id="f6ba7-114">Other local functions</span></span>

<span data-ttu-id="f6ba7-115">但是，不能在 expression-bodied 成员中声明本地函数。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-115">However, local functions can't be declared inside an expression-bodied member.</span></span>

> [!NOTE]
> <span data-ttu-id="f6ba7-116">在某些情况下，可以使用 lambda 表达式实现本地函数也支持的功能。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-116">In some cases, you can use a lambda expression to implement functionality also supported by a local function.</span></span> <span data-ttu-id="f6ba7-117">有关比较，请参阅[本地函数与 Lambda 表达式比较](../../local-functions-vs-lambdas.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-117">For a comparison, see [Local functions compared to Lambda expressions](../../local-functions-vs-lambdas.md).</span></span>

<span data-ttu-id="f6ba7-118">本地函数可使代码意图明确。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-118">Local functions make the intent of your code clear.</span></span> <span data-ttu-id="f6ba7-119">任何读取代码的人都可以看到，此方法不可调用，包含方法除外。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-119">Anyone reading you code can see that the method is not callable except by the containing method.</span></span> <span data-ttu-id="f6ba7-120">对于团队项目，它们也使得其他开发人员无法直接从类或结构中的其他位置错误调用此方法。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-120">For team projects, they also make it impossible for another developer to mistakenly call the method directly from elsewhere in the class or struct.</span></span>
 
## <a name="local-function-syntax"></a><span data-ttu-id="f6ba7-121">本地函数语法</span><span class="sxs-lookup"><span data-stu-id="f6ba7-121">Local function syntax</span></span>

<span data-ttu-id="f6ba7-122">本地函数被定义为包含成员中的嵌套方法。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-122">A local function is defined as a nested method inside a containing member.</span></span> <span data-ttu-id="f6ba7-123">其定义具有以下语法：</span><span class="sxs-lookup"><span data-stu-id="f6ba7-123">Its definition has the following syntax:</span></span>

```txt
<modifiers: async | unsafe> <return-type> <method-name> <parameter-list>
```

<span data-ttu-id="f6ba7-124">本地函数可以使用 [async](../../language-reference/keywords/async.md) 和 [unsafe](../../language-reference/keywords/unsafe.md) 修饰符。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-124">Local functions can use the [async](../../language-reference/keywords/async.md) and [unsafe](../../language-reference/keywords/unsafe.md) modifiers.</span></span> 

<span data-ttu-id="f6ba7-125">请注意，在包含成员中定义的所有本地变量（包括其方法参数）都可在本地函数中访问。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-125">Note that all local variables that are defined in the containing member, including its method parameters, are accessible in the local function.</span></span> 

<span data-ttu-id="f6ba7-126">与方法定义不同，本地函数定义不能包含下列元素：</span><span class="sxs-lookup"><span data-stu-id="f6ba7-126">Unlike a method definition, a local function definition cannot include the following elements:</span></span>

- <span data-ttu-id="f6ba7-127">成员访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-127">The member access modifier.</span></span> <span data-ttu-id="f6ba7-128">因为所有本地函数都是私有的，包括访问修饰符（如 `private` 关键字）会生成编译器错误 CS0106“修饰符‘private’对于此项无效”。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-128">Because all local functions are private, including an access modifier, such as the `private` keyword, generates compiler error CS0106, "The modifier 'private' is not valid for this item."</span></span>
 
- <span data-ttu-id="f6ba7-129">[Static](../../language-reference/keywords/static.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-129">The [static](../../language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="f6ba7-130">包括 `static` 关键字将生成编译器错误 CS0106“修饰符‘static’对于此项无效”。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-130">Including the `static` keyword generates compiler error CS0106, "The modifier 'static' is not valid for this item."</span></span>

<span data-ttu-id="f6ba7-131">此外，属性不能应用于本地函数或其参数和类型参数。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-131">In addition, attributes can't be applied to the local function or to its parameters and type parameters.</span></span> 
 
<span data-ttu-id="f6ba7-132">以下示例定义了一个名为 `AppendPathSeparator` 的本地函数，该函数对于名为 `GetText` 的方法是私有的：</span><span class="sxs-lookup"><span data-stu-id="f6ba7-132">The following example defines a local function named `AppendPathSeparator` that is private to a method named `GetText`:</span></span>
   
[!code-csharp[LocalFunctionExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions1.cs)]  
   
## <a name="local-functions-and-exceptions"></a><span data-ttu-id="f6ba7-133">本地函数和异常</span><span class="sxs-lookup"><span data-stu-id="f6ba7-133">Local functions and exceptions</span></span>

<span data-ttu-id="f6ba7-134">本地函数的一个实用功能是可以允许立即显示异常。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-134">One of the useful features of local functions is that they can allow exceptions to surface immediately.</span></span> <span data-ttu-id="f6ba7-135">对于方法迭代器，仅在枚举返回的序列时才显示异常，而非在检索迭代器时。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-135">For method iterators, exceptions are surfaced only when the returned sequence is enumerated, and not when the iterator is retrieved.</span></span> <span data-ttu-id="f6ba7-136">对于异步方法，在等待返回的任务时，将观察到异步方法中引发的任何异常。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-136">For async methods, any exceptions thrown in an async method are observed when the returned task is awaited.</span></span> 

<span data-ttu-id="f6ba7-137">以下示例定义 `OddSequence` 方法，用于枚举指定范围之间的奇数。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-137">The following example defines an `OddSequence` method that enumerates odd numbers between a specified range.</span></span> <span data-ttu-id="f6ba7-138">因为它会将一个大于 100 的数字传递到 `OddSequence` 迭代器方法，该方法将引发 <xref:System.ArgumentOutOfRangeException>。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-138">Because it passes a number greater than 100 to the `OddSequence` enumerator method, the method throws an <xref:System.ArgumentOutOfRangeException>.</span></span> <span data-ttu-id="f6ba7-139">如示例中的输出所示，仅当循环访问数字时才显示异常，而非检索迭代器时。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-139">As the output from the example shows, the exception surfaces only when you iterate the numbers, and not when you retrieve the enumerator.</span></span>

[!code-csharp[LocalFunctionIterator1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator1.cs)] 

<span data-ttu-id="f6ba7-140">相反，可以在执行验证时和通过从本地函数返回迭代器检索迭代器之前引发异常，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-140">Instead, you can throw an exception when performing validation and before retrieving the iterator by returning the iterator from a local function, as the following example shows.</span></span>

[!code-csharp[LocalFunctionIterator2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator2.cs)]

<span data-ttu-id="f6ba7-141">可以通过类似的方式使用本地函数来处理异步操作之外的异常。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-141">Local functions can be used in a similar way to handle exceptions outside of the asynchronous operation.</span></span> <span data-ttu-id="f6ba7-142">异步方法中引发的异常通常都需要检查 <xref:System.AggregateException> 的内部异常。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-142">Ordinarily, exceptions thrown in async method require that you examine the inner exceptions of an <xref:System.AggregateException>.</span></span> <span data-ttu-id="f6ba7-143">本地函数允许代码快速失败，并允许同步引发和观察异常。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-143">Local functions allow your code to fail fast and allow your exception to be both thrown and observed synchronously.</span></span>

<span data-ttu-id="f6ba7-144">以下示例使用名为 `GetMultipleAsync` 的异步方法暂停指定的秒数并返回一个值，该值是该秒数的任意倍数。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-144">The following example uses an asynchronous method named `GetMultipleAsync` to pause for a specified number of seconds and return a value that is a random multiple of that number of seconds.</span></span> <span data-ttu-id="f6ba7-145">最大延迟为 5 秒；如果该值大于 5，则结果为 <xref:System.ArgumentOutOfRangeException>。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-145">The maximum delay is 5 seconds; an <xref:System.ArgumentOutOfRangeException> results if the value is greater than 5.</span></span> <span data-ttu-id="f6ba7-146">如以下示例所示，开始执行 `GetMultipleAsync` 方法后，将值 6 传递到 `GetMultipleAsync` 方法时引发的异常将在 <xref:System.AggregateException> 中进行包装。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-146">As the following example shows, the exception that is thrown when a value of 6 is passed to the `GetMultipleAsync` method is wrapped in an <xref:System.AggregateException> after the `GetMultipleAsync` method begins execution.</span></span>

[!code-csharp[LocalFunctionAsync`](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async1.cs)] 

<span data-ttu-id="f6ba7-147">正如处理方法迭代器一样，可以在调用异步方法之前重构本示例中的代码以执行验证。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-147">As we did with the method iterator, we can refactor the code from this example to perform the validation before calling the asynchronous method.</span></span> <span data-ttu-id="f6ba7-148">如以下示例中的输出所示，<xref:System.ArgumentOutOfRangeException> 不在 <xref:System.AggregateException> 中进行包装。</span><span class="sxs-lookup"><span data-stu-id="f6ba7-148">As the output from the following example shows, the <xref:System.ArgumentOutOfRangeException> is not wrapped in a <xref:System.AggregateException>.</span></span>

[!code-csharp[LocalFunctionAsync`](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async2.cs)] 

## <a name="see-also"></a><span data-ttu-id="f6ba7-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6ba7-149">See also</span></span>

- [<span data-ttu-id="f6ba7-150">方法</span><span class="sxs-lookup"><span data-stu-id="f6ba7-150">Methods</span></span>](methods.md)
