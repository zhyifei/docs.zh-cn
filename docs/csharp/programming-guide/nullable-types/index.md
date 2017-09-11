---
title: "可以为 null 的类型（C# 编程指南）"
ms.date: 2017-05-15
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
caps.latest.revision: 44
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
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: 56e22638457017688ff380f6683b463b47c53a17
ms.contentlocale: zh-cn
ms.lasthandoff: 09/02/2017

---
# <a name="nullable-types-c-programming-guide"></a><span data-ttu-id="91266-102">可以为 null 的类型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="91266-102">Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="91266-103">可以为 null 的类型是 <xref:System.Nullable%601?displayProperty=fullName> 结构的实例。</span><span class="sxs-lookup"><span data-stu-id="91266-103">Nullable types are instances of the <xref:System.Nullable%601?displayProperty=fullName> struct.</span></span> <span data-ttu-id="91266-104">可以为 null 的类型可以表示基础值类型正常范围内的值，再加上一个 `null` 值。</span><span class="sxs-lookup"><span data-stu-id="91266-104">A nullable type can represent the correct range of values for its underlying value type, plus an additional `null` value.</span></span> <span data-ttu-id="91266-105">例如，`Nullable<Int32>` 读作“可以为 null 的 Int32”，可以将 -2147483648 到 2147483647 之间的任意值赋值给它，也可以将 `null` 赋值给它。</span><span class="sxs-lookup"><span data-stu-id="91266-105">For example, a `Nullable<Int32>`, pronounced "Nullable of Int32," can be assigned any value from -2147483648 to 2147483647, or it can be assigned the `null` value.</span></span> <span data-ttu-id="91266-106">可以将 [true](../../../csharp/language-reference/keywords/true.md)、[false](../../../csharp/language-reference/keywords/false.md) 或 [null](../../../csharp/language-reference/keywords/null.md) 赋值给 `Nullable<bool>`。</span><span class="sxs-lookup"><span data-stu-id="91266-106">A `Nullable<bool>` can be assigned the values [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md), or [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="91266-107">处理数据库和其他包含不可赋值的元素的数据类型时，能够将 `null` 赋值给数值类型和布尔类型会特别有用。</span><span class="sxs-lookup"><span data-stu-id="91266-107">The ability to assign `null` to numeric and Boolean types is especially useful when you are dealing with databases and other data types that contain elements that may not be assigned a value.</span></span> <span data-ttu-id="91266-108">例如，数据库中的布尔字段可以存储值 `true` 或 `false`，也可以处于未定义状态。</span><span class="sxs-lookup"><span data-stu-id="91266-108">For example, a Boolean field in a database can store the values `true` or `false`, or it may be undefined.</span></span> 
  
<span data-ttu-id="91266-109">[!code-cs[可以为 null 的类型](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]</span><span class="sxs-lookup"><span data-stu-id="91266-109">[!code-cs[nullable-types](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]</span></span>  
  
<span data-ttu-id="91266-110">有关更多示例，请参阅[使用可以为 null 的类型](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)</span><span class="sxs-lookup"><span data-stu-id="91266-110">For more examples, see [Using Nullable Types](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)</span></span>  
  
## <a name="nullable-types-overview"></a><span data-ttu-id="91266-111">可以为 null 的类型概述</span><span class="sxs-lookup"><span data-stu-id="91266-111">Nullable Types Overview</span></span>  
 <span data-ttu-id="91266-112">可以为 null 的类型具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="91266-112">Nullable types have the following characteristics:</span></span>  
  
-   <span data-ttu-id="91266-113">可以为 null 的类型表示可以向其赋值 `null` 的值类型变量。</span><span class="sxs-lookup"><span data-stu-id="91266-113">Nullable types represent value-type variables that can be assigned the value of `null`.</span></span> <span data-ttu-id="91266-114">不能根据引用类型创建可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="91266-114">You cannot create a nullable type based on a reference type.</span></span> <span data-ttu-id="91266-115">（引用类型已支持 `null` 值）。</span><span class="sxs-lookup"><span data-stu-id="91266-115">(Reference types already support the `null` value.)</span></span>  
  
-   <span data-ttu-id="91266-116">语法 `T?` 是 <xref:System.Nullable%601> 的简写，其中 `T` 是值类型。</span><span class="sxs-lookup"><span data-stu-id="91266-116">The syntax `T?` is shorthand for <xref:System.Nullable%601>, where `T` is a value type.</span></span> <span data-ttu-id="91266-117">这两种形式是可互换的。</span><span class="sxs-lookup"><span data-stu-id="91266-117">The two forms are interchangeable.</span></span>  
  
-   <span data-ttu-id="91266-118">向可以为 null 的类型赋值的方法与向一般值类型赋值的方法相同，如 `int? x = 10;` 或 `double? d = 4.108`。</span><span class="sxs-lookup"><span data-stu-id="91266-118">Assign a value to a nullable type just as you would for an ordinary value type, for example `int? x = 10;` or `double? d = 4.108`.</span></span> <span data-ttu-id="91266-119">也能够向可以为 null 的类型赋值 `null`：`int? x = null.`</span><span class="sxs-lookup"><span data-stu-id="91266-119">A nullable type can also be assigned the value `null`: `int? x = null.`</span></span>  
  
-   <span data-ttu-id="91266-120">使用 <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=fullName> 方法可返回分配的值或基础类型的默认值（如果值为 `null` 的话）。例如，`int j = x.GetValueOrDefault();`</span><span class="sxs-lookup"><span data-stu-id="91266-120">Use the <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=fullName> method to return either the assigned value, or the default value for the underlying type if the value is `null`, for example `int j = x.GetValueOrDefault();`</span></span>  
  
-   <span data-ttu-id="91266-121">使用 <xref:System.Nullable%601.HasValue%2A> 和 <xref:System.Nullable%601.Value%2A> 只读属性可测试是否存在 null 值并检索值，如以下示例所示：`if(x.HasValue) j = x.Value;`</span><span class="sxs-lookup"><span data-stu-id="91266-121">Use the <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> read-only properties to test for null and retrieve the value, as shown in the following example: `if(x.HasValue) j = x.Value;`</span></span>  
  
    -   <span data-ttu-id="91266-122">如果变量包含值，则 `HasValue` 属性返回 `true`；如果值为 `null`，则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="91266-122">The `HasValue` property returns `true` if the variable contains a value, or `false` if it is `null`.</span></span>  
  
    -   <span data-ttu-id="91266-123">如果已赋值，则 `Value` 属性返回值。</span><span class="sxs-lookup"><span data-stu-id="91266-123">The `Value` property returns a value if one is assigned.</span></span> <span data-ttu-id="91266-124">否则，将会引发 <xref:System.InvalidOperationException?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="91266-124">Otherwise, a <xref:System.InvalidOperationException?displayProperty=fullName> is thrown.</span></span>  
  
    -   <span data-ttu-id="91266-125">`HasValue` 的默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="91266-125">The default value for `HasValue` is `false`.</span></span> <span data-ttu-id="91266-126">`Value` 属性没有默认值。</span><span class="sxs-lookup"><span data-stu-id="91266-126">The `Value` property has no default value.</span></span>  
  
    -   <span data-ttu-id="91266-127">还能将 `==` 和 `!=` 运算符与可以为 null 的类型结合使用，如以下示例所示：`if (x != null) y = x;`</span><span class="sxs-lookup"><span data-stu-id="91266-127">You can also use the `==` and `!=` operators with a nullable type, as shown in the following example: `if (x != null) y = x;`</span></span>  
  
-   <span data-ttu-id="91266-128">将当前值为 `null` 的可以为 null 的类型赋值给不可以为 null 的类型时，能够使用 `??` 运算符赋予默认值，例如 `int? x = null; int y = x ?? -1;`</span><span class="sxs-lookup"><span data-stu-id="91266-128">Use the `??` operator to assign a default value that will be applied when a nullable type whose current value is `null` is assigned to a non-nullable type, for example `int? x = null; int y = x ?? -1;`</span></span>  
  
-   <span data-ttu-id="91266-129">不得嵌套可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="91266-129">Nested nullable types are not allowed.</span></span> <span data-ttu-id="91266-130">无法编译下面的一行代码：`Nullable<Nullable<int>> n;`</span><span class="sxs-lookup"><span data-stu-id="91266-130">The following line will not compile: `Nullable<Nullable<int>> n;`</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="91266-131">相关章节</span><span class="sxs-lookup"><span data-stu-id="91266-131">Related Sections</span></span>  
 <span data-ttu-id="91266-132">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="91266-132">For more information:</span></span>  
  
-   [<span data-ttu-id="91266-133">使用可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="91266-133">Using Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [<span data-ttu-id="91266-134">装箱可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="91266-134">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [<span data-ttu-id="91266-135">??运算符</span><span class="sxs-lookup"><span data-stu-id="91266-135">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="91266-136">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="91266-136">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="91266-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91266-137">See Also</span></span>  
 <span data-ttu-id="91266-138"><xref:System.Nullable></span><span class="sxs-lookup"><span data-stu-id="91266-138"><xref:System.Nullable></span></span>   
 <span data-ttu-id="91266-139">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="91266-139">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="91266-140">[C#](../../../csharp/index.md) </span><span class="sxs-lookup"><span data-stu-id="91266-140">[C#](../../../csharp/index.md) </span></span>  
 <span data-ttu-id="91266-141">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="91266-141">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="91266-142">“提升”的准确含义是什么？</span><span class="sxs-lookup"><span data-stu-id="91266-142">What exactly does 'lifted' mean?</span></span>](http://go.microsoft.com/fwlink/?LinkId=112382)

