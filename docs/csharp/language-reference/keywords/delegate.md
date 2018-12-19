---
title: delegate - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
ms.openlocfilehash: 233b0255121cf6e7a5283041d594e2d843f105fb
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286463"
---
# <a name="delegate-c-reference"></a><span data-ttu-id="9adbb-102">委托（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="9adbb-102">delegate (C# Reference)</span></span>

<span data-ttu-id="9adbb-103">委托类型的声明与方法签名相似。</span><span class="sxs-lookup"><span data-stu-id="9adbb-103">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="9adbb-104">它有一个返回值和任意数目任意类型的参数：</span><span class="sxs-lookup"><span data-stu-id="9adbb-104">It has a return value and any number of parameters of any type:</span></span>

```csharp
public delegate void TestDelegate(string message);
public delegate int TestDelegate(MyType m, long num);
```

<span data-ttu-id="9adbb-105">`delegate` 是一种可用于封装命名方法或匿名方法的引用类型。</span><span class="sxs-lookup"><span data-stu-id="9adbb-105">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="9adbb-106">委托类似于 C++ 中的函数指针；但是，委托是类型安全和可靠的。</span><span class="sxs-lookup"><span data-stu-id="9adbb-106">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="9adbb-107">有关委托的应用，请参阅[委托](../../../csharp/programming-guide/delegates/index.md)和[泛型委托](../../../csharp/programming-guide/generics/generic-delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="9adbb-107">For applications of delegates, see [Delegates](../../../csharp/programming-guide/delegates/index.md) and [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="9adbb-108">备注</span><span class="sxs-lookup"><span data-stu-id="9adbb-108">Remarks</span></span>

<span data-ttu-id="9adbb-109">委托是[事件](../../../csharp/programming-guide/events/index.md)的基础。</span><span class="sxs-lookup"><span data-stu-id="9adbb-109">Delegates are the basis for [Events](../../../csharp/programming-guide/events/index.md).</span></span>

<span data-ttu-id="9adbb-110">通过将委托与命名方法或匿名方法关联，可以实例化委托。</span><span class="sxs-lookup"><span data-stu-id="9adbb-110">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span> <span data-ttu-id="9adbb-111">有关详细信息，请参阅[命名方法](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)和[匿名方法](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="9adbb-111">For more information, see [Named Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) and [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>

<span data-ttu-id="9adbb-112">必须使用具有兼容返回类型和输入参数的方法或 lambda 表达式实例化委托。</span><span class="sxs-lookup"><span data-stu-id="9adbb-112">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="9adbb-113">有关方法签名中允许的差异程度的详细信息，请参阅[委托中的变体](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="9adbb-113">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span> <span data-ttu-id="9adbb-114">为了与匿名方法一起使用，委托和与之关联的代码必须一起声明。</span><span class="sxs-lookup"><span data-stu-id="9adbb-114">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> <span data-ttu-id="9adbb-115">本节讨论这两种实例化委托的方法。</span><span class="sxs-lookup"><span data-stu-id="9adbb-115">Both ways of instantiating delegates are discussed in this section.</span></span>

## <a name="example"></a><span data-ttu-id="9adbb-116">示例</span><span class="sxs-lookup"><span data-stu-id="9adbb-116">Example</span></span>

[!code-csharp[csrefKeywordsTypes#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="9adbb-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="9adbb-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9adbb-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="9adbb-118">See also</span></span>

- [<span data-ttu-id="9adbb-119">C# 参考</span><span class="sxs-lookup"><span data-stu-id="9adbb-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="9adbb-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="9adbb-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="9adbb-121">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="9adbb-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="9adbb-122">引用类型</span><span class="sxs-lookup"><span data-stu-id="9adbb-122">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
- [<span data-ttu-id="9adbb-123">委托</span><span class="sxs-lookup"><span data-stu-id="9adbb-123">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
- [<span data-ttu-id="9adbb-124">事件</span><span class="sxs-lookup"><span data-stu-id="9adbb-124">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="9adbb-125">带有命名方法的委托与带有匿名方法的委托</span><span class="sxs-lookup"><span data-stu-id="9adbb-125">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) 
- [<span data-ttu-id="9adbb-126">匿名方法</span><span class="sxs-lookup"><span data-stu-id="9adbb-126">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
- [<span data-ttu-id="9adbb-127">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="9adbb-127">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
