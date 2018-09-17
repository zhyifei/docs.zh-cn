---
title: 默认值表达式（C# 编程指南）
description: 默认值表达式生成任何引用类型或值类型的默认值
ms.date: 04/25/2018
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.openlocfilehash: 94866f22fb3ad921a834cffb16fe17e44cef5965
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2018
ms.locfileid: "45615336"
---
# <a name="default-value-expressions-c-programming-guide"></a><span data-ttu-id="c8fda-103">默认值表达式（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="c8fda-103">default value expressions (C# programming guide)</span></span>

<span data-ttu-id="c8fda-104">默认值表达式 `default(T)` 生成 `T` 类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="c8fda-104">A default value expression `default(T)` produces the default value of a type `T`.</span></span> <span data-ttu-id="c8fda-105">下表显示为各种类型生成的值：</span><span class="sxs-lookup"><span data-stu-id="c8fda-105">The following table shows which values are produced for various types:</span></span>

|<span data-ttu-id="c8fda-106">类型</span><span class="sxs-lookup"><span data-stu-id="c8fda-106">Type</span></span>|<span data-ttu-id="c8fda-107">默认值</span><span class="sxs-lookup"><span data-stu-id="c8fda-107">Default value</span></span>|
|---------|---------|
|<span data-ttu-id="c8fda-108">任何引用类型</span><span class="sxs-lookup"><span data-stu-id="c8fda-108">Any reference type</span></span>|`null`|
|<span data-ttu-id="c8fda-109">数值类型</span><span class="sxs-lookup"><span data-stu-id="c8fda-109">Numeric value type</span></span>|<span data-ttu-id="c8fda-110">零</span><span class="sxs-lookup"><span data-stu-id="c8fda-110">Zero</span></span>|
|[<span data-ttu-id="c8fda-111">bool</span><span class="sxs-lookup"><span data-stu-id="c8fda-111">bool</span></span>](../../language-reference/keywords/bool.md)|`false`|
|[<span data-ttu-id="c8fda-112">char</span><span class="sxs-lookup"><span data-stu-id="c8fda-112">char</span></span>](../../language-reference/keywords/char.md)|`'\0'`|
|[<span data-ttu-id="c8fda-113">enum</span><span class="sxs-lookup"><span data-stu-id="c8fda-113">enum</span></span>](../../language-reference/keywords/enum.md)|<span data-ttu-id="c8fda-114">表达式 `(E)0` 生成的值，其中 `E` 是枚举标识符。</span><span class="sxs-lookup"><span data-stu-id="c8fda-114">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="c8fda-115">struct</span><span class="sxs-lookup"><span data-stu-id="c8fda-115">struct</span></span>](../../language-reference/keywords/struct.md)|<span data-ttu-id="c8fda-116">通过如下设置生成的值：将所有值类型的字段设置为其默认值，将所有引用类型的字段设置为 `null`。</span><span class="sxs-lookup"><span data-stu-id="c8fda-116">The value produced by setting all value type fields to their default value and all reference type fields to `null`.</span></span>|
|<span data-ttu-id="c8fda-117">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="c8fda-117">Nullable type</span></span>|<span data-ttu-id="c8fda-118"><xref:System.Nullable%601.HasValue%2A> 属性为 `false` 且 <xref:System.Nullable%601.Value%2A> 属性未定义的实例。</span><span class="sxs-lookup"><span data-stu-id="c8fda-118">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>|

<span data-ttu-id="c8fda-119">默认值表达式在泛型类和泛型方法中非常有用。</span><span class="sxs-lookup"><span data-stu-id="c8fda-119">Default value expressions are particularly useful in generic classes and methods.</span></span> <span data-ttu-id="c8fda-120">使用泛型类和泛型方法时出现的一个问题是，如何在无法提前知道以下内容的情况下将默认值赋值给参数化类型 `T`：</span><span class="sxs-lookup"><span data-stu-id="c8fda-120">One issue that arises using generics is how to assign a default value of a parameterized type `T` when you don't know the following in advance:</span></span>

- <span data-ttu-id="c8fda-121">`T` 是引用类型还是值类型。</span><span class="sxs-lookup"><span data-stu-id="c8fda-121">Whether `T` is a reference type or a value type.</span></span>
- <span data-ttu-id="c8fda-122">如果 `T` 是值类型，它是数值还是结构。</span><span class="sxs-lookup"><span data-stu-id="c8fda-122">If `T` is a value type, whether it's a numeric value or a struct.</span></span>

 <span data-ttu-id="c8fda-123">已知参数化类型 `T` 的变量 `t`，仅当 `T` 为引用类型时，语句 `t = null` 才有效。</span><span class="sxs-lookup"><span data-stu-id="c8fda-123">Given a variable `t` of a parameterized type `T`, the statement `t = null` is only valid if `T` is a reference type.</span></span> <span data-ttu-id="c8fda-124">赋值 `t = 0` 仅对数值类型有效，对结构无效。</span><span class="sxs-lookup"><span data-stu-id="c8fda-124">The assignment `t = 0` only works for numeric value types but not for structs.</span></span> <span data-ttu-id="c8fda-125">若要解决此问题，请使用默认值表达式：</span><span class="sxs-lookup"><span data-stu-id="c8fda-125">To solve that, use a default value expression:</span></span>

```csharp
T t = default(T);
```

<span data-ttu-id="c8fda-126">`default(T)` 表达式不限于泛型类和泛型方法。</span><span class="sxs-lookup"><span data-stu-id="c8fda-126">The `default(T)` expression is not limited to generic classes and methods.</span></span> <span data-ttu-id="c8fda-127">默认值表达式可用于任何托管类型。</span><span class="sxs-lookup"><span data-stu-id="c8fda-127">Default value expressions can be used with any managed type.</span></span> <span data-ttu-id="c8fda-128">以下任一表达式都是有效的：</span><span class="sxs-lookup"><span data-stu-id="c8fda-128">Any of these expressions are valid:</span></span>

 [!code-csharp[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 <span data-ttu-id="c8fda-129">`GenericList<T>` 类的以下示例演示如何在泛型类中使用 `default(T)` 运算符。</span><span class="sxs-lookup"><span data-stu-id="c8fda-129">The following example from the `GenericList<T>` class shows how to use the `default(T)` operator in a generic class.</span></span> <span data-ttu-id="c8fda-130">有关详细信息，请参阅[泛型介绍](../generics/introduction-to-generics.md)。</span><span class="sxs-lookup"><span data-stu-id="c8fda-130">For more information, see [Introduction to Generics](../generics/introduction-to-generics.md).</span></span>

 [!code-csharp[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a><span data-ttu-id="c8fda-131">默认文本和类型推理</span><span class="sxs-lookup"><span data-stu-id="c8fda-131">default literal and type inference</span></span>

<span data-ttu-id="c8fda-132">从 C# 7.1 开始，当编译器可以推断表达式的类型时，文本 `default` 可用于默认值表达式。</span><span class="sxs-lookup"><span data-stu-id="c8fda-132">Beginning with C# 7.1, the `default` literal can be used for default value expressions when the compiler can infer the type of the expression.</span></span> <span data-ttu-id="c8fda-133">文本 `default` 生成与等效项 `default(T)`（其中，`T` 是推断的类型）相同的值。</span><span class="sxs-lookup"><span data-stu-id="c8fda-133">The `default` literal produces the same value as the equivalent `default(T)` where `T` is the inferred type.</span></span> <span data-ttu-id="c8fda-134">这可减少多次声明类型的冗余，从而使代码更加简洁。</span><span class="sxs-lookup"><span data-stu-id="c8fda-134">This can make code more concise by reducing the redundancy of declaring a type more than once.</span></span> <span data-ttu-id="c8fda-135">文本 `default` 可用于以下任一位置：</span><span class="sxs-lookup"><span data-stu-id="c8fda-135">The `default` literal can be used in any of the following locations:</span></span>

- <span data-ttu-id="c8fda-136">变量初始值设定项</span><span class="sxs-lookup"><span data-stu-id="c8fda-136">variable initializer</span></span>
- <span data-ttu-id="c8fda-137">变量赋值</span><span class="sxs-lookup"><span data-stu-id="c8fda-137">variable assignment</span></span>
- <span data-ttu-id="c8fda-138">声明可选参数的默认值</span><span class="sxs-lookup"><span data-stu-id="c8fda-138">declaring the default value for an optional parameter</span></span>
- <span data-ttu-id="c8fda-139">为方法调用参数提供值</span><span class="sxs-lookup"><span data-stu-id="c8fda-139">providing the value for a method call argument</span></span>
- <span data-ttu-id="c8fda-140">返回语句（或 expression bodied 成员中的表达式）</span><span class="sxs-lookup"><span data-stu-id="c8fda-140">return statement (or expression in an expression bodied member)</span></span>

<span data-ttu-id="c8fda-141">以下示例展示了文本 `default` 在默认值表达式中的多种用法：</span><span class="sxs-lookup"><span data-stu-id="c8fda-141">The following example shows many usages of the `default` literal in a default value expression:</span></span>

[!code-csharp[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a><span data-ttu-id="c8fda-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8fda-142">See Also</span></span>

- <xref:System.Collections.Generic>  
- [<span data-ttu-id="c8fda-143">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c8fda-143">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="c8fda-144">泛型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="c8fda-144">Generics (C# Programming Guide)</span></span>](../generics/index.md)  
- [<span data-ttu-id="c8fda-145">泛型方法</span><span class="sxs-lookup"><span data-stu-id="c8fda-145">Generic Methods</span></span>](../generics/generic-methods.md)  
- [<span data-ttu-id="c8fda-146">.NET 中的泛型</span><span class="sxs-lookup"><span data-stu-id="c8fda-146">Generics in .NET</span></span>](~/docs/standard/generics/index.md)  
- [<span data-ttu-id="c8fda-147">默认值表</span><span class="sxs-lookup"><span data-stu-id="c8fda-147">Default values table</span></span>](../../language-reference/keywords/default-values-table.md)
