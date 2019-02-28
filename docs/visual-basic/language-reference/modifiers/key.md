---
title: Key (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 0f4778b69963c7b0df14308b3cb6312555647b92
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967771"
---
# <a name="key-visual-basic"></a><span data-ttu-id="677e2-102">Key (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="677e2-102">Key (Visual Basic)</span></span>
<span data-ttu-id="677e2-103">`Key`关键字，可以指定属性的匿名类型的行为。</span><span class="sxs-lookup"><span data-stu-id="677e2-103">The `Key` keyword enables you to specify behavior for properties of anonymous types.</span></span> <span data-ttu-id="677e2-104">只有属性指定为键属性的匿名类型实例或计算的哈希代码值之间的相等性测试中。</span><span class="sxs-lookup"><span data-stu-id="677e2-104">Only properties you designate as key properties participate in tests of equality between anonymous type instances, or calculation of hash code values.</span></span> <span data-ttu-id="677e2-105">不能更改键属性的值。</span><span class="sxs-lookup"><span data-stu-id="677e2-105">The values of key properties cannot be changed.</span></span>  
  
 <span data-ttu-id="677e2-106">将匿名类型的属性为键属性指定放置关键字`Key`其声明的初始化列表中的前面。</span><span class="sxs-lookup"><span data-stu-id="677e2-106">You designate a property of an anonymous type as a key property by placing the keyword `Key` in front of its declaration in the initialization list.</span></span> <span data-ttu-id="677e2-107">在以下示例中，`Airline`并`FlightNo`是键属性，但`Gate`不是。</span><span class="sxs-lookup"><span data-stu-id="677e2-107">In the following example, `Airline` and `FlightNo` are key properties, but `Gate` is not.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 <span data-ttu-id="677e2-108">创建新的匿名类型时，它直接继承自<xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="677e2-108">When a new anonymous type is created, it inherits directly from <xref:System.Object>.</span></span> <span data-ttu-id="677e2-109">编译器重写继承的三个成员： <xref:System.Object.Equals%2A>， <xref:System.Object.GetHashCode%2A>，和<xref:System.Object.ToString%2A>。</span><span class="sxs-lookup"><span data-stu-id="677e2-109">The compiler overrides three inherited members: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="677e2-110">为生成的重写代码<xref:System.Object.Equals%2A>和<xref:System.Object.GetHashCode%2A>基于键属性。</span><span class="sxs-lookup"><span data-stu-id="677e2-110">The override code that is produced for <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> is based on key properties.</span></span> <span data-ttu-id="677e2-111">如果在类型中，没有键属性<xref:System.Object.GetHashCode%2A>和<xref:System.Object.Equals%2A>未重写。</span><span class="sxs-lookup"><span data-stu-id="677e2-111">If there are no key properties in the type, <xref:System.Object.GetHashCode%2A> and <xref:System.Object.Equals%2A> are not overridden.</span></span>  
  
## <a name="equality"></a><span data-ttu-id="677e2-112">相等</span><span class="sxs-lookup"><span data-stu-id="677e2-112">Equality</span></span>  
 <span data-ttu-id="677e2-113">匿名类型的两个实例相等，如果它们是相同类型的实例，其键属性的值是否相等。</span><span class="sxs-lookup"><span data-stu-id="677e2-113">Two anonymous type instances are equal if they are instances of the same type and if the values of their key properties are equal.</span></span> <span data-ttu-id="677e2-114">在以下示例中，`flight2`等同于`flight1`上一示例中因为它们是实例的同一匿名类型，它们有匹配的值的它们的键属性。</span><span class="sxs-lookup"><span data-stu-id="677e2-114">In the following examples, `flight2` is equal to `flight1` from the previous example because they are instances of the same anonymous type and they have matching values for their key properties.</span></span> <span data-ttu-id="677e2-115">但是，`flight3`不等于`flight1`因为它具有不同的值的键属性， `FlightNo`。</span><span class="sxs-lookup"><span data-stu-id="677e2-115">However, `flight3` is not equal to `flight1` because it has a different value for a key property, `FlightNo`.</span></span> <span data-ttu-id="677e2-116">实例`flight4`不是相同的类型`flight1`因为它们将不同的属性指定为键属性。</span><span class="sxs-lookup"><span data-stu-id="677e2-116">Instance `flight4` is not the same type as `flight1` because they designate different properties as key properties.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 <span data-ttu-id="677e2-117">如果两个实例声明仅具有非键属性，名称、 类型、 顺序和值，在相同的两个实例不相等。</span><span class="sxs-lookup"><span data-stu-id="677e2-117">If two instances are declared with only non-key properties, identical in name, type, order, and value, the two instances are not equal.</span></span> <span data-ttu-id="677e2-118">实例键属性不是只等于其自身。</span><span class="sxs-lookup"><span data-stu-id="677e2-118">An instance without key properties is equal only to itself.</span></span>  
  
 <span data-ttu-id="677e2-119">有关在其下两个匿名类型实例是同一匿名类型的实例的条件的详细信息，请参阅[匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="677e2-119">For more information about the conditions under which two anonymous type instances are instances of the same anonymous type, see [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="hash-code-calculation"></a><span data-ttu-id="677e2-120">哈希代码计算</span><span class="sxs-lookup"><span data-stu-id="677e2-120">Hash Code Calculation</span></span>  
 <span data-ttu-id="677e2-121">像<xref:System.Object.Equals%2A>，在中定义的哈希函数<xref:System.Object.GetHashCode%2A>匿名类型根据类型的键属性。</span><span class="sxs-lookup"><span data-stu-id="677e2-121">Like <xref:System.Object.Equals%2A>, the hash function that is defined in <xref:System.Object.GetHashCode%2A> for an anonymous type is based on the key properties of the type.</span></span> <span data-ttu-id="677e2-122">下面的示例显示键属性和哈希之间的交互的代码值。</span><span class="sxs-lookup"><span data-stu-id="677e2-122">The following examples show the interaction between key properties and hash code values.</span></span>  
  
 <span data-ttu-id="677e2-123">具有相同的值的所有键属性的匿名类型的实例具有相同的哈希代码值，即使非键属性没有匹配的值。</span><span class="sxs-lookup"><span data-stu-id="677e2-123">Instances of an anonymous type that have the same values for all key properties have the same hash code value, even if non-key properties do not have matching values.</span></span> <span data-ttu-id="677e2-124">下面的语句返回`True`。</span><span class="sxs-lookup"><span data-stu-id="677e2-124">The following statement returns `True`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 <span data-ttu-id="677e2-125">具有不同的一个或多个键属性的值的匿名类型的实例具有不同的哈希代码值。</span><span class="sxs-lookup"><span data-stu-id="677e2-125">Instances of an anonymous type that have different values for one or more key properties have different hash code values.</span></span> <span data-ttu-id="677e2-126">下面的语句返回`False`。</span><span class="sxs-lookup"><span data-stu-id="677e2-126">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 <span data-ttu-id="677e2-127">将不同的属性指定为键属性的匿名类型的实例不是同一类型的实例。</span><span class="sxs-lookup"><span data-stu-id="677e2-127">Instances of anonymous types that designate different properties as key properties are not instances of the same type.</span></span> <span data-ttu-id="677e2-128">即使名称和所有属性的值是相同的它们具有不同的哈希代码值。</span><span class="sxs-lookup"><span data-stu-id="677e2-128">They have different hash code values even when the names and values of all properties are the same.</span></span> <span data-ttu-id="677e2-129">下面的语句返回`False`。</span><span class="sxs-lookup"><span data-stu-id="677e2-129">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a><span data-ttu-id="677e2-130">只读的值</span><span class="sxs-lookup"><span data-stu-id="677e2-130">Read-Only Values</span></span>  
 <span data-ttu-id="677e2-131">不能更改键属性的值。</span><span class="sxs-lookup"><span data-stu-id="677e2-131">The values of key properties cannot be changed.</span></span> <span data-ttu-id="677e2-132">例如，在`flight1`前面的示例中，`Airline`并`FlightNo`字段是只读的但`Gate`可以更改。</span><span class="sxs-lookup"><span data-stu-id="677e2-132">For example, in `flight1` in the earlier examples, the `Airline` and `FlightNo` fields are read-only, but `Gate` can be changed.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="677e2-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="677e2-133">See also</span></span>
- [<span data-ttu-id="677e2-134">匿名类型定义</span><span class="sxs-lookup"><span data-stu-id="677e2-134">Anonymous Type Definition</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [<span data-ttu-id="677e2-135">如何：推断属性名和匿名类型声明中的类型</span><span class="sxs-lookup"><span data-stu-id="677e2-135">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [<span data-ttu-id="677e2-136">匿名类型</span><span class="sxs-lookup"><span data-stu-id="677e2-136">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
