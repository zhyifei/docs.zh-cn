---
title: "使用可以为 null 的类型（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c8a42392bbcd2e53c54ff4c13bf98c048262ae4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="fd9bb-102">使用可以为 null 的类型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="fd9bb-102">Using Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="fd9bb-103">可以为 null 的类型可表示一个基础类型的所有值，还可以再表示一个 [null](../../../csharp/language-reference/keywords/null.md) 值。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-103">Nullable types can represent all the values of an underlying type, and an additional [null](../../../csharp/language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="fd9bb-104">可通过以下两种方式之一声明可为 null 的类型：</span><span class="sxs-lookup"><span data-stu-id="fd9bb-104">Nullable types are declared in one of two ways:</span></span>  
  
 `System.Nullable<T> variable`  
  
 <span data-ttu-id="fd9bb-105">- 或 -</span><span class="sxs-lookup"><span data-stu-id="fd9bb-105">-or-</span></span>  
  
 `T? variable`  
  
 <span data-ttu-id="fd9bb-106">`T` 是可以为 null 的类型的基础类型。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-106">`T` is the underlying type of the nullable type.</span></span> <span data-ttu-id="fd9bb-107">`T` 可以是包括 `struct` 在内的任意值类型；它不能是引用类型。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-107">`T` can be any value type including `struct`; it cannot be a reference type.</span></span>  
  
 <span data-ttu-id="fd9bb-108">有关可为 null 的类型的使用示例，可思考一个普通布尔变量如何能够具有两个值：true 和 false。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-108">For an example of when you might use a nullable type, consider how an ordinary Boolean variable can have two values: true and false.</span></span> <span data-ttu-id="fd9bb-109">没有值表示“未定义”的意思。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-109">There is no value that signifies "undefined".</span></span> <span data-ttu-id="fd9bb-110">在许多编程应用程序中，尤其是数据库交互中，变量可能处于未定义的状态。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-110">In many programming applications, most notably database interactions, variables can occur in an undefined state.</span></span> <span data-ttu-id="fd9bb-111">例如，数据库中的字段可能包含值 true 或 false，但它也可能根本不包含任何值。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-111">For example, a field in a database may contain the values true or false, but it may also contain no value at all.</span></span> <span data-ttu-id="fd9bb-112">同样，可以将引用类型设置为 `null` 以指示它们未初始化。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-112">Similarly, reference types can be set to `null` to indicate that they are not initialized.</span></span>  
  
 <span data-ttu-id="fd9bb-113">这种不一致可能会导致额外的编程工作，包括使用更多变量来存储状态信息以及使用特殊值等。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-113">This disparity can create extra programming work, with additional variables used to store state information, the use of special values, and so on.</span></span> <span data-ttu-id="fd9bb-114">通过使用可为 null 的类型修饰符，C# 能够创建指示未定义值的值类型变量。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-114">The nullable type modifier enables C# to create value-type variables that indicate an undefined value.</span></span>  
  
## <a name="examples-of-nullable-types"></a><span data-ttu-id="fd9bb-115">可为 null 的类型的示例</span><span class="sxs-lookup"><span data-stu-id="fd9bb-115">Examples of Nullable Types</span></span>  
 <span data-ttu-id="fd9bb-116">任何值类型都可用作可为 null 的类型的基础。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-116">Any value type may be used as the basis for a nullable type.</span></span> <span data-ttu-id="fd9bb-117">例如: </span><span class="sxs-lookup"><span data-stu-id="fd9bb-117">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]  
  
## <a name="the-members-of-nullable-types"></a><span data-ttu-id="fd9bb-118">可为 null 的类型的成员</span><span class="sxs-lookup"><span data-stu-id="fd9bb-118">The Members of Nullable Types</span></span>  
 <span data-ttu-id="fd9bb-119">可以为 null 的类型的每个实例都有两个公共只读属性：</span><span class="sxs-lookup"><span data-stu-id="fd9bb-119">Each instance of a nullable type has two public read-only properties:</span></span>  
  
-   `HasValue`  
  
     <span data-ttu-id="fd9bb-120">`HasValue` 的类型为 `bool`。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-120">`HasValue` is of type `bool`.</span></span> <span data-ttu-id="fd9bb-121">如果该变量包含非 null 值，则将其设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-121">It is set to `true` when the variable contains a non-null value.</span></span>  
  
-   `Value`  
  
     <span data-ttu-id="fd9bb-122">`Value` 的类型与基础类型相同。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-122">`Value` is of the same type as the underlying type.</span></span> <span data-ttu-id="fd9bb-123">如果 `HasValue` 为 `true`，则 `Value` 包含有意义的值。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-123">If `HasValue` is `true`, `Value` contains a meaningful value.</span></span> <span data-ttu-id="fd9bb-124">如果 `HasValue` 是 `false`，则访问 `Value` 将引发 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-124">If `HasValue` is `false`, accessing `Value` will throw a <xref:System.InvalidOperationException>.</span></span>  
  
 <span data-ttu-id="fd9bb-125">在此示例中，`HasValue` 成员用于在显示变量之前测试变量是否包含值。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-125">In this example, the `HasValue` member is used to test whether the variable contains a value before it tries to display it.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]  
  
 <span data-ttu-id="fd9bb-126">也可按以下示例所示进行值测试：</span><span class="sxs-lookup"><span data-stu-id="fd9bb-126">Testing for a value can also be done as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]  
  
## <a name="explicit-conversions"></a><span data-ttu-id="fd9bb-127">显式转换</span><span class="sxs-lookup"><span data-stu-id="fd9bb-127">Explicit Conversions</span></span>  
 <span data-ttu-id="fd9bb-128">可通过显式转换或使用 `Value` 属性将可为 null 的类型转换为常规类型。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-128">A nullable type can be cast to a regular type, either explicitly with a cast, or by using the `Value` property.</span></span> <span data-ttu-id="fd9bb-129">例如: </span><span class="sxs-lookup"><span data-stu-id="fd9bb-129">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]  
  
 <span data-ttu-id="fd9bb-130">如果定义了（用户定义的）两种数据类型之间的转换，还可将同一转换用于这些数据类型的可为 null 的版本。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-130">If a user-defined conversion is defined between two data types, the same conversion can also be used with the nullable versions of these data types.</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="fd9bb-131">隐式转换</span><span class="sxs-lookup"><span data-stu-id="fd9bb-131">Implicit Conversions</span></span>  
 <span data-ttu-id="fd9bb-132">可以使用 `null` 关键字将可为 null 的类型的变量设置为 null，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="fd9bb-132">A variable of nullable type can be set to null with the `null` keyword, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]  
  
 <span data-ttu-id="fd9bb-133">普通类型到可为 null 的类型的转换是隐式的。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-133">The conversion from an ordinary type to a nullable type, is implicit.</span></span>  
  
 [!code-csharp[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]  
  
## <a name="operators"></a><span data-ttu-id="fd9bb-134">运算符</span><span class="sxs-lookup"><span data-stu-id="fd9bb-134">Operators</span></span>  
 <span data-ttu-id="fd9bb-135">可为 null 的类型还可使用预定义的一元运算符和二元运算符以及任何用于值类型的用户定义的运算符。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-135">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="fd9bb-136">如果操作数为 null，则这些运算符将产生一个 null 值；否则，运算符使用所包含的值来计算结果。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-136">These operators produce a null value if the operands are null; otherwise, the operator uses the contained value to calculate the result.</span></span> <span data-ttu-id="fd9bb-137">例如: </span><span class="sxs-lookup"><span data-stu-id="fd9bb-137">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]  
  
 <span data-ttu-id="fd9bb-138">将可为 null 的类型进行比较时，如果其中一个可以为 null 的类型的值为 null，而另一个为非 null，则除 `!=`（不等于）外，所有比较的计算结果均为 `false`。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-138">When you perform comparisons with nullable types, if the value of one of the nullable types is null and the other is not, all comparisons evaluate to `false` except for `!=` (not equal).</span></span> <span data-ttu-id="fd9bb-139">请勿假定由于某个特定的比较返回 `false`，则相反的情况下便会返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-139">It is important not to assume that because a particular comparison returns `false`, the opposite case returns `true`.</span></span> <span data-ttu-id="fd9bb-140">在下面的示例中，10 不大于、小于或等于 null。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-140">In the following example, 10 is not greater than, less than, nor equal to null.</span></span> <span data-ttu-id="fd9bb-141">仅 `num1 != num2` 的计算结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-141">Only `num1 != num2` evaluates to `true`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]  
  
 <span data-ttu-id="fd9bb-142">对两个均为 null 的可为 null 的类型进行相等比较，其计算结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-142">An equality comparison of two nullable types that are both null evaluates to `true`.</span></span>  
  
## <a name="the--operator"></a><span data-ttu-id="fd9bb-143">??</span><span class="sxs-lookup"><span data-stu-id="fd9bb-143">The ??</span></span> <span data-ttu-id="fd9bb-144">运算符</span><span class="sxs-lookup"><span data-stu-id="fd9bb-144">Operator</span></span>  
 <span data-ttu-id="fd9bb-145">`??` 运算符定义一个默认值，若将一个可为 null 的类型赋给不可为 null 的类型，则会返回该值。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-145">The `??` operator defines a default value that is returned when a nullable type is assigned to a non-nullable type.</span></span>  
  
 [!code-csharp[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]  
  
 <span data-ttu-id="fd9bb-146">此运算符还可与多个可为 null 的类型一起使用。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-146">This operator can also be used with multiple nullable types.</span></span> <span data-ttu-id="fd9bb-147">例如: </span><span class="sxs-lookup"><span data-stu-id="fd9bb-147">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]  
  
## <a name="the-bool-type"></a><span data-ttu-id="fd9bb-148">bool? 类型</span><span class="sxs-lookup"><span data-stu-id="fd9bb-148">The bool? type</span></span>  
 <span data-ttu-id="fd9bb-149">可以为 null 的类型 `bool?` 可包含三个不同的值：[true](../../../csharp/language-reference/keywords/true.md)、[false](../../../csharp/language-reference/keywords/false.md) 和 [null](../../../csharp/language-reference/keywords/null.md)。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-149">The `bool?` nullable type can contain three different values: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) and [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="fd9bb-150">若要了解如何将 bool? 转换为 bool，请参阅[如何：安全地将 bool? 转换为 bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md)。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-150">For information about how to cast from a bool? to a bool, see [How to: Safely Cast from bool? to bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span></span>  
  
 <span data-ttu-id="fd9bb-151">可为 null 的布尔值类似于在 SQL 中使用的布尔值变量类型。</span><span class="sxs-lookup"><span data-stu-id="fd9bb-151">Nullable Booleans are like the Boolean variable type that is used in SQL.</span></span> <span data-ttu-id="fd9bb-152">为确保 `&` 和 `|` 运算符产生的结果与 SQL 中具有三个值的布尔值类型一致，在此提供以下预定义运算符：</span><span class="sxs-lookup"><span data-stu-id="fd9bb-152">To ensure that the results produced by the `&` and `|` operators are consistent with the three-valued Boolean type in SQL, the following predefined operators are provided:</span></span>  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 <span data-ttu-id="fd9bb-153">下表列出了这些运算符的结果：</span><span class="sxs-lookup"><span data-stu-id="fd9bb-153">The results of these operators are listed in the following table:</span></span>  
  
|<span data-ttu-id="fd9bb-154">X</span><span class="sxs-lookup"><span data-stu-id="fd9bb-154">X</span></span>|<span data-ttu-id="fd9bb-155">y</span><span class="sxs-lookup"><span data-stu-id="fd9bb-155">y</span></span>|<span data-ttu-id="fd9bb-156">x&y</span><span class="sxs-lookup"><span data-stu-id="fd9bb-156">x&y</span></span>|<span data-ttu-id="fd9bb-157">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="fd9bb-157">x&#124;y</span></span>|  
|-------|-------|---------|--------------|  
|<span data-ttu-id="fd9bb-158">true</span><span class="sxs-lookup"><span data-stu-id="fd9bb-158">true</span></span>|<span data-ttu-id="fd9bb-159">true</span><span class="sxs-lookup"><span data-stu-id="fd9bb-159">true</span></span>|<span data-ttu-id="fd9bb-160">true</span><span class="sxs-lookup"><span data-stu-id="fd9bb-160">true</span></span>|<span data-ttu-id="fd9bb-161">true</span><span class="sxs-lookup"><span data-stu-id="fd9bb-161">true</span></span>|  
|<span data-ttu-id="fd9bb-162">true</span><span class="sxs-lookup"><span data-stu-id="fd9bb-162">true</span></span>|<span data-ttu-id="fd9bb-163">false</span><span class="sxs-lookup"><span data-stu-id="fd9bb-163">false</span></span>|<span data-ttu-id="fd9bb-164">false</span><span class="sxs-lookup"><span data-stu-id="fd9bb-164">false</span></span>|<span data-ttu-id="fd9bb-165">true</span><span class="sxs-lookup"><span data-stu-id="fd9bb-165">true</span></span>|  
|<span data-ttu-id="fd9bb-166">true</span><span class="sxs-lookup"><span data-stu-id="fd9bb-166">true</span></span>|<span data-ttu-id="fd9bb-167">null</span><span class="sxs-lookup"><span data-stu-id="fd9bb-167">null</span></span>|<span data-ttu-id="fd9bb-168">null</span><span class="sxs-lookup"><span data-stu-id="fd9bb-168">null</span></span>|<span data-ttu-id="fd9bb-169">true</span><span class="sxs-lookup"><span data-stu-id="fd9bb-169">true</span></span>|  
|<span data-ttu-id="fd9bb-170">false</span><span class="sxs-lookup"><span data-stu-id="fd9bb-170">false</span></span>|<span data-ttu-id="fd9bb-171">true</span><span class="sxs-lookup"><span data-stu-id="fd9bb-171">true</span></span>|<span data-ttu-id="fd9bb-172">false</span><span class="sxs-lookup"><span data-stu-id="fd9bb-172">false</span></span>|<span data-ttu-id="fd9bb-173">true</span><span class="sxs-lookup"><span data-stu-id="fd9bb-173">true</span></span>|  
|<span data-ttu-id="fd9bb-174">false</span><span class="sxs-lookup"><span data-stu-id="fd9bb-174">false</span></span>|<span data-ttu-id="fd9bb-175">false</span><span class="sxs-lookup"><span data-stu-id="fd9bb-175">false</span></span>|<span data-ttu-id="fd9bb-176">false</span><span class="sxs-lookup"><span data-stu-id="fd9bb-176">false</span></span>|<span data-ttu-id="fd9bb-177">false</span><span class="sxs-lookup"><span data-stu-id="fd9bb-177">false</span></span>|  
|<span data-ttu-id="fd9bb-178">false</span><span class="sxs-lookup"><span data-stu-id="fd9bb-178">false</span></span>|<span data-ttu-id="fd9bb-179">null</span><span class="sxs-lookup"><span data-stu-id="fd9bb-179">null</span></span>|<span data-ttu-id="fd9bb-180">false</span><span class="sxs-lookup"><span data-stu-id="fd9bb-180">false</span></span>|<span data-ttu-id="fd9bb-181">null</span><span class="sxs-lookup"><span data-stu-id="fd9bb-181">null</span></span>|  
|<span data-ttu-id="fd9bb-182">null</span><span class="sxs-lookup"><span data-stu-id="fd9bb-182">null</span></span>|<span data-ttu-id="fd9bb-183">true</span><span class="sxs-lookup"><span data-stu-id="fd9bb-183">true</span></span>|<span data-ttu-id="fd9bb-184">null</span><span class="sxs-lookup"><span data-stu-id="fd9bb-184">null</span></span>|<span data-ttu-id="fd9bb-185">true</span><span class="sxs-lookup"><span data-stu-id="fd9bb-185">true</span></span>|  
|<span data-ttu-id="fd9bb-186">null</span><span class="sxs-lookup"><span data-stu-id="fd9bb-186">null</span></span>|<span data-ttu-id="fd9bb-187">false</span><span class="sxs-lookup"><span data-stu-id="fd9bb-187">false</span></span>|<span data-ttu-id="fd9bb-188">false</span><span class="sxs-lookup"><span data-stu-id="fd9bb-188">false</span></span>|<span data-ttu-id="fd9bb-189">null</span><span class="sxs-lookup"><span data-stu-id="fd9bb-189">null</span></span>|  
|<span data-ttu-id="fd9bb-190">null</span><span class="sxs-lookup"><span data-stu-id="fd9bb-190">null</span></span>|<span data-ttu-id="fd9bb-191">null</span><span class="sxs-lookup"><span data-stu-id="fd9bb-191">null</span></span>|<span data-ttu-id="fd9bb-192">null</span><span class="sxs-lookup"><span data-stu-id="fd9bb-192">null</span></span>|<span data-ttu-id="fd9bb-193">null</span><span class="sxs-lookup"><span data-stu-id="fd9bb-193">null</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd9bb-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd9bb-194">See Also</span></span>  
 [<span data-ttu-id="fd9bb-195">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fd9bb-195">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fd9bb-196">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="fd9bb-196">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="fd9bb-197">装箱可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="fd9bb-197">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
 [<span data-ttu-id="fd9bb-198">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="fd9bb-198">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
