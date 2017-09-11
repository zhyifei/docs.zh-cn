---
title: "默认值表达式（C# 编程指南）"
description: "默认值表达式生成任何引用类型或值类型的默认值"
ms.date: 2017-08-23
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 1e548df4de2c07934313311a7ffcfae82be76000
ms.openlocfilehash: 7b5b53d7ed92c6f6377a3e494daf1d02a4cf0934
ms.contentlocale: zh-cn
ms.lasthandoff: 08/29/2017

---
# <a name="default-value-expressions-c-programming-guide"></a><span data-ttu-id="87359-103">默认值表达式（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="87359-103">default value expressions (C# programming guide)</span></span>

<span data-ttu-id="87359-104">默认值表达式生成类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="87359-104">A default value expression produces the default value for a type.</span></span> <span data-ttu-id="87359-105">默认值表达式在泛型类和泛型方法中非常有用。</span><span class="sxs-lookup"><span data-stu-id="87359-105">Default value expressions are particularly useful in generic classes and methods.</span></span> <span data-ttu-id="87359-106">使用泛型类和泛型方法时出现的一个问题是，如何在无法提前知道以下内容的情况下将默认值赋值给参数化类型 `T`：</span><span class="sxs-lookup"><span data-stu-id="87359-106">One issue that arises using generics is how to assign a default value to a parameterized type `T` when you do not know the following in advance:</span></span>

- <span data-ttu-id="87359-107">`T` 是引用类型还是值类型。</span><span class="sxs-lookup"><span data-stu-id="87359-107">Whether `T` is a reference type or a value type.</span></span>
- <span data-ttu-id="87359-108">如果 `T` 是值类型，它是数值还是用户定义的结构。</span><span class="sxs-lookup"><span data-stu-id="87359-108">If `T` is a value type, whether is a numeric value or a user-defined struct.</span></span>

 <span data-ttu-id="87359-109">已知参数化类型 `T` 的变量 `t`，仅当 `T` 为引用类型时，语句 `t = null` 才有效。</span><span class="sxs-lookup"><span data-stu-id="87359-109">Given a variable `t` of a parameterized type `T`, the statement `t = null` is only valid if `T` is a reference type.</span></span> <span data-ttu-id="87359-110">赋值 `t = 0` 仅对数值类型有效，对结构无效。</span><span class="sxs-lookup"><span data-stu-id="87359-110">The assignment `t = 0` only works for numeric value types but not for structs.</span></span> <span data-ttu-id="87359-111">解决方案是使用默认值表达式，该表达式对引用类型（类类型和接口类型）返回 `null`，对数值类型返回零。</span><span class="sxs-lookup"><span data-stu-id="87359-111">The solution is to use a default value expression, which returns `null` for reference types (class types and interface types) and zero for numeric value types.</span></span> <span data-ttu-id="87359-112">对于用户定义的结构，返回初始化为零位模式的结构，该结构根据成员是值还是引用类型，为每个成员生成 0 或 `null`。</span><span class="sxs-lookup"><span data-stu-id="87359-112">For user-defined structs, it returns the struct initialized to the zero bit pattern, which produces 0 or `null` for each member depending on whether that member is a value or reference type.</span></span> <span data-ttu-id="87359-113">对于可为 NULL 的值类型，`default` 返回像任何结构一样初始化的 <xref:System.Nullable%601?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="87359-113">For nullable value types, `default` returns a <xref:System.Nullable%601?displayProperty=fullName>, which is initialized like any struct.</span></span>

<span data-ttu-id="87359-114">`default(T)` 表达式不限于泛型类和泛型方法。</span><span class="sxs-lookup"><span data-stu-id="87359-114">The `default(T)` expression is not limited to generic classes and methods.</span></span> <span data-ttu-id="87359-115">默认值表达式可用于任何托管类型。</span><span class="sxs-lookup"><span data-stu-id="87359-115">Default value expressions can be used with any managed type.</span></span> <span data-ttu-id="87359-116">以下任一表达式都是有效的：</span><span class="sxs-lookup"><span data-stu-id="87359-116">Any of these expressions are valid:</span></span>

 <span data-ttu-id="87359-117">[!code-cs[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]</span><span class="sxs-lookup"><span data-stu-id="87359-117">[!code-cs[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]</span></span>

 <span data-ttu-id="87359-118">`GenericList<T>` 类的以下示例演示如何在泛型类中使用 `default(T)` 运算符。</span><span class="sxs-lookup"><span data-stu-id="87359-118">The following example from the `GenericList<T>` class shows how to use the `default(T)` operator in a generic class.</span></span> <span data-ttu-id="87359-119">有关详细信息，请参阅[泛型概述](../generics/introduction-to-generics.md)。</span><span class="sxs-lookup"><span data-stu-id="87359-119">For more information, see [Generics Overview](../generics/introduction-to-generics.md).</span></span>

 <span data-ttu-id="87359-120">[!code-cs[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]</span><span class="sxs-lookup"><span data-stu-id="87359-120">[!code-cs[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]</span></span>

## <a name="default-literal-and-type-inference"></a><span data-ttu-id="87359-121">默认文本和类型推理</span><span class="sxs-lookup"><span data-stu-id="87359-121">default literal and type inference</span></span>

<span data-ttu-id="87359-122">从 C# 7.1 开始，当编译器可以推断表达式的类型时，文本 `default` 可用于默认值表达式。</span><span class="sxs-lookup"><span data-stu-id="87359-122">Beginning with C# 7.1, the `default` literal can be used for default value expressions when the compiler can infer the type of the expression.</span></span> <span data-ttu-id="87359-123">文本 `default` 生成与等效项 `default(T)`（其中，`T` 是推断的类型）相同的值。</span><span class="sxs-lookup"><span data-stu-id="87359-123">The `default` literal produces the same value as the equivalent `default(T)` where `T` is the inferred type.</span></span> <span data-ttu-id="87359-124">这可减少多次声明类型的冗余，从而使代码更加简洁。</span><span class="sxs-lookup"><span data-stu-id="87359-124">This can make code more concise by reducing the redundancy of declaring a type more than once.</span></span> <span data-ttu-id="87359-125">文本 `default` 可用于以下任一位置：</span><span class="sxs-lookup"><span data-stu-id="87359-125">The `default` literal can be used in any of the following locations:</span></span>

- <span data-ttu-id="87359-126">变量初始值设定项</span><span class="sxs-lookup"><span data-stu-id="87359-126">variable initializer</span></span>
- <span data-ttu-id="87359-127">变量赋值</span><span class="sxs-lookup"><span data-stu-id="87359-127">variable assignment</span></span>
- <span data-ttu-id="87359-128">声明可选参数的默认值</span><span class="sxs-lookup"><span data-stu-id="87359-128">declaring the default value for an optional parameter</span></span>
- <span data-ttu-id="87359-129">为方法调用参数提供值</span><span class="sxs-lookup"><span data-stu-id="87359-129">providing the value for a method call argument</span></span>
- <span data-ttu-id="87359-130">返回语句（或 expression bodied 成员中的表达式）</span><span class="sxs-lookup"><span data-stu-id="87359-130">return statement (or expression in an expression bodied member)</span></span>

<span data-ttu-id="87359-131">以下示例展示了文本 `default` 在默认值表达式中的多种用法：</span><span class="sxs-lookup"><span data-stu-id="87359-131">The following example shows many usages of the `default` literal in a default value expression:</span></span>

<span data-ttu-id="87359-132">[!code-cs[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]</span><span class="sxs-lookup"><span data-stu-id="87359-132">[!code-cs[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]</span></span>

## <a name="see-also"></a><span data-ttu-id="87359-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="87359-133">See also</span></span>

 <span data-ttu-id="87359-134"><xref:System.Collections.Generic> [C# 编程指南](../index.md) </span><span class="sxs-lookup"><span data-stu-id="87359-134"><xref:System.Collections.Generic> [C# Programming Guide](../index.md) </span></span>  
 <span data-ttu-id="87359-135">[泛型](../generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="87359-135">[Generics](../generics/index.md) </span></span>  
 <span data-ttu-id="87359-136">[泛型方法](../generics/generic-methods.md) </span><span class="sxs-lookup"><span data-stu-id="87359-136">[Generic Methods](../generics/generic-methods.md) </span></span>  
 [<span data-ttu-id="87359-137">泛型</span><span class="sxs-lookup"><span data-stu-id="87359-137">Generics</span></span>](~/docs/standard/generics/index.md)   

