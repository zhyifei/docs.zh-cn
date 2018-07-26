---
title: 可以为 null 的类型（C# 编程指南）
ms.date: 05/15/2017
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: 64b326b82cd022ed6590a232546690e2ec2a5c78
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245579"
---
# <a name="nullable-types-c-programming-guide"></a><span data-ttu-id="3920f-102">可以为 null 的类型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="3920f-102">Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="3920f-103">可以为 null 的类型是 <xref:System.Nullable%601?displayProperty=nameWithType> 结构的实例。</span><span class="sxs-lookup"><span data-stu-id="3920f-103">Nullable types are instances of the <xref:System.Nullable%601?displayProperty=nameWithType> struct.</span></span> <span data-ttu-id="3920f-104">可以为 null 的类型可以表示基础值类型正常范围内的值，再加上一个 `null` 值。</span><span class="sxs-lookup"><span data-stu-id="3920f-104">A nullable type can represent the correct range of values for its underlying value type, plus an additional `null` value.</span></span> <span data-ttu-id="3920f-105">例如，`Nullable<Int32>` 读作“可以为 null 的 Int32”，可以将 -2147483648 到 2147483647 之间的任意值赋值给它，也可以将 `null` 赋值给它。</span><span class="sxs-lookup"><span data-stu-id="3920f-105">For example, a `Nullable<Int32>`, pronounced "Nullable of Int32," can be assigned any value from -2147483648 to 2147483647, or it can be assigned the `null` value.</span></span> <span data-ttu-id="3920f-106">可以将 [true](../../../csharp/language-reference/keywords/true.md)、[false](../../../csharp/language-reference/keywords/false.md) 或 [null](../../../csharp/language-reference/keywords/null.md) 赋值给 `Nullable<bool>`。</span><span class="sxs-lookup"><span data-stu-id="3920f-106">A `Nullable<bool>` can be assigned the values [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md), or [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="3920f-107">处理数据库和其他包含不可赋值的元素的数据类型时，能够将 `null` 赋值给数值类型和布尔类型会特别有用。</span><span class="sxs-lookup"><span data-stu-id="3920f-107">The ability to assign `null` to numeric and Boolean types is especially useful when you are dealing with databases and other data types that contain elements that may not be assigned a value.</span></span> <span data-ttu-id="3920f-108">例如，数据库中的布尔字段可以存储值 `true` 或 `false`，也可以处于未定义状态。</span><span class="sxs-lookup"><span data-stu-id="3920f-108">For example, a Boolean field in a database can store the values `true` or `false`, or it may be undefined.</span></span> 
  
[!code-csharp[nullable-types](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]  
  
<span data-ttu-id="3920f-109">有关更多示例，请参阅[使用可以为 null 的类型](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)</span><span class="sxs-lookup"><span data-stu-id="3920f-109">For more examples, see [Using Nullable Types](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)</span></span>  
  
## <a name="nullable-types-overview"></a><span data-ttu-id="3920f-110">可以为 null 的类型概述</span><span class="sxs-lookup"><span data-stu-id="3920f-110">Nullable Types Overview</span></span>  
 <span data-ttu-id="3920f-111">可以为 null 的类型具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="3920f-111">Nullable types have the following characteristics:</span></span>  
  
-   <span data-ttu-id="3920f-112">可以为 null 的类型表示可以向其赋值 `null` 的值类型变量。</span><span class="sxs-lookup"><span data-stu-id="3920f-112">Nullable types represent value-type variables that can be assigned the value of `null`.</span></span> <span data-ttu-id="3920f-113">不能根据引用类型创建可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="3920f-113">You cannot create a nullable type based on a reference type.</span></span> <span data-ttu-id="3920f-114">（引用类型已支持 `null` 值）。</span><span class="sxs-lookup"><span data-stu-id="3920f-114">(Reference types already support the `null` value.)</span></span>  
  
-   <span data-ttu-id="3920f-115">语法 `T?` 是 <xref:System.Nullable%601> 的简写，其中 `T` 是值类型。</span><span class="sxs-lookup"><span data-stu-id="3920f-115">The syntax `T?` is shorthand for <xref:System.Nullable%601>, where `T` is a value type.</span></span> <span data-ttu-id="3920f-116">这两种形式是可互换的。</span><span class="sxs-lookup"><span data-stu-id="3920f-116">The two forms are interchangeable.</span></span>  
  
-   <span data-ttu-id="3920f-117">向可以为 null 的类型赋值的方法与向一般值类型赋值的方法相同，如 `int? x = 10;` 或 `double? d = 4.108;`。</span><span class="sxs-lookup"><span data-stu-id="3920f-117">Assign a value to a nullable type just as you would for an ordinary value type, for example `int? x = 10;` or `double? d = 4.108;`.</span></span> <span data-ttu-id="3920f-118">也能够向可以为 null 的类型赋值 `null`：`int? x = null;`。</span><span class="sxs-lookup"><span data-stu-id="3920f-118">A nullable type can also be assigned the value `null`: `int? x = null;`.</span></span>  
  
-   <span data-ttu-id="3920f-119">使用 <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType> 方法可返回分配的值或基础类型的默认值（如果值为 `null` 的话）。例如，`int j = x.GetValueOrDefault();`</span><span class="sxs-lookup"><span data-stu-id="3920f-119">Use the <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType> method to return either the assigned value, or the default value for the underlying type if the value is `null`, for example `int j = x.GetValueOrDefault();`</span></span>  
  
-   <span data-ttu-id="3920f-120">使用 <xref:System.Nullable%601.HasValue%2A> 和 <xref:System.Nullable%601.Value%2A> 只读属性可测试是否存在 null 值并检索值，如以下示例所示：`if(x.HasValue) j = x.Value;`</span><span class="sxs-lookup"><span data-stu-id="3920f-120">Use the <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> read-only properties to test for null and retrieve the value, as shown in the following example: `if(x.HasValue) j = x.Value;`</span></span>  
  
    -   <span data-ttu-id="3920f-121">如果变量包含值，则 `HasValue` 属性返回 `true`；如果值为 `null`，则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="3920f-121">The `HasValue` property returns `true` if the variable contains a value, or `false` if it is `null`.</span></span>  
  
    -   <span data-ttu-id="3920f-122">如果已赋值，则 `Value` 属性返回值。</span><span class="sxs-lookup"><span data-stu-id="3920f-122">The `Value` property returns a value if one is assigned.</span></span> <span data-ttu-id="3920f-123">否则，将会引发 <xref:System.InvalidOperationException?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="3920f-123">Otherwise, a <xref:System.InvalidOperationException?displayProperty=nameWithType> is thrown.</span></span>  
  
    -   <span data-ttu-id="3920f-124">`HasValue` 的默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="3920f-124">The default value for `HasValue` is `false`.</span></span> <span data-ttu-id="3920f-125">`Value` 属性没有默认值。</span><span class="sxs-lookup"><span data-stu-id="3920f-125">The `Value` property has no default value.</span></span>  
  
    -   <span data-ttu-id="3920f-126">还能将 `==` 和 `!=` 运算符与可以为 null 的类型结合使用，如以下示例所示：`if (x != null) y = x;`</span><span class="sxs-lookup"><span data-stu-id="3920f-126">You can also use the `==` and `!=` operators with a nullable type, as shown in the following example: `if (x != null) y = x;`</span></span>  
  
-   <span data-ttu-id="3920f-127">将当前值为 `null` 的可以为 null 的类型赋值给不可以为 null 的类型时，能够使用 `??` 运算符赋予默认值，例如 `int? x = null; int y = x ?? -1;`</span><span class="sxs-lookup"><span data-stu-id="3920f-127">Use the `??` operator to assign a default value that will be applied when a nullable type whose current value is `null` is assigned to a non-nullable type, for example `int? x = null; int y = x ?? -1;`</span></span>  
  
-   <span data-ttu-id="3920f-128">不得嵌套可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="3920f-128">Nested nullable types are not allowed.</span></span> <span data-ttu-id="3920f-129">无法编译下面的一行代码：`Nullable<Nullable<int>> n;`</span><span class="sxs-lookup"><span data-stu-id="3920f-129">The following line will not compile: `Nullable<Nullable<int>> n;`</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3920f-130">相关章节</span><span class="sxs-lookup"><span data-stu-id="3920f-130">Related Sections</span></span>  
 <span data-ttu-id="3920f-131">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="3920f-131">For more information:</span></span>  
  
-   [<span data-ttu-id="3920f-132">使用可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="3920f-132">Using Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [<span data-ttu-id="3920f-133">装箱可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="3920f-133">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [<span data-ttu-id="3920f-134">??运算符</span><span class="sxs-lookup"><span data-stu-id="3920f-134">?? Operator</span></span>](../../../csharp/language-reference/operators/null-coalescing-operator.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="3920f-135">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="3920f-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3920f-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="3920f-136">See Also</span></span>  
 <xref:System.Nullable>  
 [<span data-ttu-id="3920f-137">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3920f-137">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3920f-138">C#</span><span class="sxs-lookup"><span data-stu-id="3920f-138">C#</span></span>](../../../csharp/index.md)  
 [<span data-ttu-id="3920f-139">C# 参考</span><span class="sxs-lookup"><span data-stu-id="3920f-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3920f-140">“提升”的准确含义是什么？</span><span class="sxs-lookup"><span data-stu-id="3920f-140">What exactly does 'lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
