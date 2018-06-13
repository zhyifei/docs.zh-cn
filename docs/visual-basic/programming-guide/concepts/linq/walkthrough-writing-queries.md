---
title: 在 Visual Basic 中编写查询
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: beb192f6b136455cb1adcb6cf2616578b63fcebf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655871"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a><span data-ttu-id="80c80-102">演练：用 Visual Basic 编写查询</span><span class="sxs-lookup"><span data-stu-id="80c80-102">Walkthrough: Writing Queries in Visual Basic</span></span>
<span data-ttu-id="80c80-103">本演练演示如何使用 Visual Basic 语言功能来编写[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]查询表达式。</span><span class="sxs-lookup"><span data-stu-id="80c80-103">This walkthrough demonstrates how you can use Visual Basic language features to write [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query expressions.</span></span> <span data-ttu-id="80c80-104">本演练说明如何在列表中的学生对象创建查询、 如何运行查询，以及如何对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="80c80-104">The walkthrough demonstrates how to create queries on a list of Student objects, how to run the queries, and how to modify them.</span></span> <span data-ttu-id="80c80-105">查询将包括对象初始值设定项、 本地类型推断、 和匿名类型的多个功能合并。</span><span class="sxs-lookup"><span data-stu-id="80c80-105">The queries incorporate several features including object initializers, local type inference, and anonymous types.</span></span>  
  
 <span data-ttu-id="80c80-106">完成此演练后，你将准备好将移到的示例和文档的特定[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]你感兴趣的提供程序。</span><span class="sxs-lookup"><span data-stu-id="80c80-106">After completing this walkthrough, you will be ready to move on to the samples and documentation for the specific [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider you are interested in.</span></span> [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]<span data-ttu-id="80c80-107"> 提供程序包括[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]， [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)]，和[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80c80-107"> providers include [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
## <a name="create-a-project"></a><span data-ttu-id="80c80-108">创建项目</span><span class="sxs-lookup"><span data-stu-id="80c80-108">Create a Project</span></span>  
  
#### <a name="to-create-a-console-application-project"></a><span data-ttu-id="80c80-109">若要创建控制台应用程序项目</span><span class="sxs-lookup"><span data-stu-id="80c80-109">To create a console application project</span></span>  
  
1.  <span data-ttu-id="80c80-110">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="80c80-110">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="80c80-111">在 **“文件”** 菜单上，指向 **“新建”**，然后单击 **“项目”**。</span><span class="sxs-lookup"><span data-stu-id="80c80-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="80c80-112">在**已安装的模板**列表中，单击**Visual Basic**。</span><span class="sxs-lookup"><span data-stu-id="80c80-112">In the **Installed Templates** list, click **Visual Basic**.</span></span>  
  
4.  <span data-ttu-id="80c80-113">在项目类型列表中，单击**控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="80c80-113">In the list of project types, click **Console Application**.</span></span> <span data-ttu-id="80c80-114">在**名称**框中，为项目中，键入一个名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="80c80-114">In the **Name** box, type a name for the project, and then click **OK**.</span></span>  
  
     <span data-ttu-id="80c80-115">创建一个项目。</span><span class="sxs-lookup"><span data-stu-id="80c80-115">A project is created.</span></span> <span data-ttu-id="80c80-116">默认情况下，它包含对 System.Core.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="80c80-116">By default, it contains a reference to System.Core.dll.</span></span> <span data-ttu-id="80c80-117">此外，**导入命名空间**列表上[引用页上，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)包括<xref:System.Linq?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="80c80-117">Also, the **Imported namespaces** list on the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) includes the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
5.  <span data-ttu-id="80c80-118">上[编译页，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)，确保**Option infer**设置为**上**。</span><span class="sxs-lookup"><span data-stu-id="80c80-118">On the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), ensure that **Option infer** is set to **On**.</span></span>  
  
## <a name="add-an-in-memory-data-source"></a><span data-ttu-id="80c80-119">添加一个内存中数据源</span><span class="sxs-lookup"><span data-stu-id="80c80-119">Add an In-Memory Data Source</span></span>  
 <span data-ttu-id="80c80-120">本演练中的查询的数据源是一份`Student`对象。</span><span class="sxs-lookup"><span data-stu-id="80c80-120">The data source for the queries in this walkthrough is a list of `Student` objects.</span></span> <span data-ttu-id="80c80-121">每个`Student`对象包含名字、 姓氏、 类年、 和中学生正文学术级别。</span><span class="sxs-lookup"><span data-stu-id="80c80-121">Each `Student` object contains a first name, a last name, a class year, and an academic rank in the student body.</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="80c80-122">添加数据源</span><span class="sxs-lookup"><span data-stu-id="80c80-122">To add the data source</span></span>  
  
-   <span data-ttu-id="80c80-123">定义`Student`类，并创建的类的实例的列表。</span><span class="sxs-lookup"><span data-stu-id="80c80-123">Define a `Student` class, and create a list of instances of the class.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="80c80-124">定义所需的代码`Student`类，并创建使用的列表在本演练中提供示例[如何： 创建项列表](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)。</span><span class="sxs-lookup"><span data-stu-id="80c80-124">The code needed to define the `Student` class and create the list used in the walkthrough examples is provided in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="80c80-125">你可以在此处复制，并将其粘贴到你的项目。</span><span class="sxs-lookup"><span data-stu-id="80c80-125">You can copy it from there and paste it into your project.</span></span> <span data-ttu-id="80c80-126">新代码将替换出现在创建项目时的代码。</span><span class="sxs-lookup"><span data-stu-id="80c80-126">The new code replaces the code that appeared when you created the project.</span></span>  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="80c80-127">若要将新的学生添加到学生列表</span><span class="sxs-lookup"><span data-stu-id="80c80-127">To add a new student to the students list</span></span>  
  
-   <span data-ttu-id="80c80-128">请按照中的模式`getStudents`方法将添加的另一个实例`Student`到列表的类。</span><span class="sxs-lookup"><span data-stu-id="80c80-128">Follow the pattern in the `getStudents` method to add another instance of the `Student` class to the list.</span></span> <span data-ttu-id="80c80-129">添加学生将向你介绍对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="80c80-129">Adding the student will introduce you to object initializers.</span></span> <span data-ttu-id="80c80-130">有关详细信息，请参阅[对象初始值设定项： 命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="80c80-130">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>  
  
## <a name="create-a-query"></a><span data-ttu-id="80c80-131">创建查询</span><span class="sxs-lookup"><span data-stu-id="80c80-131">Create a Query</span></span>  
 <span data-ttu-id="80c80-132">在执行时，此部分中添加此查询将生成其学术级别将它们放入前 10 个学生的列表。</span><span class="sxs-lookup"><span data-stu-id="80c80-132">When executed, the query added in this section produces a list of the students whose academic rank puts them in the top ten.</span></span> <span data-ttu-id="80c80-133">因为查询选择完整`Student`对象每次查询结果的类型是`IEnumerable(Of Student)`。</span><span class="sxs-lookup"><span data-stu-id="80c80-133">Because the query selects the complete `Student` object each time, the type of the query result is `IEnumerable(Of Student)`.</span></span> <span data-ttu-id="80c80-134">但是，查询的类型通常是未指定查询定义中。</span><span class="sxs-lookup"><span data-stu-id="80c80-134">However, the type of the query typically is not specified in query definitions.</span></span> <span data-ttu-id="80c80-135">相反，编译器使用局部类型推理来确定类型。</span><span class="sxs-lookup"><span data-stu-id="80c80-135">Instead, the compiler uses local type inference to determine the type.</span></span> <span data-ttu-id="80c80-136">有关详细信息，请参阅[本地类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="80c80-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span> <span data-ttu-id="80c80-137">查询的范围变量`currentStudent`，用作参考，给每个`Student`源中的实例`students`，提供对中每个对象的属性访问`students`。</span><span class="sxs-lookup"><span data-stu-id="80c80-137">The query's range variable, `currentStudent`, serves as a reference to each `Student` instance in the source, `students`, providing access to the properties of each object in `students`.</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="80c80-138">创建简单查询</span><span class="sxs-lookup"><span data-stu-id="80c80-138">To create a simple query</span></span>  
  
1.  <span data-ttu-id="80c80-139">查找中的位置`Main`标记，如下所示的项目的方法：</span><span class="sxs-lookup"><span data-stu-id="80c80-139">Find the place in the `Main` method of the project that is marked as follows:</span></span>  
  
     [!code-vb[VbLINQWalkthrough#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]  
  
     <span data-ttu-id="80c80-140">复制下面的代码并将其粘贴中。</span><span class="sxs-lookup"><span data-stu-id="80c80-140">Copy the following code and paste it in.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]  
  
2.  <span data-ttu-id="80c80-141">将鼠标指针停留在`studentQuery`代码来验证编译器分配类型是否为`IEnumerable(Of Student)`。</span><span class="sxs-lookup"><span data-stu-id="80c80-141">Rest the mouse pointer over `studentQuery` in your code to verify that the compiler-assigned type is `IEnumerable(Of Student)`.</span></span>  
  
## <a name="run-the-query"></a><span data-ttu-id="80c80-142">运行查询</span><span class="sxs-lookup"><span data-stu-id="80c80-142">Run the Query</span></span>  
 <span data-ttu-id="80c80-143">变量`studentQuery`包含定义的查询，不运行查询的结果。</span><span class="sxs-lookup"><span data-stu-id="80c80-143">The variable `studentQuery` contains the definition of the query, not the results of running the query.</span></span> <span data-ttu-id="80c80-144">用于运行查询的典型机制是`For Each`循环。</span><span class="sxs-lookup"><span data-stu-id="80c80-144">A typical mechanism for running a query is a `For Each` loop.</span></span> <span data-ttu-id="80c80-145">返回序列中的每个元素进行访问通过循环迭代变量。</span><span class="sxs-lookup"><span data-stu-id="80c80-145">Each element in the returned sequence is accessed through the loop iteration variable.</span></span> <span data-ttu-id="80c80-146">有关执行查询的详细信息，请参阅[编写你的第一个 LINQ 查询](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)。</span><span class="sxs-lookup"><span data-stu-id="80c80-146">For more information about query execution, see [Writing Your First LINQ Query](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
#### <a name="to-run-the-query"></a><span data-ttu-id="80c80-147">若要运行查询</span><span class="sxs-lookup"><span data-stu-id="80c80-147">To run the query</span></span>  
  
1.  <span data-ttu-id="80c80-148">添加以下`For Each`下面你的项目中的查询的循环。</span><span class="sxs-lookup"><span data-stu-id="80c80-148">Add the following `For Each` loop below the query in your project.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]  
  
2.  <span data-ttu-id="80c80-149">将鼠标指针停留在循环控制变量`studentRecord`以查看其数据类型。</span><span class="sxs-lookup"><span data-stu-id="80c80-149">Rest the mouse pointer over the loop control variable `studentRecord` to see its data type.</span></span> <span data-ttu-id="80c80-150">一种`studentRecord`将被推断`Student`，这是因为`studentQuery`返回的集合`Student`实例。</span><span class="sxs-lookup"><span data-stu-id="80c80-150">The type of `studentRecord` is inferred to be `Student`, because `studentQuery` returns a collection of `Student` instances.</span></span>  
  
3.  <span data-ttu-id="80c80-151">生成并通过按 CTRL + F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="80c80-151">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="80c80-152">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="80c80-152">Note the results in the console window.</span></span>  
  
## <a name="modify-the-query"></a><span data-ttu-id="80c80-153">修改查询</span><span class="sxs-lookup"><span data-stu-id="80c80-153">Modify the Query</span></span>  
 <span data-ttu-id="80c80-154">很容易地扫描查询结果，如果它们在指定的顺序。</span><span class="sxs-lookup"><span data-stu-id="80c80-154">It is easier to scan query results if they are in a specified order.</span></span> <span data-ttu-id="80c80-155">可以对返回基于任何可用字段的序列进行排序。</span><span class="sxs-lookup"><span data-stu-id="80c80-155">You can sort the returned sequence based on any available field.</span></span>  
  
#### <a name="to-order-the-results"></a><span data-ttu-id="80c80-156">对结果进行排序</span><span class="sxs-lookup"><span data-stu-id="80c80-156">To order the results</span></span>  
  
1.  <span data-ttu-id="80c80-157">添加以下`Order By`之间子句`Where`语句和`Select`语句的查询。</span><span class="sxs-lookup"><span data-stu-id="80c80-157">Add the following `Order By` clause between the `Where` statement and the `Select` statement of the query.</span></span> <span data-ttu-id="80c80-158">`Order By`子句将字母顺序对结果从 A 到 Z、 到最后一个根据每个学生的名字。</span><span class="sxs-lookup"><span data-stu-id="80c80-158">The `Order By` clause will order the results alphabetically from A to Z, according to the last name of each student.</span></span>  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  <span data-ttu-id="80c80-159">若要通过最后一个名称，然后按名字排序，请向查询添加这两个字段：</span><span class="sxs-lookup"><span data-stu-id="80c80-159">To order by last name and then first name, add both fields to the query:</span></span>  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     <span data-ttu-id="80c80-160">你还可以指定`Descending`到顺序从 Z 到 a。</span><span class="sxs-lookup"><span data-stu-id="80c80-160">You can also specify `Descending` to order from Z to A.</span></span>  
  
3.  <span data-ttu-id="80c80-161">生成并通过按 CTRL + F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="80c80-161">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="80c80-162">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="80c80-162">Note the results in the console window.</span></span>  
  
#### <a name="to-introduce-a-local-identifier"></a><span data-ttu-id="80c80-163">若要将本地标识符引入</span><span class="sxs-lookup"><span data-stu-id="80c80-163">To introduce a local identifier</span></span>  
  
1.  <span data-ttu-id="80c80-164">在查询表达式将本地标识符引入此部分中添加代码。</span><span class="sxs-lookup"><span data-stu-id="80c80-164">Add the code in this section to introduce a local identifier in the query expression.</span></span> <span data-ttu-id="80c80-165">本地标识符将保留中间结果。</span><span class="sxs-lookup"><span data-stu-id="80c80-165">The local identifier will hold an intermediate result.</span></span> <span data-ttu-id="80c80-166">在下面的示例中，`name`是保存学生的串联的标识符的名字和姓氏。</span><span class="sxs-lookup"><span data-stu-id="80c80-166">In the following example, `name` is an identifier that holds a concatenation of the student's first and last names.</span></span> <span data-ttu-id="80c80-167">为方便起见，可以使用的本地标识符或也可以通过将存储否则可计算多次表达式的结果来提高性能。</span><span class="sxs-lookup"><span data-stu-id="80c80-167">A local identifier can be used for convenience, or it can enhance performance by storing the results of an expression that would otherwise be calculated multiple times.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]  
  
2.  <span data-ttu-id="80c80-168">生成并通过按 CTRL + F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="80c80-168">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="80c80-169">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="80c80-169">Note the results in the console window.</span></span>  
  
#### <a name="to-project-one-field-in-the-select-clause"></a><span data-ttu-id="80c80-170">投影 Select 子句中的一个字段</span><span class="sxs-lookup"><span data-stu-id="80c80-170">To project one field in the Select clause</span></span>  
  
1.  <span data-ttu-id="80c80-171">将查询添加和`For Each`从此部分以创建一个查询，生成一个序列，其元素与不同的源中的元素的循环。</span><span class="sxs-lookup"><span data-stu-id="80c80-171">Add the query and `For Each` loop from this section to create a query that produces a sequence whose elements differ from the elements in the source.</span></span> <span data-ttu-id="80c80-172">在以下示例中，源是一套`Student`返回对象，但只有一个成员的每个对象： 其姓氏为 Garcia 学生的名字。</span><span class="sxs-lookup"><span data-stu-id="80c80-172">In the following example, the source is a collection of `Student` objects, but only one member of each object is returned: the first name of students whose last name is Garcia.</span></span> <span data-ttu-id="80c80-173">因为`currentStudent.First`是一个字符串，返回的序列的数据类型`studentQuery3`是`IEnumerable(Of String)`，一个字符串序列。</span><span class="sxs-lookup"><span data-stu-id="80c80-173">Because `currentStudent.First` is a string, the data type of the sequence returned by `studentQuery3` is `IEnumerable(Of String)`, a sequence of strings.</span></span> <span data-ttu-id="80c80-174">如前面的示例所示的数据分配键入`studentQuery3`留给编译器使用局部类型推理来确定。</span><span class="sxs-lookup"><span data-stu-id="80c80-174">As in earlier examples, the assignment of a data type for `studentQuery3` is left for the compiler to determine by using local type inference.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]  
  
2.  <span data-ttu-id="80c80-175">将鼠标指针停留在`studentQuery3`代码来验证分配的类型是否为`IEnumerable(Of String)`。</span><span class="sxs-lookup"><span data-stu-id="80c80-175">Rest the mouse pointer over `studentQuery3` in your code to verify that the assigned type is `IEnumerable(Of String)`.</span></span>  
  
3.  <span data-ttu-id="80c80-176">生成并通过按 CTRL + F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="80c80-176">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="80c80-177">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="80c80-177">Note the results in the console window.</span></span>  
  
#### <a name="to-create-an-anonymous-type-in-the-select-clause"></a><span data-ttu-id="80c80-178">若要在 Select 子句中创建一个匿名类型</span><span class="sxs-lookup"><span data-stu-id="80c80-178">To create an anonymous type in the Select clause</span></span>  
  
1.  <span data-ttu-id="80c80-179">添加查询中使用的该部分以查看如何匿名类型中的代码。</span><span class="sxs-lookup"><span data-stu-id="80c80-179">Add the code from this section to see how anonymous types are used in queries.</span></span> <span data-ttu-id="80c80-180">如果您使用它们在查询中你想要从数据源而不是完整记录返回多个字段 (`currentStudent`前面的示例中的记录) 或单个字段 (`First`在上一部分中)。</span><span class="sxs-lookup"><span data-stu-id="80c80-180">You use them in queries when you want to return several fields from the data source rather than complete records (`currentStudent` records in previous examples) or single fields (`First` in the preceding section).</span></span> <span data-ttu-id="80c80-181">而不是定义新命名的类型，包含你想要在结果中包含的字段，指定中的字段`Select`子句和编译器创建一个匿名类型以这些字段作为其属性。</span><span class="sxs-lookup"><span data-stu-id="80c80-181">Instead of defining a new named type that contains the fields you want to include in the result, you specify the fields in the `Select` clause and the compiler creates an anonymous type with those fields as its properties.</span></span> <span data-ttu-id="80c80-182">有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="80c80-182">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="80c80-183">下面的示例创建查询返回的名称和其学术级别是介于 1 和 10，顺序学术级别之间的高年级学生的秩。</span><span class="sxs-lookup"><span data-stu-id="80c80-183">The following example creates a query that returns the name and rank of seniors whose academic rank is between 1 and 10, in order of academic rank.</span></span> <span data-ttu-id="80c80-184">在此示例中的一种`studentQuery4`必须无法推断，因为`Select`子句将返回一个匿名类型的实例和一个匿名类型有没有可用的名称。</span><span class="sxs-lookup"><span data-stu-id="80c80-184">In this example, the type of `studentQuery4` must be inferred because the `Select` clause returns an instance of an anonymous type, and an anonymous type has no usable name.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]  
  
2.  <span data-ttu-id="80c80-185">生成并通过按 CTRL + F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="80c80-185">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="80c80-186">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="80c80-186">Note the results in the console window.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="80c80-187">其他示例</span><span class="sxs-lookup"><span data-stu-id="80c80-187">Additional Examples</span></span>  
 <span data-ttu-id="80c80-188">现在，你已了解基础知识，下面是其他示例来演示灵活的列表以及的幂[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询。</span><span class="sxs-lookup"><span data-stu-id="80c80-188">Now that you understand the basics, the following is a list of additional examples to illustrate the flexibility and power of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="80c80-189">每个示例被前面其用途的简短说明。</span><span class="sxs-lookup"><span data-stu-id="80c80-189">Each example is preceded by a brief description of what it does.</span></span> <span data-ttu-id="80c80-190">鼠标指针停留在每个查询，以查看推断出的类型的查询结果变量。</span><span class="sxs-lookup"><span data-stu-id="80c80-190">Rest the mouse pointer over the query result variable for each query to see the inferred type.</span></span> <span data-ttu-id="80c80-191">使用`For Each`循环以产生的结果。</span><span class="sxs-lookup"><span data-stu-id="80c80-191">Use a `For Each` loop to produce the results.</span></span>  
  
 [!code-vb[VbLINQWalkthrough#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]  
  
## <a name="additional-information"></a><span data-ttu-id="80c80-192">其他信息</span><span class="sxs-lookup"><span data-stu-id="80c80-192">Additional Information</span></span>  
 <span data-ttu-id="80c80-193">你熟悉使用查询的基本概念后，你就可以读取的特定类型的文档和示例[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]你感兴趣的提供程序：</span><span class="sxs-lookup"><span data-stu-id="80c80-193">After you are familiar with the basic concepts of working with queries, you are ready to read the documentation and samples for the specific type of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider that you are interested in:</span></span>  
  
 [<span data-ttu-id="80c80-194">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="80c80-194">LINQ to Objects</span></span>](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)  
  
 [<span data-ttu-id="80c80-195">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="80c80-195">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [<span data-ttu-id="80c80-196">LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="80c80-196">LINQ to XML</span></span>](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)  
  
 [<span data-ttu-id="80c80-197">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="80c80-197">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)  
  
## <a name="see-also"></a><span data-ttu-id="80c80-198">请参阅</span><span class="sxs-lookup"><span data-stu-id="80c80-198">See Also</span></span>  
 [<span data-ttu-id="80c80-199">语言集成查询 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80c80-199">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 [<span data-ttu-id="80c80-200">Visual Basic 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="80c80-200">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="80c80-201">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="80c80-201">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="80c80-202">对象初始值设定项：命名类型和匿名类型</span><span class="sxs-lookup"><span data-stu-id="80c80-202">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="80c80-203">匿名类型</span><span class="sxs-lookup"><span data-stu-id="80c80-203">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="80c80-204">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="80c80-204">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="80c80-205">LINQ</span><span class="sxs-lookup"><span data-stu-id="80c80-205">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="80c80-206">查询</span><span class="sxs-lookup"><span data-stu-id="80c80-206">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)
