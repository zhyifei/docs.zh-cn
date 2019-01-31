---
title: 在运行时动态指定谓词筛选器（C# 中的 LINQ）
description: 了解如何使用 C# 中的 LINQ 在运行时动态指定谓词筛选器。
ms.date: 12/01/2016
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.openlocfilehash: 314be8f98b9ff014f14bef11a1f3581eff8574b4
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857731"
---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="4c56b-103">在运行时动态指定谓词筛选器</span><span class="sxs-lookup"><span data-stu-id="4c56b-103">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="4c56b-104">在某些情况下，在运行时之前你不知道必须将多少个谓词应用于 `where` 子句中的源元素。</span><span class="sxs-lookup"><span data-stu-id="4c56b-104">In some cases, you don't know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="4c56b-105">动态指定多个谓词筛选器的方法之一是使用 <xref:System.Linq.Enumerable.Contains%2A> 方法，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="4c56b-105">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="4c56b-106">该示例通过两种方式构造。</span><span class="sxs-lookup"><span data-stu-id="4c56b-106">The example is constructed in two ways.</span></span> <span data-ttu-id="4c56b-107">首先，通过对程序中提供的值进行筛选来运行项目。</span><span class="sxs-lookup"><span data-stu-id="4c56b-107">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="4c56b-108">然后通过使用在运行时提供的输入再次运行该项目。</span><span class="sxs-lookup"><span data-stu-id="4c56b-108">Then the project is run again by using input provided at run time.</span></span>

## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="4c56b-109">使用 Contains 方法进行筛选</span><span class="sxs-lookup"><span data-stu-id="4c56b-109">To filter by using the Contains method</span></span>

1. <span data-ttu-id="4c56b-110">打开一个新的控制台应用程序并将其命名为 `PredicateFilters`。</span><span class="sxs-lookup"><span data-stu-id="4c56b-110">Open a new console application and name it `PredicateFilters`.</span></span>

2. <span data-ttu-id="4c56b-111">从[查询对象的集合](query-a-collection-of-objects.md)复制 `StudentClass` 类，并将其粘贴到类 `Program` 下方的命名空间 `PredicateFilters`。</span><span class="sxs-lookup"><span data-stu-id="4c56b-111">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="4c56b-112">`StudentClass` 提供 `Student` 对象的列表。</span><span class="sxs-lookup"><span data-stu-id="4c56b-112">`StudentClass` provides a list of `Student` objects.</span></span>

3. <span data-ttu-id="4c56b-113">注释禁止 `StudentClass` 中的 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="4c56b-113">Comment out the `Main` method in `StudentClass`.</span></span>

4. <span data-ttu-id="4c56b-114">将类 `Program` 替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="4c56b-114">Replace class `Program` with the following code:</span></span>

     [!code-csharp[csProgGuideLINQ#26](~/samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]

5. <span data-ttu-id="4c56b-115">将以下行添加到类 `DynamicPredicates` 中 `ids` 声明下的 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="4c56b-115">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>

     ```csharp
     QueryById(ids);
     ```

6. <span data-ttu-id="4c56b-116">运行该项目。</span><span class="sxs-lookup"><span data-stu-id="4c56b-116">Run the project.</span></span>

7. <span data-ttu-id="4c56b-117">在控制台窗口中显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="4c56b-117">The following output is displayed in a console window:</span></span>

     <span data-ttu-id="4c56b-118">Garcia:114</span><span class="sxs-lookup"><span data-stu-id="4c56b-118">Garcia: 114</span></span>

     <span data-ttu-id="4c56b-119">O'Donnell:112</span><span class="sxs-lookup"><span data-stu-id="4c56b-119">O'Donnell: 112</span></span>

     <span data-ttu-id="4c56b-120">Omelchenko:111</span><span class="sxs-lookup"><span data-stu-id="4c56b-120">Omelchenko: 111</span></span>

8. <span data-ttu-id="4c56b-121">下一步是再次运行该项目，此次是通过使用在运行时输入的输入而非数组 `ids` 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4c56b-121">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="4c56b-122">在 `Main` 方法中，将 `QueryByID(ids)` 更改为 `QueryByID(args)`。</span><span class="sxs-lookup"><span data-stu-id="4c56b-122">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>

9. <span data-ttu-id="4c56b-123">使用命令行参数 `122 117 120 115` 运行该项目。</span><span class="sxs-lookup"><span data-stu-id="4c56b-123">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="4c56b-124">运行项目时，这些值将成为 `args` 的元素，它们是 `Main` 方法的参数。</span><span class="sxs-lookup"><span data-stu-id="4c56b-124">When the project is run, those values become elements of `args`, the parameter of the `Main` method.</span></span>

10. <span data-ttu-id="4c56b-125">在控制台窗口中显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="4c56b-125">The following output is displayed in a console window:</span></span>

     <span data-ttu-id="4c56b-126">Adams:120</span><span class="sxs-lookup"><span data-stu-id="4c56b-126">Adams: 120</span></span>

     <span data-ttu-id="4c56b-127">Feng:117</span><span class="sxs-lookup"><span data-stu-id="4c56b-127">Feng: 117</span></span>

     <span data-ttu-id="4c56b-128">Garcia:115</span><span class="sxs-lookup"><span data-stu-id="4c56b-128">Garcia: 115</span></span>

     <span data-ttu-id="4c56b-129">Tucker:122</span><span class="sxs-lookup"><span data-stu-id="4c56b-129">Tucker: 122</span></span>

## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="4c56b-130">使用 switch 语句进行筛选</span><span class="sxs-lookup"><span data-stu-id="4c56b-130">To filter by using a switch statement</span></span>

1. <span data-ttu-id="4c56b-131">可以使用 `switch` 语句在预先确定的备选查询中进行选择。</span><span class="sxs-lookup"><span data-stu-id="4c56b-131">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="4c56b-132">在下面的示例中，`studentQuery` 使用不同的 `where` 子句，具体取决于在运行时指定的等级级别或年。</span><span class="sxs-lookup"><span data-stu-id="4c56b-132">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>

2. <span data-ttu-id="4c56b-133">复制下面的方法，并将其粘贴到类 `DynamicPredicates`。</span><span class="sxs-lookup"><span data-stu-id="4c56b-133">Copy the following method and paste it into class `DynamicPredicates`.</span></span>

     [!code-csharp[csProgGuideLINQ#27](~/samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]

3. <span data-ttu-id="4c56b-134">在 `Main` 方法中，将对 `QueryByID` 的调用替换为以下调用，该调用将 `args` 数组中的第一个元素作为其参数发送：`QueryByYear(args[0])`。</span><span class="sxs-lookup"><span data-stu-id="4c56b-134">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>

4. <span data-ttu-id="4c56b-135">运行该项目，其命令行参数为介于 1 和 4 之间的整数值。</span><span class="sxs-lookup"><span data-stu-id="4c56b-135">Run the project with a command line argument of an integer value between 1 and 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c56b-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c56b-136">See also</span></span>

- [<span data-ttu-id="4c56b-137">语言集成查询 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="4c56b-137">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="4c56b-138">where 子句</span><span class="sxs-lookup"><span data-stu-id="4c56b-138">where clause</span></span>](../language-reference/keywords/where-clause.md)
