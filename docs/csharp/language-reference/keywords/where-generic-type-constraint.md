---
title: where（泛型类型约束）（C# 参考）
ms.date: 04/12/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 16be19e342016becd100e2c21434393c3f36f815
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="eb110-102">where（泛型类型约束）（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="eb110-102">where (generic type constraint) (C# Reference)</span></span>

<span data-ttu-id="eb110-103">泛型定义中的 `where` 子句指定对用作泛型类型、方法、委托或本地函数中类型参数的参数类型的约束。</span><span class="sxs-lookup"><span data-stu-id="eb110-103">The `where` clause in a generic definition specifies constraints on the types that are used as arguments for type parameters in a generic type, method, delegate, or local function.</span></span> <span data-ttu-id="eb110-104">约束可指定接口、基类或要求泛型类型为引用、值或非托管类型。</span><span class="sxs-lookup"><span data-stu-id="eb110-104">Constraints can specify interfaces, base classes, or require a generic type to be a reference, value or unmanaged type.</span></span> <span data-ttu-id="eb110-105">它们声明类型参数必须具备的功能。</span><span class="sxs-lookup"><span data-stu-id="eb110-105">They declare capabilities that the type argument must possess.</span></span>

<span data-ttu-id="eb110-106">例如，可以声明一个泛型类 `MyGenericClass`，以使类型参数 `T` 实现 <xref:System.IComparable%601> 接口：</span><span class="sxs-lookup"><span data-stu-id="eb110-106">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>

[!code-csharp[using an interface constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#1)]

> [!NOTE]
> <span data-ttu-id="eb110-107">有关查询表达式中的 where 子句的详细信息，请参阅 [where 子句](where-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="eb110-107">For more information on the where clause in a query expression, see [where clause](where-clause.md).</span></span>

<span data-ttu-id="eb110-108">`where` 子句还可包括基类约束。</span><span class="sxs-lookup"><span data-stu-id="eb110-108">The `where` clause can also include a base class constraint.</span></span> <span data-ttu-id="eb110-109">基类约束表明用作该泛型类型的类型参数的类型具有指定的类作为基类（或者是该基类），以用作该泛型类型的类型参数。</span><span class="sxs-lookup"><span data-stu-id="eb110-109">The base class constraint states that a type to be used as a type argument for that generic type has the specified class as a base class (or is that base class) to be used as a type argument for that generic type.</span></span> <span data-ttu-id="eb110-110">该基类约束一经使用，就必须出现在该类型参数的所有其他约束之前。</span><span class="sxs-lookup"><span data-stu-id="eb110-110">If the base class constraint is used, it must appear before any other constraints on that type parameter.</span></span> <span data-ttu-id="eb110-111">某些类型不允许作为基类约束：<xref:System.Object>、<xref:System.Array> 和 <xref:System.ValueType>。</span><span class="sxs-lookup"><span data-stu-id="eb110-111">Some types are disallowed as a base class constraint: <xref:System.Object>, <xref:System.Array>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="eb110-112">在 C# 7.3 之前，<xref:System.Enum>、<xref:System.Delegate> 和 <xref:System.MulticastDelegate> 也不允许作为基类约束。</span><span class="sxs-lookup"><span data-stu-id="eb110-112">Prior to C# 7.3, <xref:System.Enum>, <xref:System.Delegate>, and <xref:System.MulticastDelegate> were also disallowed as base class constraints.</span></span> <span data-ttu-id="eb110-113">以下示例显示现可指定为基类的类型：</span><span class="sxs-lookup"><span data-stu-id="eb110-113">The following example shows the types that can now be specified as a base class:</span></span>

[!code-csharp[using an interface constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#2)]

<span data-ttu-id="eb110-114">`where` 子句可指定类型为 `class` 或 `struct`。</span><span class="sxs-lookup"><span data-stu-id="eb110-114">The `where` clause can specify that the type is a `class` or a `struct`.</span></span> <span data-ttu-id="eb110-115">`struct` 约束不再需要指定 `System.ValueType` 的基类约束。</span><span class="sxs-lookup"><span data-stu-id="eb110-115">The `struct` constraint removes the need to specify a base class constraint of `System.ValueType`.</span></span> <span data-ttu-id="eb110-116">`System.ValueType` 类型可能不用作基类约束。</span><span class="sxs-lookup"><span data-stu-id="eb110-116">The `System.ValueType` type may not be used as a base class constraint.</span></span> <span data-ttu-id="eb110-117">以下示例显示 `class` 和 `struct` 约束：</span><span class="sxs-lookup"><span data-stu-id="eb110-117">The following example shows both the `class` and `struct` constraints:</span></span>

[!code-csharp[using the class and struct constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#3)]

<span data-ttu-id="eb110-118">`where` 子句还可包括 `unmanaged` 约束。</span><span class="sxs-lookup"><span data-stu-id="eb110-118">The `where` clause may also include an `unmanaged` constraint.</span></span> <span data-ttu-id="eb110-119">`unmanaged` 约束将类型参数限制为名为“非托管类型”的类型。</span><span class="sxs-lookup"><span data-stu-id="eb110-119">The `unmanaged` constraint limits the type parameter to types known as **unmanaged types**.</span></span> <span data-ttu-id="eb110-120">“非托管类型”不是引用类型，且任何嵌套级别都不包含引用类型字段。</span><span class="sxs-lookup"><span data-stu-id="eb110-120">An **unmanaged type** is a type that isn't a reference type and doesn't contain reference type fields at any level of nesting.</span></span> <span data-ttu-id="eb110-121">`unmanaged` 约束使得在 C# 中编写低级别的互操作代码变得更容易。</span><span class="sxs-lookup"><span data-stu-id="eb110-121">The `unmanaged` constraint makes it easier to write low-level interop code in C#.</span></span> <span data-ttu-id="eb110-122">此约束支持跨所有非托管类型的可重用例程。</span><span class="sxs-lookup"><span data-stu-id="eb110-122">This constraint enables reusable routines across all unmanaged types.</span></span> <span data-ttu-id="eb110-123">`unmanaged` 约束不能与 `class` 或 `struct` 约束结合使用。</span><span class="sxs-lookup"><span data-stu-id="eb110-123">The `unmanaged` constraint can't be combined with the `class` or `struct` constraint.</span></span> <span data-ttu-id="eb110-124">`unmanaged` 约束强制该类型必须为 `struct`：</span><span class="sxs-lookup"><span data-stu-id="eb110-124">The `unmanaged` constraint enforces that the type must be a `struct`:</span></span>

[!code-csharp[using the unmanaged constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#4)]

<span data-ttu-id="eb110-125">`where` 子句也可能包括构造函数约束 `new()`。</span><span class="sxs-lookup"><span data-stu-id="eb110-125">The `where` clause may also include a constructor constraint, `new()`.</span></span> <span data-ttu-id="eb110-126">该约束使得能够使用 `new` 运算符创建类型参数的实例。</span><span class="sxs-lookup"><span data-stu-id="eb110-126">That constraint makes it possible to create an instance of a type parameter using the `new` operator.</span></span> <span data-ttu-id="eb110-127">[new() 约束](new-constraint.md)可以让编译器知道：提供的任何类型参数都必须具有可访问的无参数（或默认）构造函数。</span><span class="sxs-lookup"><span data-stu-id="eb110-127">The [new() Constraint](new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless--or default-- constructor.</span></span> <span data-ttu-id="eb110-128">例如:</span><span class="sxs-lookup"><span data-stu-id="eb110-128">For example:</span></span>

[!code-csharp[using the new constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#5)]

<span data-ttu-id="eb110-129">`new()` 约束出现在 `where` 子句的最后。</span><span class="sxs-lookup"><span data-stu-id="eb110-129">The `new()` constraint appears last in the `where` clause.</span></span> <span data-ttu-id="eb110-130">`new()` 约束不能与 `struct` 或 `unmanaged` 约束结合使用。</span><span class="sxs-lookup"><span data-stu-id="eb110-130">The `new()` constraint can't be combined with the `struct` or `unmanaged` constraints.</span></span> <span data-ttu-id="eb110-131">所有满足这些约束的类型必须具有可访问的无参数构造函数，这使得 `new()` 约束冗余。</span><span class="sxs-lookup"><span data-stu-id="eb110-131">All types satisfying those constraints must have an accessible parameterless constructor, making the `new()` constraint redundant.</span></span>

<span data-ttu-id="eb110-132">对于多个类型参数，每个类型参数都使用一个 `where` 子句，例如：</span><span class="sxs-lookup"><span data-stu-id="eb110-132">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>

[!code-csharp[using multiple where constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#6)]

<span data-ttu-id="eb110-133">还可将约束附加到泛型方法的类型参数，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="eb110-133">You can also attach constraints to type parameters of generic methods, as shown in the following example:</span></span>

[!code-csharp[where constraints with generic methods](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#7)]

<span data-ttu-id="eb110-134">请注意，对于委托和方法两者来说，描述类型参数约束的语法是一样的：</span><span class="sxs-lookup"><span data-stu-id="eb110-134">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>

[!code-csharp[where constraints with generic methods](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#8)]

<span data-ttu-id="eb110-135">有关泛型委托的信息，请参阅[泛型委托](../../../csharp/programming-guide/generics/generic-delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="eb110-135">For information on generic delegates, see [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>

<span data-ttu-id="eb110-136">有关约束的语法和用法的详细信息，请参阅[类型参数的约束](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="eb110-136">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="eb110-137">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="eb110-137">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="eb110-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb110-138">See also</span></span>

 [<span data-ttu-id="eb110-139">C# 参考</span><span class="sxs-lookup"><span data-stu-id="eb110-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="eb110-140">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="eb110-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="eb110-141">泛型介绍</span><span class="sxs-lookup"><span data-stu-id="eb110-141">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [<span data-ttu-id="eb110-142">new 约束</span><span class="sxs-lookup"><span data-stu-id="eb110-142">new Constraint</span></span>](../../../csharp/language-reference/keywords/new-constraint.md)  
 [<span data-ttu-id="eb110-143">类型参数的约束</span><span class="sxs-lookup"><span data-stu-id="eb110-143">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
