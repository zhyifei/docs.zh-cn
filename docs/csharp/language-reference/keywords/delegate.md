---
title: 委托（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
ms.openlocfilehash: 4eafd0ffb6da191db80fd69f1980a167dbfc742b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172105"
---
# <a name="delegate-c-reference"></a><span data-ttu-id="5fb46-102">委托（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5fb46-102">delegate (C# Reference)</span></span>
<span data-ttu-id="5fb46-103">委托类型的声明与方法签名相似。</span><span class="sxs-lookup"><span data-stu-id="5fb46-103">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="5fb46-104">它有一个返回值和任意数目任意类型的参数：</span><span class="sxs-lookup"><span data-stu-id="5fb46-104">It has a return value and any number of parameters of any type:</span></span>  
  
```csharp  
public delegate void TestDelegate(string message);  
public delegate int TestDelegate(MyType m, long num);  
```  
  
 <span data-ttu-id="5fb46-105">`delegate` 是一种可用于封装命名方法或匿名方法的引用类型。</span><span class="sxs-lookup"><span data-stu-id="5fb46-105">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="5fb46-106">委托类似于 C++ 中的函数指针；但是，委托是类型安全和可靠的。</span><span class="sxs-lookup"><span data-stu-id="5fb46-106">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="5fb46-107">有关委托的应用，请参阅[委托](../../../csharp/programming-guide/delegates/index.md)和[泛型委托](../../../csharp/programming-guide/generics/generic-delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="5fb46-107">For applications of delegates, see [Delegates](../../../csharp/programming-guide/delegates/index.md) and [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fb46-108">备注</span><span class="sxs-lookup"><span data-stu-id="5fb46-108">Remarks</span></span>  
 <span data-ttu-id="5fb46-109">委托是[事件](../../../csharp/programming-guide/events/index.md)的基础。</span><span class="sxs-lookup"><span data-stu-id="5fb46-109">Delegates are the basis for [Events](../../../csharp/programming-guide/events/index.md).</span></span>  
  
 <span data-ttu-id="5fb46-110">通过将委托与命名方法或匿名方法关联，可以实例化委托。</span><span class="sxs-lookup"><span data-stu-id="5fb46-110">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span> <span data-ttu-id="5fb46-111">有关详细信息，请参阅[命名方法](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)和[匿名方法](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="5fb46-111">For more information, see [Named Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) and [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
 <span data-ttu-id="5fb46-112">必须使用具有兼容返回类型和输入参数的方法或 lambda 表达式实例化委托。</span><span class="sxs-lookup"><span data-stu-id="5fb46-112">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="5fb46-113">有关方法签名中允许的差异程度的详细信息，请参阅[委托中的变体](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="5fb46-113">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span> <span data-ttu-id="5fb46-114">为了与匿名方法一起使用，委托和与之关联的代码必须一起声明。</span><span class="sxs-lookup"><span data-stu-id="5fb46-114">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> <span data-ttu-id="5fb46-115">本节讨论这两种实例化委托的方法。</span><span class="sxs-lookup"><span data-stu-id="5fb46-115">Both ways of instantiating delegates are discussed in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fb46-116">示例</span><span class="sxs-lookup"><span data-stu-id="5fb46-116">Example</span></span>  
 [!code-csharp[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="5fb46-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5fb46-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5fb46-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fb46-118">See Also</span></span>  
 [<span data-ttu-id="5fb46-119">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5fb46-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5fb46-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5fb46-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5fb46-121">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="5fb46-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="5fb46-122">引用类型</span><span class="sxs-lookup"><span data-stu-id="5fb46-122">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="5fb46-123">委托</span><span class="sxs-lookup"><span data-stu-id="5fb46-123">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="5fb46-124">事件</span><span class="sxs-lookup"><span data-stu-id="5fb46-124">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="5fb46-125">带有命名方法的委托与带有匿名方法的委托</span><span class="sxs-lookup"><span data-stu-id="5fb46-125">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
 [<span data-ttu-id="5fb46-126">匿名方法</span><span class="sxs-lookup"><span data-stu-id="5fb46-126">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
