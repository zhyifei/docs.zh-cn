---
title: "如何：为类型定义值相等性（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- overriding Equals method [C#]
- object equivalence [C#]
- Equals method [C#] , overriding
- value equality [C#]
- equivalence [C#]
ms.assetid: 4084581e-b931-498b-9534-cf7ef5b68690
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e008be022765ff7d2bb440f0a37193b882038b76
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-define-value-equality-for-a-type-c-programming-guide"></a><span data-ttu-id="557b5-102">如何：为类型定义值相等性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="557b5-102">How to: Define Value Equality for a Type (C# Programming Guide)</span></span>
<span data-ttu-id="557b5-103">定义类或结构时，需确定为类型创建值相等性（或等效性）的自定义定义是否有意义。</span><span class="sxs-lookup"><span data-stu-id="557b5-103">When you define a class or struct, you decide whether it makes sense to create a custom definition of value equality (or equivalence) for the type.</span></span> <span data-ttu-id="557b5-104">通常，类型的对象预期要添加到某类集合时，或者这些对象主要用于存储一组字段或属性时，需实现值相等性。</span><span class="sxs-lookup"><span data-stu-id="557b5-104">Typically, you implement value equality when objects of the type are expected to be added to a collection of some sort, or when their primary purpose is to store a set of fields or properties.</span></span> <span data-ttu-id="557b5-105">可以基于类型中所有字段和属性的比较结果来定义值相等性，也可以基于子集进行定义。</span><span class="sxs-lookup"><span data-stu-id="557b5-105">You can base your definition of value equality on a comparison of all the fields and properties in the type, or you can base the definition on a subset.</span></span> <span data-ttu-id="557b5-106">但在任何一种情况下，类和结构中的实现均应遵循 5 个等效性保证条件：</span><span class="sxs-lookup"><span data-stu-id="557b5-106">But in either case, and in both classes and structs, your implementation should follow the five guarantees of equivalence:</span></span>  
  
1.  <span data-ttu-id="557b5-107">x.`Equals`(x) 返回 `true.`。这称为自反属性。</span><span class="sxs-lookup"><span data-stu-id="557b5-107">x.`Equals`(x) returns `true.` This is called the reflexive property.</span></span>  
  
2.  <span data-ttu-id="557b5-108">x.`Equals`(y) 返回与 y.`Equals`(x) 相同的值。</span><span class="sxs-lookup"><span data-stu-id="557b5-108">x.`Equals`(y) returns the same value as y.`Equals`(x).</span></span> <span data-ttu-id="557b5-109">这称为对称属性。</span><span class="sxs-lookup"><span data-stu-id="557b5-109">This is called the symmetric property.</span></span>  
  
3.  <span data-ttu-id="557b5-110">如果 (x.`Equals`(y) && y.`Equals`(z)) 返回 `true`，则 x.`Equals`(z) 返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="557b5-110">if (x.`Equals`(y) && y.`Equals`(z)) returns `true`, then x.`Equals`(z) returns `true`.</span></span> <span data-ttu-id="557b5-111">这称为可传递属性。</span><span class="sxs-lookup"><span data-stu-id="557b5-111">This is called the transitive property.</span></span>  
  
4.  <span data-ttu-id="557b5-112">只要不修改 x 和 y 引用的对象，x.`Equals`(y) 的后续调用就会返回相同的值。</span><span class="sxs-lookup"><span data-stu-id="557b5-112">Successive invocations of x.`Equals`(y) return the same value as long as the objects referenced by x and y are not modified.</span></span>  
  
5.  <span data-ttu-id="557b5-113">x.`Equals`(null) 返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="557b5-113">x.`Equals`(null) returns `false`.</span></span> <span data-ttu-id="557b5-114">但是，null.Equals(null) 会引发异常；它未遵循上面的第 2 条规则。</span><span class="sxs-lookup"><span data-stu-id="557b5-114">However, null.Equals(null) throws an exception; it does not obey rule number two above.</span></span>  
  
 <span data-ttu-id="557b5-115">定义的任何结构都已具有其从 <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> 方法的 <xref:System.ValueType?displayProperty=fullName> 替代中继承的值相等性的默认实现。</span><span class="sxs-lookup"><span data-stu-id="557b5-115">Any struct that you define already has a default implementation of value equality that it inherits from the <xref:System.ValueType?displayProperty=fullName> override of the <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> method.</span></span> <span data-ttu-id="557b5-116">此实现使用反射来检查类型中的所有字段和属性。</span><span class="sxs-lookup"><span data-stu-id="557b5-116">This implementation uses reflection to examine all the fields and properties in the type.</span></span> <span data-ttu-id="557b5-117">尽管此实现可生成正确的结果，但与专门为类型编写的自定义实现相比，它的速度相对较慢。</span><span class="sxs-lookup"><span data-stu-id="557b5-117">Although this implementation produces correct results, it is relatively slow compared to a custom implementation that you write specifically for the type.</span></span>  
  
 <span data-ttu-id="557b5-118">类和结构的值相等性的实现详细信息有所不同。</span><span class="sxs-lookup"><span data-stu-id="557b5-118">The implementation details for value equality are different for classes and structs.</span></span> <span data-ttu-id="557b5-119">但是，类和结构都需要相同的基础步骤来实现相等性：</span><span class="sxs-lookup"><span data-stu-id="557b5-119">However, both classes and structs require the same basic steps for implementing equality:</span></span>  
  
1.  <span data-ttu-id="557b5-120">替代[虚拟](../../../csharp/language-reference/keywords/virtual.md) <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> 方法。</span><span class="sxs-lookup"><span data-stu-id="557b5-120">Override the [virtual](../../../csharp/language-reference/keywords/virtual.md) <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> method.</span></span> <span data-ttu-id="557b5-121">大多数情况下，`bool Equals( object obj )` 实现应只调入作为 <xref:System.IEquatable%601?displayProperty=fullName> 接口的实现的类型特定 `Equals` 方法。</span><span class="sxs-lookup"><span data-stu-id="557b5-121">In most cases, your implementation of `bool Equals( object obj )` should just call into the type-specific `Equals` method that is the implementation of the <xref:System.IEquatable%601?displayProperty=fullName> interface.</span></span> <span data-ttu-id="557b5-122">（请参阅步骤 2。）</span><span class="sxs-lookup"><span data-stu-id="557b5-122">(See step 2.)</span></span>  
  
2.  <span data-ttu-id="557b5-123">通过提供类型特定的 `Equals` 方法实现 <xref:System.IEquatable%601?displayProperty=fullName> 接口。</span><span class="sxs-lookup"><span data-stu-id="557b5-123">Implement the <xref:System.IEquatable%601?displayProperty=fullName> interface by providing a type-specific `Equals` method.</span></span> <span data-ttu-id="557b5-124">实际的等效性比较将在此接口中执行。</span><span class="sxs-lookup"><span data-stu-id="557b5-124">This is where the actual equivalence comparison is performed.</span></span> <span data-ttu-id="557b5-125">例如，可能决定通过仅比较类型中的一两个字段来定义相等性。</span><span class="sxs-lookup"><span data-stu-id="557b5-125">For example, you might decide to define equality by comparing only one or two fields in your type.</span></span> <span data-ttu-id="557b5-126">不会从 `Equals` 引发异常。</span><span class="sxs-lookup"><span data-stu-id="557b5-126">Do not throw exceptions from `Equals`.</span></span> <span data-ttu-id="557b5-127">仅适用于类：此方法应仅检查类中声明的字段。</span><span class="sxs-lookup"><span data-stu-id="557b5-127">For classes only: This method should examine only fields that are declared in the class.</span></span> <span data-ttu-id="557b5-128">它应调用 `base.Equals` 来检查基类中的字段。</span><span class="sxs-lookup"><span data-stu-id="557b5-128">It should call `base.Equals` to examine fields that are in the base class.</span></span> <span data-ttu-id="557b5-129">（如果类型直接从 <xref:System.Object> 中继承，则不要这样做，因为 <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> 的 <xref:System.Object> 实现会执行引用相等性检查。）</span><span class="sxs-lookup"><span data-stu-id="557b5-129">(Do not do this if the type inherits directly from <xref:System.Object>, because the <xref:System.Object> implementation of <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> performs a reference equality check.)</span></span>  
  
3.  <span data-ttu-id="557b5-130">可选，但建议这样做：重载 [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) 和 [!=](../../../csharp/language-reference/operators/not-equal-operator.md) 运算符。</span><span class="sxs-lookup"><span data-stu-id="557b5-130">Optional but recommended: Overload the [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) and [!=](../../../csharp/language-reference/operators/not-equal-operator.md) operators.</span></span>  
  
4.  <span data-ttu-id="557b5-131">替代 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>，以便具有值相等性的两个对象生成相同的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="557b5-131">Override <xref:System.Object.GetHashCode%2A?displayProperty=fullName> so that two objects that have value equality produce the same hash code.</span></span>  
  
5.  <span data-ttu-id="557b5-132">可选：若要支持“大于”或“小于”定义，请为类型实现 <xref:System.IComparable%601> 接口，并同时重载 [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) 和 [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) 运算符。</span><span class="sxs-lookup"><span data-stu-id="557b5-132">Optional: To support definitions for "greater than" or "less than," implement the <xref:System.IComparable%601> interface for your type, and also overload the [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) and [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) operators.</span></span>  
  
 <span data-ttu-id="557b5-133">下面的第 1 个示例演示了类实现。</span><span class="sxs-lookup"><span data-stu-id="557b5-133">The first example that follows shows a class implementation.</span></span> <span data-ttu-id="557b5-134">第 2 个示例演示了结构实现。</span><span class="sxs-lookup"><span data-stu-id="557b5-134">The second example shows a struct implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="557b5-135">示例</span><span class="sxs-lookup"><span data-stu-id="557b5-135">Example</span></span>  
 <span data-ttu-id="557b5-136">下面的示例演示如何在类（引用类型）中实现值相等性。</span><span class="sxs-lookup"><span data-stu-id="557b5-136">The following example shows how to implement value equality in a class (reference type).</span></span>  
  
 <span data-ttu-id="557b5-137">[!code-cs[csProgGuideStatements#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-value-equality-for-a-type_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="557b5-137">[!code-cs[csProgGuideStatements#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-value-equality-for-a-type_1.cs)]</span></span>  
  
 <span data-ttu-id="557b5-138">在类（引用类型）上，两种 <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> 方法的默认实现均执行引用相等性比较，而不是值相等性检查。</span><span class="sxs-lookup"><span data-stu-id="557b5-138">On classes (reference types), the default implementation of both <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> methods performs a reference equality comparison, not a value equality check.</span></span> <span data-ttu-id="557b5-139">实施者替代虚方法时，目的是为其指定值相等性语义。</span><span class="sxs-lookup"><span data-stu-id="557b5-139">When an implementer overrides the virtual method, the purpose is to give it value equality semantics.</span></span>  
  
 <span data-ttu-id="557b5-140">即使类不重载 `==` 和 `!=` 运算符，也可将这些运算符与类一起使用。</span><span class="sxs-lookup"><span data-stu-id="557b5-140">The `==` and `!=` operators can be used with classes even if the class does not overload them.</span></span> <span data-ttu-id="557b5-141">但是，默认行为是执行引用相等性检查。</span><span class="sxs-lookup"><span data-stu-id="557b5-141">However, the default behavior is to perform a reference equality check.</span></span> <span data-ttu-id="557b5-142">在类中，如果重载 `Equals` 方法，则应重载 `==` 和 `!=` 运算符，但这并不是必需的。</span><span class="sxs-lookup"><span data-stu-id="557b5-142">In a class, if you overload the `Equals` method, you should overload the `==` and `!=` operators, but it is not required.</span></span>  
  
## <a name="example"></a><span data-ttu-id="557b5-143">示例</span><span class="sxs-lookup"><span data-stu-id="557b5-143">Example</span></span>  
 <span data-ttu-id="557b5-144">下面的示例演示如何在结构（值类型）中实现值相等性：</span><span class="sxs-lookup"><span data-stu-id="557b5-144">The following example shows how to implement value equality in a struct (value type):</span></span>  
  
 <span data-ttu-id="557b5-145">[!code-cs[csProgGuideStatements#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-value-equality-for-a-type_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="557b5-145">[!code-cs[csProgGuideStatements#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-value-equality-for-a-type_2.cs)]</span></span>  
  
 <span data-ttu-id="557b5-146">对于结构，<xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>（<xref:System.ValueType?displayProperty=fullName> 中的替代版本）的默认实现通过使用反射来比较类型中每个字段的值，从而执行值相等性检查。</span><span class="sxs-lookup"><span data-stu-id="557b5-146">For structs, the default implementation of <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> (which is the overridden version in <xref:System.ValueType?displayProperty=fullName>) performs a value equality check by using reflection to compare the values of every field in the type.</span></span> <span data-ttu-id="557b5-147">实施者替代结构中的 `Equals` 虚方法时，目的是提供更高效的方法来执行值相等性检查，并选择根据结构字段或属性的某个子集来进行比较。</span><span class="sxs-lookup"><span data-stu-id="557b5-147">When an implementer overrides the virtual `Equals` method in a struct, the purpose is to provide a more efficient means of performing the value equality check and optionally to base the comparison on some subset of the struct's field or properties.</span></span>  
  
 <span data-ttu-id="557b5-148">除非结构显式重载了 [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) 和 [!=](../../../csharp/language-reference/operators/not-equal-operator.md) 运算符，否则这些运算符无法对结构进行运算。</span><span class="sxs-lookup"><span data-stu-id="557b5-148">The [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) and [!=](../../../csharp/language-reference/operators/not-equal-operator.md) operators cannot operate on a struct unless the struct explicitly overloads them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="557b5-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="557b5-149">See Also</span></span>  
 <span data-ttu-id="557b5-150">[相等比较](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md) </span><span class="sxs-lookup"><span data-stu-id="557b5-150">[Equality Comparisons](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md) </span></span>  
 [<span data-ttu-id="557b5-151">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="557b5-151">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

