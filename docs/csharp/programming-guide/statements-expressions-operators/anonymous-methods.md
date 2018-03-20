---
title: "匿名方法（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- anonymous methods [C#]
- methods [C#], anonymous
- delegates [C#], anonymous methods
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 96e78257c5aab84562cd8cdb336bb5a91ba59534
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="anonymous-methods-c-programming-guide"></a><span data-ttu-id="54674-102">匿名方法（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="54674-102">Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="54674-103">在 2.0 之前的 C# 版本中，声明[委托](../../../csharp/language-reference/keywords/delegate.md)的唯一方式是使用[命名方法](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="54674-103">In versions of C# before 2.0, the only way to declare a [delegate](../../../csharp/language-reference/keywords/delegate.md) was to use [named methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md).</span></span> <span data-ttu-id="54674-104">C# 2.0 引入匿名方法，在 C# 3.0 及更高版本中，Lambda 表达式取代匿名方法作为编写内联代码的首选方式。</span><span class="sxs-lookup"><span data-stu-id="54674-104">C# 2.0 introduced anonymous methods and in C# 3.0 and later, lambda expressions supersede anonymous methods as the preferred way to write inline code.</span></span> <span data-ttu-id="54674-105">但是，本主题中有关匿名方法的信息也适用于 Lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="54674-105">However, the information about anonymous methods in this topic also applies to lambda expressions.</span></span> <span data-ttu-id="54674-106">在有一种情况下，匿名方法提供 Lambda 表达式中没有的功能。</span><span class="sxs-lookup"><span data-stu-id="54674-106">There is one case in which an anonymous method provides functionality not found in lambda expressions.</span></span> <span data-ttu-id="54674-107">使用匿名方法可省略参数列表。</span><span class="sxs-lookup"><span data-stu-id="54674-107">Anonymous methods enable you to omit the parameter list.</span></span> <span data-ttu-id="54674-108">这意味着匿名方法可转换为具有多种签名的委托。</span><span class="sxs-lookup"><span data-stu-id="54674-108">This means that an anonymous method can be converted to delegates with a variety of signatures.</span></span> <span data-ttu-id="54674-109">Lambda 表达式无法实现这一点。</span><span class="sxs-lookup"><span data-stu-id="54674-109">This is not possible with lambda expressions.</span></span> <span data-ttu-id="54674-110">有关 Lambda 表达式的详细信息，请参阅 [Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="54674-110">For more information specifically about lambda expressions, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="54674-111">创建匿名方法实际上是一种将代码块作为委托参数传递的方式。</span><span class="sxs-lookup"><span data-stu-id="54674-111">Creating anonymous methods is essentially a way to pass a code block as a delegate parameter.</span></span> <span data-ttu-id="54674-112">这里是两个示例：</span><span class="sxs-lookup"><span data-stu-id="54674-112">Here are two examples:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]  
  
 [!code-csharp[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]  
  
 <span data-ttu-id="54674-113">由于使用匿名方法无需创建单独的方法，因此可减少对委托进行实例化的编码开销。</span><span class="sxs-lookup"><span data-stu-id="54674-113">By using anonymous methods, you reduce the coding overhead in instantiating delegates because you do not have to create a separate method.</span></span>  
  
 <span data-ttu-id="54674-114">例如，在因不得不创建方法而可能出现非必要开销的情况下，指定代码块（而不是委托）很有用处。</span><span class="sxs-lookup"><span data-stu-id="54674-114">For example, specifying a code block instead of a delegate can be useful in a situation when having to create a method might seem an unnecessary overhead.</span></span> <span data-ttu-id="54674-115">开始新线程就是一个很好的示例。</span><span class="sxs-lookup"><span data-stu-id="54674-115">A good example would be when you start a new thread.</span></span> <span data-ttu-id="54674-116">此类创建一个线程，且还包含该线程执行的代码，而无需为委托创建其他方法。</span><span class="sxs-lookup"><span data-stu-id="54674-116">This class creates a thread and also contains the code that the thread executes without creating an additional method for the delegate.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="54674-117">备注</span><span class="sxs-lookup"><span data-stu-id="54674-117">Remarks</span></span>  
 <span data-ttu-id="54674-118">匿名方法的参数范围为匿名方法块。</span><span class="sxs-lookup"><span data-stu-id="54674-118">The scope of the parameters of an anonymous method is the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="54674-119">如果目标在匿名方法块之外，匿名方法块内具有 [goto](../../../csharp/language-reference/keywords/goto.md)、[break](../../../csharp/language-reference/keywords/break.md) 或 [continue](../../../csharp/language-reference/keywords/continue.md) 等跳转语句是一种错误。</span><span class="sxs-lookup"><span data-stu-id="54674-119">It is an error to have a jump statement, such as [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md), or [continue](../../../csharp/language-reference/keywords/continue.md), inside the anonymous method block if the target is outside the block.</span></span> <span data-ttu-id="54674-120">如果目标在匿名方法块之内，匿名方法块外具有 `goto`、`break` 或 `continue` 等跳转语句也是一种错误。</span><span class="sxs-lookup"><span data-stu-id="54674-120">It is also an error to have a jump statement, such as `goto`, `break`, or `continue`, outside the anonymous method block if the target is inside the block.</span></span>  
  
 <span data-ttu-id="54674-121">范围包含匿名方法声明的本地变量和参数称为此匿名方法的外部变量。</span><span class="sxs-lookup"><span data-stu-id="54674-121">The local variables and parameters whose scope contains an anonymous method declaration are called *outer* variables of the anonymous method.</span></span> <span data-ttu-id="54674-122">例如，在如下代码段中，`n` 是一个外部变量：</span><span class="sxs-lookup"><span data-stu-id="54674-122">For example, in the following code segment, `n` is an outer variable:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]  
  
 <span data-ttu-id="54674-123">创建委托时，对外部变量 `n` 的引用被视为已捕获。</span><span class="sxs-lookup"><span data-stu-id="54674-123">A reference to the outer variable `n` is said to be *captured* when the delegate is created.</span></span> <span data-ttu-id="54674-124">不同于本地变量，已捕获的变量的生存期一直延伸至引用匿名方法的委托具有垃圾回收资格为止。</span><span class="sxs-lookup"><span data-stu-id="54674-124">Unlike local variables, the lifetime of a captured variable extends until the delegates that reference the anonymous methods are eligible for garbage collection.</span></span>  
  
 <span data-ttu-id="54674-125">匿名方法无法访问外部范围的 [in](../../../csharp/language-reference/keywords/in.md)、[ref](../../../csharp/language-reference/keywords/ref.md) 或 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 参数。</span><span class="sxs-lookup"><span data-stu-id="54674-125">An anonymous method cannot access the [in](../../../csharp/language-reference/keywords/in.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters of an outer scope.</span></span>  
  
 <span data-ttu-id="54674-126">无法在匿名方法块内访问任何不安全代码。</span><span class="sxs-lookup"><span data-stu-id="54674-126">No unsafe code can be accessed within the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="54674-127">不允许在 [is](../../../csharp/language-reference/keywords/is.md) 运算符左侧使用匿名方法。</span><span class="sxs-lookup"><span data-stu-id="54674-127">Anonymous methods are not allowed on the left side of the [is](../../../csharp/language-reference/keywords/is.md) operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54674-128">示例</span><span class="sxs-lookup"><span data-stu-id="54674-128">Example</span></span>  
 <span data-ttu-id="54674-129">如下示例演示实例化委托的两种方式：</span><span class="sxs-lookup"><span data-stu-id="54674-129">The following example demonstrates two ways of instantiating a delegate:</span></span>  
  
-   <span data-ttu-id="54674-130">将委托与匿名方法相关联。</span><span class="sxs-lookup"><span data-stu-id="54674-130">Associating the delegate with an anonymous method.</span></span>  
  
-   <span data-ttu-id="54674-131">将委托与命名方法 (`DoWork`) 相关联。</span><span class="sxs-lookup"><span data-stu-id="54674-131">Associating the delegate with a named method (`DoWork`).</span></span>  
  
 <span data-ttu-id="54674-132">在每一种情况下，调用委托时均显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="54674-132">In each case, a message is displayed when the delegate is invoked.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="54674-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="54674-133">See Also</span></span>  
 [<span data-ttu-id="54674-134">C# 参考</span><span class="sxs-lookup"><span data-stu-id="54674-134">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="54674-135">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="54674-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="54674-136">委托</span><span class="sxs-lookup"><span data-stu-id="54674-136">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="54674-137">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="54674-137">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [<span data-ttu-id="54674-138">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="54674-138">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="54674-139">方法</span><span class="sxs-lookup"><span data-stu-id="54674-139">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [<span data-ttu-id="54674-140">带有命名方法的委托与带有匿名方法的委托</span><span class="sxs-lookup"><span data-stu-id="54674-140">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)
