---
title: "如何：声明、实例化和使用委托（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
caps.latest.revision: 21
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
ms.openlocfilehash: 5a16fe4c627989f701ba523769cd87839d074849
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a><span data-ttu-id="909b6-102">如何：声明、实例化和使用委托（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="909b6-102">How to: Declare, Instantiate, and Use a Delegate (C# Programming Guide)</span></span>
<span data-ttu-id="909b6-103">在 C# 1.0 和更高版本中，可以如下面的示例所示声明委托。</span><span class="sxs-lookup"><span data-stu-id="909b6-103">In C# 1.0 and later, delegates can be declared as shown in the following example.</span></span>  
  
 <span data-ttu-id="909b6-104">[!code-cs[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="909b6-104">[!code-cs[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_1.cs)]</span></span>  
  
 <span data-ttu-id="909b6-105">[!code-cs[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="909b6-105">[!code-cs[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_2.cs)]</span></span>  
  
 <span data-ttu-id="909b6-106">C# 2.0 提供了更简单的方法来编写前面的声明，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="909b6-106">C# 2.0 provides a simpler way to write the previous declaration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="909b6-107">[!code-cs[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="909b6-107">[!code-cs[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_3.cs)]</span></span>  
  
 <span data-ttu-id="909b6-108">在 C# 2.0 和更高版本中，还可以使用匿名方法来声明和初始化[委托](../../../csharp/language-reference/keywords/delegate.md)，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="909b6-108">In C# 2.0 and later, it is also possible to use an anonymous method to declare and initialize a [delegate](../../../csharp/language-reference/keywords/delegate.md), as shown in the following example.</span></span>  
  
 <span data-ttu-id="909b6-109">[!code-cs[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="909b6-109">[!code-cs[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_4.cs)]</span></span>  
  
 <span data-ttu-id="909b6-110">在 C# 3.0 和更高版本中，还可以通过使用 lambda 表达式声明和实例化委托，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="909b6-110">In C# 3.0 and later, delegates can also be declared and instantiated by using a lambda expression, as shown in the following example.</span></span>  
  
 <span data-ttu-id="909b6-111">[!code-cs[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="909b6-111">[!code-cs[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_5.cs)]</span></span>  
  
 <span data-ttu-id="909b6-112">有关详细信息，请参阅 [Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="909b6-112">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="909b6-113">下面的示例演示如何声明、实例化和使用委托。</span><span class="sxs-lookup"><span data-stu-id="909b6-113">The following example illustrates declaring, instantiating, and using a delegate.</span></span> <span data-ttu-id="909b6-114">`BookDB` 类封装用来维护书籍数据库的书店数据库。</span><span class="sxs-lookup"><span data-stu-id="909b6-114">The `BookDB` class encapsulates a bookstore database that maintains a database of books.</span></span> <span data-ttu-id="909b6-115">它公开一个方法 `ProcessPaperbackBooks`，用于在数据库中查找所有平装书并为每本书调用委托。</span><span class="sxs-lookup"><span data-stu-id="909b6-115">It exposes a method, `ProcessPaperbackBooks`, which finds all paperback books in the database and calls a delegate for each one.</span></span> <span data-ttu-id="909b6-116">使用的 `delegate` 类型名为 `ProcessBookDelegate`。</span><span class="sxs-lookup"><span data-stu-id="909b6-116">The `delegate` type that is used is named `ProcessBookDelegate`.</span></span> <span data-ttu-id="909b6-117">`Test` 类使用此类打印平装书的书名和平均价格。</span><span class="sxs-lookup"><span data-stu-id="909b6-117">The `Test` class uses this class to print the titles and average price of the paperback books.</span></span>  
  
 <span data-ttu-id="909b6-118">使用委托提升书店数据库和客户端代码之间的良好分隔功能。</span><span class="sxs-lookup"><span data-stu-id="909b6-118">The use of delegates promotes good separation of functionality between the bookstore database and the client code.</span></span> <span data-ttu-id="909b6-119">客户端代码程序不知道如何存储书籍或书店代码如何查找平装书。</span><span class="sxs-lookup"><span data-stu-id="909b6-119">The client code has no knowledge of how the books are stored or how the bookstore code finds paperback books.</span></span> <span data-ttu-id="909b6-120">书店代码不知道它在找到平装书之后对其执行什么处理。</span><span class="sxs-lookup"><span data-stu-id="909b6-120">The bookstore code has no knowledge of what processing is performed on the paperback books after it finds them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="909b6-121">示例</span><span class="sxs-lookup"><span data-stu-id="909b6-121">Example</span></span>  
 <span data-ttu-id="909b6-122">[!code-cs[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="909b6-122">[!code-cs[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_6.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="909b6-123">可靠编程</span><span class="sxs-lookup"><span data-stu-id="909b6-123">Robust Programming</span></span>  
  
-   <span data-ttu-id="909b6-124">声明委托。</span><span class="sxs-lookup"><span data-stu-id="909b6-124">Declaring a delegate.</span></span>  
  
     <span data-ttu-id="909b6-125">以下语句声明新的委托类型。</span><span class="sxs-lookup"><span data-stu-id="909b6-125">The following statement declares a new delegate type.</span></span>  
  
     <span data-ttu-id="909b6-126">[!code-cs[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="909b6-126">[!code-cs[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_7.cs)]</span></span>  
  
     <span data-ttu-id="909b6-127">每个委托类型描述自变量的数量和类型，以及它可以封装的方法的返回值类型。</span><span class="sxs-lookup"><span data-stu-id="909b6-127">Each delegate type describes the number and types of the arguments, and the type of the return value of methods that it can encapsulate.</span></span> <span data-ttu-id="909b6-128">每当需要一组新的自变量类型或返回值类型，则必须声明一个新的委托类型。</span><span class="sxs-lookup"><span data-stu-id="909b6-128">Whenever a new set of argument types or return value type is needed, a new delegate type must be declared.</span></span>  
  
-   <span data-ttu-id="909b6-129">实例化委托。</span><span class="sxs-lookup"><span data-stu-id="909b6-129">Instantiating a delegate.</span></span>  
  
     <span data-ttu-id="909b6-130">声明委托类型后，则必须创建委托对象并将其与特定的方法相关联。</span><span class="sxs-lookup"><span data-stu-id="909b6-130">After a delegate type has been declared, a delegate object must be created and associated with a particular method.</span></span> <span data-ttu-id="909b6-131">在上例中，你通过将 `PrintTitle` 方法传递给 `ProcessPaperbackBooks` 方法执行此操作，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="909b6-131">In the previous example, you do this by passing the `PrintTitle` method to the `ProcessPaperbackBooks` method as in the following example:</span></span>  
  
     <span data-ttu-id="909b6-132">[!code-cs[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="909b6-132">[!code-cs[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_8.cs)]</span></span>  
  
     <span data-ttu-id="909b6-133">这将创建一个新的与[静态](../../../csharp/language-reference/keywords/static.md)方法 `Test.PrintTitle` 关联的委托对象。</span><span class="sxs-lookup"><span data-stu-id="909b6-133">This creates a new delegate object associated with the [static](../../../csharp/language-reference/keywords/static.md) method `Test.PrintTitle`.</span></span> <span data-ttu-id="909b6-134">同样，如下面的示例所示，传递对象 `totaller` 中的非静态方法 `AddBookToTotal`：</span><span class="sxs-lookup"><span data-stu-id="909b6-134">Similarly, the non-static method `AddBookToTotal` on the object `totaller` is passed as in the following example:</span></span>  
  
     <span data-ttu-id="909b6-135">[!code-cs[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="909b6-135">[!code-cs[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_9.cs)]</span></span>  
  
     <span data-ttu-id="909b6-136">在这两种情况下，都将新的委托对象传递给 `ProcessPaperbackBooks` 方法。</span><span class="sxs-lookup"><span data-stu-id="909b6-136">In both cases a new delegate object is passed to the `ProcessPaperbackBooks` method.</span></span>  
  
     <span data-ttu-id="909b6-137">创建委托后，它与之关联的方法就永远不会更改；委托对象是不可变的。</span><span class="sxs-lookup"><span data-stu-id="909b6-137">After a delegate is created, the method it is associated with never changes; delegate objects are immutable.</span></span>  
  
-   <span data-ttu-id="909b6-138">调用委托。</span><span class="sxs-lookup"><span data-stu-id="909b6-138">Calling a delegate.</span></span>  
  
     <span data-ttu-id="909b6-139">创建委托对象后，通常会将委托对象传递给将调用该委托的其他代码。</span><span class="sxs-lookup"><span data-stu-id="909b6-139">After a delegate object is created, the delegate object is typically passed to other code that will call the delegate.</span></span> <span data-ttu-id="909b6-140">委托对象是通过使用委托对象的名称调用的，后跟用圆括号括起来的将传递给委托的自变量。</span><span class="sxs-lookup"><span data-stu-id="909b6-140">A delegate object is called by using the name of the delegate object, followed by the parenthesized arguments to be passed to the delegate.</span></span> <span data-ttu-id="909b6-141">下面是一个委托调用示例：</span><span class="sxs-lookup"><span data-stu-id="909b6-141">Following is an example of a delegate call:</span></span>  
  
     <span data-ttu-id="909b6-142">[!code-cs[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="909b6-142">[!code-cs[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_10.cs)]</span></span>  
  
     <span data-ttu-id="909b6-143">委托可以同步调用（如在本例中）或通过使用 `BeginInvoke` 和 `EndInvoke` 方法异步调用。</span><span class="sxs-lookup"><span data-stu-id="909b6-143">A delegate can be either called synchronously, as in this example, or asynchronously by using `BeginInvoke` and `EndInvoke` methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="909b6-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="909b6-144">See Also</span></span>  
 <span data-ttu-id="909b6-145">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="909b6-145">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="909b6-146">[事件](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="909b6-146">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 [<span data-ttu-id="909b6-147">委托</span><span class="sxs-lookup"><span data-stu-id="909b6-147">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)

