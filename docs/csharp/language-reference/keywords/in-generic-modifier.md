---
title: "in（泛型修饰符）（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2af4e27034af0067e81a52c81991edaf5a5415d8
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="37850-102">in（泛型修饰符）（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="37850-102">in (Generic Modifier) (C# Reference)</span></span>

<span data-ttu-id="37850-103">对于泛型类型参数，`in` 关键字可指定类型参数是逆变的。</span><span class="sxs-lookup"><span data-stu-id="37850-103">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="37850-104">可以在泛型接口和委托中使用 `in` 关键字。</span><span class="sxs-lookup"><span data-stu-id="37850-104">You can use the `in` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="37850-105">逆变使你使用的类型可以比泛型参数指定的类型派生程度更小。</span><span class="sxs-lookup"><span data-stu-id="37850-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="37850-106">这样可以隐式转换实现变体接口的类以及隐式转换委托类型。</span><span class="sxs-lookup"><span data-stu-id="37850-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="37850-107">引用类型支持泛型类型参数中的协变和逆变，但值类型不支持它们。</span><span class="sxs-lookup"><span data-stu-id="37850-107">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="37850-108">仅在类型定义方法参数的类型，而不是方法返回类型时，类型可以在泛型接口或委托中声明为逆变。</span><span class="sxs-lookup"><span data-stu-id="37850-108">A type can be declared contravariant in a generic interface or delegate only if it defines the type of a method's parameters and not of a method's return type.</span></span> <span data-ttu-id="37850-109">`In`、`ref` 和 `out` 参数必须是固定的，这意味着它们既不为协变又不为逆变。</span><span class="sxs-lookup"><span data-stu-id="37850-109">`In`, `ref`, and `out` parameters must be invariant, meaning they are neither covariant or contravariant.</span></span>
  
 <span data-ttu-id="37850-110">具有逆变类型参数的接口使其方法接受的参数的类型可以比接口类型参数指定的类型派生程度更小。</span><span class="sxs-lookup"><span data-stu-id="37850-110">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="37850-111">例如，在 <xref:System.Collections.Generic.IComparer%601> 接口中，类型 T 是逆变的，可以将 `IComparer<Person>` 类型的对象分配给 `IComparer<Employee>` 类型的对象，而无需使用任何特殊转换方法（如果 `Employee` 继承 `Person`）。</span><span class="sxs-lookup"><span data-stu-id="37850-111">For example, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer<Person>` type to an object of the `IComparer<Employee>` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>  
  
 <span data-ttu-id="37850-112">可以向逆变委托分配相同类型的其他委托，不过要使用派生程度更小的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="37850-112">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>  
  
 <span data-ttu-id="37850-113">有关详细信息，请参阅[协变和逆变](../../programming-guide/concepts/covariance-contravariance/index.md)。</span><span class="sxs-lookup"><span data-stu-id="37850-113">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="contravariant-generic-interface"></a><span data-ttu-id="37850-114">逆变泛型接口</span><span class="sxs-lookup"><span data-stu-id="37850-114">Contravariant generic interface</span></span>   

 <span data-ttu-id="37850-115">下面的示例演示如何声明、扩展和实现逆变泛型接口。</span><span class="sxs-lookup"><span data-stu-id="37850-115">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="37850-116">它还演示如何对实现此接口的类使用隐式转换。</span><span class="sxs-lookup"><span data-stu-id="37850-116">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>  
  
 [!code-csharp[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]  
  
## <a name="contravariant-generic-delegate"></a><span data-ttu-id="37850-117">逆变泛型委托</span><span class="sxs-lookup"><span data-stu-id="37850-117">Contravariant generic delegate</span></span>  

 <span data-ttu-id="37850-118">以下示例演示如何声明、实例化和调用逆变泛型委托。</span><span class="sxs-lookup"><span data-stu-id="37850-118">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="37850-119">它还演示如何隐式转换委托类型。</span><span class="sxs-lookup"><span data-stu-id="37850-119">It also shows how you can implicitly convert a delegate type.</span></span>  
  
 [!code-csharp[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="37850-120">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="37850-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="37850-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="37850-121">See Also</span></span>  
 [<span data-ttu-id="37850-122">out</span><span class="sxs-lookup"><span data-stu-id="37850-122">out</span></span>](../../../csharp/language-reference/keywords/out-generic-modifier.md)  
 [<span data-ttu-id="37850-123">协变和逆变</span><span class="sxs-lookup"><span data-stu-id="37850-123">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [<span data-ttu-id="37850-124">修饰符</span><span class="sxs-lookup"><span data-stu-id="37850-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
