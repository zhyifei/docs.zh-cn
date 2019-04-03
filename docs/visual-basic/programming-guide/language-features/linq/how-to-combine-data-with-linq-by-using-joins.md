---
title: 如何：通过合并数据 LINQ 使用联接 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: dde627edfeb1d4473c9d2e01b9ff83c580a0f122
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822682"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a><span data-ttu-id="ba33a-102">如何：通过合并数据 LINQ 使用联接 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba33a-102">How to: Combine Data with LINQ by Using Joins (Visual Basic)</span></span>
<span data-ttu-id="ba33a-103">Visual Basic 提供了一些`Join`和`Group Join`查询子句以使您能够合并多个集合根据集合之间的常见值的内容。</span><span class="sxs-lookup"><span data-stu-id="ba33a-103">Visual Basic provides the `Join` and `Group Join` query clauses to enable you to combine the contents of multiple collections based on common values between the collections.</span></span> <span data-ttu-id="ba33a-104">这些值称为*密钥*值。</span><span class="sxs-lookup"><span data-stu-id="ba33a-104">These values are known as *key* values.</span></span> <span data-ttu-id="ba33a-105">开发人员熟悉关系数据库的概念将识别`Join`INNER JOIN 子句和`Group Join`作为，实际上，左外部联接子句。</span><span class="sxs-lookup"><span data-stu-id="ba33a-105">Developers familiar with relational database concepts will recognize the `Join` clause as an INNER JOIN and the `Group Join` clause as, effectively, a LEFT OUTER JOIN.</span></span>  
  
 <span data-ttu-id="ba33a-106">本主题中的示例演示了几种方法使用合并数据`Join`和`Group Join`查询子句。</span><span class="sxs-lookup"><span data-stu-id="ba33a-106">The examples in this topic demonstrate a few ways to combine data by using the `Join` and `Group Join` query clauses.</span></span>  
  
## <a name="create-a-project-and-add-sample-data"></a><span data-ttu-id="ba33a-107">创建项目并添加示例数据</span><span class="sxs-lookup"><span data-stu-id="ba33a-107">Create a Project and Add Sample Data</span></span>  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a><span data-ttu-id="ba33a-108">若要创建包含示例数据和类型的项目</span><span class="sxs-lookup"><span data-stu-id="ba33a-108">To create a project that contains sample data and types</span></span>  
  
1.  <span data-ttu-id="ba33a-109">若要运行本主题中的示例，请打开 Visual Studio，并添加新的 Visual Basic 控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="ba33a-109">To run the samples in this topic, open Visual Studio and add a new Visual Basic Console Application project.</span></span> <span data-ttu-id="ba33a-110">双击创建 Visual basic 的 Module1.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="ba33a-110">Double-click the Module1.vb file created by Visual Basic.</span></span>  
  
2.  <span data-ttu-id="ba33a-111">在本主题使用示例`Person`和`Pet`类型和数据从下面的代码示例。</span><span class="sxs-lookup"><span data-stu-id="ba33a-111">The samples in this topic use the `Person` and `Pet` types and data from the following code example.</span></span> <span data-ttu-id="ba33a-112">将此代码复制到默认`Module1`创建 Visual Basic 模块。</span><span class="sxs-lookup"><span data-stu-id="ba33a-112">Copy this code into the default `Module1` module created by Visual Basic.</span></span>  
  
     [!code-vb[VbLINQHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#2)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="ba33a-113">通过使用联接子句执行内部联接</span><span class="sxs-lookup"><span data-stu-id="ba33a-113">Perform an Inner Join by Using the Join Clause</span></span>  
 <span data-ttu-id="ba33a-114">INNER JOIN 结合了两个集合中的数据。</span><span class="sxs-lookup"><span data-stu-id="ba33a-114">An INNER JOIN combines data from two collections.</span></span> <span data-ttu-id="ba33a-115">包含为其指定的密钥值匹配的项。</span><span class="sxs-lookup"><span data-stu-id="ba33a-115">Items for which the specified key values match are included.</span></span> <span data-ttu-id="ba33a-116">不是集合中的另一个集合中没有匹配项的项。</span><span class="sxs-lookup"><span data-stu-id="ba33a-116">Any items from either collection that do not have a matching item in the other collection are excluded.</span></span>  
  
 <span data-ttu-id="ba33a-117">在 Visual Basic 中，LINQ 提供了用于执行内部联接的两个选项： 隐式联接和显式联接。</span><span class="sxs-lookup"><span data-stu-id="ba33a-117">In Visual Basic, LINQ provides two options for performing an INNER JOIN: an implicit join and an explicit join.</span></span>  
  
 <span data-ttu-id="ba33a-118">隐式联接指定集合要联接`From`子句，并标识中匹配的键字段`Where`子句。</span><span class="sxs-lookup"><span data-stu-id="ba33a-118">An implicit join specifies the collections to be joined in a `From` clause and identifies the matching key fields in a `Where` clause.</span></span> <span data-ttu-id="ba33a-119">Visual Basic 隐式联接两个集合根据指定的键字段。</span><span class="sxs-lookup"><span data-stu-id="ba33a-119">Visual Basic implicitly joins the two collections based on the specified key fields.</span></span>  
  
 <span data-ttu-id="ba33a-120">可以通过使用指定的显式联接`Join`子句时想可以细致地指出哪个密钥在联接中使用的字段。</span><span class="sxs-lookup"><span data-stu-id="ba33a-120">You can specify an explicit join by using the `Join` clause when you want to be specific about which key fields to use in the join.</span></span> <span data-ttu-id="ba33a-121">在这种情况下，`Where`子句仍可用于筛选查询结果。</span><span class="sxs-lookup"><span data-stu-id="ba33a-121">In this case, a `Where` clause can still be used to filter the query results.</span></span>  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="ba33a-122">若要执行 Inner Join 使用 Join 子句</span><span class="sxs-lookup"><span data-stu-id="ba33a-122">To perform an Inner Join by using the Join clause</span></span>  
  
1.  <span data-ttu-id="ba33a-123">将以下代码添加到`Module1`项目若要查看这两个隐式和显式内部联接的示例中的模块。</span><span class="sxs-lookup"><span data-stu-id="ba33a-123">Add the following code to the `Module1` module in your project to see examples of both an implicit and explicit inner join.</span></span>  
  
     [!code-vb[VbLINQHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#4)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="ba33a-124">使用 Group Join 子句执行左外部联接</span><span class="sxs-lookup"><span data-stu-id="ba33a-124">Perform a Left Outer Join by Using the Group Join Clause</span></span>  
 <span data-ttu-id="ba33a-125">LEFT OUTER JOIN 包括所有的项从左侧集合联接和仅匹配联接的右端集合中的值。</span><span class="sxs-lookup"><span data-stu-id="ba33a-125">A LEFT OUTER JOIN includes all the items from the left-side collection of the join and only matching values from the right-side collection of the join.</span></span> <span data-ttu-id="ba33a-126">从右侧集合联接的左侧集合中没有匹配项的任何项不在查询结果。</span><span class="sxs-lookup"><span data-stu-id="ba33a-126">Any items from the right-side collection of the join that do not have a matching item in the left-side collection are excluded from the query result.</span></span>  
  
 <span data-ttu-id="ba33a-127">`Group Join`子句执行时，实际上，左外部联接。</span><span class="sxs-lookup"><span data-stu-id="ba33a-127">The `Group Join` clause performs, in effect, a LEFT OUTER JOIN.</span></span> <span data-ttu-id="ba33a-128">通常称作 LEFT OUTER JOIN 和之间的区别`Group Join`子句将返回在于`Group Join`子句从左侧集合中每一项联接右侧集合对结果进行分组。</span><span class="sxs-lookup"><span data-stu-id="ba33a-128">The difference between what is typically known as a LEFT OUTER JOIN and what the `Group Join` clause returns is that the `Group Join` clause groups results from the right-side collection of the join for each item in the left-side collection.</span></span> <span data-ttu-id="ba33a-129">在关系数据库中，左外部联接返回在其在查询中的每个项生成一个未分组的结果包含联接这两个集合中的匹配项。</span><span class="sxs-lookup"><span data-stu-id="ba33a-129">In a relational database, a LEFT OUTER JOIN returns an ungrouped result in which each item in the query result contains matching items from both collections in the join.</span></span> <span data-ttu-id="ba33a-130">在这种情况下，从左侧集合联接的项的右侧集合的每个匹配项都重复。</span><span class="sxs-lookup"><span data-stu-id="ba33a-130">In this case, the items from the left-side collection of the join are repeated for each matching item from the right-side collection.</span></span> <span data-ttu-id="ba33a-131">您将看到这种情况下一个过程完成。</span><span class="sxs-lookup"><span data-stu-id="ba33a-131">You will see what this looks like when you complete the next procedure.</span></span>  
  
 <span data-ttu-id="ba33a-132">你可以检索的结果`Group Join`查询与通过扩展查询，以返回每个分组的查询结果的项分组结果的查询。</span><span class="sxs-lookup"><span data-stu-id="ba33a-132">You can retrieve the results of a `Group Join` query as an ungrouped result by extending your query to return an item for each grouped query result.</span></span> <span data-ttu-id="ba33a-133">若要实现此目的，必须确保您查询在`DefaultIfEmpty`分组集合的方法。</span><span class="sxs-lookup"><span data-stu-id="ba33a-133">To accomplish this, you have to ensure that you query on the `DefaultIfEmpty` method of the grouped collection.</span></span> <span data-ttu-id="ba33a-134">这可确保，联接的左侧集合中的项仍包含在查询结果即使它们具有匹配的结果从右侧的集合。</span><span class="sxs-lookup"><span data-stu-id="ba33a-134">This ensures that items from the left-side collection of the join are still included in the query result even if they have no matching results from the right-side collection.</span></span> <span data-ttu-id="ba33a-135">可以将代码添加到查询以从联接的右侧集合没有匹配值时提供一个默认结果值。</span><span class="sxs-lookup"><span data-stu-id="ba33a-135">You can add code to your query to provide a default result value when there is no matching value from the right-side collection of the join.</span></span>  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="ba33a-136">若要通过使用 Group Join 子句执行左外部联接</span><span class="sxs-lookup"><span data-stu-id="ba33a-136">To perform a Left Outer Join by using the Group Join clause</span></span>  
  
1.  <span data-ttu-id="ba33a-137">将以下代码添加到`Module1`项目以查看分组左外部联接和分组的左外部联接的示例中的模块。</span><span class="sxs-lookup"><span data-stu-id="ba33a-137">Add the following code to the `Module1` module in your project to see examples of both a grouped left outer join and an ungrouped left outer join.</span></span>  
  
     [!code-vb[VbLINQHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#3)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="ba33a-138">使用组合键进行联接</span><span class="sxs-lookup"><span data-stu-id="ba33a-138">Perform a Join by Using a Composite Key</span></span>  
 <span data-ttu-id="ba33a-139">可以使用`And`中的关键字`Join`或`Group Join`子句来标识匹配时要使用的多个键字段值从要联接的集合。</span><span class="sxs-lookup"><span data-stu-id="ba33a-139">You can use the `And` keyword in a `Join` or `Group Join` clause to identify multiple key fields to use when matching values from the collections being joined.</span></span> <span data-ttu-id="ba33a-140">`And`关键字指定所有指定的键字段都必须匹配要联接的项。</span><span class="sxs-lookup"><span data-stu-id="ba33a-140">The `And` keyword specifies that all specified key fields must match for items to be joined.</span></span>  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="ba33a-141">使用组合键进行联接</span><span class="sxs-lookup"><span data-stu-id="ba33a-141">To perform a Join by using a composite key</span></span>  
  
1.  <span data-ttu-id="ba33a-142">将以下代码添加到`Module1`项目若要查看使用复合键联接的示例中的模块。</span><span class="sxs-lookup"><span data-stu-id="ba33a-142">Add the following code to the `Module1` module in your project to see examples of a join that uses a composite key.</span></span>  
  
     [!code-vb[VbLINQHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#5)]  
  
## <a name="run-the-code"></a><span data-ttu-id="ba33a-143">运行代码</span><span class="sxs-lookup"><span data-stu-id="ba33a-143">Run the Code</span></span>  
  
#### <a name="to-add-code-to-run-the-examples"></a><span data-ttu-id="ba33a-144">若要添加代码以运行示例</span><span class="sxs-lookup"><span data-stu-id="ba33a-144">To add code to run the examples</span></span>  
  
1.  <span data-ttu-id="ba33a-145">替换`Sub Main`在`Module1`以下代码，以运行本主题中的示例项目中的模块。</span><span class="sxs-lookup"><span data-stu-id="ba33a-145">Replace the `Sub Main` in the `Module1` module in your project with the following code to run the examples in this topic.</span></span>  
  
     [!code-vb[VbLINQHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#6)]  
  
2.  <span data-ttu-id="ba33a-146">按 F5 以运行示例。</span><span class="sxs-lookup"><span data-stu-id="ba33a-146">Press F5 to run the examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba33a-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba33a-147">See also</span></span>

- [<span data-ttu-id="ba33a-148">LINQ</span><span class="sxs-lookup"><span data-stu-id="ba33a-148">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="ba33a-149">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="ba33a-149">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="ba33a-150">Join 子句</span><span class="sxs-lookup"><span data-stu-id="ba33a-150">Join Clause</span></span>](../../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="ba33a-151">Group Join 子句</span><span class="sxs-lookup"><span data-stu-id="ba33a-151">Group Join Clause</span></span>](../../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="ba33a-152">From 子句</span><span class="sxs-lookup"><span data-stu-id="ba33a-152">From Clause</span></span>](../../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="ba33a-153">Where 子句</span><span class="sxs-lookup"><span data-stu-id="ba33a-153">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="ba33a-154">查询</span><span class="sxs-lookup"><span data-stu-id="ba33a-154">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="ba33a-155">使用 LINQ 进行数据转换 (C#)</span><span class="sxs-lookup"><span data-stu-id="ba33a-155">Data Transformations with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
