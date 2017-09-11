---
title: "相等比较（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- object equality [C#]
ms.assetid: 10b865ea-4e7b-4127-9242-c9b8f57d9f04
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 948bbc1b5b8535cc31ea362497fa69a816b43edc
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="equality-comparisons-c-programming-guide"></a><span data-ttu-id="a3f62-102">相等比较（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="a3f62-102">Equality Comparisons (C# Programming Guide)</span></span>
<span data-ttu-id="a3f62-103">有时需要比较两个值是否相等。</span><span class="sxs-lookup"><span data-stu-id="a3f62-103">It is sometimes necessary to compare two values for equality.</span></span> <span data-ttu-id="a3f62-104">在某些情况下，测试的是“值相等性”，也称为“等效性”，这意味着两个变量包含的值相等。</span><span class="sxs-lookup"><span data-stu-id="a3f62-104">In some cases, you are testing for *value equality*, also known as *equivalence*, which means that the values that are contained by the two variables are equal.</span></span> <span data-ttu-id="a3f62-105">在其他情况下，必须确定两个变量是否引用内存中的同一基础对象。</span><span class="sxs-lookup"><span data-stu-id="a3f62-105">In other cases, you have to determine whether two variables refer to the same underlying object in memory.</span></span> <span data-ttu-id="a3f62-106">此类型的相等性称为“引用相等性”或“标识”。</span><span class="sxs-lookup"><span data-stu-id="a3f62-106">This type of equality is called *reference equality*, or *identity*.</span></span> <span data-ttu-id="a3f62-107">本主题介绍这两种相等性，并提供指向其他主题的链接，供用户了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a3f62-107">This topic describes these two kinds of equality and provides links to other topics for more information.</span></span>  
  
## <a name="reference-equality"></a><span data-ttu-id="a3f62-108">引用相等性</span><span class="sxs-lookup"><span data-stu-id="a3f62-108">Reference Equality</span></span>  
 <span data-ttu-id="a3f62-109">引用相等性指两个对象引用均引用同一基础对象。</span><span class="sxs-lookup"><span data-stu-id="a3f62-109">Reference equality means that two object references refer to the same underlying object.</span></span> <span data-ttu-id="a3f62-110">这可以通过简单的赋值来实现，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a3f62-110">This can occur through simple assignment, as shown in the following example.</span></span>  
  
 <span data-ttu-id="a3f62-111">[!code-cs[csProgGuideStatements#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/equality-comparisons_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a3f62-111">[!code-cs[csProgGuideStatements#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/equality-comparisons_1.cs)]</span></span>  
  
 <span data-ttu-id="a3f62-112">在此代码中，创建了两个对象，但在赋值语句后，这两个引用所引用的是同一对象。</span><span class="sxs-lookup"><span data-stu-id="a3f62-112">In this code, two objects are created, but after the assignment statement, both references refer to the same object.</span></span> <span data-ttu-id="a3f62-113">因此，它们具有引用相等性。</span><span class="sxs-lookup"><span data-stu-id="a3f62-113">Therefore they have reference equality.</span></span> <span data-ttu-id="a3f62-114">使用 <xref:System.Object.ReferenceEquals%2A> 方法确定两个引用是否引用同一对象。</span><span class="sxs-lookup"><span data-stu-id="a3f62-114">Use the <xref:System.Object.ReferenceEquals%2A> method to determine whether two references refer to the same object.</span></span>  
  
 <span data-ttu-id="a3f62-115">引用相等性的概念仅适用于引用类型。</span><span class="sxs-lookup"><span data-stu-id="a3f62-115">The concept of reference equality applies only to reference types.</span></span> <span data-ttu-id="a3f62-116">由于在将值类型的实例赋给变量时将产生值的副本，因此值类型对象无法具有引用相等性。</span><span class="sxs-lookup"><span data-stu-id="a3f62-116">Value type objects cannot have reference equality because when an instance of a value type is assigned to a variable, a copy of the value is made.</span></span> <span data-ttu-id="a3f62-117">因此，永远不会有两个未装箱结构引用内存中的同一位置。</span><span class="sxs-lookup"><span data-stu-id="a3f62-117">Therefore you can never have two unboxed structs that refer to the same location in memory.</span></span> <span data-ttu-id="a3f62-118">此外，如果使用 <xref:System.Object.ReferenceEquals%2A> 比较两个值类型，结果将始终为 `false`，即使对象中包含的值都相同也是如此。</span><span class="sxs-lookup"><span data-stu-id="a3f62-118">Furthermore, if you use <xref:System.Object.ReferenceEquals%2A> to compare two value types, the result will always be `false`, even if the values that are contained in the objects are all identical.</span></span> <span data-ttu-id="a3f62-119">这是因为会将每个变量装箱到单独的对象实例中。</span><span class="sxs-lookup"><span data-stu-id="a3f62-119">This is because each variable is boxed into a separate object instance.</span></span> <span data-ttu-id="a3f62-120">有关详细信息，请参阅[如何：测试引用相等性（标识）](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="a3f62-120">For more information, see [How to: Test for Reference Equality (Identity)](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md).</span></span>  
  
## <a name="value-equality"></a><span data-ttu-id="a3f62-121">值相等性</span><span class="sxs-lookup"><span data-stu-id="a3f62-121">Value Equality</span></span>  
 <span data-ttu-id="a3f62-122">值相等性指两个对象包含相同的一个或多个值。</span><span class="sxs-lookup"><span data-stu-id="a3f62-122">Value equality means that two objects contain the same value or values.</span></span> <span data-ttu-id="a3f62-123">对于基元值类型（例如 [int](../../../csharp/language-reference/keywords/int.md) 或 [bool](../../../csharp/language-reference/keywords/bool.md)），针对值相等性的测试简单明了。</span><span class="sxs-lookup"><span data-stu-id="a3f62-123">For primitive value types such as [int](../../../csharp/language-reference/keywords/int.md) or [bool](../../../csharp/language-reference/keywords/bool.md), tests for value equality are straightforward.</span></span> <span data-ttu-id="a3f62-124">可以使用 [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) 运算符，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a3f62-124">You can use the [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) operator, as shown in the following example.</span></span>  
  
```csharp  
int a = GetOriginalValue();  
int b = GetCurrentValue();  
  
// Test for value equality.   
if( b == a)   
{  
    // The two integers are equal.  
}  
```  
  
 <span data-ttu-id="a3f62-125">对于大多数其他类型，针对值相等性的测试较为复杂，因为它需要用户了解类型对值相等性的定义方式。</span><span class="sxs-lookup"><span data-stu-id="a3f62-125">For most other types, testing for value equality is more complex because it requires that you understand how the type defines it.</span></span> <span data-ttu-id="a3f62-126">对于具有多个字段或属性的类和结构，值相等性的定义通常指所有字段或属性都具有相同的值。</span><span class="sxs-lookup"><span data-stu-id="a3f62-126">For classes and structs that have multiple fields or properties, value equality is often defined to mean that all fields or properties have the same value.</span></span> <span data-ttu-id="a3f62-127">例如，如果 pointA.X 等于 pointB.X，并且 pointA.Y 等于 pointB.Y，则可以将两个 `Point` 对象定义为相等。</span><span class="sxs-lookup"><span data-stu-id="a3f62-127">For example, two `Point` objects might be defined to be equivalent if pointA.X is equal to pointB.X and pointA.Y is equal to pointB.Y.</span></span>  
  
 <span data-ttu-id="a3f62-128">但是，并不要求类型中的所有字段均相等。</span><span class="sxs-lookup"><span data-stu-id="a3f62-128">However, there is no requirement that equivalence be based on all the fields in a type.</span></span> <span data-ttu-id="a3f62-129">只需子集相等即可。</span><span class="sxs-lookup"><span data-stu-id="a3f62-129">It can be based on a subset.</span></span> <span data-ttu-id="a3f62-130">比较不具所有权的类型时，应确保明确了解相等性对于该类型是如何定义的。</span><span class="sxs-lookup"><span data-stu-id="a3f62-130">When you compare types that you do not own, you should make sure to understand specifically how equivalence is defined for that type.</span></span> <span data-ttu-id="a3f62-131">若要详细了解如何在自己的类和结构中定义值相等性，请参阅[如何：为类型定义值相等性](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md)。</span><span class="sxs-lookup"><span data-stu-id="a3f62-131">For more information about how to define value equality in your own classes and structs, see [How to: Define Value Equality for a Type](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md).</span></span>  
  
### <a name="value-equality-for-floating-point-values"></a><span data-ttu-id="a3f62-132">浮点值的值相等性</span><span class="sxs-lookup"><span data-stu-id="a3f62-132">Value Equality for Floating Point Values</span></span>  
 <span data-ttu-id="a3f62-133">由于二进制计算机上的浮点算法不精确，因此浮点值（[double](../../../csharp/language-reference/keywords/double.md) 和 [float](../../../csharp/language-reference/keywords/float.md)）的相等比较会出现问题。</span><span class="sxs-lookup"><span data-stu-id="a3f62-133">Equality comparisons of floating point values ([double](../../../csharp/language-reference/keywords/double.md) and [float](../../../csharp/language-reference/keywords/float.md)) are problematic because of the imprecision of floating point arithmetic on binary computers.</span></span> <span data-ttu-id="a3f62-134">有关更多信息，请参阅 <xref:System.Double?displayProperty=fullName> 主题中的备注部分。</span><span class="sxs-lookup"><span data-stu-id="a3f62-134">For more information, see the remarks in the topic <xref:System.Double?displayProperty=fullName>.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="a3f62-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="a3f62-135">Related Topics</span></span>  
  
|<span data-ttu-id="a3f62-136">标题</span><span class="sxs-lookup"><span data-stu-id="a3f62-136">Title</span></span>|<span data-ttu-id="a3f62-137">描述</span><span class="sxs-lookup"><span data-stu-id="a3f62-137">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a3f62-138">如何：测试引用相等性（标识）</span><span class="sxs-lookup"><span data-stu-id="a3f62-138">How to: Test for Reference Equality (Identity)</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md)|<span data-ttu-id="a3f62-139">介绍如何确定两个变量是否具有引用相等性。</span><span class="sxs-lookup"><span data-stu-id="a3f62-139">Describes how to determine whether two variables have reference equality.</span></span>|  
|[<span data-ttu-id="a3f62-140">如何：为类型定义值相等性</span><span class="sxs-lookup"><span data-stu-id="a3f62-140">How to: Define Value Equality for a Type</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md)|<span data-ttu-id="a3f62-141">介绍如何为类型提供值相等性的自定义定义。</span><span class="sxs-lookup"><span data-stu-id="a3f62-141">Describes how to provide a custom definition of value equality for a type.</span></span>|  
|[<span data-ttu-id="a3f62-142">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a3f62-142">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)|<span data-ttu-id="a3f62-143">提供一些链接，这些链接指向重要 C# 语言功能以及通过 .NET Framework 提供给 C# 的功能的相关详细信息。</span><span class="sxs-lookup"><span data-stu-id="a3f62-143">Provides links to detailed information about important C# language features and features that are available to C# through the .NET Framework.</span></span>|  
|[<span data-ttu-id="a3f62-144">类型</span><span class="sxs-lookup"><span data-stu-id="a3f62-144">Types</span></span>](../../../csharp/programming-guide/types/index.md)|<span data-ttu-id="a3f62-145">提供有关 C# 类型系统的信息以及指向附加信息的链接。</span><span class="sxs-lookup"><span data-stu-id="a3f62-145">Provides information about the C# type system and links to additional information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3f62-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3f62-146">See Also</span></span>  
 [<span data-ttu-id="a3f62-147">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a3f62-147">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

