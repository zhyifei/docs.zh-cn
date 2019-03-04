---
title: '委托 - C# 编程指南'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
  - 'C# language, delegates'
  - 'delegates [C#]'
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
---
# <a name="delegates-c-programming-guide"></a><span data-ttu-id="210ad-102">委托（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="210ad-102">Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="210ad-103">[委托](../../../csharp/language-reference/keywords/delegate.md)是一种引用类型，表示对具有特定参数列表和返回类型的方法的引用。</span><span class="sxs-lookup"><span data-stu-id="210ad-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) is a type that represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="210ad-104">在实例化委托时，你可以将其实例与任何具有兼容签名和返回类型的方法相关联。</span><span class="sxs-lookup"><span data-stu-id="210ad-104">When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.</span></span> <span data-ttu-id="210ad-105">你可以通过委托实例调用方法。</span><span class="sxs-lookup"><span data-stu-id="210ad-105">You can invoke (or call) the method through the delegate instance.</span></span>  
  
 <span data-ttu-id="210ad-106">委托用于将方法作为参数传递给其他方法。</span><span class="sxs-lookup"><span data-stu-id="210ad-106">Delegates are used to pass methods as arguments to other methods.</span></span> <span data-ttu-id="210ad-107">事件处理程序就是通过委托调用的方法。</span><span class="sxs-lookup"><span data-stu-id="210ad-107">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="210ad-108">你可以创建一个自定义方法，当发生特定事件时，某个类（如 Windows 控件）就可以调用你的方法。</span><span class="sxs-lookup"><span data-stu-id="210ad-108">You create a custom method, and a class such as a windows control can call your method when a certain event occurs.</span></span> <span data-ttu-id="210ad-109">下面的示例演示了一个委托声明：</span><span class="sxs-lookup"><span data-stu-id="210ad-109">The following example shows a delegate declaration:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#20)]  
  
 <span data-ttu-id="210ad-110">可将任何可访问类或结构中与委托类型匹配的任何方法分配给委托。</span><span class="sxs-lookup"><span data-stu-id="210ad-110">Any method from any accessible class or struct that matches the delegate type can be assigned to the delegate.</span></span> <span data-ttu-id="210ad-111">该方法可以是静态方法，也可以是实例方法。</span><span class="sxs-lookup"><span data-stu-id="210ad-111">The method can be either static or an instance method.</span></span> <span data-ttu-id="210ad-112">这样便能通过编程方式来更改方法调用，还可以向现有类中插入新代码。</span><span class="sxs-lookup"><span data-stu-id="210ad-112">This makes it possible to programmatically change method calls, and also plug new code into existing classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="210ad-113">在方法重载的上下文中，方法的签名不包括返回值。</span><span class="sxs-lookup"><span data-stu-id="210ad-113">In the context of method overloading, the signature of a method does not include the return value.</span></span> <span data-ttu-id="210ad-114">但在委托的上下文中，签名包括返回值。</span><span class="sxs-lookup"><span data-stu-id="210ad-114">But in the context of delegates, the signature does include the return value.</span></span> <span data-ttu-id="210ad-115">换句话说，方法和委托必须具有相同的返回类型。</span><span class="sxs-lookup"><span data-stu-id="210ad-115">In other words, a method must have the same return type as the delegate.</span></span>  
  
 <span data-ttu-id="210ad-116">将方法作为参数进行引用的能力使委托成为定义回调方法的理想选择。</span><span class="sxs-lookup"><span data-stu-id="210ad-116">This ability to refer to a method as a parameter makes delegates ideal for defining callback methods.</span></span> <span data-ttu-id="210ad-117">例如，对比较两个对象的方法的引用可以作为参数传递到排序算法中。</span><span class="sxs-lookup"><span data-stu-id="210ad-117">For example, a reference to a method that compares two objects could be passed as an argument to a sort algorithm.</span></span> <span data-ttu-id="210ad-118">由于比较代码在一个单独的过程中，因此可通过更常见的方式编写排序算法。</span><span class="sxs-lookup"><span data-stu-id="210ad-118">Because the comparison code is in a separate procedure, the sort algorithm can be written in a more general way.</span></span>  
  
## <a name="delegates-overview"></a><span data-ttu-id="210ad-119">委托概述</span><span class="sxs-lookup"><span data-stu-id="210ad-119">Delegates Overview</span></span>  
 <span data-ttu-id="210ad-120">委托具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="210ad-120">Delegates have the following properties:</span></span>  
  
-   <span data-ttu-id="210ad-121">委托类似于 C++ 函数指针，但委托完全面向对象，不像 C++ 指针会记住函数，委托会同时封装对象实例和方法。</span><span class="sxs-lookup"><span data-stu-id="210ad-121">Delegates are similar to C++ function pointers, but delegates are fully object-oriented, and unlike C++ pointers to member functions, delegates encapsulate both an object instance and a method.</span></span>
  
-   <span data-ttu-id="210ad-122">委托允许将方法作为参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="210ad-122">Delegates allow methods to be passed as parameters.</span></span>  
  
-   <span data-ttu-id="210ad-123">委托可用于定义回调方法。</span><span class="sxs-lookup"><span data-stu-id="210ad-123">Delegates can be used to define callback methods.</span></span>  
  
-   <span data-ttu-id="210ad-124">委托可以链接在一起；例如，可以对一个事件调用多个方法。</span><span class="sxs-lookup"><span data-stu-id="210ad-124">Delegates can be chained together; for example, multiple methods can be called on a single event.</span></span>  
  
-   <span data-ttu-id="210ad-125">方法不必与委托类型完全匹配。</span><span class="sxs-lookup"><span data-stu-id="210ad-125">Methods do not have to match the delegate type exactly.</span></span> <span data-ttu-id="210ad-126">有关详细信息，请参阅[使用委托中的变体](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="210ad-126">For more information, see [Using Variance in Delegates](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
-   <span data-ttu-id="210ad-127">C# 2.0 版引入了[匿名方法](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)的概念，可以将代码块作为参数（而不是单独定义的方法）进行传递。</span><span class="sxs-lookup"><span data-stu-id="210ad-127">C# version 2.0 introduced the concept of [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), which allow code blocks to be passed as parameters in place of a separately defined method.</span></span> <span data-ttu-id="210ad-128">C# 3.0 引入了 Lambda 表达式，利用它们可以更简练地编写内联代码块。</span><span class="sxs-lookup"><span data-stu-id="210ad-128">C# 3.0 introduced lambda expressions as a more concise way of writing inline code blocks.</span></span> <span data-ttu-id="210ad-129">匿名方法和 Lambda 表达式（在某些上下文中）都可编译为委托类型。</span><span class="sxs-lookup"><span data-stu-id="210ad-129">Both anonymous methods and lambda expressions (in certain contexts) are compiled to delegate types.</span></span> <span data-ttu-id="210ad-130">这些功能现在统称为匿名函数。</span><span class="sxs-lookup"><span data-stu-id="210ad-130">Together, these features are now known as anonymous functions.</span></span> <span data-ttu-id="210ad-131">有关 lambda 表达式的详细信息，请参阅[匿名函数](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="210ad-131">For more information about lambda expressions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="210ad-132">本节内容</span><span class="sxs-lookup"><span data-stu-id="210ad-132">In This Section</span></span>  
  
-   [<span data-ttu-id="210ad-133">使用委托</span><span class="sxs-lookup"><span data-stu-id="210ad-133">Using Delegates</span></span>](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
-   <span data-ttu-id="210ad-134">[何时使用委托，而不是接口（C# 编程指南）](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms173173(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="210ad-134">[When to Use Delegates Instead of Interfaces (C# Programming Guide)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms173173(v=vs.100))</span></span>  
  
-   [<span data-ttu-id="210ad-135">带有命名方法的委托与带有匿名方法的委托</span><span class="sxs-lookup"><span data-stu-id="210ad-135">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
-   [<span data-ttu-id="210ad-136">匿名方法</span><span class="sxs-lookup"><span data-stu-id="210ad-136">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
-   [<span data-ttu-id="210ad-137">使用委托中的变体</span><span class="sxs-lookup"><span data-stu-id="210ad-137">Using Variance in Delegates</span></span>](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
-   [<span data-ttu-id="210ad-138">如何：合并委托（多播委托）</span><span class="sxs-lookup"><span data-stu-id="210ad-138">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
-   [<span data-ttu-id="210ad-139">如何：声明、实例化和使用委托</span><span class="sxs-lookup"><span data-stu-id="210ad-139">How to: Declare, Instantiate, and Use a Delegate</span></span>](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  
  
  
## <a name="c-language-specification"></a><span data-ttu-id="210ad-140">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="210ad-140">C# Language Specification</span></span>  

<span data-ttu-id="210ad-141">有关详细信息，请参阅 [C# 语言规范](../../language-reference/language-specification/index.md)中的[委托](~/_csharplang/spec/delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="210ad-141">For more information, see [Delegates](~/_csharplang/spec/delegates.md) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="210ad-142">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="210ad-142">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="210ad-143">重要章节</span><span class="sxs-lookup"><span data-stu-id="210ad-143">Featured Book Chapters</span></span>  
 <span data-ttu-id="210ad-144">[C# 3.0 手册（第三版）：面向 C# 3.0 程序员的超过 250 个解决方案](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)中的[委托、事件和 Lambda 表达式](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="210ad-144">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
 <span data-ttu-id="210ad-145">[学习 C# 3.0：掌握 C# 3.0 基础知识](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)中的[委托和事件](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="210ad-145">[Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="210ad-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="210ad-146">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="210ad-147">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="210ad-147">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="210ad-148">事件</span><span class="sxs-lookup"><span data-stu-id="210ad-148">Events</span></span>](../../../csharp/programming-guide/events/index.md)
