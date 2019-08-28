---
title: 在 Visual Basic 中编写查询
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 256075ad5de5b88595dd4be7f199a74b5912c082
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046552"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a><span data-ttu-id="0535a-102">演练：在 Visual Basic 中编写查询</span><span class="sxs-lookup"><span data-stu-id="0535a-102">Walkthrough: Writing Queries in Visual Basic</span></span>

<span data-ttu-id="0535a-103">本演练演示如何使用 Visual Basic 语言功能编写[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]查询表达式。</span><span class="sxs-lookup"><span data-stu-id="0535a-103">This walkthrough demonstrates how you can use Visual Basic language features to write [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query expressions.</span></span> <span data-ttu-id="0535a-104">本演练演示如何对学生对象列表创建查询, 如何运行查询, 以及如何修改查询。</span><span class="sxs-lookup"><span data-stu-id="0535a-104">The walkthrough demonstrates how to create queries on a list of Student objects, how to run the queries, and how to modify them.</span></span> <span data-ttu-id="0535a-105">查询包含多个功能, 包括对象初始值设定项、本地类型推理和匿名类型。</span><span class="sxs-lookup"><span data-stu-id="0535a-105">The queries incorporate several features including object initializers, local type inference, and anonymous types.</span></span>

<span data-ttu-id="0535a-106">完成本演练后, 你将准备好进入你感兴趣的特定[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]提供程序的示例和文档。</span><span class="sxs-lookup"><span data-stu-id="0535a-106">After completing this walkthrough, you will be ready to move on to the samples and documentation for the specific [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider you are interested in.</span></span> [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]<span data-ttu-id="0535a-107">提供程序[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]包括、LINQ to DataSet 和[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0535a-107">providers include [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], LINQ to DataSet, and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>

## <a name="create-a-project"></a><span data-ttu-id="0535a-108">创建项目</span><span class="sxs-lookup"><span data-stu-id="0535a-108">Create a Project</span></span>

### <a name="to-create-a-console-application-project"></a><span data-ttu-id="0535a-109">创建控制台应用程序项目</span><span class="sxs-lookup"><span data-stu-id="0535a-109">To create a console application project</span></span>

1. <span data-ttu-id="0535a-110">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="0535a-110">Start Visual Studio.</span></span>

2. <span data-ttu-id="0535a-111">在 **“文件”** 菜单上，指向 **“新建”** ，然后单击 **“项目”** 。</span><span class="sxs-lookup"><span data-stu-id="0535a-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>

3. <span data-ttu-id="0535a-112">在 "**已安装的模板**" 列表中, 单击**Visual Basic**。</span><span class="sxs-lookup"><span data-stu-id="0535a-112">In the **Installed Templates** list, click **Visual Basic**.</span></span>

4. <span data-ttu-id="0535a-113">在项目类型列表中, 单击 "**控制台应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="0535a-113">In the list of project types, click **Console Application**.</span></span> <span data-ttu-id="0535a-114">在 "**名称**" 框中, 键入项目的名称, 然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="0535a-114">In the **Name** box, type a name for the project, and then click **OK**.</span></span>

    <span data-ttu-id="0535a-115">创建一个项目。</span><span class="sxs-lookup"><span data-stu-id="0535a-115">A project is created.</span></span> <span data-ttu-id="0535a-116">默认情况下, 它包含对 System.object 的引用。</span><span class="sxs-lookup"><span data-stu-id="0535a-116">By default, it contains a reference to System.Core.dll.</span></span> <span data-ttu-id="0535a-117">此外, "引用" 页上的 "已**导入命名空间**" 列表[Visual Basic 中](/visualstudio/ide/reference/references-page-project-designer-visual-basic)包含<xref:System.Linq?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="0535a-117">Also, the **Imported namespaces** list on the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) includes the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>

5. <span data-ttu-id="0535a-118">在 "编译" 页上的 "[项目设计器" (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)上, 确保 "**选项推断**" 设置为 **"开"** 。</span><span class="sxs-lookup"><span data-stu-id="0535a-118">On the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), ensure that **Option infer** is set to **On**.</span></span>

## <a name="add-an-in-memory-data-source"></a><span data-ttu-id="0535a-119">添加内存中数据源</span><span class="sxs-lookup"><span data-stu-id="0535a-119">Add an In-Memory Data Source</span></span>

<span data-ttu-id="0535a-120">此演练中的查询的数据源是`Student`对象的列表。</span><span class="sxs-lookup"><span data-stu-id="0535a-120">The data source for the queries in this walkthrough is a list of `Student` objects.</span></span> <span data-ttu-id="0535a-121">每`Student`个对象都包含学生正文中的名字、姓氏、课程年份和学术排名。</span><span class="sxs-lookup"><span data-stu-id="0535a-121">Each `Student` object contains a first name, a last name, a class year, and an academic rank in the student body.</span></span>

### <a name="to-add-the-data-source"></a><span data-ttu-id="0535a-122">添加数据源</span><span class="sxs-lookup"><span data-stu-id="0535a-122">To add the data source</span></span>

- <span data-ttu-id="0535a-123">`Student`定义类, 并创建类的实例的列表。</span><span class="sxs-lookup"><span data-stu-id="0535a-123">Define a `Student` class, and create a list of instances of the class.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="0535a-124">以下内容`Student` [提供了定义类并创建在演练示例中所使用的列表所需的代码。创建项](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)列表。</span><span class="sxs-lookup"><span data-stu-id="0535a-124">The code needed to define the `Student` class and create the list used in the walkthrough examples is provided in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="0535a-125">可以将其复制到项目中, 并将其粘贴到你的项目中。</span><span class="sxs-lookup"><span data-stu-id="0535a-125">You can copy it from there and paste it into your project.</span></span> <span data-ttu-id="0535a-126">新代码将替换在创建项目时显示的代码。</span><span class="sxs-lookup"><span data-stu-id="0535a-126">The new code replaces the code that appeared when you created the project.</span></span>

### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="0535a-127">向学生列表中添加新的学生</span><span class="sxs-lookup"><span data-stu-id="0535a-127">To add a new student to the students list</span></span>

- <span data-ttu-id="0535a-128">按照`getStudents`方法中的模式将`Student`类的另一个实例添加到列表。</span><span class="sxs-lookup"><span data-stu-id="0535a-128">Follow the pattern in the `getStudents` method to add another instance of the `Student` class to the list.</span></span> <span data-ttu-id="0535a-129">添加学生将向你介绍对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="0535a-129">Adding the student will introduce you to object initializers.</span></span> <span data-ttu-id="0535a-130">有关详细信息, 请[参阅对象初始值设定项:命名类型和匿名](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)类型。</span><span class="sxs-lookup"><span data-stu-id="0535a-130">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

## <a name="create-a-query"></a><span data-ttu-id="0535a-131">创建查询</span><span class="sxs-lookup"><span data-stu-id="0535a-131">Create a Query</span></span>

<span data-ttu-id="0535a-132">执行时, 此部分中添加的查询将生成一个学生列表, 其中的学生排名将其放在前十位。</span><span class="sxs-lookup"><span data-stu-id="0535a-132">When executed, the query added in this section produces a list of the students whose academic rank puts them in the top ten.</span></span> <span data-ttu-id="0535a-133">由于查询每次都选择`Student`完整的对象, 因此查询结果的类型为。 `IEnumerable(Of Student)`</span><span class="sxs-lookup"><span data-stu-id="0535a-133">Because the query selects the complete `Student` object each time, the type of the query result is `IEnumerable(Of Student)`.</span></span> <span data-ttu-id="0535a-134">但是, 查询的类型通常不在查询定义中指定。</span><span class="sxs-lookup"><span data-stu-id="0535a-134">However, the type of the query typically is not specified in query definitions.</span></span> <span data-ttu-id="0535a-135">相反, 编译器将使用局部类型推理来确定类型。</span><span class="sxs-lookup"><span data-stu-id="0535a-135">Instead, the compiler uses local type inference to determine the type.</span></span> <span data-ttu-id="0535a-136">有关详细信息, 请参阅[局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="0535a-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span> <span data-ttu-id="0535a-137">`currentStudent`查询的范围变量用作对源中每个`Student` `students`实例的引用, 提供对中`students`每个对象的属性的访问。</span><span class="sxs-lookup"><span data-stu-id="0535a-137">The query's range variable, `currentStudent`, serves as a reference to each `Student` instance in the source, `students`, providing access to the properties of each object in `students`.</span></span>

### <a name="to-create-a-simple-query"></a><span data-ttu-id="0535a-138">创建简单查询</span><span class="sxs-lookup"><span data-stu-id="0535a-138">To create a simple query</span></span>

1. <span data-ttu-id="0535a-139">查找项目的`Main`方法中标记为以下内容的位置:</span><span class="sxs-lookup"><span data-stu-id="0535a-139">Find the place in the `Main` method of the project that is marked as follows:</span></span>

    [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]

    <span data-ttu-id="0535a-140">复制以下代码并将其粘贴到中。</span><span class="sxs-lookup"><span data-stu-id="0535a-140">Copy the following code and paste it in.</span></span>

    [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]

2. <span data-ttu-id="0535a-141">将鼠标指针`studentQuery`停留在代码中, 以验证编译器分配的类型是否为`IEnumerable(Of Student)`。</span><span class="sxs-lookup"><span data-stu-id="0535a-141">Rest the mouse pointer over `studentQuery` in your code to verify that the compiler-assigned type is `IEnumerable(Of Student)`.</span></span>

## <a name="run-the-query"></a><span data-ttu-id="0535a-142">运行查询</span><span class="sxs-lookup"><span data-stu-id="0535a-142">Run the Query</span></span>

<span data-ttu-id="0535a-143">变量`studentQuery`包含查询的定义, 而不是运行查询的结果。</span><span class="sxs-lookup"><span data-stu-id="0535a-143">The variable `studentQuery` contains the definition of the query, not the results of running the query.</span></span> <span data-ttu-id="0535a-144">用于运行查询的一种典型机制是`For Each`循环。</span><span class="sxs-lookup"><span data-stu-id="0535a-144">A typical mechanism for running a query is a `For Each` loop.</span></span> <span data-ttu-id="0535a-145">返回序列中的每个元素都通过循环迭代变量来访问。</span><span class="sxs-lookup"><span data-stu-id="0535a-145">Each element in the returned sequence is accessed through the loop iteration variable.</span></span> <span data-ttu-id="0535a-146">有关查询执行的详细信息, 请参阅[编写第一个 LINQ 查询](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)。</span><span class="sxs-lookup"><span data-stu-id="0535a-146">For more information about query execution, see [Writing Your First LINQ Query](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>

### <a name="to-run-the-query"></a><span data-ttu-id="0535a-147">运行查询</span><span class="sxs-lookup"><span data-stu-id="0535a-147">To run the query</span></span>

1. <span data-ttu-id="0535a-148">在项目中`For Each`的查询下添加以下循环。</span><span class="sxs-lookup"><span data-stu-id="0535a-148">Add the following `For Each` loop below the query in your project.</span></span>

    [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]

2. <span data-ttu-id="0535a-149">将鼠标指针停留在循环控制变量`studentRecord`上, 以查看其数据类型。</span><span class="sxs-lookup"><span data-stu-id="0535a-149">Rest the mouse pointer over the loop control variable `studentRecord` to see its data type.</span></span> <span data-ttu-id="0535a-150">的类型`studentRecord`被推断`Student`为, 因为`studentQuery`返回实例的`Student`集合。</span><span class="sxs-lookup"><span data-stu-id="0535a-150">The type of `studentRecord` is inferred to be `Student`, because `studentQuery` returns a collection of `Student` instances.</span></span>

3. <span data-ttu-id="0535a-151">按 CTRL + F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="0535a-151">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="0535a-152">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="0535a-152">Note the results in the console window.</span></span>

## <a name="modify-the-query"></a><span data-ttu-id="0535a-153">修改查询</span><span class="sxs-lookup"><span data-stu-id="0535a-153">Modify the Query</span></span>

<span data-ttu-id="0535a-154">如果查询结果按指定顺序进行扫描, 则会更容易。</span><span class="sxs-lookup"><span data-stu-id="0535a-154">It is easier to scan query results if they are in a specified order.</span></span> <span data-ttu-id="0535a-155">您可以基于任何可用字段对返回的序列进行排序。</span><span class="sxs-lookup"><span data-stu-id="0535a-155">You can sort the returned sequence based on any available field.</span></span>

### <a name="to-order-the-results"></a><span data-ttu-id="0535a-156">对结果进行排序</span><span class="sxs-lookup"><span data-stu-id="0535a-156">To order the results</span></span>

1. <span data-ttu-id="0535a-157">在`Where`语句和`Order By` 查询的语句之间添加以下子句。`Select`</span><span class="sxs-lookup"><span data-stu-id="0535a-157">Add the following `Order By` clause between the `Where` statement and the `Select` statement of the query.</span></span> <span data-ttu-id="0535a-158">`Order By`子句根据每个学生的姓氏从 A 到 Z 的顺序对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="0535a-158">The `Order By` clause will order the results alphabetically from A to Z, according to the last name of each student.</span></span>

    ```
    Order By currentStudent.Last Ascending
    ```

2. <span data-ttu-id="0535a-159">若要按姓氏再按名字排序, 请将这两个字段添加到查询中:</span><span class="sxs-lookup"><span data-stu-id="0535a-159">To order by last name and then first name, add both fields to the query:</span></span>

    ```
    Order By currentStudent.Last Ascending, currentStudent.First Ascending
    ```

    <span data-ttu-id="0535a-160">您还可以指定`Descending`从 Z 到 A 的顺序。</span><span class="sxs-lookup"><span data-stu-id="0535a-160">You can also specify `Descending` to order from Z to A.</span></span>

3. <span data-ttu-id="0535a-161">按 CTRL + F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="0535a-161">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="0535a-162">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="0535a-162">Note the results in the console window.</span></span>

### <a name="to-introduce-a-local-identifier"></a><span data-ttu-id="0535a-163">引入本地标识符</span><span class="sxs-lookup"><span data-stu-id="0535a-163">To introduce a local identifier</span></span>

1. <span data-ttu-id="0535a-164">添加此部分中的代码, 以在查询表达式中引入本地标识符。</span><span class="sxs-lookup"><span data-stu-id="0535a-164">Add the code in this section to introduce a local identifier in the query expression.</span></span> <span data-ttu-id="0535a-165">本地标识符将保存中间结果。</span><span class="sxs-lookup"><span data-stu-id="0535a-165">The local identifier will hold an intermediate result.</span></span> <span data-ttu-id="0535a-166">在下面的示例中`name` , 是一个标识符, 该标识符保存学生的名字和姓氏的连接。</span><span class="sxs-lookup"><span data-stu-id="0535a-166">In the following example, `name` is an identifier that holds a concatenation of the student's first and last names.</span></span> <span data-ttu-id="0535a-167">本地标识符可用于方便起见, 也可通过存储表达式的结果来提高性能, 此表达式的计算结果将为多次。</span><span class="sxs-lookup"><span data-stu-id="0535a-167">A local identifier can be used for convenience, or it can enhance performance by storing the results of an expression that would otherwise be calculated multiple times.</span></span>

    [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]

2. <span data-ttu-id="0535a-168">按 CTRL + F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="0535a-168">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="0535a-169">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="0535a-169">Note the results in the console window.</span></span>

### <a name="to-project-one-field-in-the-select-clause"></a><span data-ttu-id="0535a-170">在 Select 子句中投影一个字段</span><span class="sxs-lookup"><span data-stu-id="0535a-170">To project one field in the Select clause</span></span>

1. <span data-ttu-id="0535a-171">添加此部分中`For Each`的查询和循环, 以创建一个查询, 该查询将生成一个其元素不同于源中的元素的序列。</span><span class="sxs-lookup"><span data-stu-id="0535a-171">Add the query and `For Each` loop from this section to create a query that produces a sequence whose elements differ from the elements in the source.</span></span> <span data-ttu-id="0535a-172">在下面的示例中, 源是`Student`对象的集合, 但只返回每个对象的一个成员: 姓氏为 Garcia 的学生名字。</span><span class="sxs-lookup"><span data-stu-id="0535a-172">In the following example, the source is a collection of `Student` objects, but only one member of each object is returned: the first name of students whose last name is Garcia.</span></span> <span data-ttu-id="0535a-173">由于`currentStudent.First`是一个字符串, `studentQuery3`返回的序列的数据类型是`IEnumerable(Of String)`一个字符串序列。</span><span class="sxs-lookup"><span data-stu-id="0535a-173">Because `currentStudent.First` is a string, the data type of the sequence returned by `studentQuery3` is `IEnumerable(Of String)`, a sequence of strings.</span></span> <span data-ttu-id="0535a-174">如前面的示例所示, 的数据类型`studentQuery3`的分配留给编译器通过使用局部类型推理来确定。</span><span class="sxs-lookup"><span data-stu-id="0535a-174">As in earlier examples, the assignment of a data type for `studentQuery3` is left for the compiler to determine by using local type inference.</span></span>

    [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]

2. <span data-ttu-id="0535a-175">将鼠标指针`studentQuery3`停留在代码中, 以验证分配的类型是否为`IEnumerable(Of String)`。</span><span class="sxs-lookup"><span data-stu-id="0535a-175">Rest the mouse pointer over `studentQuery3` in your code to verify that the assigned type is `IEnumerable(Of String)`.</span></span>

3. <span data-ttu-id="0535a-176">按 CTRL + F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="0535a-176">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="0535a-177">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="0535a-177">Note the results in the console window.</span></span>

### <a name="to-create-an-anonymous-type-in-the-select-clause"></a><span data-ttu-id="0535a-178">在 Select 子句中创建匿名类型</span><span class="sxs-lookup"><span data-stu-id="0535a-178">To create an anonymous type in the Select clause</span></span>

1. <span data-ttu-id="0535a-179">添加此部分中的代码, 以了解如何在查询中使用匿名类型。</span><span class="sxs-lookup"><span data-stu-id="0535a-179">Add the code from this section to see how anonymous types are used in queries.</span></span> <span data-ttu-id="0535a-180">如果要从数据源返回多个字段, 而不是完整记录 (`currentStudent`前面示例中的记录) 或单个字段 (`First`在上一节中), 可以在查询中使用它们。</span><span class="sxs-lookup"><span data-stu-id="0535a-180">You use them in queries when you want to return several fields from the data source rather than complete records (`currentStudent` records in previous examples) or single fields (`First` in the preceding section).</span></span> <span data-ttu-id="0535a-181">您可以在`Select`子句中指定字段, 而不是定义一个新的命名类型 (其中包含您想要包括在结果中的字段), 而编译器会创建一个匿名类型, 并将这些字段作为其属性。</span><span class="sxs-lookup"><span data-stu-id="0535a-181">Instead of defining a new named type that contains the fields you want to include in the result, you specify the fields in the `Select` clause and the compiler creates an anonymous type with those fields as its properties.</span></span> <span data-ttu-id="0535a-182">有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="0535a-182">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

    <span data-ttu-id="0535a-183">下面的示例创建一个查询, 该查询返回学术排名介于1到10之间的发言的名称和排名, 按学术排名排序。</span><span class="sxs-lookup"><span data-stu-id="0535a-183">The following example creates a query that returns the name and rank of seniors whose academic rank is between 1 and 10, in order of academic rank.</span></span> <span data-ttu-id="0535a-184">在此示例中, `studentQuery4`必须推断的类型, `Select`因为子句返回匿名类型的实例, 而匿名类型没有可使用的名称。</span><span class="sxs-lookup"><span data-stu-id="0535a-184">In this example, the type of `studentQuery4` must be inferred because the `Select` clause returns an instance of an anonymous type, and an anonymous type has no usable name.</span></span>

    [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]

2. <span data-ttu-id="0535a-185">按 CTRL + F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="0535a-185">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="0535a-186">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="0535a-186">Note the results in the console window.</span></span>

## <a name="additional-examples"></a><span data-ttu-id="0535a-187">其他示例</span><span class="sxs-lookup"><span data-stu-id="0535a-187">Additional Examples</span></span>

<span data-ttu-id="0535a-188">现在, 你已了解基础知识, 以下是说明[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询灵活性和功能的其他示例的列表。</span><span class="sxs-lookup"><span data-stu-id="0535a-188">Now that you understand the basics, the following is a list of additional examples to illustrate the flexibility and power of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="0535a-189">每个示例前面都有其作用的简短说明。</span><span class="sxs-lookup"><span data-stu-id="0535a-189">Each example is preceded by a brief description of what it does.</span></span> <span data-ttu-id="0535a-190">将鼠标指针停留在每个查询的查询结果变量上, 以查看推断出的类型。</span><span class="sxs-lookup"><span data-stu-id="0535a-190">Rest the mouse pointer over the query result variable for each query to see the inferred type.</span></span> <span data-ttu-id="0535a-191">`For Each`使用循环来生成结果。</span><span class="sxs-lookup"><span data-stu-id="0535a-191">Use a `For Each` loop to produce the results.</span></span>

[!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]

## <a name="additional-information"></a><span data-ttu-id="0535a-192">其他信息</span><span class="sxs-lookup"><span data-stu-id="0535a-192">Additional Information</span></span>

<span data-ttu-id="0535a-193">熟悉使用查询的基本概念后, 就可以阅读感兴趣的特定类型[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]提供程序的文档和示例:</span><span class="sxs-lookup"><span data-stu-id="0535a-193">After you are familiar with the basic concepts of working with queries, you are ready to read the documentation and samples for the specific type of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider that you are interested in:</span></span>

- [<span data-ttu-id="0535a-194">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="0535a-194">LINQ to Objects</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)

- [<span data-ttu-id="0535a-195">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0535a-195">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)

- [<span data-ttu-id="0535a-196">LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="0535a-196">LINQ to XML</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)

- [<span data-ttu-id="0535a-197">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="0535a-197">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)

## <a name="see-also"></a><span data-ttu-id="0535a-198">请参阅</span><span class="sxs-lookup"><span data-stu-id="0535a-198">See also</span></span>

- [<span data-ttu-id="0535a-199">语言集成查询 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0535a-199">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="0535a-200">Visual Basic 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="0535a-200">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="0535a-201">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="0535a-201">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="0535a-202">对象初始值设定项:命名类型和匿名类型</span><span class="sxs-lookup"><span data-stu-id="0535a-202">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="0535a-203">匿名类型</span><span class="sxs-lookup"><span data-stu-id="0535a-203">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="0535a-204">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="0535a-204">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="0535a-205">LINQ</span><span class="sxs-lookup"><span data-stu-id="0535a-205">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="0535a-206">查询</span><span class="sxs-lookup"><span data-stu-id="0535a-206">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
