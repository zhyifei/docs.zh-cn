---
title: "在运行时动态指定谓词筛选器"
description: "如何在运行时动态指定谓词筛选器。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e724428bce09e2b2fa20b9391ad131424e16413
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="ff167-104">在运行时动态指定谓词筛选器</span><span class="sxs-lookup"><span data-stu-id="ff167-104">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="ff167-105">在某些情况下，在运行时之前你不知道必须将多少个谓词应用于 `where` 子句中的源元素。</span><span class="sxs-lookup"><span data-stu-id="ff167-105">In some cases you do not know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="ff167-106">动态指定多个谓词筛选器的方法之一是使用 <xref:System.Linq.Enumerable.Contains%2A> 方法，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="ff167-106">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="ff167-107">该示例通过两种方式构造。</span><span class="sxs-lookup"><span data-stu-id="ff167-107">The example is constructed in two ways.</span></span> <span data-ttu-id="ff167-108">首先，通过对程序中提供的值进行筛选来运行项目。</span><span class="sxs-lookup"><span data-stu-id="ff167-108">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="ff167-109">然后通过使用在运行时提供的输入再次运行该项目。</span><span class="sxs-lookup"><span data-stu-id="ff167-109">Then the project is run again by using input provided at run time.</span></span>  
  
## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="ff167-110">使用 Contains 方法进行筛选</span><span class="sxs-lookup"><span data-stu-id="ff167-110">To filter by using the Contains method</span></span>  
  
1.  <span data-ttu-id="ff167-111">打开一个新的控制台应用程序并将其命名为 `PredicateFilters`。</span><span class="sxs-lookup"><span data-stu-id="ff167-111">Open a new console application and name it `PredicateFilters`.</span></span>  
  
2.  <span data-ttu-id="ff167-112">从[查询对象的集合](query-a-collection-of-objects.md)复制 `StudentClass` 类，并将其粘贴到类 `Program` 下方的命名空间 `PredicateFilters`。</span><span class="sxs-lookup"><span data-stu-id="ff167-112">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="ff167-113">`StudentClass` 提供 `Student` 对象的列表。</span><span class="sxs-lookup"><span data-stu-id="ff167-113">`StudentClass` provides a list of `Student` objects.</span></span>  
  
3.  <span data-ttu-id="ff167-114">注释禁止 `StudentClass` 中的 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="ff167-114">Comment out the `Main` method in `StudentClass`.</span></span>  
  
4.  <span data-ttu-id="ff167-115">将类 `Program` 替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="ff167-115">Replace class `Program` with the following code.</span></span>  
  
     <span data-ttu-id="ff167-116">[!code-cs[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ff167-116">[!code-cs[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]</span></span>  
  
5.  <span data-ttu-id="ff167-117">将以下行添加到类 `DynamicPredicates` 中 `ids` 声明下的 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="ff167-117">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>  
  
     ```csharp
     QueryById(ids);
     ```

6.  <span data-ttu-id="ff167-118">运行该项目。</span><span class="sxs-lookup"><span data-stu-id="ff167-118">Run the project.</span></span>  
  
7.  <span data-ttu-id="ff167-119">在控制台窗口中显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="ff167-119">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="ff167-120">Garcia: 114</span><span class="sxs-lookup"><span data-stu-id="ff167-120">Garcia: 114</span></span>  
  
     <span data-ttu-id="ff167-121">O'Donnell: 112</span><span class="sxs-lookup"><span data-stu-id="ff167-121">O'Donnell: 112</span></span>  
  
     <span data-ttu-id="ff167-122">Omelchenko: 111</span><span class="sxs-lookup"><span data-stu-id="ff167-122">Omelchenko: 111</span></span>  
  
8.  <span data-ttu-id="ff167-123">下一步是再次运行该项目，此次是通过使用在运行时输入的输入而非数组 `ids` 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ff167-123">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="ff167-124">在 `Main` 方法中，将 `QueryByID(ids)` 更改为 `QueryByID(args)`。</span><span class="sxs-lookup"><span data-stu-id="ff167-124">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>  
  
9. <span data-ttu-id="ff167-125">使用命令行参数 `122 117 120 115` 运行该项目。</span><span class="sxs-lookup"><span data-stu-id="ff167-125">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="ff167-126">运行项目时，这些值将成为 `args` 的元素，它们是 `Main` 方法的参数。</span><span class="sxs-lookup"><span data-stu-id="ff167-126">When the project is run, those values become elements of `args`, the parameter of the `Main` method..</span></span>  
  
10. <span data-ttu-id="ff167-127">在控制台窗口中显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="ff167-127">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="ff167-128">Adams: 120</span><span class="sxs-lookup"><span data-stu-id="ff167-128">Adams: 120</span></span>  
  
     <span data-ttu-id="ff167-129">Feng: 117</span><span class="sxs-lookup"><span data-stu-id="ff167-129">Feng: 117</span></span>  
  
     <span data-ttu-id="ff167-130">Garcia: 115</span><span class="sxs-lookup"><span data-stu-id="ff167-130">Garcia: 115</span></span>  
  
     <span data-ttu-id="ff167-131">Tucker: 122</span><span class="sxs-lookup"><span data-stu-id="ff167-131">Tucker: 122</span></span>  
  
## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="ff167-132">使用 switch 语句进行筛选</span><span class="sxs-lookup"><span data-stu-id="ff167-132">To filter by using a switch statement</span></span>  
  
1.  <span data-ttu-id="ff167-133">可以使用 `switch` 语句在预先确定的备选查询中进行选择。</span><span class="sxs-lookup"><span data-stu-id="ff167-133">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="ff167-134">在下面的示例中，`studentQuery` 使用不同的 `where` 子句，具体取决于在运行时指定的等级级别或年。</span><span class="sxs-lookup"><span data-stu-id="ff167-134">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>  
  
2.  <span data-ttu-id="ff167-135">复制下面的方法，并将其粘贴到类 `DynamicPredicates`。</span><span class="sxs-lookup"><span data-stu-id="ff167-135">Copy the following method and paste it into class `DynamicPredicates`.</span></span>  
  
     <span data-ttu-id="ff167-136">[!code-cs[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ff167-136">[!code-cs[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]</span></span>  
  
3.  <span data-ttu-id="ff167-137">在 `Main` 方法中，将对 `QueryByID` 的调用替换为以下调用，该调用将 `args` 数组中的第一个元素作为其参数发送：`QueryByYear(args[0])`。</span><span class="sxs-lookup"><span data-stu-id="ff167-137">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>  
  
4.  <span data-ttu-id="ff167-138">运行该项目，其命令行参数为介于 1 和 4 之间的整数值。</span><span class="sxs-lookup"><span data-stu-id="ff167-138">Run the project with a command line argument of an integer value between 1 and 4.</span></span>  
  
 
## <a name="see-also"></a><span data-ttu-id="ff167-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff167-139">See Also</span></span>  
 <span data-ttu-id="ff167-140">[LINQ 查询表达式](index.md) </span><span class="sxs-lookup"><span data-stu-id="ff167-140">[LINQ Query Expressions](index.md) </span></span>  
 [<span data-ttu-id="ff167-141">where 子句</span><span class="sxs-lookup"><span data-stu-id="ff167-141">where clause</span></span>](../language-reference/keywords/where-clause.md)

