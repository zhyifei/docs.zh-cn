---
title: 演练：用 C# 编写查询 (LINQ)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], walkthroughs
- LINQ [C#], writing queries
- queries [LINQ in C#], writing
- writing LINQ queries
ms.assetid: 2962a610-419a-4276-9ec8-4b7f2af0c081
ms.openlocfilehash: 10ffdbd6430c0ad55b0a5d71f217a7cb18163741
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340406"
---
# <a name="walkthrough-writing-queries-in-c-linq"></a><span data-ttu-id="a100a-102">演练：用 C# 编写查询 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="a100a-102">Walkthrough: Writing Queries in C# (LINQ)</span></span>
<span data-ttu-id="a100a-103">此演练演示用于编写 LINQ 查询表达式的 C# 语言功能。</span><span class="sxs-lookup"><span data-stu-id="a100a-103">This walkthrough demonstrates the C# language features that are used to write LINQ query expressions.</span></span>  
  
## <a name="create-a-c-project"></a><span data-ttu-id="a100a-104">创建 C# 项目</span><span class="sxs-lookup"><span data-stu-id="a100a-104">Create a C# Project</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a100a-105">以下说明适用于 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="a100a-105">The following instructions are for Visual Studio.</span></span> <span data-ttu-id="a100a-106">如果使用其他开发环境，请创建包含对 System.Core.dll 的引用的控制台项目和用于 <xref:System.Linq?displayProperty=nameWithType> 命名空间的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="a100a-106">If you are using a different development environment, create a console project with a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
#### <a name="to-create-a-project-in-visual-studio"></a><span data-ttu-id="a100a-107">在 Visual Studio 中创建项目</span><span class="sxs-lookup"><span data-stu-id="a100a-107">To create a project in Visual Studio</span></span>  
  
1.  <span data-ttu-id="a100a-108">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="a100a-108">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="a100a-109">在菜单栏上，依次选择“文件” 、“新建” 、“项目” 。</span><span class="sxs-lookup"><span data-stu-id="a100a-109">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="a100a-110">**“新建项目”** 对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="a100a-110">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="a100a-111">依次展开“已安装”、“模板”、“Visual C#”，然后选择“控制台应用程序”。</span><span class="sxs-lookup"><span data-stu-id="a100a-111">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>  
  
4.  <span data-ttu-id="a100a-112">在“名称”文本框中，输入不同的名称或接受默认名称，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="a100a-112">In the **Name** text box, enter a different name or accept the default name, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="a100a-113">新项目将出现在“解决方案资源管理器”中。</span><span class="sxs-lookup"><span data-stu-id="a100a-113">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="a100a-114">注意，此项目包含对 System.Core.dll 的引用和用于 <xref:System.Linq?displayProperty=nameWithType> 命名空间的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="a100a-114">Notice that your project has a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="create-an-in-memory-data-source"></a><span data-ttu-id="a100a-115">创建内存中的数据源</span><span class="sxs-lookup"><span data-stu-id="a100a-115">Create an in-Memory Data Source</span></span>  
 <span data-ttu-id="a100a-116">用于查询的数据源是 `Student` 对象的简单列表。</span><span class="sxs-lookup"><span data-stu-id="a100a-116">The data source for the queries is a simple list of `Student` objects.</span></span> <span data-ttu-id="a100a-117">每个 `Student` 记录都有名字、姓氏和整数数组（表示该学生在课堂上的测试分数）。</span><span class="sxs-lookup"><span data-stu-id="a100a-117">Each `Student` record has a first name, last name, and an array of integers that represents their test scores in the class.</span></span> <span data-ttu-id="a100a-118">将此代码复制到项目中。</span><span class="sxs-lookup"><span data-stu-id="a100a-118">Copy this code into your project.</span></span> <span data-ttu-id="a100a-119">请注意下列特性：</span><span class="sxs-lookup"><span data-stu-id="a100a-119">Note the following characteristics:</span></span>  
  
-   <span data-ttu-id="a100a-120">`Student` 类包含自动实现的属性。</span><span class="sxs-lookup"><span data-stu-id="a100a-120">The `Student` class consists of auto-implemented properties.</span></span>  
  
-   <span data-ttu-id="a100a-121">列表中的每个学生都可使用对象初始值设定项进行初始化。</span><span class="sxs-lookup"><span data-stu-id="a100a-121">Each student in the list is initialized with an object initializer.</span></span>  
  
-   <span data-ttu-id="a100a-122">列表本身可使用集合初始值设定项进行初始化。</span><span class="sxs-lookup"><span data-stu-id="a100a-122">The list itself is initialized with a collection initializer.</span></span>  
  
 <span data-ttu-id="a100a-123">将在不显式调用任何构造函数和使用显式成员访问的情况下初始化并实例化整个数据结构。</span><span class="sxs-lookup"><span data-stu-id="a100a-123">This whole data structure will be initialized and instantiated without explicit calls to any constructor or explicit member access.</span></span> <span data-ttu-id="a100a-124">有关这些新功能的详细信息，请参阅[自动实现的属性](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)与[对象和集合初始值设定项](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)。</span><span class="sxs-lookup"><span data-stu-id="a100a-124">For more information about these new features, see [Auto-Implemented Properties](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) and [Object and Collection Initializers](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="a100a-125">添加数据源</span><span class="sxs-lookup"><span data-stu-id="a100a-125">To add the data source</span></span>  
  
-   <span data-ttu-id="a100a-126">向项目中的 `Program` 类添加 `Student` 类和经过初始化的学生列表。</span><span class="sxs-lookup"><span data-stu-id="a100a-126">Add the `Student` class and the initialized list of students to the `Program` class in your project.</span></span>  
  
     [!code-csharp[CsLinqGettingStarted#11](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_1.cs)]  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="a100a-127">向学生列表添加新学生</span><span class="sxs-lookup"><span data-stu-id="a100a-127">To add a new Student to the Students list</span></span>  
  
1.  <span data-ttu-id="a100a-128">向 `Students` 列表添加一个新 `Student`，并按自己的选择使用名称和测试分数。</span><span class="sxs-lookup"><span data-stu-id="a100a-128">Add a new `Student` to the `Students` list and use a name and test scores of your choice.</span></span> <span data-ttu-id="a100a-129">尝试键入所有新学生信息，以便更好地了解对象初始值设定项的语法。</span><span class="sxs-lookup"><span data-stu-id="a100a-129">Try typing all the new student information in order to better learn the syntax for the object initializer.</span></span>  
  
## <a name="create-the-query"></a><span data-ttu-id="a100a-130">创建查询</span><span class="sxs-lookup"><span data-stu-id="a100a-130">Create the Query</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="a100a-131">创建简单查询</span><span class="sxs-lookup"><span data-stu-id="a100a-131">To create a simple query</span></span>  
  
-   <span data-ttu-id="a100a-132">在应用程序的 `Main` 方法中，创建简单查询，执行该查询时，将生成所有在第一次测试中分数高于 90 的学生的列表。</span><span class="sxs-lookup"><span data-stu-id="a100a-132">In the application's `Main` method, create a simple query that, when it is executed, will produce a list of all students whose score on the first test was greater than 90.</span></span> <span data-ttu-id="a100a-133">注意，由于选定全部 `Student` 对象，所以查询的类型为 `IEnumerable<Student>`。</span><span class="sxs-lookup"><span data-stu-id="a100a-133">Note that because the whole `Student` object is selected, the type of the query is `IEnumerable<Student>`.</span></span> <span data-ttu-id="a100a-134">尽管该代码也可以通过使用 [var](../../../../csharp/language-reference/keywords/var.md) 关键字来使用隐式类型化，但可以使用显式类型化清楚地展示结果。</span><span class="sxs-lookup"><span data-stu-id="a100a-134">Although the code could also use implicit typing by using the [var](../../../../csharp/language-reference/keywords/var.md) keyword, explicit typing is used to clearly illustrate results.</span></span> <span data-ttu-id="a100a-135">（有关 `var` 的详细信息，请参阅[隐式类型化局部变量](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)。）</span><span class="sxs-lookup"><span data-stu-id="a100a-135">(For more information about `var`, see [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).)</span></span>  
  
     <span data-ttu-id="a100a-136">另请注意，查询的范围变量 `student` 用作指向源中每个 `Student` 引用，提供对每个对象的成员访问。</span><span class="sxs-lookup"><span data-stu-id="a100a-136">Note also that the query's range variable, `student`, serves as a reference to each `Student` in the source, providing member access for each object.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#12](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_2.cs)]  
  
## <a name="execute-the-query"></a><span data-ttu-id="a100a-137">执行查询</span><span class="sxs-lookup"><span data-stu-id="a100a-137">Execute the Query</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="a100a-138">执行查询</span><span class="sxs-lookup"><span data-stu-id="a100a-138">To execute the query</span></span>  
  
1.  <span data-ttu-id="a100a-139">现在，编写 `foreach` 循环，用于执行查询。</span><span class="sxs-lookup"><span data-stu-id="a100a-139">Now write the `foreach` loop that will cause the query to execute.</span></span> <span data-ttu-id="a100a-140">注意以下有关代码的注意事项：</span><span class="sxs-lookup"><span data-stu-id="a100a-140">Note the following about the code:</span></span>  
  
    -   <span data-ttu-id="a100a-141">通过 `foreach` 循环中的迭代变量，可访问返回的序列中的每个元素。</span><span class="sxs-lookup"><span data-stu-id="a100a-141">Each element in the returned sequence is accessed through the iteration variable in the `foreach` loop.</span></span>  
  
    -   <span data-ttu-id="a100a-142">此变量的类型是 `Student`，并且可与查询变量 `IEnumerable<Student>` 的类型兼容。</span><span class="sxs-lookup"><span data-stu-id="a100a-142">The type of this variable is `Student`, and the type of the query variable is compatible, `IEnumerable<Student>`.</span></span>  
  
2.  <span data-ttu-id="a100a-143">添加此代码后，生成并运行应用程序，以在“控制台”窗口中查看结果。</span><span class="sxs-lookup"><span data-stu-id="a100a-143">After you have added this code, build and run the application to see the results in the **Console** window.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#13](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_3.cs)]  
  
#### <a name="to-add-another-filter-condition"></a><span data-ttu-id="a100a-144">添加其他筛选条件</span><span class="sxs-lookup"><span data-stu-id="a100a-144">To add another filter condition</span></span>  
  
1.  <span data-ttu-id="a100a-145">在 `where` 子句中，可以组合多个布尔条件，以便进一步细化查询。</span><span class="sxs-lookup"><span data-stu-id="a100a-145">You can combine multiple Boolean conditions in the `where` clause in order to further refine a query.</span></span> <span data-ttu-id="a100a-146">以下代码添加了一个条件，以便该查询返回第一个分数高于 90 分，并且最后一个分数低于 80 分的那些学生。</span><span class="sxs-lookup"><span data-stu-id="a100a-146">The following code adds a condition so that the query returns those students whose first score was over 90 and whose last score was less than 80.</span></span> <span data-ttu-id="a100a-147">`where` 子句应与以下代码类似。</span><span class="sxs-lookup"><span data-stu-id="a100a-147">The `where` clause should resemble the following code.</span></span>  
  
    ```  
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     <span data-ttu-id="a100a-148">有关详细信息，请参阅 [where 子句](../../../../csharp/language-reference/keywords/where-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="a100a-148">For more information, see [where clause](../../../../csharp/language-reference/keywords/where-clause.md).</span></span>  
  
## <a name="modify-the-query"></a><span data-ttu-id="a100a-149">修改查询</span><span class="sxs-lookup"><span data-stu-id="a100a-149">Modify the Query</span></span>  
  
#### <a name="to-order-the-results"></a><span data-ttu-id="a100a-150">对结果进行排序</span><span class="sxs-lookup"><span data-stu-id="a100a-150">To order the results</span></span>  
  
1.  <span data-ttu-id="a100a-151">如果结果按某种顺序排列，则浏览结果会更容易。</span><span class="sxs-lookup"><span data-stu-id="a100a-151">It will be easier to scan the results if they are in some kind of order.</span></span> <span data-ttu-id="a100a-152">你可以根据源元素中的任何可访问字段对返回的序列进行排序。</span><span class="sxs-lookup"><span data-stu-id="a100a-152">You can order the returned sequence by any accessible field in the source elements.</span></span> <span data-ttu-id="a100a-153">例如，以下 `orderby` 子句将结果按照每个学生的姓氏以字母从 A 到 Z 的顺序排列。</span><span class="sxs-lookup"><span data-stu-id="a100a-153">For example, the following `orderby` clause orders the results in alphabetical order from A to Z according to the last name of each student.</span></span> <span data-ttu-id="a100a-154">将以下 `orderby` 子句添加到查询中，紧跟 `where` 语句之后、`select` 语句之前：</span><span class="sxs-lookup"><span data-stu-id="a100a-154">Add the following `orderby` clause to your query, right after the `where` statement and before the `select` statement:</span></span>  
  
    ```  
    orderby student.Last ascending  
    ```  
  
2.  <span data-ttu-id="a100a-155">现在，更改 `orderby` 子句，以便将结果根据第一次测试的分数以倒序（从最高分到最低分）的顺序排列。</span><span class="sxs-lookup"><span data-stu-id="a100a-155">Now change the `orderby` clause so that it orders the results in reverse order according to the score on the first test, from the highest score to the lowest score.</span></span>  
  
    ```  
    orderby student.Scores[0] descending  
    ```  
  
3.  <span data-ttu-id="a100a-156">更改 `WriteLine` 格式字符串，以便查看分数：</span><span class="sxs-lookup"><span data-stu-id="a100a-156">Change the `WriteLine` format string so that you can see the scores:</span></span>  
  
    ```  
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     <span data-ttu-id="a100a-157">有关详细信息，请参阅 [orderby 子句](../../../../csharp/language-reference/keywords/orderby-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="a100a-157">For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).</span></span>  
  
#### <a name="to-group-the-results"></a><span data-ttu-id="a100a-158">对结果进行分组</span><span class="sxs-lookup"><span data-stu-id="a100a-158">To group the results</span></span>  
  
1.  <span data-ttu-id="a100a-159">分组是查询表达式中的强大功能。</span><span class="sxs-lookup"><span data-stu-id="a100a-159">Grouping is a powerful capability in query expressions.</span></span> <span data-ttu-id="a100a-160">包含 group 子句的查询将生成一系列组，每个组本身包含一个 `Key` 和一个序列，该序列由该组的所有成员组成。</span><span class="sxs-lookup"><span data-stu-id="a100a-160">A query with a group clause produces a sequence of groups, and each group itself contains a `Key` and a sequence that consists of all the members of that group.</span></span> <span data-ttu-id="a100a-161">以下新查询使用学生的姓的第一个字母作为关键字对学生进行分组。</span><span class="sxs-lookup"><span data-stu-id="a100a-161">The following new query groups the students by using the first letter of their last name as the key.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#14](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_4.cs)]  
  
2.  <span data-ttu-id="a100a-162">注意，查询类型现已更改。</span><span class="sxs-lookup"><span data-stu-id="a100a-162">Note that the type of the query has now changed.</span></span> <span data-ttu-id="a100a-163">该查询现在生成一系列将 `char` 类型作为键的组，以及一系列 `Student` 对象。</span><span class="sxs-lookup"><span data-stu-id="a100a-163">It now produces a sequence of groups that have a `char` type as a key, and a sequence of `Student` objects.</span></span> <span data-ttu-id="a100a-164">由于查询的类型已更改，因此以下代码也将更改 `foreach` 执行循环：</span><span class="sxs-lookup"><span data-stu-id="a100a-164">Because the type of the query has changed, the following code changes the `foreach` execution loop also:</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#15](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_5.cs)]  
  
3.  <span data-ttu-id="a100a-165">在“控制台”窗口中运行应用程序并查看结果。</span><span class="sxs-lookup"><span data-stu-id="a100a-165">Run the application and view the results in the **Console** window.</span></span>  
  
     <span data-ttu-id="a100a-166">有关详细信息，请参阅 [group 子句](../../../../csharp/language-reference/keywords/group-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="a100a-166">For more information, see [group clause](../../../../csharp/language-reference/keywords/group-clause.md).</span></span>  
  
#### <a name="to-make-the-variables-implicitly-typed"></a><span data-ttu-id="a100a-167">对变量进行隐式类型化</span><span class="sxs-lookup"><span data-stu-id="a100a-167">To make the variables implicitly typed</span></span>  
  
1.  <span data-ttu-id="a100a-168">`IGroupings` 的显式编码 `IEnumerables` 将快速变得冗长。</span><span class="sxs-lookup"><span data-stu-id="a100a-168">Explicitly coding `IEnumerables` of `IGroupings` can quickly become tedious.</span></span> <span data-ttu-id="a100a-169">使用 `var` 可以更方便地编写相同的查询和 `foreach` 循环。</span><span class="sxs-lookup"><span data-stu-id="a100a-169">You can write the same query and `foreach` loop much more conveniently by using `var`.</span></span> <span data-ttu-id="a100a-170">`var` 关键字不会更改对象的类型；它仅指示编译器推断类型。</span><span class="sxs-lookup"><span data-stu-id="a100a-170">The `var` keyword does not change the types of your objects; it just instructs the compiler to infer the types.</span></span> <span data-ttu-id="a100a-171">将 `studentQuery` 和迭代变量 `group` 的类型更改为 `var`，然后重新运行查询。</span><span class="sxs-lookup"><span data-stu-id="a100a-171">Change the type of `studentQuery` and the iteration variable `group` to `var` and rerun the query.</span></span> <span data-ttu-id="a100a-172">注意，在内部 `foreach` 循环中，该迭代变量仍类型化为 `Student`，并且查询的工作原理和以前一样。</span><span class="sxs-lookup"><span data-stu-id="a100a-172">Note that in the inner `foreach` loop, the iteration variable is still typed as `Student`, and the query works just as before.</span></span> <span data-ttu-id="a100a-173">将 `s` 迭代变量更改为 `var`，然后再次运行查询。</span><span class="sxs-lookup"><span data-stu-id="a100a-173">Change the `s` iteration variable to `var` and run the query again.</span></span> <span data-ttu-id="a100a-174">将看到完全相同的结果。</span><span class="sxs-lookup"><span data-stu-id="a100a-174">You see that you get exactly the same results.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#16](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_6.cs)]  
  
     <span data-ttu-id="a100a-175">有关 [var](../../../../csharp/language-reference/keywords/var.md) 的详细信息，请参阅[隐式类型化局部变量](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="a100a-175">For more information about [var](../../../../csharp/language-reference/keywords/var.md), see [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
#### <a name="to-order-the-groups-by-their-key-value"></a><span data-ttu-id="a100a-176">按照键值对组进行排序</span><span class="sxs-lookup"><span data-stu-id="a100a-176">To order the groups by their key value</span></span>  
  
1.  <span data-ttu-id="a100a-177">运行上一查询时，会发现这些组不是按字母顺序排序的。</span><span class="sxs-lookup"><span data-stu-id="a100a-177">When you run the previous query, you notice that the groups are not in alphabetical order.</span></span> <span data-ttu-id="a100a-178">若要更改此排序，必须在 `group` 子句后提供 `orderby` 子句。</span><span class="sxs-lookup"><span data-stu-id="a100a-178">To change this, you must provide an `orderby` clause after the `group` clause.</span></span> <span data-ttu-id="a100a-179">但若要使用 `orderby` 子句，首先需要一个标识符，用作对 `group` 子句创建的组的引用。</span><span class="sxs-lookup"><span data-stu-id="a100a-179">But to use an `orderby` clause, you first need an identifier that serves as a reference to the groups created by the `group` clause.</span></span> <span data-ttu-id="a100a-180">可以使用 `into` 关键字提供该标识符，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a100a-180">You provide the identifier by using the `into` keyword, as follows:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#17](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_7.cs)]  
  
     <span data-ttu-id="a100a-181">运行此查询时，将看到这些组现在已按字母顺序排序。</span><span class="sxs-lookup"><span data-stu-id="a100a-181">When you run this query, you will see the groups are now sorted in alphabetical order.</span></span>  
  
#### <a name="to-introduce-an-identifier-by-using-let"></a><span data-ttu-id="a100a-182">使用 let 引入标识符</span><span class="sxs-lookup"><span data-stu-id="a100a-182">To introduce an identifier by using let</span></span>  
  
1.  <span data-ttu-id="a100a-183">可以使用 `let` 关键字来引入查询表达式中任何表达式结果的标识符。</span><span class="sxs-lookup"><span data-stu-id="a100a-183">You can use the `let` keyword to introduce an identifier for any expression result in the query expression.</span></span> <span data-ttu-id="a100a-184">此标识符可以提供方便（如下面的示例所示），也可以通过存储表达式的结果来避免多次计算，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="a100a-184">This identifier can be a convenience, as in the following example, or it can enhance performance by storing the results of an expression so that it does not have to be calculated multiple times.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#18](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_8.cs)]  
  
     <span data-ttu-id="a100a-185">有关详细信息，请参阅 [let 子句](../../../../csharp/language-reference/keywords/let-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="a100a-185">For more information, see [let clause](../../../../csharp/language-reference/keywords/let-clause.md).</span></span>  
  
#### <a name="to-use-method-syntax-in-a-query-expression"></a><span data-ttu-id="a100a-186">在查询表达式中使用方法语法</span><span class="sxs-lookup"><span data-stu-id="a100a-186">To use method syntax in a query expression</span></span>  
  
1.  <span data-ttu-id="a100a-187">如 [LINQ 中的查询语法和方法语法](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md) 中所述，某些查询操作只能使用方法语法来表示。</span><span class="sxs-lookup"><span data-stu-id="a100a-187">As described in [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md), some query operations can only be expressed by using method syntax.</span></span> <span data-ttu-id="a100a-188">以下代码为源序列中的每个 `Student` 计算总分，然后对该查询的结果调用 `Average()` 方法来计算班级平均分。</span><span class="sxs-lookup"><span data-stu-id="a100a-188">The following code calculates the total score for each `Student` in the source sequence, and then calls the `Average()` method on the results of that query to calculate the average score of the class.</span></span> <span data-ttu-id="a100a-189">请注意，查询表达式的两边使用了括号。</span><span class="sxs-lookup"><span data-stu-id="a100a-189">Note the placement of parentheses around the query expression.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#19](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_9.cs)]  
  
#### <a name="to-transform-or-project-in-the-select-clause"></a><span data-ttu-id="a100a-190">在 select 子句转换或投影</span><span class="sxs-lookup"><span data-stu-id="a100a-190">To transform or project in the select clause</span></span>  
  
1.  <span data-ttu-id="a100a-191">查询生成的序列的元素与源序列中的元素不同，这种情况很常见。</span><span class="sxs-lookup"><span data-stu-id="a100a-191">It is very common for a query to produce a sequence whose elements differ from the elements in the source sequences.</span></span> <span data-ttu-id="a100a-192">删除或注释掉以前的查询和执行循环，并将其替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="a100a-192">Delete or comment out your previous query and execution loop, and replace it with the following code.</span></span> <span data-ttu-id="a100a-193">请注意，该查询将返回字符串序列，而不是 `Students`，这种情况将反映在 `foreach` 循环中。</span><span class="sxs-lookup"><span data-stu-id="a100a-193">Note that the query returns a sequence of strings (not `Students`), and this fact is reflected in the `foreach` loop.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#20](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_10.cs)]  
  
2.  <span data-ttu-id="a100a-194">本演练中前面的代码表明班级平均分大约为 334 分。</span><span class="sxs-lookup"><span data-stu-id="a100a-194">Code earlier in this walkthrough indicated that the average class score is approximately 334.</span></span> <span data-ttu-id="a100a-195">若要生成总分数高于班级平均分的 `Students` 及其 `Student ID` 的序列，可以在 `select` 语句中使用匿名类型：</span><span class="sxs-lookup"><span data-stu-id="a100a-195">To produce a sequence of `Students` whose total score is greater than the class average, together with their `Student ID`, you can use an anonymous type in the `select` statement:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#21](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_11.cs)]  
  
## <a name="next-steps"></a><span data-ttu-id="a100a-196">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a100a-196">Next Steps</span></span>  
 <span data-ttu-id="a100a-197">熟悉了在 C# 中使用查询的基本情况后，便可以开始阅读你感兴趣的具体类型的 LINQ 提供程序的文档和示例：</span><span class="sxs-lookup"><span data-stu-id="a100a-197">After you are familiar with the basic aspects of working with queries in C#, you are ready to read the documentation and samples for the specific type of LINQ provider you are interested in:</span></span>  
  
 [<span data-ttu-id="a100a-198">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a100a-198">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
  
 [<span data-ttu-id="a100a-199">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="a100a-199">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)  
  
 [<span data-ttu-id="a100a-200">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="a100a-200">LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [<span data-ttu-id="a100a-201">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="a100a-201">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="a100a-202">请参阅</span><span class="sxs-lookup"><span data-stu-id="a100a-202">See Also</span></span>  
 [<span data-ttu-id="a100a-203">语言集成查询 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="a100a-203">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)  
 [<span data-ttu-id="a100a-204">C# 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="a100a-204">Getting Started with LINQ in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="a100a-205">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="a100a-205">LINQ Query Expressions</span></span>](../../../../csharp/programming-guide/linq-query-expressions/index.md)
