---
title: where（泛型类型约束）（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f2b7b159689aa771d3f9d59e3b1dd340c85b1d79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="e5c29-102">where（泛型类型约束）（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e5c29-102">where (generic type constraint) (C# Reference)</span></span>
<span data-ttu-id="e5c29-103">在泛型类型定义中，`where` 子句用于指定对下列类型的约束：这些类型可用作泛型声明中定义的类型形参的实参。</span><span class="sxs-lookup"><span data-stu-id="e5c29-103">In a generic type definition, the `where` clause is used to specify constraints on the types that can be used as arguments for a type parameter defined in a generic declaration.</span></span> <span data-ttu-id="e5c29-104">例如，可以声明一个泛型类 `MyGenericClass`，以使类型参数 `T` 实现 <xref:System.IComparable%601> 接口：</span><span class="sxs-lookup"><span data-stu-id="e5c29-104">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>  
  
```csharp  
public class MyGenericClass<T> where T:IComparable { }  
```  
  
> [!NOTE]
>  <span data-ttu-id="e5c29-105">有关查询表达式中的 where 子句的详细信息，请参阅 [where 子句](../../../csharp/language-reference/keywords/where-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="e5c29-105">For more information on the where clause in a query expression, see [where clause](../../../csharp/language-reference/keywords/where-clause.md).</span></span>  
  
 <span data-ttu-id="e5c29-106">除了接口约束，`where` 子句还可以包括基类约束，以指出某个类型必须将指定的类作为基类（或者就是该类本身），才能用作该泛型类型的类型参数。</span><span class="sxs-lookup"><span data-stu-id="e5c29-106">In addition to interface constraints, a `where` clause can include a base class constraint, which states that a type must have the specified class as a base class (or be that class itself) in order to be used as a type argument for that generic type.</span></span> <span data-ttu-id="e5c29-107">这样的约束一经使用，就必须出现在该类型参数的所有其他约束之前。</span><span class="sxs-lookup"><span data-stu-id="e5c29-107">If such a constraint is used, it must appear before any other constraints on that type parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]  
  
 <span data-ttu-id="e5c29-108">`where` 子句还可以包括构造函数约束。</span><span class="sxs-lookup"><span data-stu-id="e5c29-108">The `where` clause may also include a constructor constraint.</span></span> <span data-ttu-id="e5c29-109">可以使用 new 运算符创建类型参数的实例；但类型参数为此必须受构造函数约束 `new()` 的约束。</span><span class="sxs-lookup"><span data-stu-id="e5c29-109">It is possible to create an instance of a type parameter using the new operator; however, in order to do so the type parameter must be constrained by the constructor constraint, `new()`.</span></span> <span data-ttu-id="e5c29-110">[new() 约束](../../../csharp/language-reference/keywords/new-constraint.md)可以让编译器知道：提供的任何类型参数都必须具有可访问的无参数（或默认）构造函数。</span><span class="sxs-lookup"><span data-stu-id="e5c29-110">The [new() Constraint](../../../csharp/language-reference/keywords/new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless--or default-- constructor.</span></span> <span data-ttu-id="e5c29-111">例如: </span><span class="sxs-lookup"><span data-stu-id="e5c29-111">For example:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]  
  
 <span data-ttu-id="e5c29-112">`new()` 约束出现在 `where` 子句的最后。</span><span class="sxs-lookup"><span data-stu-id="e5c29-112">The `new()` constraint appears last in the `where` clause.</span></span>  
  
 <span data-ttu-id="e5c29-113">对于多个类型参数，每个类型参数都使用一个 `where` 子句，例如：</span><span class="sxs-lookup"><span data-stu-id="e5c29-113">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]  
  
 <span data-ttu-id="e5c29-114">还可以将约束附加到泛型方法的类型参数，例如：</span><span class="sxs-lookup"><span data-stu-id="e5c29-114">You can also attach constraints to type parameters of generic methods, like this:</span></span>  
  
```csharp  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 <span data-ttu-id="e5c29-115">请注意，对于委托和方法两者来说，描述类型参数约束的语法是一样的：</span><span class="sxs-lookup"><span data-stu-id="e5c29-115">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>  
  
```csharp  
delegate T MyDelegate<T>() where T : new()  
```  
  
 <span data-ttu-id="e5c29-116">有关泛型委托的信息，请参阅[泛型委托](../../../csharp/programming-guide/generics/generic-delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="e5c29-116">For information on generic delegates, see [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
 <span data-ttu-id="e5c29-117">有关约束的语法和用法的详细信息，请参阅[类型参数的约束](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="e5c29-117">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e5c29-118">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="e5c29-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e5c29-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5c29-119">See Also</span></span>  
 [<span data-ttu-id="e5c29-120">C# 参考</span><span class="sxs-lookup"><span data-stu-id="e5c29-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e5c29-121">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="e5c29-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e5c29-122">泛型介绍</span><span class="sxs-lookup"><span data-stu-id="e5c29-122">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [<span data-ttu-id="e5c29-123">new 约束</span><span class="sxs-lookup"><span data-stu-id="e5c29-123">new Constraint</span></span>](../../../csharp/language-reference/keywords/new-constraint.md)  
 [<span data-ttu-id="e5c29-124">类型参数的约束</span><span class="sxs-lookup"><span data-stu-id="e5c29-124">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)
