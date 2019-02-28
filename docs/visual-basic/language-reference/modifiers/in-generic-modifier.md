---
title: In（泛型修饰符）(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: 91a0b9c1188820f8fc466ce1bb123b704fcd94b7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972504"
---
# <a name="in-generic-modifier-visual-basic"></a><span data-ttu-id="a449b-102">In（泛型修饰符）(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a449b-102">In (Generic Modifier) (Visual Basic)</span></span>
<span data-ttu-id="a449b-103">对于泛型类型参数，`In` 关键字可指定类型参数是逆变的。</span><span class="sxs-lookup"><span data-stu-id="a449b-103">For generic type parameters, the `In` keyword specifies that the type parameter is contravariant.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a449b-104">备注</span><span class="sxs-lookup"><span data-stu-id="a449b-104">Remarks</span></span>  
 <span data-ttu-id="a449b-105">逆变使你使用的类型可以比泛型参数指定的类型派生程度更小。</span><span class="sxs-lookup"><span data-stu-id="a449b-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="a449b-106">这样可以隐式转换实现变体接口的类以及隐式转换委托类型。</span><span class="sxs-lookup"><span data-stu-id="a449b-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>  
  
 <span data-ttu-id="a449b-107">有关详细信息，请参阅[协变和逆变](../../programming-guide/concepts/covariance-contravariance/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a449b-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a449b-108">规则</span><span class="sxs-lookup"><span data-stu-id="a449b-108">Rules</span></span>  
 <span data-ttu-id="a449b-109">可以在泛型接口和委托中使用 `In` 关键字。</span><span class="sxs-lookup"><span data-stu-id="a449b-109">You can use the `In` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="a449b-110">类型参数可以声明为逆变在泛型接口或委托中的如果它是仅用作方法参数的类型，不用作方法返回类型。</span><span class="sxs-lookup"><span data-stu-id="a449b-110">A type parameter can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="a449b-111">`ByRef` 参数不能为协变或逆变。</span><span class="sxs-lookup"><span data-stu-id="a449b-111">`ByRef` parameters cannot be covariant or contravariant.</span></span>  
  
 <span data-ttu-id="a449b-112">协变和逆变是引用类型支持和不支持值类型。</span><span class="sxs-lookup"><span data-stu-id="a449b-112">Covariance and contravariance are supported for reference types and not supported for value types.</span></span>  
  
 <span data-ttu-id="a449b-113">在 Visual Basic 中，不能声明逆变接口中的事件，而不指定委托类型。</span><span class="sxs-lookup"><span data-stu-id="a449b-113">In Visual Basic, you cannot declare events in contravariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="a449b-114">此外，不能包含嵌套逆变接口，类、 枚举或结构，但它们可以嵌套接口。</span><span class="sxs-lookup"><span data-stu-id="a449b-114">Also, contravariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="a449b-115">行为</span><span class="sxs-lookup"><span data-stu-id="a449b-115">Behavior</span></span>  
 <span data-ttu-id="a449b-116">具有逆变类型参数的接口使其方法接受的参数的类型可以比接口类型参数指定的类型派生程度更小。</span><span class="sxs-lookup"><span data-stu-id="a449b-116">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="a449b-117">例如，因为在 .NET Framework 4 的 <xref:System.Collections.Generic.IComparer%601> 接口中，类型 T 是逆变的，所以可以将 `IComparer(Of Person)` 类型的对象分配给 `IComparer(Of Employee)` 类型的对象，而无需使用任何特殊转换方法（如果 `Person` 继承 `Employee`）。</span><span class="sxs-lookup"><span data-stu-id="a449b-117">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Person` inherits `Employee`.</span></span>  
  
 <span data-ttu-id="a449b-118">可以向逆变委托分配相同类型的其他委托，不过要使用派生程度更小的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="a449b-118">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a449b-119">示例</span><span class="sxs-lookup"><span data-stu-id="a449b-119">Example</span></span>  
 <span data-ttu-id="a449b-120">下面的示例演示如何声明、扩展和实现逆变泛型接口。</span><span class="sxs-lookup"><span data-stu-id="a449b-120">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="a449b-121">它还演示如何对实现此接口的类使用隐式转换。</span><span class="sxs-lookup"><span data-stu-id="a449b-121">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>  
  
 [!code-vb[vbVarianceKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="a449b-122">示例</span><span class="sxs-lookup"><span data-stu-id="a449b-122">Example</span></span>  
 <span data-ttu-id="a449b-123">以下示例演示如何声明、实例化和调用逆变泛型委托。</span><span class="sxs-lookup"><span data-stu-id="a449b-123">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="a449b-124">它还演示如何隐式转换委托类型。</span><span class="sxs-lookup"><span data-stu-id="a449b-124">It also shows how you can implicitly convert a delegate type.</span></span>  
  
 [!code-vb[vbVarianceKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a449b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="a449b-125">See also</span></span>
- [<span data-ttu-id="a449b-126">泛型接口中的变体</span><span class="sxs-lookup"><span data-stu-id="a449b-126">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="a449b-127">Out</span><span class="sxs-lookup"><span data-stu-id="a449b-127">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
