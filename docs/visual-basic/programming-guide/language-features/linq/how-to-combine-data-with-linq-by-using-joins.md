---
title: "如何：通过 LINQ 使用联接合并数据 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 432be646ce4353fd4627a34f363e7562f6181e92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a><span data-ttu-id="d2cb7-102">如何：通过 LINQ 使用联接合并数据 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2cb7-102">How to: Combine Data with LINQ by Using Joins (Visual Basic)</span></span>
<span data-ttu-id="d2cb7-103">Visual Basic 提供`Join`和`Group Join`查询子句以使您能够合并根据集合之间的常见值的多个集合的内容。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-103">Visual Basic provides the `Join` and `Group Join` query clauses to enable you to combine the contents of multiple collections based on common values between the collections.</span></span> <span data-ttu-id="d2cb7-104">这些值称为*密钥*值。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-104">These values are known as *key* values.</span></span> <span data-ttu-id="d2cb7-105">开发人员熟悉关系数据库概念将识别`Join`作为 INNER JOIN 子句和`Group Join`作为，实际上，LEFT OUTER JOIN 子句。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-105">Developers familiar with relational database concepts will recognize the `Join` clause as an INNER JOIN and the `Group Join` clause as, effectively, a LEFT OUTER JOIN.</span></span>  
  
 <span data-ttu-id="d2cb7-106">本主题中的示例演示几种方法可以通过使用组合数据`Join`和`Group Join`查询子句。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-106">The examples in this topic demonstrate a few ways to combine data by using the `Join` and `Group Join` query clauses.</span></span>  
  
## <a name="create-a-project-and-add-sample-data"></a><span data-ttu-id="d2cb7-107">创建项目并添加示例数据</span><span class="sxs-lookup"><span data-stu-id="d2cb7-107">Create a Project and Add Sample Data</span></span>  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a><span data-ttu-id="d2cb7-108">若要创建包含示例数据和类型的项目</span><span class="sxs-lookup"><span data-stu-id="d2cb7-108">To create a project that contains sample data and types</span></span>  
  
1.  <span data-ttu-id="d2cb7-109">若要运行本主题中的这些示例，请打开 Visual Studio，并添加新的 Visual Basic 控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-109">To run the samples in this topic, open Visual Studio and add a new Visual Basic Console Application project.</span></span> <span data-ttu-id="d2cb7-110">双击创建 Visual Basic 的 Module1.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-110">Double-click the Module1.vb file created by Visual Basic.</span></span>  
  
2.  <span data-ttu-id="d2cb7-111">在此主题使用示例`Person`和`Pet`类型和数据从下面的代码示例。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-111">The samples in this topic use the `Person` and `Pet` types and data from the following code example.</span></span> <span data-ttu-id="d2cb7-112">将此代码复制到默认值`Module1`由 Visual Basic 创建的模块。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-112">Copy this code into the default `Module1` module created by Visual Basic.</span></span>  
  
     [!code-vb[VbLINQHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_1.vb)]  
    [!code-vb[VbLINQHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_2.vb)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="d2cb7-113">通过使用联接子句执行内部联接</span><span class="sxs-lookup"><span data-stu-id="d2cb7-113">Perform an Inner Join by Using the Join Clause</span></span>  
 <span data-ttu-id="d2cb7-114">INNER JOIN 将合并两个集合中的数据。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-114">An INNER JOIN combines data from two collections.</span></span> <span data-ttu-id="d2cb7-115">要包含指定的键值与匹配的项。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-115">Items for which the specified key values match are included.</span></span> <span data-ttu-id="d2cb7-116">排除其他集合中没有匹配项的任一集合中的任何项。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-116">Any items from either collection that do not have a matching item in the other collection are excluded.</span></span>  
  
 <span data-ttu-id="d2cb7-117">在 Visual Basic 中，LINQ 提供执行内部联接的两个选项： 隐式联接和显式联接。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-117">In Visual Basic, LINQ provides two options for performing an INNER JOIN: an implicit join and an explicit join.</span></span>  
  
 <span data-ttu-id="d2cb7-118">隐式联接指定要在中联接的集合`From`子句和标识中的匹配键字段`Where`子句。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-118">An implicit join specifies the collections to be joined in a `From` clause and identifies the matching key fields in a `Where` clause.</span></span> <span data-ttu-id="d2cb7-119">Visual Basic 隐式联接两个基于指定的键字段的集合。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-119">Visual Basic implicitly joins the two collections based on the specified key fields.</span></span>  
  
 <span data-ttu-id="d2cb7-120">你可以通过使用指定显式联接`Join`子句时你想要特定有关要在联接中使用的键字段。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-120">You can specify an explicit join by using the `Join` clause when you want to be specific about which key fields to use in the join.</span></span> <span data-ttu-id="d2cb7-121">在这种情况下，`Where`仍可以使用子句来筛选查询结果。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-121">In this case, a `Where` clause can still be used to filter the query results.</span></span>  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="d2cb7-122">若要通过使用联接子句执行 Inner Join</span><span class="sxs-lookup"><span data-stu-id="d2cb7-122">To perform an Inner Join by using the Join clause</span></span>  
  
1.  <span data-ttu-id="d2cb7-123">以下代码添加到`Module1`项目以查看这两个隐式和显式内部联接的示例中的模块。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-123">Add the following code to the `Module1` module in your project to see examples of both an implicit and explicit inner join.</span></span>  
  
     [!code-vb[VbLINQHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_3.vb)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="d2cb7-124">通过使用 Group Join 子句执行左外部联接</span><span class="sxs-lookup"><span data-stu-id="d2cb7-124">Perform a Left Outer Join by Using the Group Join Clause</span></span>  
 <span data-ttu-id="d2cb7-125">LEFT OUTER JOIN 包括所有集合中的项左侧的联接和仅匹配中的联接的右侧集合的值。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-125">A LEFT OUTER JOIN includes all the items from the left-side collection of the join and only matching values from the right-side collection of the join.</span></span> <span data-ttu-id="d2cb7-126">从查询结果中排除任何联接的右侧集合中的项左侧集合中没有匹配项。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-126">Any items from the right-side collection of the join that do not have a matching item in the left-side collection are excluded from the query result.</span></span>  
  
 <span data-ttu-id="d2cb7-127">`Group Join`子句执行时，实际上，左外部联接。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-127">The `Group Join` clause performs, in effect, a LEFT OUTER JOIN.</span></span> <span data-ttu-id="d2cb7-128">新增功能通常称为 LEFT OUTER JOIN 和之间的差异`Group Join`子句将返回在于`Group Join`从右侧集合的每个集合中的项左侧的联接子句组结果。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-128">The difference between what is typically known as a LEFT OUTER JOIN and what the `Group Join` clause returns is that the `Group Join` clause groups results from the right-side collection of the join for each item in the left-side collection.</span></span> <span data-ttu-id="d2cb7-129">在关系数据库中，左外部联接返回在其中查询中的每个项导致了未分组的结果包含在联接两个集合中的匹配项。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-129">In a relational database, a LEFT OUTER JOIN returns an ungrouped result in which each item in the query result contains matching items from both collections in the join.</span></span> <span data-ttu-id="d2cb7-130">在这种情况下，从联接的左侧集合项的从右侧集合的每个匹配项都重复。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-130">In this case, the items from the left-side collection of the join are repeated for each matching item from the right-side collection.</span></span> <span data-ttu-id="d2cb7-131">你将看到这种情况下一个过程完成。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-131">You will see what this looks like when you complete the next procedure.</span></span>  
  
 <span data-ttu-id="d2cb7-132">你可以检索的结果`Group Join`通过扩展你的查询以返回某个项的每个分组的查询结果未分组结果的查询。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-132">You can retrieve the results of a `Group Join` query as an ungrouped result by extending your query to return an item for each grouped query result.</span></span> <span data-ttu-id="d2cb7-133">若要实现此目的，你必须确保您查询在`DefaultIfEmpty`分组的集合的方法。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-133">To accomplish this, you have to ensure that you query on the `DefaultIfEmpty` method of the grouped collection.</span></span> <span data-ttu-id="d2cb7-134">这可确保到仍查询结果中包含联接的左侧集合中的项即使它们具有从右侧集合没有匹配结果。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-134">This ensures that items from the left-side collection of the join are still included in the query result even if they have no matching results from the right-side collection.</span></span> <span data-ttu-id="d2cb7-135">可以将代码添加到你的查询以从联接的右侧集合没有匹配值时提供默认结果值。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-135">You can add code to your query to provide a default result value when there is no matching value from the right-side collection of the join.</span></span>  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="d2cb7-136">若要通过使用 Group Join 子句执行左外部联接</span><span class="sxs-lookup"><span data-stu-id="d2cb7-136">To perform a Left Outer Join by using the Group Join clause</span></span>  
  
1.  <span data-ttu-id="d2cb7-137">以下代码添加到`Module1`项目以查看分组左外部联接和未分组的左外部联接的示例中的模块。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-137">Add the following code to the `Module1` module in your project to see examples of both a grouped left outer join and an ungrouped left outer join.</span></span>  
  
     [!code-vb[VbLINQHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_4.vb)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="d2cb7-138">通过使用复合键执行联接</span><span class="sxs-lookup"><span data-stu-id="d2cb7-138">Perform a Join by Using a Composite Key</span></span>  
 <span data-ttu-id="d2cb7-139">你可以使用`And`中的关键字`Join`或`Group Join`子句，以此标识匹配时要使用的多个键字段中被联接集合的值。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-139">You can use the `And` keyword in a `Join` or `Group Join` clause to identify multiple key fields to use when matching values from the collections being joined.</span></span> <span data-ttu-id="d2cb7-140">`And`关键字指定所有指定的键字段都必须匹配要联接的项。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-140">The `And` keyword specifies that all specified key fields must match for items to be joined.</span></span>  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="d2cb7-141">若要通过使用复合键执行联接</span><span class="sxs-lookup"><span data-stu-id="d2cb7-141">To perform a Join by using a composite key</span></span>  
  
1.  <span data-ttu-id="d2cb7-142">以下代码添加到`Module1`项目若要查看的一种联接，使用复合键的示例中的模块。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-142">Add the following code to the `Module1` module in your project to see examples of a join that uses a composite key.</span></span>  
  
     [!code-vb[VbLINQHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_5.vb)]  
  
## <a name="run-the-code"></a><span data-ttu-id="d2cb7-143">运行代码</span><span class="sxs-lookup"><span data-stu-id="d2cb7-143">Run the Code</span></span>  
  
#### <a name="to-add-code-to-run-the-examples"></a><span data-ttu-id="d2cb7-144">若要添加代码以运行示例</span><span class="sxs-lookup"><span data-stu-id="d2cb7-144">To add code to run the examples</span></span>  
  
1.  <span data-ttu-id="d2cb7-145">替换`Sub Main`中`Module1`替换为以下代码，若要运行本主题中的示例项目中的模块。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-145">Replace the `Sub Main` in the `Module1` module in your project with the following code to run the examples in this topic.</span></span>  
  
     [!code-vb[VbLINQHowTos#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_6.vb)]  
  
2.  <span data-ttu-id="d2cb7-146">按 f5 键以运行这些示例。</span><span class="sxs-lookup"><span data-stu-id="d2cb7-146">Press F5 to run the examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2cb7-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2cb7-147">See Also</span></span>  
 [<span data-ttu-id="d2cb7-148">LINQ</span><span class="sxs-lookup"><span data-stu-id="d2cb7-148">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="d2cb7-149">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="d2cb7-149">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="d2cb7-150">Join 子句</span><span class="sxs-lookup"><span data-stu-id="d2cb7-150">Join Clause</span></span>](../../../../visual-basic/language-reference/queries/join-clause.md)  
 [<span data-ttu-id="d2cb7-151">Group Join 子句</span><span class="sxs-lookup"><span data-stu-id="d2cb7-151">Group Join Clause</span></span>](../../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="d2cb7-152">From 子句</span><span class="sxs-lookup"><span data-stu-id="d2cb7-152">From Clause</span></span>](../../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="d2cb7-153">Where 子句</span><span class="sxs-lookup"><span data-stu-id="d2cb7-153">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="d2cb7-154">查询</span><span class="sxs-lookup"><span data-stu-id="d2cb7-154">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="d2cb7-155">使用 LINQ 进行数据转换 (C#)</span><span class="sxs-lookup"><span data-stu-id="d2cb7-155">Data Transformations with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
