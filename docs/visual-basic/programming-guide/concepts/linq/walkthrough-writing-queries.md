---
title: 在 Visual Basic 中编写查询
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 8e3d893a21b36868f59d132bd8ba9a6f634cac62
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296064"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a><span data-ttu-id="c74a3-102">演练：在 Visual Basic 中编写查询</span><span class="sxs-lookup"><span data-stu-id="c74a3-102">Walkthrough: Writing Queries in Visual Basic</span></span>
<span data-ttu-id="c74a3-103">本演练演示如何使用 Visual Basic 语言功能编写[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]查询表达式。</span><span class="sxs-lookup"><span data-stu-id="c74a3-103">This walkthrough demonstrates how you can use Visual Basic language features to write [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query expressions.</span></span> <span data-ttu-id="c74a3-104">本演练演示如何在列表中的学生对象创建查询、 运行查询，以及如何对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="c74a3-104">The walkthrough demonstrates how to create queries on a list of Student objects, how to run the queries, and how to modify them.</span></span> <span data-ttu-id="c74a3-105">查询将合并多个功能，包括对象初始值设定项、 局部类型推理和匿名类型。</span><span class="sxs-lookup"><span data-stu-id="c74a3-105">The queries incorporate several features including object initializers, local type inference, and anonymous types.</span></span>  
  
 <span data-ttu-id="c74a3-106">完成此演练后，您将随时可以转到示例和文档的特定[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]感兴趣的提供程序。</span><span class="sxs-lookup"><span data-stu-id="c74a3-106">After completing this walkthrough, you will be ready to move on to the samples and documentation for the specific [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider you are interested in.</span></span> [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] <span data-ttu-id="c74a3-107">提供程序包括[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]， [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)]，和[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c74a3-107">providers include [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
## <a name="create-a-project"></a><span data-ttu-id="c74a3-108">创建项目</span><span class="sxs-lookup"><span data-stu-id="c74a3-108">Create a Project</span></span>  
  
#### <a name="to-create-a-console-application-project"></a><span data-ttu-id="c74a3-109">若要创建控制台应用程序项目</span><span class="sxs-lookup"><span data-stu-id="c74a3-109">To create a console application project</span></span>  
  
1. <span data-ttu-id="c74a3-110">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="c74a3-110">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="c74a3-111">在 **“文件”** 菜单上，指向 **“新建”**，然后单击 **“项目”**。</span><span class="sxs-lookup"><span data-stu-id="c74a3-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="c74a3-112">在中**已安装的模板**列表中，单击**Visual Basic**。</span><span class="sxs-lookup"><span data-stu-id="c74a3-112">In the **Installed Templates** list, click **Visual Basic**.</span></span>  
  
4. <span data-ttu-id="c74a3-113">在项目类型列表中，单击**控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="c74a3-113">In the list of project types, click **Console Application**.</span></span> <span data-ttu-id="c74a3-114">在中**名称**框中，键入项目的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c74a3-114">In the **Name** box, type a name for the project, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c74a3-115">创建一个项目。</span><span class="sxs-lookup"><span data-stu-id="c74a3-115">A project is created.</span></span> <span data-ttu-id="c74a3-116">默认情况下，它包含对 system.core.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="c74a3-116">By default, it contains a reference to System.Core.dll.</span></span> <span data-ttu-id="c74a3-117">此外，**导入命名空间**上列出[，项目设计器 (Visual Basic) 引用页](/visualstudio/ide/reference/references-page-project-designer-visual-basic)包括<xref:System.Linq?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="c74a3-117">Also, the **Imported namespaces** list on the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) includes the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
5. <span data-ttu-id="c74a3-118">上[编译页，项目设计器 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)，确保**Option infer**设置为**上**。</span><span class="sxs-lookup"><span data-stu-id="c74a3-118">On the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), ensure that **Option infer** is set to **On**.</span></span>  
  
## <a name="add-an-in-memory-data-source"></a><span data-ttu-id="c74a3-119">添加的内存中数据源</span><span class="sxs-lookup"><span data-stu-id="c74a3-119">Add an In-Memory Data Source</span></span>  
 <span data-ttu-id="c74a3-120">在本演练中的查询的数据源是一系列`Student`对象。</span><span class="sxs-lookup"><span data-stu-id="c74a3-120">The data source for the queries in this walkthrough is a list of `Student` objects.</span></span> <span data-ttu-id="c74a3-121">每个`Student`对象包含名字、 姓氏、 一类和学术排名学生正文中的。</span><span class="sxs-lookup"><span data-stu-id="c74a3-121">Each `Student` object contains a first name, a last name, a class year, and an academic rank in the student body.</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="c74a3-122">添加数据源</span><span class="sxs-lookup"><span data-stu-id="c74a3-122">To add the data source</span></span>  
  
-   <span data-ttu-id="c74a3-123">定义`Student`类，并创建类的实例的列表。</span><span class="sxs-lookup"><span data-stu-id="c74a3-123">Define a `Student` class, and create a list of instances of the class.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c74a3-124">定义所需的代码`Student`类，并创建使用的列表在本演练中提供示例[如何：创建的项列表](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)。</span><span class="sxs-lookup"><span data-stu-id="c74a3-124">The code needed to define the `Student` class and create the list used in the walkthrough examples is provided in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="c74a3-125">可以在此处复制并将其粘贴到你的项目。</span><span class="sxs-lookup"><span data-stu-id="c74a3-125">You can copy it from there and paste it into your project.</span></span> <span data-ttu-id="c74a3-126">新代码将替换在创建项目时出现的代码。</span><span class="sxs-lookup"><span data-stu-id="c74a3-126">The new code replaces the code that appeared when you created the project.</span></span>  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="c74a3-127">若要向学生列表添加新学生</span><span class="sxs-lookup"><span data-stu-id="c74a3-127">To add a new student to the students list</span></span>  
  
-   <span data-ttu-id="c74a3-128">请按照中的模式`getStudents`方法中添加的另一个实例`Student`到列表的类。</span><span class="sxs-lookup"><span data-stu-id="c74a3-128">Follow the pattern in the `getStudents` method to add another instance of the `Student` class to the list.</span></span> <span data-ttu-id="c74a3-129">添加学生将介绍对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="c74a3-129">Adding the student will introduce you to object initializers.</span></span> <span data-ttu-id="c74a3-130">有关详细信息，请参阅[对象初始值设定项：命名和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="c74a3-130">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>  
  
## <a name="create-a-query"></a><span data-ttu-id="c74a3-131">创建查询</span><span class="sxs-lookup"><span data-stu-id="c74a3-131">Create a Query</span></span>  
 <span data-ttu-id="c74a3-132">执行时，在本部分中添加查询将生成其学术排名将其放入前十个学生列表。</span><span class="sxs-lookup"><span data-stu-id="c74a3-132">When executed, the query added in this section produces a list of the students whose academic rank puts them in the top ten.</span></span> <span data-ttu-id="c74a3-133">因为该查询用于选择完整`Student`对象每次查询结果的类型是`IEnumerable(Of Student)`。</span><span class="sxs-lookup"><span data-stu-id="c74a3-133">Because the query selects the complete `Student` object each time, the type of the query result is `IEnumerable(Of Student)`.</span></span> <span data-ttu-id="c74a3-134">但是，查询类型通常是未指定在查询定义中。</span><span class="sxs-lookup"><span data-stu-id="c74a3-134">However, the type of the query typically is not specified in query definitions.</span></span> <span data-ttu-id="c74a3-135">相反，编译器使用局部类型推理来确定的类型。</span><span class="sxs-lookup"><span data-stu-id="c74a3-135">Instead, the compiler uses local type inference to determine the type.</span></span> <span data-ttu-id="c74a3-136">有关详细信息，请参阅[本地类型推断](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="c74a3-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span> <span data-ttu-id="c74a3-137">查询的范围变量`currentStudent`，可作为对每个引用`Student`在源中的实例`students`，提供对中的每个对象的属性访问`students`。</span><span class="sxs-lookup"><span data-stu-id="c74a3-137">The query's range variable, `currentStudent`, serves as a reference to each `Student` instance in the source, `students`, providing access to the properties of each object in `students`.</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="c74a3-138">创建简单查询</span><span class="sxs-lookup"><span data-stu-id="c74a3-138">To create a simple query</span></span>  
  
1. <span data-ttu-id="c74a3-139">查找中的位置`Main`方法的项目的标记，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c74a3-139">Find the place in the `Main` method of the project that is marked as follows:</span></span>  
  
     [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]  
  
     <span data-ttu-id="c74a3-140">将以下代码复制并粘贴到此位置。</span><span class="sxs-lookup"><span data-stu-id="c74a3-140">Copy the following code and paste it in.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]  
  
2. <span data-ttu-id="c74a3-141">将鼠标指针停留在`studentQuery`若要验证编译器分配的类型是在代码中`IEnumerable(Of Student)`。</span><span class="sxs-lookup"><span data-stu-id="c74a3-141">Rest the mouse pointer over `studentQuery` in your code to verify that the compiler-assigned type is `IEnumerable(Of Student)`.</span></span>  
  
## <a name="run-the-query"></a><span data-ttu-id="c74a3-142">运行查询</span><span class="sxs-lookup"><span data-stu-id="c74a3-142">Run the Query</span></span>  
 <span data-ttu-id="c74a3-143">该变量`studentQuery`包含定义的查询，而不运行查询的结果。</span><span class="sxs-lookup"><span data-stu-id="c74a3-143">The variable `studentQuery` contains the definition of the query, not the results of running the query.</span></span> <span data-ttu-id="c74a3-144">用于运行查询的典型机制是`For Each`循环。</span><span class="sxs-lookup"><span data-stu-id="c74a3-144">A typical mechanism for running a query is a `For Each` loop.</span></span> <span data-ttu-id="c74a3-145">返回序列中的每个元素的循环迭代变量可通过访问。</span><span class="sxs-lookup"><span data-stu-id="c74a3-145">Each element in the returned sequence is accessed through the loop iteration variable.</span></span> <span data-ttu-id="c74a3-146">有关执行查询的详细信息，请参阅[编写你的第一个 LINQ 查询](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)。</span><span class="sxs-lookup"><span data-stu-id="c74a3-146">For more information about query execution, see [Writing Your First LINQ Query](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
#### <a name="to-run-the-query"></a><span data-ttu-id="c74a3-147">若要运行查询</span><span class="sxs-lookup"><span data-stu-id="c74a3-147">To run the query</span></span>  
  
1. <span data-ttu-id="c74a3-148">以下代码添加到`For Each`循环在项目中查询的下面。</span><span class="sxs-lookup"><span data-stu-id="c74a3-148">Add the following `For Each` loop below the query in your project.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]  
  
2. <span data-ttu-id="c74a3-149">将鼠标指针停留在循环控制变量`studentRecord`以查看其数据类型。</span><span class="sxs-lookup"><span data-stu-id="c74a3-149">Rest the mouse pointer over the loop control variable `studentRecord` to see its data type.</span></span> <span data-ttu-id="c74a3-150">类型`studentRecord`被推断为`Student`，因为`studentQuery`返回的集合`Student`实例。</span><span class="sxs-lookup"><span data-stu-id="c74a3-150">The type of `studentRecord` is inferred to be `Student`, because `studentQuery` returns a collection of `Student` instances.</span></span>  
  
3. <span data-ttu-id="c74a3-151">生成并通过按 CTRL + F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c74a3-151">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="c74a3-152">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="c74a3-152">Note the results in the console window.</span></span>  
  
## <a name="modify-the-query"></a><span data-ttu-id="c74a3-153">修改查询</span><span class="sxs-lookup"><span data-stu-id="c74a3-153">Modify the Query</span></span>  
 <span data-ttu-id="c74a3-154">它是更轻松地扫描查询结果，如果它们在指定的顺序。</span><span class="sxs-lookup"><span data-stu-id="c74a3-154">It is easier to scan query results if they are in a specified order.</span></span> <span data-ttu-id="c74a3-155">可以对基于任何可用字段返回的序列进行排序。</span><span class="sxs-lookup"><span data-stu-id="c74a3-155">You can sort the returned sequence based on any available field.</span></span>  
  
#### <a name="to-order-the-results"></a><span data-ttu-id="c74a3-156">对结果进行排序</span><span class="sxs-lookup"><span data-stu-id="c74a3-156">To order the results</span></span>  
  
1. <span data-ttu-id="c74a3-157">添加以下`Order By`子句之间`Where`语句和`Select`查询语句。</span><span class="sxs-lookup"><span data-stu-id="c74a3-157">Add the following `Order By` clause between the `Where` statement and the `Select` statement of the query.</span></span> <span data-ttu-id="c74a3-158">`Order By`子句将排序结果按字母顺序从 A 到 Z、 的最后一个根据每个学生的名字。</span><span class="sxs-lookup"><span data-stu-id="c74a3-158">The `Order By` clause will order the results alphabetically from A to Z, according to the last name of each student.</span></span>  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2. <span data-ttu-id="c74a3-159">若要按姓氏，然后按名字排序，请将这两个字段添加到查询：</span><span class="sxs-lookup"><span data-stu-id="c74a3-159">To order by last name and then first name, add both fields to the query:</span></span>  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     <span data-ttu-id="c74a3-160">此外可以指定`Descending`顺序从 Z 到 a。</span><span class="sxs-lookup"><span data-stu-id="c74a3-160">You can also specify `Descending` to order from Z to A.</span></span>  
  
3. <span data-ttu-id="c74a3-161">生成并通过按 CTRL + F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c74a3-161">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="c74a3-162">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="c74a3-162">Note the results in the console window.</span></span>  
  
#### <a name="to-introduce-a-local-identifier"></a><span data-ttu-id="c74a3-163">引入本地标识符</span><span class="sxs-lookup"><span data-stu-id="c74a3-163">To introduce a local identifier</span></span>  
  
1. <span data-ttu-id="c74a3-164">将代码添加在本部分介绍在查询表达式中的本地标识符。</span><span class="sxs-lookup"><span data-stu-id="c74a3-164">Add the code in this section to introduce a local identifier in the query expression.</span></span> <span data-ttu-id="c74a3-165">本地标识符将用于保存中间结果。</span><span class="sxs-lookup"><span data-stu-id="c74a3-165">The local identifier will hold an intermediate result.</span></span> <span data-ttu-id="c74a3-166">在以下示例中，`name`是包含学生的串联的标识符的名字和姓氏。</span><span class="sxs-lookup"><span data-stu-id="c74a3-166">In the following example, `name` is an identifier that holds a concatenation of the student's first and last names.</span></span> <span data-ttu-id="c74a3-167">为方便起见，可以使用的本地标识符或也可以通过将存储的一个表达式，否则将计算多次结果来提高性能。</span><span class="sxs-lookup"><span data-stu-id="c74a3-167">A local identifier can be used for convenience, or it can enhance performance by storing the results of an expression that would otherwise be calculated multiple times.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]  
  
2. <span data-ttu-id="c74a3-168">生成并通过按 CTRL + F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c74a3-168">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="c74a3-169">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="c74a3-169">Note the results in the console window.</span></span>  
  
#### <a name="to-project-one-field-in-the-select-clause"></a><span data-ttu-id="c74a3-170">投影在 Select 子句中的一个字段</span><span class="sxs-lookup"><span data-stu-id="c74a3-170">To project one field in the Select clause</span></span>  
  
1. <span data-ttu-id="c74a3-171">添加查询和`For Each`来创建查询，以生成一个序列，其元素与不同源中元素的此部分中的循环。</span><span class="sxs-lookup"><span data-stu-id="c74a3-171">Add the query and `For Each` loop from this section to create a query that produces a sequence whose elements differ from the elements in the source.</span></span> <span data-ttu-id="c74a3-172">在以下示例中，源是一系列`Student`返回对象，但只有一个成员的每个对象： 其姓氏为 Garcia 学生的名字。</span><span class="sxs-lookup"><span data-stu-id="c74a3-172">In the following example, the source is a collection of `Student` objects, but only one member of each object is returned: the first name of students whose last name is Garcia.</span></span> <span data-ttu-id="c74a3-173">因为`currentStudent.First`是一个字符串，返回的序列的数据类型`studentQuery3`是`IEnumerable(Of String)`，一个字符串序列。</span><span class="sxs-lookup"><span data-stu-id="c74a3-173">Because `currentStudent.First` is a string, the data type of the sequence returned by `studentQuery3` is `IEnumerable(Of String)`, a sequence of strings.</span></span> <span data-ttu-id="c74a3-174">如前面的示例中所示分配的数据类型为`studentQuery3`留给编译器通过使用局部类型推理来确定。</span><span class="sxs-lookup"><span data-stu-id="c74a3-174">As in earlier examples, the assignment of a data type for `studentQuery3` is left for the compiler to determine by using local type inference.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]  
  
2. <span data-ttu-id="c74a3-175">将鼠标指针停留在`studentQuery3`以验证是否已分配的类型在代码中`IEnumerable(Of String)`。</span><span class="sxs-lookup"><span data-stu-id="c74a3-175">Rest the mouse pointer over `studentQuery3` in your code to verify that the assigned type is `IEnumerable(Of String)`.</span></span>  
  
3. <span data-ttu-id="c74a3-176">生成并通过按 CTRL + F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c74a3-176">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="c74a3-177">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="c74a3-177">Note the results in the console window.</span></span>  
  
#### <a name="to-create-an-anonymous-type-in-the-select-clause"></a><span data-ttu-id="c74a3-178">若要在 Select 子句中创建一个匿名类型</span><span class="sxs-lookup"><span data-stu-id="c74a3-178">To create an anonymous type in the Select clause</span></span>  
  
1. <span data-ttu-id="c74a3-179">添加查询中使用此部分，以查看如何匿名类型中的代码。</span><span class="sxs-lookup"><span data-stu-id="c74a3-179">Add the code from this section to see how anonymous types are used in queries.</span></span> <span data-ttu-id="c74a3-180">如果您使用它们在查询中你想要从数据源而不是完整记录返回多个字段 (`currentStudent`前面的示例中的记录) 或单个字段 (`First`前面部分中)。</span><span class="sxs-lookup"><span data-stu-id="c74a3-180">You use them in queries when you want to return several fields from the data source rather than complete records (`currentStudent` records in previous examples) or single fields (`First` in the preceding section).</span></span> <span data-ttu-id="c74a3-181">而不是定义新的命名的类型包含你想要在结果中包含的字段，你可以指定在字段`Select`子句和编译器创建一个匿名类型与这些字段作为其属性。</span><span class="sxs-lookup"><span data-stu-id="c74a3-181">Instead of defining a new named type that contains the fields you want to include in the result, you specify the fields in the `Select` clause and the compiler creates an anonymous type with those fields as its properties.</span></span> <span data-ttu-id="c74a3-182">有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="c74a3-182">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="c74a3-183">以下示例创建的查询返回的名称和的高年级学生其学术排名是介于 1 和 10，学术排名的顺序。</span><span class="sxs-lookup"><span data-stu-id="c74a3-183">The following example creates a query that returns the name and rank of seniors whose academic rank is between 1 and 10, in order of academic rank.</span></span> <span data-ttu-id="c74a3-184">在此示例中，类型`studentQuery4`必须推断，因为`Select`子句将返回一个匿名类型的实例和匿名类型已没有可用的名称。</span><span class="sxs-lookup"><span data-stu-id="c74a3-184">In this example, the type of `studentQuery4` must be inferred because the `Select` clause returns an instance of an anonymous type, and an anonymous type has no usable name.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]  
  
2. <span data-ttu-id="c74a3-185">生成并通过按 CTRL + F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c74a3-185">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="c74a3-186">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="c74a3-186">Note the results in the console window.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="c74a3-187">其他示例</span><span class="sxs-lookup"><span data-stu-id="c74a3-187">Additional Examples</span></span>  
 <span data-ttu-id="c74a3-188">现在，你已了解基础知识，下面是其他示例来演示灵活的列表，以及利用[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询。</span><span class="sxs-lookup"><span data-stu-id="c74a3-188">Now that you understand the basics, the following is a list of additional examples to illustrate the flexibility and power of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="c74a3-189">每个示例被前面其用途的简短说明。</span><span class="sxs-lookup"><span data-stu-id="c74a3-189">Each example is preceded by a brief description of what it does.</span></span> <span data-ttu-id="c74a3-190">将鼠标指针停留在每个查询，以查看推断出的类型的查询结果变量。</span><span class="sxs-lookup"><span data-stu-id="c74a3-190">Rest the mouse pointer over the query result variable for each query to see the inferred type.</span></span> <span data-ttu-id="c74a3-191">使用`For Each`循环生成的结果。</span><span class="sxs-lookup"><span data-stu-id="c74a3-191">Use a `For Each` loop to produce the results.</span></span>  
  
 [!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]  
  
## <a name="additional-information"></a><span data-ttu-id="c74a3-192">其他信息</span><span class="sxs-lookup"><span data-stu-id="c74a3-192">Additional Information</span></span>  
 <span data-ttu-id="c74a3-193">了解如何使用查询的基本概念后，已准备好读取的特定类型的文档和示例[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]感兴趣的提供程序：</span><span class="sxs-lookup"><span data-stu-id="c74a3-193">After you are familiar with the basic concepts of working with queries, you are ready to read the documentation and samples for the specific type of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider that you are interested in:</span></span>  
  
 [<span data-ttu-id="c74a3-194">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="c74a3-194">LINQ to Objects</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
 [<span data-ttu-id="c74a3-195">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c74a3-195">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [<span data-ttu-id="c74a3-196">LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="c74a3-196">LINQ to XML</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [<span data-ttu-id="c74a3-197">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="c74a3-197">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)  
  
## <a name="see-also"></a><span data-ttu-id="c74a3-198">请参阅</span><span class="sxs-lookup"><span data-stu-id="c74a3-198">See also</span></span>

- [<span data-ttu-id="c74a3-199">语言集成查询 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c74a3-199">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="c74a3-200">Visual Basic 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="c74a3-200">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="c74a3-201">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="c74a3-201">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="c74a3-202">对象初始值设定项：命名和匿名类型</span><span class="sxs-lookup"><span data-stu-id="c74a3-202">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="c74a3-203">匿名类型</span><span class="sxs-lookup"><span data-stu-id="c74a3-203">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="c74a3-204">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="c74a3-204">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="c74a3-205">LINQ</span><span class="sxs-lookup"><span data-stu-id="c74a3-205">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="c74a3-206">查询</span><span class="sxs-lookup"><span data-stu-id="c74a3-206">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
