---
title: "where（泛型类型约束）（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: 10
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
ms.openlocfilehash: 8e81640ee56ed672bb09242a070fdf167740874b
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="98615-102">where（泛型类型约束）（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="98615-102">where (generic type constraint) (C# Reference)</span></span>
<span data-ttu-id="98615-103">在泛型类型定义中，`where` 子句用于指定对下列类型的约束：这些类型可用作泛型声明中定义的类型形参的实参。</span><span class="sxs-lookup"><span data-stu-id="98615-103">In a generic type definition, the `where` clause is used to specify constraints on the types that can be used as arguments for a type parameter defined in a generic declaration.</span></span> <span data-ttu-id="98615-104">例如，可以声明一个泛型类 `MyGenericClass`，以使类型参数 `T` 实现 <xref:System.IComparable%601> 接口：</span><span class="sxs-lookup"><span data-stu-id="98615-104">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>  
  
```csharp  
public class MyGenericClass<T> where T:IComparable { }  
```  
  
> [!NOTE]
>  <span data-ttu-id="98615-105">有关查询表达式中的 where 子句的详细信息，请参阅 [where 子句](../../../csharp/language-reference/keywords/where-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="98615-105">For more information on the where clause in a query expression, see [where clause](../../../csharp/language-reference/keywords/where-clause.md).</span></span>  
  
 <span data-ttu-id="98615-106">除了接口约束，`where` 子句还可以包括基类约束，以指出某个类型必须将指定的类作为基类（或者就是该类本身），才能用作该泛型类型的类型参数。</span><span class="sxs-lookup"><span data-stu-id="98615-106">In addition to interface constraints, a `where` clause can include a base class constraint, which states that a type must have the specified class as a base class (or be that class itself) in order to be used as a type argument for that generic type.</span></span> <span data-ttu-id="98615-107">这样的约束一经使用，就必须出现在该类型参数的所有其他约束之前。</span><span class="sxs-lookup"><span data-stu-id="98615-107">If such a constraint is used, it must appear before any other constraints on that type parameter.</span></span>  
  
 <span data-ttu-id="98615-108">[!code-cs[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="98615-108">[!code-cs[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]</span></span>  
  
 <span data-ttu-id="98615-109">`where` 子句还可以包括构造函数约束。</span><span class="sxs-lookup"><span data-stu-id="98615-109">The `where` clause may also include a constructor constraint.</span></span> <span data-ttu-id="98615-110">可以使用 new 运算符创建类型参数的实例；但类型参数为此必须受构造函数约束 `new()` 的约束。</span><span class="sxs-lookup"><span data-stu-id="98615-110">It is possible to create an instance of a type parameter using the new operator; however, in order to do so the type parameter must be constrained by the constructor constraint, `new()`.</span></span> <span data-ttu-id="98615-111">[new() 约束](../../../csharp/language-reference/keywords/new-constraint.md)可以让编译器知道：提供的任何类型参数都必须具有可访问的无参数（或默认）构造函数。</span><span class="sxs-lookup"><span data-stu-id="98615-111">The [new() Constraint](../../../csharp/language-reference/keywords/new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless--or default-- constructor.</span></span> <span data-ttu-id="98615-112">例如: </span><span class="sxs-lookup"><span data-stu-id="98615-112">For example:</span></span>  
  
 <span data-ttu-id="98615-113">[!code-cs[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="98615-113">[!code-cs[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]</span></span>  
  
 <span data-ttu-id="98615-114">`new()` 约束出现在 `where` 子句的最后。</span><span class="sxs-lookup"><span data-stu-id="98615-114">The `new()` constraint appears last in the `where` clause.</span></span>  
  
 <span data-ttu-id="98615-115">对于多个类型参数，每个类型参数都使用一个 `where` 子句，例如：</span><span class="sxs-lookup"><span data-stu-id="98615-115">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>  
  
 <span data-ttu-id="98615-116">[!code-cs[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="98615-116">[!code-cs[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]</span></span>  
  
 <span data-ttu-id="98615-117">还可以将约束附加到泛型方法的类型参数，例如：</span><span class="sxs-lookup"><span data-stu-id="98615-117">You can also attach constraints to type parameters of generic methods, like this:</span></span>  
  
```csharp  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 <span data-ttu-id="98615-118">请注意，对于委托和方法两者来说，描述类型参数约束的语法是一样的：</span><span class="sxs-lookup"><span data-stu-id="98615-118">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>  
  
```csharp  
delegate T MyDelegate<T>() where T : new()  
```  
  
 <span data-ttu-id="98615-119">有关泛型委托的信息，请参阅[泛型委托](../../../csharp/programming-guide/generics/generic-delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="98615-119">For information on generic delegates, see [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
 <span data-ttu-id="98615-120">有关约束的语法和用法的详细信息，请参阅[类型参数的约束](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="98615-120">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="98615-121">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="98615-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="98615-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="98615-122">See Also</span></span>  
 <span data-ttu-id="98615-123">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="98615-123">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="98615-124">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="98615-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="98615-125">[泛型简介](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="98615-125">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="98615-126">[new 约束](../../../csharp/language-reference/keywords/new-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="98615-126">[new Constraint](../../../csharp/language-reference/keywords/new-constraint.md) </span></span>  
 [<span data-ttu-id="98615-127">类型参数的约束</span><span class="sxs-lookup"><span data-stu-id="98615-127">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)

