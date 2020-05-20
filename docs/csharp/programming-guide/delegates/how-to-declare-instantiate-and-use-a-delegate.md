---
title: 如何声明、实例化和使用委托 - C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
ms.openlocfilehash: 7ac1d736e19c4dcf1c8408db944505c399762778
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712359"
---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a><span data-ttu-id="24da8-102">如何声明、实例化和使用委托（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="24da8-102">How to declare, instantiate, and use a Delegate (C# Programming Guide)</span></span>
<span data-ttu-id="24da8-103">在 C# 1.0 和更高版本中，可以如下面的示例所示声明委托。</span><span class="sxs-lookup"><span data-stu-id="24da8-103">In C# 1.0 and later, delegates can be declared as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#13)]  
  
 [!code-csharp[csProgGuideDelegates#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#14)]  
  
 <span data-ttu-id="24da8-104">C# 2.0 提供了更简单的方法来编写前面的声明，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="24da8-104">C# 2.0 provides a simpler way to write the previous declaration, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#32)]  
  
 <span data-ttu-id="24da8-105">在 C# 2.0 和更高版本中，还可以使用匿名方法来声明和初始化[委托](../../language-reference/builtin-types/reference-types.md)，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="24da8-105">In C# 2.0 and later, it is also possible to use an anonymous method to declare and initialize a [delegate](../../language-reference/builtin-types/reference-types.md), as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#15)]  
  
 <span data-ttu-id="24da8-106">在 C# 3.0 和更高版本中，还可以通过使用 lambda 表达式声明和实例化委托，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="24da8-106">In C# 3.0 and later, delegates can also be declared and instantiated by using a lambda expression, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#31)]  
  
 <span data-ttu-id="24da8-107">有关详细信息，请参阅 [Lambda 表达式](../statements-expressions-operators/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="24da8-107">For more information, see [Lambda Expressions](../statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="24da8-108">下面的示例演示如何声明、实例化和使用委托。</span><span class="sxs-lookup"><span data-stu-id="24da8-108">The following example illustrates declaring, instantiating, and using a delegate.</span></span> <span data-ttu-id="24da8-109">`BookDB` 类封装用来维护书籍数据库的书店数据库。</span><span class="sxs-lookup"><span data-stu-id="24da8-109">The `BookDB` class encapsulates a bookstore database that maintains a database of books.</span></span> <span data-ttu-id="24da8-110">它公开一个方法 `ProcessPaperbackBooks`，用于在数据库中查找所有平装书并为每本书调用委托。</span><span class="sxs-lookup"><span data-stu-id="24da8-110">It exposes a method, `ProcessPaperbackBooks`, which finds all paperback books in the database and calls a delegate for each one.</span></span> <span data-ttu-id="24da8-111">使用的 `delegate` 类型名为 `ProcessBookDelegate`。</span><span class="sxs-lookup"><span data-stu-id="24da8-111">The `delegate` type that is used is named `ProcessBookDelegate`.</span></span> <span data-ttu-id="24da8-112">`Test` 类使用此类打印平装书的书名和平均价格。</span><span class="sxs-lookup"><span data-stu-id="24da8-112">The `Test` class uses this class to print the titles and average price of the paperback books.</span></span>  
  
 <span data-ttu-id="24da8-113">使用委托提升书店数据库和客户端代码之间的良好分隔功能。</span><span class="sxs-lookup"><span data-stu-id="24da8-113">The use of delegates promotes good separation of functionality between the bookstore database and the client code.</span></span> <span data-ttu-id="24da8-114">客户端代码程序不知道如何存储书籍或书店代码如何查找平装书。</span><span class="sxs-lookup"><span data-stu-id="24da8-114">The client code has no knowledge of how the books are stored or how the bookstore code finds paperback books.</span></span> <span data-ttu-id="24da8-115">书店代码不知道它在找到平装书之后对其执行什么处理。</span><span class="sxs-lookup"><span data-stu-id="24da8-115">The bookstore code has no knowledge of what processing is performed on the paperback books after it finds them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24da8-116">示例</span><span class="sxs-lookup"><span data-stu-id="24da8-116">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#12)]  
  
## <a name="robust-programming"></a><span data-ttu-id="24da8-117">可靠编程</span><span class="sxs-lookup"><span data-stu-id="24da8-117">Robust Programming</span></span>  
  
- <span data-ttu-id="24da8-118">声明委托。</span><span class="sxs-lookup"><span data-stu-id="24da8-118">Declaring a delegate.</span></span>  
  
     <span data-ttu-id="24da8-119">以下语句声明新的委托类型。</span><span class="sxs-lookup"><span data-stu-id="24da8-119">The following statement declares a new delegate type.</span></span>  
  
     [!code-csharp[csProgGuideDelegates#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#16)]  
  
     <span data-ttu-id="24da8-120">每个委托类型描述自变量的数量和类型，以及它可以封装的方法的返回值类型。</span><span class="sxs-lookup"><span data-stu-id="24da8-120">Each delegate type describes the number and types of the arguments, and the type of the return value of methods that it can encapsulate.</span></span> <span data-ttu-id="24da8-121">每当需要一组新的自变量类型或返回值类型，则必须声明一个新的委托类型。</span><span class="sxs-lookup"><span data-stu-id="24da8-121">Whenever a new set of argument types or return value type is needed, a new delegate type must be declared.</span></span>  
  
- <span data-ttu-id="24da8-122">实例化委托。</span><span class="sxs-lookup"><span data-stu-id="24da8-122">Instantiating a delegate.</span></span>  
  
     <span data-ttu-id="24da8-123">声明委托类型后，则必须创建委托对象并将其与特定的方法相关联。</span><span class="sxs-lookup"><span data-stu-id="24da8-123">After a delegate type has been declared, a delegate object must be created and associated with a particular method.</span></span> <span data-ttu-id="24da8-124">在上例中，你通过将 `PrintTitle` 方法传递给 `ProcessPaperbackBooks` 方法执行此操作，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="24da8-124">In the previous example, you do this by passing the `PrintTitle` method to the `ProcessPaperbackBooks` method as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#17)]  
  
     <span data-ttu-id="24da8-125">这将创建一个新的与[静态](../../language-reference/keywords/static.md)方法 `Test.PrintTitle` 关联的委托对象。</span><span class="sxs-lookup"><span data-stu-id="24da8-125">This creates a new delegate object associated with the [static](../../language-reference/keywords/static.md) method `Test.PrintTitle`.</span></span> <span data-ttu-id="24da8-126">同样，如下面的示例所示，传递对象 `totaller` 中的非静态方法 `AddBookToTotal`：</span><span class="sxs-lookup"><span data-stu-id="24da8-126">Similarly, the non-static method `AddBookToTotal` on the object `totaller` is passed as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#18)]  
  
     <span data-ttu-id="24da8-127">在这两种情况下，都将新的委托对象传递给 `ProcessPaperbackBooks` 方法。</span><span class="sxs-lookup"><span data-stu-id="24da8-127">In both cases a new delegate object is passed to the `ProcessPaperbackBooks` method.</span></span>  
  
     <span data-ttu-id="24da8-128">创建委托后，它与之关联的方法就永远不会更改；委托对象是不可变的。</span><span class="sxs-lookup"><span data-stu-id="24da8-128">After a delegate is created, the method it is associated with never changes; delegate objects are immutable.</span></span>  
  
- <span data-ttu-id="24da8-129">调用委托。</span><span class="sxs-lookup"><span data-stu-id="24da8-129">Calling a delegate.</span></span>  
  
     <span data-ttu-id="24da8-130">创建委托对象后，通常会将委托对象传递给将调用该委托的其他代码。</span><span class="sxs-lookup"><span data-stu-id="24da8-130">After a delegate object is created, the delegate object is typically passed to other code that will call the delegate.</span></span> <span data-ttu-id="24da8-131">委托对象是通过使用委托对象的名称调用的，后跟用圆括号括起来的将传递给委托的自变量。</span><span class="sxs-lookup"><span data-stu-id="24da8-131">A delegate object is called by using the name of the delegate object, followed by the parenthesized arguments to be passed to the delegate.</span></span> <span data-ttu-id="24da8-132">下面是一个委托调用示例：</span><span class="sxs-lookup"><span data-stu-id="24da8-132">Following is an example of a delegate call:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#19)]  
  
     <span data-ttu-id="24da8-133">委托可以同步调用（如在本例中）或通过使用 `BeginInvoke` 和 `EndInvoke` 方法异步调用。</span><span class="sxs-lookup"><span data-stu-id="24da8-133">A delegate can be either called synchronously, as in this example, or asynchronously by using `BeginInvoke` and `EndInvoke` methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24da8-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24da8-134">See also</span></span>

- [<span data-ttu-id="24da8-135">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="24da8-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="24da8-136">事件</span><span class="sxs-lookup"><span data-stu-id="24da8-136">Events</span></span>](../events/index.md)
- [<span data-ttu-id="24da8-137">委托</span><span class="sxs-lookup"><span data-stu-id="24da8-137">Delegates</span></span>](./index.md)
