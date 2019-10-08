---
title: In （泛型修饰符）-Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: 9c0f7d454767112e1e309af81407b5fdef22eee9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004873"
---
# <a name="in-generic-modifier-visual-basic"></a><span data-ttu-id="f7293-102">In（泛型修饰符）(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7293-102">In (Generic Modifier) (Visual Basic)</span></span>

<span data-ttu-id="f7293-103">对于泛型类型参数，`In` 关键字可指定类型参数是逆变的。</span><span class="sxs-lookup"><span data-stu-id="f7293-103">For generic type parameters, the `In` keyword specifies that the type parameter is contravariant.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7293-104">备注</span><span class="sxs-lookup"><span data-stu-id="f7293-104">Remarks</span></span>

<span data-ttu-id="f7293-105">逆变使你使用的类型可以比泛型参数指定的类型派生程度更小。</span><span class="sxs-lookup"><span data-stu-id="f7293-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="f7293-106">这样可以隐式转换实现变体接口的类以及隐式转换委托类型。</span><span class="sxs-lookup"><span data-stu-id="f7293-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>

<span data-ttu-id="f7293-107">有关详细信息，请参阅[协变和逆变](../../programming-guide/concepts/covariance-contravariance/index.md)。</span><span class="sxs-lookup"><span data-stu-id="f7293-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="f7293-108">规则</span><span class="sxs-lookup"><span data-stu-id="f7293-108">Rules</span></span>

<span data-ttu-id="f7293-109">可以在泛型接口和委托中使用 `In` 关键字。</span><span class="sxs-lookup"><span data-stu-id="f7293-109">You can use the `In` keyword in generic interfaces and delegates.</span></span>
  
<span data-ttu-id="f7293-110">如果类型参数仅用作方法参数的类型并且不用作方法返回类型，则可以在泛型接口或委托中声明为逆变。</span><span class="sxs-lookup"><span data-stu-id="f7293-110">A type parameter can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="f7293-111">@no__t 参数不能是协变或逆变。</span><span class="sxs-lookup"><span data-stu-id="f7293-111">`ByRef` parameters cannot be covariant or contravariant.</span></span>

<span data-ttu-id="f7293-112">引用类型支持协变和逆变，但值类型不支持协变和逆变。</span><span class="sxs-lookup"><span data-stu-id="f7293-112">Covariance and contravariance are supported for reference types and not supported for value types.</span></span>

<span data-ttu-id="f7293-113">在 Visual Basic 中，不能声明逆变接口中的事件，而无需指定委托类型。</span><span class="sxs-lookup"><span data-stu-id="f7293-113">In Visual Basic, you cannot declare events in contravariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="f7293-114">此外，逆变接口不能有嵌套的类、枚举或结构，但它们可以有嵌套的接口。</span><span class="sxs-lookup"><span data-stu-id="f7293-114">Also, contravariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>

## <a name="behavior"></a><span data-ttu-id="f7293-115">行为</span><span class="sxs-lookup"><span data-stu-id="f7293-115">Behavior</span></span>

<span data-ttu-id="f7293-116">具有逆变类型参数的接口使其方法接受的参数的类型可以比接口类型参数指定的类型派生程度更小。</span><span class="sxs-lookup"><span data-stu-id="f7293-116">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="f7293-117">例如，由于在 .NET Framework 4 中，在 @no__t 的接口中，类型 T 是逆变的，因此，如果 @no__t 从 @no__t 继承，则无需使用任何特殊转换方法，即可将 @no__t 类型的对象分配给 @no__t 2 类型的对象。</span><span class="sxs-lookup"><span data-stu-id="f7293-117">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Employee` inherits from `Person`.</span></span>

<span data-ttu-id="f7293-118">可以向逆变委托分配相同类型的其他委托，不过要使用派生程度更小的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="f7293-118">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>

## <a name="example---contravariant-generic-interface"></a><span data-ttu-id="f7293-119">示例-逆变泛型接口</span><span class="sxs-lookup"><span data-stu-id="f7293-119">Example - contravariant generic interface</span></span>

<span data-ttu-id="f7293-120">下面的示例演示如何声明、扩展和实现逆变泛型接口。</span><span class="sxs-lookup"><span data-stu-id="f7293-120">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="f7293-121">它还演示如何对实现此接口的类使用隐式转换。</span><span class="sxs-lookup"><span data-stu-id="f7293-121">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>

[!code-vb[vbVarianceKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#1)]

## <a name="example---contravariant-generic-delegate"></a><span data-ttu-id="f7293-122">示例-逆变泛型委托</span><span class="sxs-lookup"><span data-stu-id="f7293-122">Example - contravariant generic delegate</span></span>

<span data-ttu-id="f7293-123">以下示例演示如何声明、实例化和调用逆变泛型委托。</span><span class="sxs-lookup"><span data-stu-id="f7293-123">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="f7293-124">它还演示如何隐式转换委托类型。</span><span class="sxs-lookup"><span data-stu-id="f7293-124">It also shows how you can implicitly convert a delegate type.</span></span>

[!code-vb[vbVarianceKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="f7293-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7293-125">See also</span></span>

- [<span data-ttu-id="f7293-126">泛型接口中的变体</span><span class="sxs-lookup"><span data-stu-id="f7293-126">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="f7293-127">Out</span><span class="sxs-lookup"><span data-stu-id="f7293-127">Out</span></span>](out-generic-modifier.md)
