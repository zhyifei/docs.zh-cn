---
title: Out（泛型修饰符）(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceOut
helpviewer_keywords:
- Out keyword [Visual Basic]
- covariance, Out keyword [Visual Basic]
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
ms.openlocfilehash: 367cbd373df2a38a56e5362f66bedd5c0ec24efb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522749"
---
# <a name="out-generic-modifier-visual-basic"></a><span data-ttu-id="af53b-102">Out（泛型修饰符）(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af53b-102">Out (Generic Modifier) (Visual Basic)</span></span>
<span data-ttu-id="af53b-103">对于泛型类型参数，`Out`关键字指定的类型是协变。</span><span class="sxs-lookup"><span data-stu-id="af53b-103">For generic type parameters, the `Out` keyword specifies that the type is covariant.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af53b-104">备注</span><span class="sxs-lookup"><span data-stu-id="af53b-104">Remarks</span></span>  
 <span data-ttu-id="af53b-105">协变使你使用的类型可以比泛型参数指定的类型派生程度更大。</span><span class="sxs-lookup"><span data-stu-id="af53b-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="af53b-106">这样可以隐式转换实现变体接口的类以及隐式转换委托类型。</span><span class="sxs-lookup"><span data-stu-id="af53b-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>  
  
 <span data-ttu-id="af53b-107">有关详细信息，请参阅[协变和逆变](../../programming-guide/concepts/covariance-contravariance/index.md)。</span><span class="sxs-lookup"><span data-stu-id="af53b-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="af53b-108">规则</span><span class="sxs-lookup"><span data-stu-id="af53b-108">Rules</span></span>  
 <span data-ttu-id="af53b-109">可以在泛型接口和委托中使用 `Out` 关键字。</span><span class="sxs-lookup"><span data-stu-id="af53b-109">You can use the `Out` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="af53b-110">在泛型接口中，如果类型参数满足以下条件，则可以声明为协变：</span><span class="sxs-lookup"><span data-stu-id="af53b-110">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>  
  
-   <span data-ttu-id="af53b-111">类型参数只用作接口方法的返回类型，而不用作方法参数的类型。</span><span class="sxs-lookup"><span data-stu-id="af53b-111">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="af53b-112">此规则有一个例外。</span><span class="sxs-lookup"><span data-stu-id="af53b-112">There is one exception to this rule.</span></span> <span data-ttu-id="af53b-113">如果在协变接口中将逆变泛型委托用作方法参数，则可以将协变类型用作此委托的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="af53b-113">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="af53b-114">有关协变和逆变泛型委托的详细信息，请参阅[委托中的变体](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)和[对 Func 和 Action 泛型委托使用变体](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="af53b-114">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
-   <span data-ttu-id="af53b-115">类型参数不用作接口方法的泛型约束。</span><span class="sxs-lookup"><span data-stu-id="af53b-115">The type parameter is not used as a generic constraint for the interface methods.</span></span>  
  
 <span data-ttu-id="af53b-116">在泛型委托中，类型参数可以声明为协变如果它是仅用作方法返回类型，不用于方法参数。</span><span class="sxs-lookup"><span data-stu-id="af53b-116">In a generic delegate, a type parameter can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>  
  
 <span data-ttu-id="af53b-117">引用类型支持协变和逆变，但值类型不支持它们。</span><span class="sxs-lookup"><span data-stu-id="af53b-117">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="af53b-118">在 Visual Basic 中，不能声明协变接口中的事件，而不指定委托类型。</span><span class="sxs-lookup"><span data-stu-id="af53b-118">In Visual Basic, you cannot declare events in covariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="af53b-119">此外，协变接口不能包含嵌套类、 枚举或结构，但它们可以嵌套接口。</span><span class="sxs-lookup"><span data-stu-id="af53b-119">Also, covariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="af53b-120">行为</span><span class="sxs-lookup"><span data-stu-id="af53b-120">Behavior</span></span>  
 <span data-ttu-id="af53b-121">具有协变类型参数的接口使其方法返回的类型可以比类型参数指定的类型派生程度更大。</span><span class="sxs-lookup"><span data-stu-id="af53b-121">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="af53b-122">例如，因为在 .NET Framework 4 的 <xref:System.Collections.Generic.IEnumerable%601> 中，类型 T 是协变的，所以可以将 `IEnumerabe(Of String)` 类型的对象分配给 `IEnumerable(Of Object)` 类型的对象，而无需使用任何特殊转换方法。</span><span class="sxs-lookup"><span data-stu-id="af53b-122">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerabe(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>  
  
 <span data-ttu-id="af53b-123">可以向协变委托分配相同类型的其他委托，不过要使用派生程度更大的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="af53b-123">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af53b-124">示例</span><span class="sxs-lookup"><span data-stu-id="af53b-124">Example</span></span>  
 <span data-ttu-id="af53b-125">下面的示例演示如何声明、扩展和实现协变泛型接口。</span><span class="sxs-lookup"><span data-stu-id="af53b-125">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="af53b-126">它还演示如何对实现协变接口的类使用隐式转换。</span><span class="sxs-lookup"><span data-stu-id="af53b-126">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>  
  
 [!code-vb[vbVarianceKeywords#3](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="af53b-127">示例</span><span class="sxs-lookup"><span data-stu-id="af53b-127">Example</span></span>  
 <span data-ttu-id="af53b-128">以下示例演示如何声明、实例化和调用协变泛型委托。</span><span class="sxs-lookup"><span data-stu-id="af53b-128">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="af53b-129">它还显示如何使用隐式转换为委托类型。</span><span class="sxs-lookup"><span data-stu-id="af53b-129">It also shows how you can use implicit conversion for delegate types.</span></span>  
  
 [!code-vb[vbVarianceKeywords#4](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="af53b-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="af53b-130">See also</span></span>
- [<span data-ttu-id="af53b-131">泛型接口中的变体</span><span class="sxs-lookup"><span data-stu-id="af53b-131">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="af53b-132">In</span><span class="sxs-lookup"><span data-stu-id="af53b-132">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
