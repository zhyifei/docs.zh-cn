---
title: 带有命名方法的委托与匿名方法 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: 8d3cecbaecc8cf5af1e06f29c9bb8a151523d3e8
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970943"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="18ef2-102">带有命名方法的委托与匿名方法（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="18ef2-102">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="18ef2-103">[委托](../../../csharp/language-reference/keywords/delegate.md)可以与命名方法相关联。</span><span class="sxs-lookup"><span data-stu-id="18ef2-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can be associated with a named method.</span></span> <span data-ttu-id="18ef2-104">使用命名方法实例化委托时，该方法作为参数传递，例如：</span><span class="sxs-lookup"><span data-stu-id="18ef2-104">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#1)]  
  
 <span data-ttu-id="18ef2-105">这称为使用命名方法。</span><span class="sxs-lookup"><span data-stu-id="18ef2-105">This is called using a named method.</span></span> <span data-ttu-id="18ef2-106">使用命名方法构造的委托可以封装[静态](../../../csharp/language-reference/keywords/static.md)方法或实例方法。</span><span class="sxs-lookup"><span data-stu-id="18ef2-106">Delegates constructed with a named method can encapsulate either a [static](../../../csharp/language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="18ef2-107">命名方法是在早期版本的 C# 中实例化委托的唯一方式。</span><span class="sxs-lookup"><span data-stu-id="18ef2-107">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="18ef2-108">但是，如果创建新方法会造成多余开销，C# 允许你实例化委托并立即指定调用委托时委托将处理的代码块。</span><span class="sxs-lookup"><span data-stu-id="18ef2-108">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="18ef2-109">代码块可包含 Lambda 表达式或匿名方法。</span><span class="sxs-lookup"><span data-stu-id="18ef2-109">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="18ef2-110">有关详细信息，请参阅[匿名函数](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="18ef2-110">For more information, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18ef2-111">备注</span><span class="sxs-lookup"><span data-stu-id="18ef2-111">Remarks</span></span>  
 <span data-ttu-id="18ef2-112">作为委托参数传递的方法必须具有与委托声明相同的签名。</span><span class="sxs-lookup"><span data-stu-id="18ef2-112">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="18ef2-113">委托实例可以封装静态方法或实例方法。</span><span class="sxs-lookup"><span data-stu-id="18ef2-113">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="18ef2-114">尽管委托可以使用 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 参数，但不建议将该委托与多播事件委托配合使用，因为你无法知道将调用哪个委托。</span><span class="sxs-lookup"><span data-stu-id="18ef2-114">Although the delegate can use an [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="18ef2-115">示例 1</span><span class="sxs-lookup"><span data-stu-id="18ef2-115">Example 1</span></span>  
 <span data-ttu-id="18ef2-116">以下是声明和使用委托的简单示例。</span><span class="sxs-lookup"><span data-stu-id="18ef2-116">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="18ef2-117">请注意，委托 `Del` 与关联的方法 `MultiplyNumbers` 具有相同的签名</span><span class="sxs-lookup"><span data-stu-id="18ef2-117">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 [!code-csharp[csProgGuideDelegates#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#2)]  
  
## <a name="example-2"></a><span data-ttu-id="18ef2-118">示例 2</span><span class="sxs-lookup"><span data-stu-id="18ef2-118">Example 2</span></span>  
 <span data-ttu-id="18ef2-119">在下面的示例中，一个委托映射到静态方法和实例方法，并返回来自两种方法的具体信息。</span><span class="sxs-lookup"><span data-stu-id="18ef2-119">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="18ef2-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="18ef2-120">See also</span></span>

- [<span data-ttu-id="18ef2-121">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="18ef2-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="18ef2-122">委托</span><span class="sxs-lookup"><span data-stu-id="18ef2-122">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="18ef2-123">匿名方法</span><span class="sxs-lookup"><span data-stu-id="18ef2-123">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
- [<span data-ttu-id="18ef2-124">如何：合并委托（多播委托）</span><span class="sxs-lookup"><span data-stu-id="18ef2-124">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)
- [<span data-ttu-id="18ef2-125">事件</span><span class="sxs-lookup"><span data-stu-id="18ef2-125">Events</span></span>](../../../csharp/programming-guide/events/index.md)
