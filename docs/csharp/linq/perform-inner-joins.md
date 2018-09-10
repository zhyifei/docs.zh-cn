---
title: 执行内联（C# 中的 LINQ）
description: 了解如何使用 C# 中的 LINQ 执行内联。
ms.date: 12/1/2016
ms.assetid: 45bceed6-f549-4114-a9b1-b44feb497742
ms.openlocfilehash: 2f6aad30dc8278ce1bb88bacc19b27deaa0288c7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210125"
---
# <a name="perform-inner-joins"></a><span data-ttu-id="b918e-103">执行内部联接</span><span class="sxs-lookup"><span data-stu-id="b918e-103">Perform inner joins</span></span>

<span data-ttu-id="b918e-104">在关系数据库术语中，内部联接会生成一个结果集，在该结果集中，第一个集合的每个元素对于第二个集合中的每个匹配元素都会出现一次。</span><span class="sxs-lookup"><span data-stu-id="b918e-104">In relational database terms, an *inner join* produces a result set in which each element of the first collection appears one time for every matching element in the second collection.</span></span> <span data-ttu-id="b918e-105">如果第一个集合中的元素没有匹配元素，则它不会出现在结果集中。</span><span class="sxs-lookup"><span data-stu-id="b918e-105">If an element in the first collection has no matching elements, it does not appear in the result set.</span></span> <span data-ttu-id="b918e-106">由 C# 中的 `join` 子句调用的 <xref:System.Linq.Enumerable.Join%2A> 方法可实现内部联接。</span><span class="sxs-lookup"><span data-stu-id="b918e-106">The <xref:System.Linq.Enumerable.Join%2A> method, which is called by the `join` clause in C#, implements an inner join.</span></span>

<span data-ttu-id="b918e-107">本文演示如何执行内联的四种变体：</span><span class="sxs-lookup"><span data-stu-id="b918e-107">This article shows you how to perform four variations of an inner join:</span></span>

- <span data-ttu-id="b918e-108">基于简单键使两个数据源中的元素相关联的简单内部联接。</span><span class="sxs-lookup"><span data-stu-id="b918e-108">A simple inner join that correlates elements from two data sources based on a simple key.</span></span>

- <span data-ttu-id="b918e-109">基于复合键使两个数据源中的元素相关联的内部联接。</span><span class="sxs-lookup"><span data-stu-id="b918e-109">An inner join that correlates elements from two data sources based on a *composite* key.</span></span> <span data-ttu-id="b918e-110">复合键是由多个值组成的键，使你可以基于多个属性使元素相关联。</span><span class="sxs-lookup"><span data-stu-id="b918e-110">A composite key, which is a key that consists of more than one value, enables you to correlate elements based on more than one property.</span></span>

- <span data-ttu-id="b918e-111">在其中将连续联接操作相互追加的多联接。</span><span class="sxs-lookup"><span data-stu-id="b918e-111">A *multiple join* in which successive join operations are appended to each other.</span></span>

- <span data-ttu-id="b918e-112">使用分组联接实现的内部联接。</span><span class="sxs-lookup"><span data-stu-id="b918e-112">An inner join that is implemented by using a group join.</span></span>

## <a name="example---simple-key-join"></a><span data-ttu-id="b918e-113">示例 - 简单键联接</span><span class="sxs-lookup"><span data-stu-id="b918e-113">Example - Simple key join</span></span>

<span data-ttu-id="b918e-114">下面的示例创建两个集合，其中包含两种用户定义类型 `Person` 和 `Pet` 的对象。</span><span class="sxs-lookup"><span data-stu-id="b918e-114">The following example creates two collections that contain objects of two user-defined types, `Person` and `Pet`.</span></span> <span data-ttu-id="b918e-115">查询使用 C# 中的 `join` 子句将 `Person` 对象与 `Owner` 是该 `Person` 的 `Pet` 对象匹配。</span><span class="sxs-lookup"><span data-stu-id="b918e-115">The query uses the `join` clause in C# to match `Person` objects with `Pet` objects whose `Owner` is that `Person`.</span></span> <span data-ttu-id="b918e-116">C# 中的 `select` 子句定义结果对象的外观。</span><span class="sxs-lookup"><span data-stu-id="b918e-116">The `select` clause in C# defines how the resulting objects will look.</span></span> <span data-ttu-id="b918e-117">在此示例中，结果对象是由所有者名字和宠物姓名组成的匿名类型。</span><span class="sxs-lookup"><span data-stu-id="b918e-117">In this example the resulting objects are anonymous types that consist of the owner's first name and the pet's name.</span></span>

[!code-csharp[CsLINQProgJoining#1](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_1.cs)]

<span data-ttu-id="b918e-118">请注意，`LastName` 是“Huff”的 `Person` 对象未出现在结果集中，因为没有 `Pet` 对象的 `Pet.Owner` 等于该 `Person`。</span><span class="sxs-lookup"><span data-stu-id="b918e-118">Note that the `Person` object whose `LastName` is "Huff" does not appear in the result set because there is no `Pet` object that has `Pet.Owner` equal to that `Person`.</span></span>

## <a name="example---composite-key-join"></a><span data-ttu-id="b918e-119">示例 - 组合键联接</span><span class="sxs-lookup"><span data-stu-id="b918e-119">Example - Composite key join</span></span>

<span data-ttu-id="b918e-120">可以使用复合键基于多个属性来比较元素，而不是只基于一个属性使元素相关联。</span><span class="sxs-lookup"><span data-stu-id="b918e-120">Instead of correlating elements based on just one property, you can use a composite key to compare elements based on multiple properties.</span></span> <span data-ttu-id="b918e-121">为此，请为每个集合指定键选择器函数，以返回由要比较的属性组成的匿名类型。</span><span class="sxs-lookup"><span data-stu-id="b918e-121">To do this, specify the key selector function for each collection to return an anonymous type that consists of the properties you want to compare.</span></span> <span data-ttu-id="b918e-122">如果对属性进行标记，则它们必须在每个键的匿名类型中具有相同标签。</span><span class="sxs-lookup"><span data-stu-id="b918e-122">If you label the properties, they must have the same label in each key's anonymous type.</span></span> <span data-ttu-id="b918e-123">属性还必须按相同顺序出现。</span><span class="sxs-lookup"><span data-stu-id="b918e-123">The properties must also appear in the same order.</span></span>

<span data-ttu-id="b918e-124">下面的示例使用 `Employee` 对象的列表和 `Student` 对象的列表来确定哪些雇员同时还是学生。</span><span class="sxs-lookup"><span data-stu-id="b918e-124">The following example uses a list of `Employee` objects and a list of `Student` objects to determine which employees are also students.</span></span> <span data-ttu-id="b918e-125">这两种类型都具有 <xref:System.String> 类型的 `FirstName` 和 `LastName` 属性。</span><span class="sxs-lookup"><span data-stu-id="b918e-125">Both of these types have a `FirstName` and a `LastName` property of type <xref:System.String>.</span></span> <span data-ttu-id="b918e-126">通过每个列表的元素创建联接键的函数会返回由每个元素的 `FirstName` 和 `LastName` 属性组成的匿名类型。</span><span class="sxs-lookup"><span data-stu-id="b918e-126">The functions that create the join keys from each list's elements return an anonymous type that consists of the `FirstName` and `LastName` properties of each element.</span></span> <span data-ttu-id="b918e-127">联接运算会比较这些复合键是否相等，并从每个列表返回名字和姓氏都匹配的对象对。</span><span class="sxs-lookup"><span data-stu-id="b918e-127">The join operation compares these composite keys for equality and returns pairs of objects from each list where both the first name and the last name match.</span></span>

[!code-csharp[CsLINQProgJoining#2](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_2.cs)]

## <a name="example---multiple-join"></a><span data-ttu-id="b918e-128">示例 - 多联接</span><span class="sxs-lookup"><span data-stu-id="b918e-128">Example - Multiple join</span></span>

<span data-ttu-id="b918e-129">可以将任意数量的联接操作相互追加，以执行多联接。</span><span class="sxs-lookup"><span data-stu-id="b918e-129">Any number of join operations can be appended to each other to perform a multiple join.</span></span> <span data-ttu-id="b918e-130">C# 中的每个 `join` 子句会将指定数据源与上一个联接的结果相关联。</span><span class="sxs-lookup"><span data-stu-id="b918e-130">Each `join` clause in C# correlates a specified data source with the results of the previous join.</span></span>

<span data-ttu-id="b918e-131">下面的示例创建三个集合：`Person` 对象的列表、`Cat` 对象的列表和 `Dog` 对象的列表。</span><span class="sxs-lookup"><span data-stu-id="b918e-131">The following example creates three collections: a list of `Person` objects, a list of `Cat` objects, and a list of `Dog` objects.</span></span>

<span data-ttu-id="b918e-132">C# 中的第一个 `join` 子句基于与 `Cat.Owner` 匹配的 `Person` 对象来匹配人和猫。</span><span class="sxs-lookup"><span data-stu-id="b918e-132">The first `join` clause in C# matches people and cats based on a `Person` object matching `Cat.Owner`.</span></span> <span data-ttu-id="b918e-133">它返回包含 `Person` 对象和 `Cat.Name` 的匿名类型的序列。</span><span class="sxs-lookup"><span data-stu-id="b918e-133">It returns a sequence of anonymous types that contain the `Person` object and `Cat.Name`.</span></span>

<span data-ttu-id="b918e-134">C# 中的第二个 `join` 子句基于由 `Owner` 类型的 `Person` 属性和动物姓名的第一个字母组成的复合键，将第一个联接返回的匿名类型与提供的狗列表中的 `Dog` 对象相关联。</span><span class="sxs-lookup"><span data-stu-id="b918e-134">The second `join` clause in C# correlates the anonymous types returned by the first join with `Dog` objects in the supplied list of dogs, based on a composite key that consists of the `Owner` property of type `Person`, and the first letter of the animal's name.</span></span> <span data-ttu-id="b918e-135">它返回包含来自每个匹配对的 `Cat.Name` 和 `Dog.Name` 属性的匿名类型的序列。</span><span class="sxs-lookup"><span data-stu-id="b918e-135">It returns a sequence of anonymous types that contain the `Cat.Name` and `Dog.Name` properties from each matching pair.</span></span> <span data-ttu-id="b918e-136">由于这是内部联接，因此只返回第一个数据源中在第二个数据源中具有匹配项的对象。</span><span class="sxs-lookup"><span data-stu-id="b918e-136">Because this is an inner join, only those objects from the first data source that have a match in the second data source are returned.</span></span>

[!code-csharp[CsLINQProgJoining#3](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_3.cs)]

## <a name="example---inner-join-by-using-grouped-join"></a><span data-ttu-id="b918e-137">示例 - 使用分组联接的内联</span><span class="sxs-lookup"><span data-stu-id="b918e-137">Example - Inner join by using grouped join</span></span>

<span data-ttu-id="b918e-138">下面的示例演示如何使用分组联接实现内部联接。</span><span class="sxs-lookup"><span data-stu-id="b918e-138">The following example shows you how to implement an inner join by using a group join.</span></span>

<span data-ttu-id="b918e-139">在 `query1` 中，`Person` 对象的列表会基于与 `Pet.Owner` 属性匹配的 `Person`，分组联接到 `Pet` 对象队列中。</span><span class="sxs-lookup"><span data-stu-id="b918e-139">In `query1`, the list of `Person` objects is group-joined to the list of `Pet` objects based on the `Person` matching the `Pet.Owner` property.</span></span> <span data-ttu-id="b918e-140">分组联接会创建中间组的集合，其中每个组都包含 `Person` 对象和匹配 `Pet` 对象的序列。</span><span class="sxs-lookup"><span data-stu-id="b918e-140">The group join creates a collection of intermediate groups, where each group consists of a `Person` object and a sequence of matching `Pet` objects.</span></span>

<span data-ttu-id="b918e-141">通过向查询添加另一个 `from` 子句，此序列的序列会合并（或平展）为一个较长的序列。</span><span class="sxs-lookup"><span data-stu-id="b918e-141">By adding a second `from` clause to the query, this sequence of sequences is combined (or flattened) into one longer sequence.</span></span> <span data-ttu-id="b918e-142">最后一个序列的元素的类型由 `select` 子句指定。</span><span class="sxs-lookup"><span data-stu-id="b918e-142">The type of the elements of the final sequence is specified by the `select` clause.</span></span> <span data-ttu-id="b918e-143">在此示例中，该类型是由每个匹配对的 `Person.FirstName` 和 `Pet.Name` 属性组成的匿名类型。</span><span class="sxs-lookup"><span data-stu-id="b918e-143">In this example, that type is an anonymous type that consists of the `Person.FirstName` and `Pet.Name` properties for each matching pair.</span></span>

<span data-ttu-id="b918e-144">`query1` 的结果等效于通过使用 `join` 子句（不使用 `into` 子句）执行内部联接来获取的结果集。</span><span class="sxs-lookup"><span data-stu-id="b918e-144">The result of `query1` is equivalent to the result set that would have been obtained by using the `join` clause without the `into` clause to perform an inner join.</span></span> <span data-ttu-id="b918e-145">`query2` 变量演示了此等效查询。</span><span class="sxs-lookup"><span data-stu-id="b918e-145">The `query2` variable demonstrates this equivalent query.</span></span>

[!code-csharp[CsLINQProgJoining#4](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_4.cs)]

## <a name="see-also"></a><span data-ttu-id="b918e-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="b918e-146">See also</span></span>

- <xref:System.Linq.Enumerable.Join%2A>  
- <xref:System.Linq.Enumerable.GroupJoin%2A>  
- [<span data-ttu-id="b918e-147">执行分组联接</span><span class="sxs-lookup"><span data-stu-id="b918e-147">Perform grouped joins</span></span>](perform-grouped-joins.md)  
- [<span data-ttu-id="b918e-148">执行左外部联接</span><span class="sxs-lookup"><span data-stu-id="b918e-148">Perform left outer joins</span></span>](perform-left-outer-joins.md)  
- [<span data-ttu-id="b918e-149">匿名类型</span><span class="sxs-lookup"><span data-stu-id="b918e-149">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  