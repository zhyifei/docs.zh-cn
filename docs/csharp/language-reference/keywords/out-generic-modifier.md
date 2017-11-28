---
title: "out（泛型修饰符）（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5c63fe2229d4b7190397d3ba98fa150c84a12fb2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="out-generic-modifier-c-reference"></a><span data-ttu-id="a98b9-102">out（泛型修饰符）（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a98b9-102">out (Generic Modifier) (C# Reference)</span></span>
<span data-ttu-id="a98b9-103">对于泛型类型参数，`out` 关键字可指定类型参数是协变的。</span><span class="sxs-lookup"><span data-stu-id="a98b9-103">For generic type parameters, the `out` keyword specifies that the type parameter is covariant.</span></span> <span data-ttu-id="a98b9-104">可以在泛型接口和委托中使用 `out` 关键字。</span><span class="sxs-lookup"><span data-stu-id="a98b9-104">You can use the `out` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="a98b9-105">协变使你使用的类型可以比泛型参数指定的类型派生程度更大。</span><span class="sxs-lookup"><span data-stu-id="a98b9-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="a98b9-106">这样可以隐式转换实现变体接口的类以及隐式转换委托类型。</span><span class="sxs-lookup"><span data-stu-id="a98b9-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="a98b9-107">引用类型支持协变和逆变，但值类型不支持它们。</span><span class="sxs-lookup"><span data-stu-id="a98b9-107">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="a98b9-108">具有协变类型参数的接口使其方法返回的类型可以比类型参数指定的类型派生程度更大。</span><span class="sxs-lookup"><span data-stu-id="a98b9-108">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="a98b9-109">例如，因为在 .NET Framework 4 的 <xref:System.Collections.Generic.IEnumerable%601> 中，类型 T 是协变的，所以可以将 `IEnumerabe(Of String)` 类型的对象分配给 `IEnumerable(Of Object)` 类型的对象，而无需使用任何特殊转换方法。</span><span class="sxs-lookup"><span data-stu-id="a98b9-109">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerabe(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>  
  
 <span data-ttu-id="a98b9-110">可以向协变委托分配相同类型的其他委托，不过要使用派生程度更大的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="a98b9-110">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>  
  
 <span data-ttu-id="a98b9-111">有关详细信息，请参阅[协变和逆变](../../programming-guide/concepts/covariance-contravariance/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a98b9-111">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a98b9-112">示例</span><span class="sxs-lookup"><span data-stu-id="a98b9-112">Example</span></span>  
 <span data-ttu-id="a98b9-113">下面的示例演示如何声明、扩展和实现协变泛型接口。</span><span class="sxs-lookup"><span data-stu-id="a98b9-113">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="a98b9-114">它还演示如何对实现协变接口的类使用隐式转换。</span><span class="sxs-lookup"><span data-stu-id="a98b9-114">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>  
  
 [!code-csharp[csVarianceKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_1.cs)]  
  
 <span data-ttu-id="a98b9-115">在泛型接口中，如果类型参数满足以下条件，则可以声明为协变：</span><span class="sxs-lookup"><span data-stu-id="a98b9-115">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>  
  
-   <span data-ttu-id="a98b9-116">类型参数只用作接口方法的返回类型，而不用作方法参数的类型。</span><span class="sxs-lookup"><span data-stu-id="a98b9-116">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a98b9-117">此规则有一个例外。</span><span class="sxs-lookup"><span data-stu-id="a98b9-117">There is one exception to this rule.</span></span> <span data-ttu-id="a98b9-118">如果在协变接口中将逆变泛型委托用作方法参数，则可以将协变类型用作此委托的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="a98b9-118">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="a98b9-119">有关协变和逆变泛型委托的详细信息，请参阅[委托中的变体](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)和[对 Func 和 Action 泛型委托使用变体](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="a98b9-119">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
-   <span data-ttu-id="a98b9-120">类型参数不用作接口方法的泛型约束。</span><span class="sxs-lookup"><span data-stu-id="a98b9-120">The type parameter is not used as a generic constraint for the interface methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a98b9-121">示例</span><span class="sxs-lookup"><span data-stu-id="a98b9-121">Example</span></span>  
 <span data-ttu-id="a98b9-122">以下示例演示如何声明、实例化和调用协变泛型委托。</span><span class="sxs-lookup"><span data-stu-id="a98b9-122">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="a98b9-123">它还演示如何隐式转换委托类型。</span><span class="sxs-lookup"><span data-stu-id="a98b9-123">It also shows how to implicitly convert delegate types.</span></span>  
  
 [!code-csharp[csVarianceKeywords#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_2.cs)]  
  
 <span data-ttu-id="a98b9-124">在泛型委托中，如果类型仅用作方法返回类型，而不用于方法参数，则可以声明为协变。</span><span class="sxs-lookup"><span data-stu-id="a98b9-124">In a generic delegate, a type can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a98b9-125">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="a98b9-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a98b9-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a98b9-126">See Also</span></span>  
 [<span data-ttu-id="a98b9-127">泛型接口中的变体</span><span class="sxs-lookup"><span data-stu-id="a98b9-127">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [<span data-ttu-id="a98b9-128">in</span><span class="sxs-lookup"><span data-stu-id="a98b9-128">in</span></span>](../../../csharp/language-reference/keywords/in-generic-modifier.md)  
 [<span data-ttu-id="a98b9-129">修饰符</span><span class="sxs-lookup"><span data-stu-id="a98b9-129">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
