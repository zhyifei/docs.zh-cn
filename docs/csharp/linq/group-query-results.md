---
title: "对查询结果进行分组"
description: "如何对结果进行分组。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2e4ec27f-06fb-4de7-8973-0189906d4520
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1c1639651699afbe5fb768db26b98a9b2d734315
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="group-query-results"></a><span data-ttu-id="4da0d-104">对查询结果进行分组</span><span class="sxs-lookup"><span data-stu-id="4da0d-104">Group query results</span></span>

<span data-ttu-id="4da0d-105">分组是 LINQ 最强大的功能之一。</span><span class="sxs-lookup"><span data-stu-id="4da0d-105">Grouping is one of the most powerful capabilities of LINQ.</span></span> <span data-ttu-id="4da0d-106">以下示例演示如何以各种方式对数据进行分组：</span><span class="sxs-lookup"><span data-stu-id="4da0d-106">The following examples show how to group data in various ways:</span></span>  
  
-   <span data-ttu-id="4da0d-107">依据单个属性。</span><span class="sxs-lookup"><span data-stu-id="4da0d-107">By a single property.</span></span>  
  
-   <span data-ttu-id="4da0d-108">依据字符串属性的首字母。</span><span class="sxs-lookup"><span data-stu-id="4da0d-108">By the first letter of a string property.</span></span>  
  
-   <span data-ttu-id="4da0d-109">依据计算出的数值范围。</span><span class="sxs-lookup"><span data-stu-id="4da0d-109">By a computed numeric range.</span></span>  
  
-   <span data-ttu-id="4da0d-110">依据布尔谓词或其他表达式。</span><span class="sxs-lookup"><span data-stu-id="4da0d-110">By Boolean predicate or other expression.</span></span>  
  
-   <span data-ttu-id="4da0d-111">依据组合键。</span><span class="sxs-lookup"><span data-stu-id="4da0d-111">By a compound key.</span></span>  
  
 <span data-ttu-id="4da0d-112">此外，最后两个查询将其结果投影到一个新的匿名类型中，该类型仅包含学生的名字和姓氏。</span><span class="sxs-lookup"><span data-stu-id="4da0d-112">In addition, the last two queries project their results into a new anonymous type that contains only the student's first and last name.</span></span> <span data-ttu-id="4da0d-113">有关详细信息，请参阅 [group 子句](../language-reference/keywords/group-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="4da0d-113">For more information, see the [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4da0d-114">示例</span><span class="sxs-lookup"><span data-stu-id="4da0d-114">Example</span></span>  
 <span data-ttu-id="4da0d-115">本主题中的所有示例都使用下列帮助程序类和数据源。</span><span class="sxs-lookup"><span data-stu-id="4da0d-115">All the examples in this topic use the following helper classes and data sources.</span></span>  
  
 <span data-ttu-id="4da0d-116">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4da0d-116">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4da0d-117">示例</span><span class="sxs-lookup"><span data-stu-id="4da0d-117">Example</span></span>  
 <span data-ttu-id="4da0d-118">以下示例演示如何通过使用元素的单个属性作为分组键对源元素进行分组。</span><span class="sxs-lookup"><span data-stu-id="4da0d-118">The following example shows how to group source elements by using a single property of the element as the group key.</span></span> <span data-ttu-id="4da0d-119">在此示例中，键是 `string`，即学生的姓氏。</span><span class="sxs-lookup"><span data-stu-id="4da0d-119">In this case the key is a `string`, the student's last name.</span></span> <span data-ttu-id="4da0d-120">还可以使用子字符串作为键。</span><span class="sxs-lookup"><span data-stu-id="4da0d-120">It is also possible to use a substring for the key.</span></span> <span data-ttu-id="4da0d-121">分组操作对该类型使用默认的相等比较器。</span><span class="sxs-lookup"><span data-stu-id="4da0d-121">The grouping operation uses the default equality comparer for the type.</span></span>  
  
 <span data-ttu-id="4da0d-122">将以下方法粘贴到 `StudentClass` 类。</span><span class="sxs-lookup"><span data-stu-id="4da0d-122">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="4da0d-123">将 `Main` 方法中的调用语句更改为 `sc.GroupBySingleProperty()`。</span><span class="sxs-lookup"><span data-stu-id="4da0d-123">Change the calling statement in the `Main` method to `sc.GroupBySingleProperty()`.</span></span>  
  
 <span data-ttu-id="4da0d-124">[!code-cs[csProgGuideLINQ#17](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4da0d-124">[!code-cs[csProgGuideLINQ#17](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4da0d-125">示例</span><span class="sxs-lookup"><span data-stu-id="4da0d-125">Example</span></span>  
 <span data-ttu-id="4da0d-126">下例演示如何通过使用除对象属性以外的某个项作为分组键对源元素进行分组。</span><span class="sxs-lookup"><span data-stu-id="4da0d-126">The following example shows how to group source elements by using something other than a property of the object for the group key.</span></span> <span data-ttu-id="4da0d-127">在此示例中，键是学生姓氏的第一个字母。</span><span class="sxs-lookup"><span data-stu-id="4da0d-127">In this example, the key is the first letter of the student's last name.</span></span>  
  
 <span data-ttu-id="4da0d-128">将以下方法粘贴到 `StudentClass` 类。</span><span class="sxs-lookup"><span data-stu-id="4da0d-128">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="4da0d-129">将 `Main` 方法中的调用语句更改为 `sc.GroupBySubstring()`。</span><span class="sxs-lookup"><span data-stu-id="4da0d-129">Change the calling statement in the `Main` method to `sc.GroupBySubstring()`.</span></span>  
  
 <span data-ttu-id="4da0d-130">[!code-cs[csProgGuideLINQ#18](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="4da0d-130">[!code-cs[csProgGuideLINQ#18](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4da0d-131">示例</span><span class="sxs-lookup"><span data-stu-id="4da0d-131">Example</span></span>  
 <span data-ttu-id="4da0d-132">以下示例演示如何通过使用某个数值范围作为分组键对源元素进行分组。</span><span class="sxs-lookup"><span data-stu-id="4da0d-132">The following example shows how to group source elements by using a numeric range as a group key.</span></span> <span data-ttu-id="4da0d-133">然后，查询将结果投影到一个匿名类型中，该类型仅包含学生的名字和姓氏以及该学生所属的百分点范围。</span><span class="sxs-lookup"><span data-stu-id="4da0d-133">The query then projects the results into an anonymous type that contains only the first and last name and the percentile range to which the student belongs.</span></span> <span data-ttu-id="4da0d-134">使用匿名类型的原因是没有必要使用完整的 `Student` 对象来显示结果。</span><span class="sxs-lookup"><span data-stu-id="4da0d-134">An anonymous type is used because it is not necessary to use the complete `Student` object to display the results.</span></span> <span data-ttu-id="4da0d-135">`GetPercentile` 是一个帮助程序函数，它根据学生的平均分数计算百分比。</span><span class="sxs-lookup"><span data-stu-id="4da0d-135">`GetPercentile` is a helper function that calculates a percentile based on the student's average score.</span></span> <span data-ttu-id="4da0d-136">该方法返回 0 到 10 之间的整数。</span><span class="sxs-lookup"><span data-stu-id="4da0d-136">The method returns an integer between 0 and 10.</span></span>  
  
 <span data-ttu-id="4da0d-137">[!code-cs[csProgGuideLINQ#50](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="4da0d-137">[!code-cs[csProgGuideLINQ#50](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]</span></span>  
  
 <span data-ttu-id="4da0d-138">将以下方法粘贴到 `StudentClass` 类。</span><span class="sxs-lookup"><span data-stu-id="4da0d-138">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="4da0d-139">将 `Main` 方法中的调用语句更改为 `sc.GroupByRange()`。</span><span class="sxs-lookup"><span data-stu-id="4da0d-139">Change the calling statement in the `Main` method to `sc.GroupByRange()`.</span></span>  
  
 <span data-ttu-id="4da0d-140">[!code-cs[csProgGuideLINQ#19](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="4da0d-140">[!code-cs[csProgGuideLINQ#19](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4da0d-141">示例</span><span class="sxs-lookup"><span data-stu-id="4da0d-141">Example</span></span>  
 <span data-ttu-id="4da0d-142">以下示例演示如何通过使用布尔比较表达式对源元素进行分组。</span><span class="sxs-lookup"><span data-stu-id="4da0d-142">The following example shows how to group source elements by using a Boolean comparison expression.</span></span> <span data-ttu-id="4da0d-143">在此示例中，布尔表达式会测试学生的平均考试分数是否超过 75。</span><span class="sxs-lookup"><span data-stu-id="4da0d-143">In this example, the Boolean expression tests whether a student's average exam score is greater than 75.</span></span> <span data-ttu-id="4da0d-144">与上述示例一样，结果被投影到一个匿名类型中，因为不需要完整的源元素。</span><span class="sxs-lookup"><span data-stu-id="4da0d-144">As in previous examples, the results are projected into an anonymous type because the complete source element is not needed.</span></span> <span data-ttu-id="4da0d-145">请注意，执行查询时，该匿名类型中的属性会变成 `Key` 成员上的属性，并且可以通过名称进行访问。</span><span class="sxs-lookup"><span data-stu-id="4da0d-145">Note that the properties in the anonymous type become properties on the `Key` member and can be accessed by name when the query is executed.</span></span>  
  
 <span data-ttu-id="4da0d-146">将以下方法粘贴到 `StudentClass` 类。</span><span class="sxs-lookup"><span data-stu-id="4da0d-146">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="4da0d-147">将 `Main` 方法中的调用语句更改为 `sc.GroupByBoolean()`。</span><span class="sxs-lookup"><span data-stu-id="4da0d-147">Change the calling statement in the `Main` method to `sc.GroupByBoolean()`.</span></span>  
  
 <span data-ttu-id="4da0d-148">[!code-cs[csProgGuideLINQ#20](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="4da0d-148">[!code-cs[csProgGuideLINQ#20](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4da0d-149">示例</span><span class="sxs-lookup"><span data-stu-id="4da0d-149">Example</span></span>  
 <span data-ttu-id="4da0d-150">以下示例演示如何使用匿名类型来封装包含多个值的键。</span><span class="sxs-lookup"><span data-stu-id="4da0d-150">The following example shows how to use an anonymous type to encapsulate a key that contains multiple values.</span></span> <span data-ttu-id="4da0d-151">在此示例中，第一个键值是学生姓氏的第一个字母。</span><span class="sxs-lookup"><span data-stu-id="4da0d-151">In this example, the first key value is the first letter of the student's last name.</span></span> <span data-ttu-id="4da0d-152">第二个键值是一个布尔值，指定该学生在第一次考试中的得分是否超过了 85。</span><span class="sxs-lookup"><span data-stu-id="4da0d-152">The second key value is a Boolean that specifies whether the student scored over 85 on the first exam.</span></span> <span data-ttu-id="4da0d-153">可以按照该键中的任何属性对组进行排序。</span><span class="sxs-lookup"><span data-stu-id="4da0d-153">You can order the groups by any property in the key.</span></span>  
  
 <span data-ttu-id="4da0d-154">将以下方法粘贴到 `StudentClass` 类。</span><span class="sxs-lookup"><span data-stu-id="4da0d-154">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="4da0d-155">将 `Main` 方法中的调用语句更改为 `sc.GroupByCompositeKey()`。</span><span class="sxs-lookup"><span data-stu-id="4da0d-155">Change the calling statement in the `Main` method to `sc.GroupByCompositeKey()`.</span></span>  
  
 <span data-ttu-id="4da0d-156">[!code-cs[csProgGuideLINQ#21](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="4da0d-156">[!code-cs[csProgGuideLINQ#21](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da0d-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="4da0d-157">See also</span></span>  
 <span data-ttu-id="4da0d-158"><xref:System.Linq.Enumerable.GroupBy%2A></span><span class="sxs-lookup"><span data-stu-id="4da0d-158"><xref:System.Linq.Enumerable.GroupBy%2A></span></span>   
 <span data-ttu-id="4da0d-159"><xref:System.Linq.IGrouping%602></span><span class="sxs-lookup"><span data-stu-id="4da0d-159"><xref:System.Linq.IGrouping%602></span></span>   
 <span data-ttu-id="4da0d-160">[LINQ 查询表达式](index.md) </span><span class="sxs-lookup"><span data-stu-id="4da0d-160">[LINQ Query Expressions](index.md) </span></span>  
 <span data-ttu-id="4da0d-161">[group 子句](../language-reference/keywords/group-clause.md) </span><span class="sxs-lookup"><span data-stu-id="4da0d-161">[group clause](../language-reference/keywords/group-clause.md) </span></span>  
 <span data-ttu-id="4da0d-162">[匿名类型](../programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="4da0d-162">[Anonymous Types](../programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="4da0d-163">[对分组操作执行子查询](perform-a-subquery-on-a-grouping-operation.md) </span><span class="sxs-lookup"><span data-stu-id="4da0d-163">[Perform a Subquery on a Grouping Operation](perform-a-subquery-on-a-grouping-operation.md) </span></span>  
 <span data-ttu-id="4da0d-164">[创建嵌套组](create-a-nested-group.md) </span><span class="sxs-lookup"><span data-stu-id="4da0d-164">[Create a Nested Group](create-a-nested-group.md) </span></span>  
 [<span data-ttu-id="4da0d-165">数据分组</span><span class="sxs-lookup"><span data-stu-id="4da0d-165">Grouping Data</span></span>](../programming-guide/concepts/linq/grouping-data.md)

