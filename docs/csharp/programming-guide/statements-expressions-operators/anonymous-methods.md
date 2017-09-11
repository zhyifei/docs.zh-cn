---
title: "匿名方法（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- anonymous methods [C#]
- methods [C#], anonymous
- delegates [C#], anonymous methods
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 92842becf26a15ab1a6f5e9621002abf71dc67bc
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="anonymous-methods-c-programming-guide"></a><span data-ttu-id="e10e2-102">匿名方法（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="e10e2-102">Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="e10e2-103">在 2.0 之前的 C# 版本中，声明[委托](../../../csharp/language-reference/keywords/delegate.md)的唯一方式是使用[命名方法](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="e10e2-103">In versions of C# before 2.0, the only way to declare a [delegate](../../../csharp/language-reference/keywords/delegate.md) was to use [named methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md).</span></span> <span data-ttu-id="e10e2-104">C# 2.0 引入匿名方法，在 C# 3.0 及更高版本中，Lambda 表达式取代匿名方法作为编写内联代码的首选方式。</span><span class="sxs-lookup"><span data-stu-id="e10e2-104">C# 2.0 introduced anonymous methods and in C# 3.0 and later, lambda expressions supersede anonymous methods as the preferred way to write inline code.</span></span> <span data-ttu-id="e10e2-105">但是，本主题中有关匿名方法的信息也适用于 Lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="e10e2-105">However, the information about anonymous methods in this topic also applies to lambda expressions.</span></span> <span data-ttu-id="e10e2-106">在有一种情况下，匿名方法提供 Lambda 表达式中没有的功能。</span><span class="sxs-lookup"><span data-stu-id="e10e2-106">There is one case in which an anonymous method provides functionality not found in lambda expressions.</span></span> <span data-ttu-id="e10e2-107">使用匿名方法可省略参数列表。</span><span class="sxs-lookup"><span data-stu-id="e10e2-107">Anonymous methods enable you to omit the parameter list.</span></span> <span data-ttu-id="e10e2-108">这意味着匿名方法可转换为具有多种签名的委托。</span><span class="sxs-lookup"><span data-stu-id="e10e2-108">This means that an anonymous method can be converted to delegates with a variety of signatures.</span></span> <span data-ttu-id="e10e2-109">Lambda 表达式无法实现这一点。</span><span class="sxs-lookup"><span data-stu-id="e10e2-109">This is not possible with lambda expressions.</span></span> <span data-ttu-id="e10e2-110">有关 Lambda 表达式的详细信息，请参阅 [Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="e10e2-110">For more information specifically about lambda expressions, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="e10e2-111">创建匿名方法实际上是一种将代码块作为委托参数传递的方式。</span><span class="sxs-lookup"><span data-stu-id="e10e2-111">Creating anonymous methods is essentially a way to pass a code block as a delegate parameter.</span></span> <span data-ttu-id="e10e2-112">这里是两个示例：</span><span class="sxs-lookup"><span data-stu-id="e10e2-112">Here are two examples:</span></span>  
  
 <span data-ttu-id="e10e2-113">[!code-cs[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e10e2-113">[!code-cs[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="e10e2-114">[!code-cs[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e10e2-114">[!code-cs[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]</span></span>  
  
 <span data-ttu-id="e10e2-115">由于使用匿名方法无需创建单独的方法，因此可减少对委托进行实例化的编码开销。</span><span class="sxs-lookup"><span data-stu-id="e10e2-115">By using anonymous methods, you reduce the coding overhead in instantiating delegates because you do not have to create a separate method.</span></span>  
  
 <span data-ttu-id="e10e2-116">例如，在因不得不创建方法而可能出现非必要开销的情况下，指定代码块（而不是委托）很有用处。</span><span class="sxs-lookup"><span data-stu-id="e10e2-116">For example, specifying a code block instead of a delegate can be useful in a situation when having to create a method might seem an unnecessary overhead.</span></span> <span data-ttu-id="e10e2-117">开始新线程就是一个很好的示例。</span><span class="sxs-lookup"><span data-stu-id="e10e2-117">A good example would be when you start a new thread.</span></span> <span data-ttu-id="e10e2-118">此类创建一个线程，且还包含该线程执行的代码，而无需为委托创建其他方法。</span><span class="sxs-lookup"><span data-stu-id="e10e2-118">This class creates a thread and also contains the code that the thread executes without creating an additional method for the delegate.</span></span>  
  
 <span data-ttu-id="e10e2-119">[!code-cs[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="e10e2-119">[!code-cs[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e10e2-120">备注</span><span class="sxs-lookup"><span data-stu-id="e10e2-120">Remarks</span></span>  
 <span data-ttu-id="e10e2-121">匿名方法的参数范围为匿名方法块。</span><span class="sxs-lookup"><span data-stu-id="e10e2-121">The scope of the parameters of an anonymous method is the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="e10e2-122">如果目标在匿名方法块之外，匿名方法块内具有 [goto](../../../csharp/language-reference/keywords/goto.md)、[break](../../../csharp/language-reference/keywords/break.md) 或 [continue](../../../csharp/language-reference/keywords/continue.md) 等跳转语句是一种错误。</span><span class="sxs-lookup"><span data-stu-id="e10e2-122">It is an error to have a jump statement, such as [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md), or [continue](../../../csharp/language-reference/keywords/continue.md), inside the anonymous method block if the target is outside the block.</span></span> <span data-ttu-id="e10e2-123">如果目标在匿名方法块之内，匿名方法块外具有 `goto`、`break` 或 `continue` 等跳转语句也是一种错误。</span><span class="sxs-lookup"><span data-stu-id="e10e2-123">It is also an error to have a jump statement, such as `goto`, `break`, or `continue`, outside the anonymous method block if the target is inside the block.</span></span>  
  
 <span data-ttu-id="e10e2-124">范围包含匿名方法声明的本地变量和参数称为此匿名方法的外部变量。</span><span class="sxs-lookup"><span data-stu-id="e10e2-124">The local variables and parameters whose scope contains an anonymous method declaration are called *outer* variables of the anonymous method.</span></span> <span data-ttu-id="e10e2-125">例如，在如下代码段中，`n` 是一个外部变量：</span><span class="sxs-lookup"><span data-stu-id="e10e2-125">For example, in the following code segment, `n` is an outer variable:</span></span>  
  
 <span data-ttu-id="e10e2-126">[!code-cs[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="e10e2-126">[!code-cs[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]</span></span>  
  
 <span data-ttu-id="e10e2-127">创建委托时，对外部变量 `n` 的引用被视为已捕获。</span><span class="sxs-lookup"><span data-stu-id="e10e2-127">A reference to the outer variable `n` is said to be *captured* when the delegate is created.</span></span> <span data-ttu-id="e10e2-128">不同于本地变量，已捕获的变量的生存期一直延伸至引用匿名方法的委托具有垃圾回收资格为止。</span><span class="sxs-lookup"><span data-stu-id="e10e2-128">Unlike local variables, the lifetime of a captured variable extends until the delegates that reference the anonymous methods are eligible for garbage collection.</span></span>  
  
 <span data-ttu-id="e10e2-129">匿名方法无法访问外部范围的 [ref](../../../csharp/language-reference/keywords/ref.md) 或 [out](../../../csharp/language-reference/keywords/out.md) 参数。</span><span class="sxs-lookup"><span data-stu-id="e10e2-129">An anonymous method cannot access the [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) parameters of an outer scope.</span></span>  
  
 <span data-ttu-id="e10e2-130">无法在匿名方法块内访问任何不安全代码。</span><span class="sxs-lookup"><span data-stu-id="e10e2-130">No unsafe code can be accessed within the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="e10e2-131">不允许在 [is](../../../csharp/language-reference/keywords/is.md) 运算符左侧使用匿名方法。</span><span class="sxs-lookup"><span data-stu-id="e10e2-131">Anonymous methods are not allowed on the left side of the [is](../../../csharp/language-reference/keywords/is.md) operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e10e2-132">示例</span><span class="sxs-lookup"><span data-stu-id="e10e2-132">Example</span></span>  
 <span data-ttu-id="e10e2-133">如下示例演示实例化委托的两种方式：</span><span class="sxs-lookup"><span data-stu-id="e10e2-133">The following example demonstrates two ways of instantiating a delegate:</span></span>  
  
-   <span data-ttu-id="e10e2-134">将委托与匿名方法相关联。</span><span class="sxs-lookup"><span data-stu-id="e10e2-134">Associating the delegate with an anonymous method.</span></span>  
  
-   <span data-ttu-id="e10e2-135">将委托与命名方法 (`DoWork`) 相关联。</span><span class="sxs-lookup"><span data-stu-id="e10e2-135">Associating the delegate with a named method (`DoWork`).</span></span>  
  
 <span data-ttu-id="e10e2-136">在每一种情况下，调用委托时均显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="e10e2-136">In each case, a message is displayed when the delegate is invoked.</span></span>  
  
 <span data-ttu-id="e10e2-137">[!code-cs[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="e10e2-137">[!code-cs[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e10e2-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e10e2-138">See Also</span></span>  
 <span data-ttu-id="e10e2-139">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e10e2-139">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e10e2-140">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e10e2-140">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e10e2-141">[委托](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="e10e2-141">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="e10e2-142">[Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="e10e2-142">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
 <span data-ttu-id="e10e2-143">[不安全代码和指针](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="e10e2-143">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="e10e2-144">[方法](../../../csharp/programming-guide/classes-and-structs/methods.md) </span><span class="sxs-lookup"><span data-stu-id="e10e2-144">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 [<span data-ttu-id="e10e2-145">带有命名方法的委托与带有匿名方法的委托</span><span class="sxs-lookup"><span data-stu-id="e10e2-145">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)

