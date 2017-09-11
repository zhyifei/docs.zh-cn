---
title: "在 Visual Basic 中编写查询 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- VB
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
caps.latest.revision: 70
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3e946ad09c36e94758ce13b4a37a6bf6ae54f947
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-writing-queries-in-visual-basic"></a><span data-ttu-id="97ebc-102">演练：用 Visual Basic 编写查询</span><span class="sxs-lookup"><span data-stu-id="97ebc-102">Walkthrough: Writing Queries in Visual Basic</span></span>
<span data-ttu-id="97ebc-103">本演练演示如何使用 Visual Basic 语言功能来编写[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]查询表达式。</span><span class="sxs-lookup"><span data-stu-id="97ebc-103">This walkthrough demonstrates how you can use Visual Basic language features to write [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] query expressions.</span></span> <span data-ttu-id="97ebc-104">本演练演示如何在列表中的学生对象创建查询、 如何运行查询，以及如何对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="97ebc-104">The walkthrough demonstrates how to create queries on a list of Student objects, how to run the queries, and how to modify them.</span></span> <span data-ttu-id="97ebc-105">这些查询加入了多种功能，包括对象初始值设定项、 局部类型推理和匿名类型。</span><span class="sxs-lookup"><span data-stu-id="97ebc-105">The queries incorporate several features including object initializers, local type inference, and anonymous types.</span></span>  
  
 <span data-ttu-id="97ebc-106">完成此演练后，您将准备好迎接的示例和文档的特定[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]您感兴趣的提供程序。</span><span class="sxs-lookup"><span data-stu-id="97ebc-106">After completing this walkthrough, you will be ready to move on to the samples and documentation for the specific [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] provider you are interested in.</span></span> [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]<span data-ttu-id="97ebc-107">提供程序包括[!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]， [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)]，和[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="97ebc-107"> providers include [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)], and [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>  
  
## <a name="create-a-project"></a><span data-ttu-id="97ebc-108">创建项目</span><span class="sxs-lookup"><span data-stu-id="97ebc-108">Create a Project</span></span>  
  
#### <a name="to-create-a-console-application-project"></a><span data-ttu-id="97ebc-109">若要创建控制台应用程序项目</span><span class="sxs-lookup"><span data-stu-id="97ebc-109">To create a console application project</span></span>  
  
1.  <span data-ttu-id="97ebc-110">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="97ebc-110">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="97ebc-111">在 **“文件”** 菜单上，指向 **“新建”**，然后单击 **“项目”**。</span><span class="sxs-lookup"><span data-stu-id="97ebc-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="97ebc-112">在**已安装的模板**列表中，单击**Visual Basic**。</span><span class="sxs-lookup"><span data-stu-id="97ebc-112">In the **Installed Templates** list, click **Visual Basic**.</span></span>  
  
4.  <span data-ttu-id="97ebc-113">在项目类型列表中，单击**控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="97ebc-113">In the list of project types, click **Console Application**.</span></span> <span data-ttu-id="97ebc-114">在**名称**框中，为项目中，键入一个名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="97ebc-114">In the **Name** box, type a name for the project, and then click **OK**.</span></span>  
  
     <span data-ttu-id="97ebc-115">创建一个项目。</span><span class="sxs-lookup"><span data-stu-id="97ebc-115">A project is created.</span></span> <span data-ttu-id="97ebc-116">默认情况下，它包含对 System.Core.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="97ebc-116">By default, it contains a reference to System.Core.dll.</span></span> <span data-ttu-id="97ebc-117">此外，**导入的命名空间**列表[，项目设计器 (Visual Basic 中) 引用页](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)包括<xref:System.Linq?displayProperty=fullName>命名空间。</xref:System.Linq?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="97ebc-117">Also, the **Imported namespaces** list on the [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) includes the <xref:System.Linq?displayProperty=fullName> namespace.</span></span>  
  
5.  <span data-ttu-id="97ebc-118">在[编译页，项目设计器 (Visual Basic 中)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)，确保**Option infer**设置为**上**。</span><span class="sxs-lookup"><span data-stu-id="97ebc-118">On the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic), ensure that **Option infer** is set to **On**.</span></span>  
  
## <a name="add-an-in-memory-data-source"></a><span data-ttu-id="97ebc-119">添加一个内存中数据源</span><span class="sxs-lookup"><span data-stu-id="97ebc-119">Add an In-Memory Data Source</span></span>  
 <span data-ttu-id="97ebc-120">在本演练中的查询的数据源是一份`Student`对象。</span><span class="sxs-lookup"><span data-stu-id="97ebc-120">The data source for the queries in this walkthrough is a list of `Student` objects.</span></span> <span data-ttu-id="97ebc-121">每个`Student`对象包含名字、 姓氏、 一类和学术排名学生正文内的。</span><span class="sxs-lookup"><span data-stu-id="97ebc-121">Each `Student` object contains a first name, a last name, a class year, and an academic rank in the student body.</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="97ebc-122">若要添加数据源</span><span class="sxs-lookup"><span data-stu-id="97ebc-122">To add the data source</span></span>  
  
-   <span data-ttu-id="97ebc-123">定义`Student`类，并创建一个类的实例的列表。</span><span class="sxs-lookup"><span data-stu-id="97ebc-123">Define a `Student` class, and create a list of instances of the class.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="97ebc-124">定义所需的代码`Student`类，并创建使用的列表在本演练中提供示例[如何︰ 创建列表项](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)。</span><span class="sxs-lookup"><span data-stu-id="97ebc-124">The code needed to define the `Student` class and create the list used in the walkthrough examples is provided in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="97ebc-125">可以将其复制并将其粘贴到您的项目。</span><span class="sxs-lookup"><span data-stu-id="97ebc-125">You can copy it from there and paste it into your project.</span></span> <span data-ttu-id="97ebc-126">新的代码替换在创建项目时显示的代码。</span><span class="sxs-lookup"><span data-stu-id="97ebc-126">The new code replaces the code that appeared when you created the project.</span></span>  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="97ebc-127">若要向学生列表中添加新的学生</span><span class="sxs-lookup"><span data-stu-id="97ebc-127">To add a new student to the students list</span></span>  
  
-   <span data-ttu-id="97ebc-128">请按照中的模式`getStudents`方法添加的另一个实例`Student`到列表的类。</span><span class="sxs-lookup"><span data-stu-id="97ebc-128">Follow the pattern in the `getStudents` method to add another instance of the `Student` class to the list.</span></span> <span data-ttu-id="97ebc-129">添加学生将向您介绍对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="97ebc-129">Adding the student will introduce you to object initializers.</span></span> <span data-ttu-id="97ebc-130">有关详细信息，请参阅[对象初始值设定项︰ 命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="97ebc-130">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>  
  
## <a name="create-a-query"></a><span data-ttu-id="97ebc-131">创建查询</span><span class="sxs-lookup"><span data-stu-id="97ebc-131">Create a Query</span></span>  
 <span data-ttu-id="97ebc-132">在执行时，此部分中添加此查询将生成其学术排名将其放入前&10; 个学生列表。</span><span class="sxs-lookup"><span data-stu-id="97ebc-132">When executed, the query added in this section produces a list of the students whose academic rank puts them in the top ten.</span></span> <span data-ttu-id="97ebc-133">因为该查询用于选择完整`Student`对象在每次，查询结果的类型是`IEnumerable(Of Student)`。</span><span class="sxs-lookup"><span data-stu-id="97ebc-133">Because the query selects the complete `Student` object each time, the type of the query result is `IEnumerable(Of Student)`.</span></span> <span data-ttu-id="97ebc-134">但是，查询的类型通常是未指定在查询定义中。</span><span class="sxs-lookup"><span data-stu-id="97ebc-134">However, the type of the query typically is not specified in query definitions.</span></span> <span data-ttu-id="97ebc-135">相反，编译器使用局部类型推理来确定的类型。</span><span class="sxs-lookup"><span data-stu-id="97ebc-135">Instead, the compiler uses local type inference to determine the type.</span></span> <span data-ttu-id="97ebc-136">有关详细信息，请参阅[本地类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="97ebc-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span> <span data-ttu-id="97ebc-137">查询的范围变量`currentStudent`，用作一个对所有引用`Student`源中的实例`students`，提供对中的每个对象的属性访问`students`。</span><span class="sxs-lookup"><span data-stu-id="97ebc-137">The query's range variable, `currentStudent`, serves as a reference to each `Student` instance in the source, `students`, providing access to the properties of each object in `students`.</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="97ebc-138">创建简单查询</span><span class="sxs-lookup"><span data-stu-id="97ebc-138">To create a simple query</span></span>  
  
1.  <span data-ttu-id="97ebc-139">查找中的位置`Main`标记，如下所示的项目的方法︰</span><span class="sxs-lookup"><span data-stu-id="97ebc-139">Find the place in the `Main` method of the project that is marked as follows:</span></span>  
  
     <span data-ttu-id="97ebc-140">[!code-vb[VbLINQWalkthrough #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="97ebc-140">[!code-vb[VbLINQWalkthrough#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]</span></span>  
  
     <span data-ttu-id="97ebc-141">将以下代码复制并粘贴到此位置。</span><span class="sxs-lookup"><span data-stu-id="97ebc-141">Copy the following code and paste it in.</span></span>  
  
     <span data-ttu-id="97ebc-142">[!code-vb[VbLINQWalkthrough #&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="97ebc-142">[!code-vb[VbLINQWalkthrough#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]</span></span>  
  
2.  <span data-ttu-id="97ebc-143">将鼠标指针停留在`studentQuery`代码来验证编译器指定类型是否为`IEnumerable(Of Student)`。</span><span class="sxs-lookup"><span data-stu-id="97ebc-143">Rest the mouse pointer over `studentQuery` in your code to verify that the compiler-assigned type is `IEnumerable(Of Student)`.</span></span>  
  
## <a name="run-the-query"></a><span data-ttu-id="97ebc-144">运行查询</span><span class="sxs-lookup"><span data-stu-id="97ebc-144">Run the Query</span></span>  
 <span data-ttu-id="97ebc-145">该变量`studentQuery`包含定义的查询，而不是运行查询的结果。</span><span class="sxs-lookup"><span data-stu-id="97ebc-145">The variable `studentQuery` contains the definition of the query, not the results of running the query.</span></span> <span data-ttu-id="97ebc-146">运行查询的典型机制是`For Each`循环。</span><span class="sxs-lookup"><span data-stu-id="97ebc-146">A typical mechanism for running a query is a `For Each` loop.</span></span> <span data-ttu-id="97ebc-147">返回序列中的每个元素的访问的循环迭代变量。</span><span class="sxs-lookup"><span data-stu-id="97ebc-147">Each element in the returned sequence is accessed through the loop iteration variable.</span></span> <span data-ttu-id="97ebc-148">查询执行有关的详细信息，请参阅[编写您的第一个 LINQ 查询](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)。</span><span class="sxs-lookup"><span data-stu-id="97ebc-148">For more information about query execution, see [Writing Your First LINQ Query](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
#### <a name="to-run-the-query"></a><span data-ttu-id="97ebc-149">若要运行查询</span><span class="sxs-lookup"><span data-stu-id="97ebc-149">To run the query</span></span>  
  
1.  <span data-ttu-id="97ebc-150">将以下代码添加`For Each`循环在项目中查询的下面。</span><span class="sxs-lookup"><span data-stu-id="97ebc-150">Add the following `For Each` loop below the query in your project.</span></span>  
  
     <span data-ttu-id="97ebc-151">[!code-vb[VbLINQWalkthrough #&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="97ebc-151">[!code-vb[VbLINQWalkthrough#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]</span></span>  
  
2.  <span data-ttu-id="97ebc-152">将鼠标指针停留在循环控制变量`studentRecord`以查看其数据类型。</span><span class="sxs-lookup"><span data-stu-id="97ebc-152">Rest the mouse pointer over the loop control variable `studentRecord` to see its data type.</span></span> <span data-ttu-id="97ebc-153">一种`studentRecord`被推断为`Student`，这是因为`studentQuery`返回的集合`Student`实例。</span><span class="sxs-lookup"><span data-stu-id="97ebc-153">The type of `studentRecord` is inferred to be `Student`, because `studentQuery` returns a collection of `Student` instances.</span></span>  
  
3.  <span data-ttu-id="97ebc-154">生成并按 CTRL + F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="97ebc-154">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="97ebc-155">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="97ebc-155">Note the results in the console window.</span></span>  
  
## <a name="modify-the-query"></a><span data-ttu-id="97ebc-156">修改查询</span><span class="sxs-lookup"><span data-stu-id="97ebc-156">Modify the Query</span></span>  
 <span data-ttu-id="97ebc-157">很方便地扫描查询结果，它们是否按指定顺序。</span><span class="sxs-lookup"><span data-stu-id="97ebc-157">It is easier to scan query results if they are in a specified order.</span></span> <span data-ttu-id="97ebc-158">可以对基于任何可用字段返回的序列进行排序。</span><span class="sxs-lookup"><span data-stu-id="97ebc-158">You can sort the returned sequence based on any available field.</span></span>  
  
#### <a name="to-order-the-results"></a><span data-ttu-id="97ebc-159">对结果进行排序</span><span class="sxs-lookup"><span data-stu-id="97ebc-159">To order the results</span></span>  
  
1.  <span data-ttu-id="97ebc-160">将以下代码添加`Order By`之间子句`Where`语句和`Select`查询语句。</span><span class="sxs-lookup"><span data-stu-id="97ebc-160">Add the following `Order By` clause between the `Where` statement and the `Select` statement of the query.</span></span> <span data-ttu-id="97ebc-161">`Order By`子句将字母顺序对结果从 A 到 Z，到最后一个根据每个学生的名字。</span><span class="sxs-lookup"><span data-stu-id="97ebc-161">The `Order By` clause will order the results alphabetically from A to Z, according to the last name of each student.</span></span>  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  <span data-ttu-id="97ebc-162">若要按姓氏，然后按名字排序，请向查询添加这两个字段︰</span><span class="sxs-lookup"><span data-stu-id="97ebc-162">To order by last name and then first name, add both fields to the query:</span></span>  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     <span data-ttu-id="97ebc-163">您还可以指定`Descending`到订单从 Z 到 a。</span><span class="sxs-lookup"><span data-stu-id="97ebc-163">You can also specify `Descending` to order from Z to A.</span></span>  
  
3.  <span data-ttu-id="97ebc-164">生成并按 CTRL + F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="97ebc-164">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="97ebc-165">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="97ebc-165">Note the results in the console window.</span></span>  
  
#### <a name="to-introduce-a-local-identifier"></a><span data-ttu-id="97ebc-166">若要将本地标识符引入</span><span class="sxs-lookup"><span data-stu-id="97ebc-166">To introduce a local identifier</span></span>  
  
1.  <span data-ttu-id="97ebc-167">在查询表达式将本地标识符引入此部分中添加代码。</span><span class="sxs-lookup"><span data-stu-id="97ebc-167">Add the code in this section to introduce a local identifier in the query expression.</span></span> <span data-ttu-id="97ebc-168">本地标识符将用于保存中间结果。</span><span class="sxs-lookup"><span data-stu-id="97ebc-168">The local identifier will hold an intermediate result.</span></span> <span data-ttu-id="97ebc-169">在下面的示例中，`name`是保留的学生串联的标识符的姓和名。</span><span class="sxs-lookup"><span data-stu-id="97ebc-169">In the following example, `name` is an identifier that holds a concatenation of the student's first and last names.</span></span> <span data-ttu-id="97ebc-170">可以为方便起见，使用的本地标识符，或者也可以通过将存储结果的表达式，否则将计算多次用于提高性能。</span><span class="sxs-lookup"><span data-stu-id="97ebc-170">A local identifier can be used for convenience, or it can enhance performance by storing the results of an expression that would otherwise be calculated multiple times.</span></span>  
  
     <span data-ttu-id="97ebc-171">[!code-vb[VbLINQWalkthrough #&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="97ebc-171">[!code-vb[VbLINQWalkthrough#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]</span></span>  
  
2.  <span data-ttu-id="97ebc-172">生成并按 CTRL + F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="97ebc-172">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="97ebc-173">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="97ebc-173">Note the results in the console window.</span></span>  
  
#### <a name="to-project-one-field-in-the-select-clause"></a><span data-ttu-id="97ebc-174">投影在 Select 子句中的一个字段</span><span class="sxs-lookup"><span data-stu-id="97ebc-174">To project one field in the Select clause</span></span>  
  
1.  <span data-ttu-id="97ebc-175">将查询添加和`For Each`从该部分以创建一个查询，生成一个序列，其元素与不同的源中元素的循环。</span><span class="sxs-lookup"><span data-stu-id="97ebc-175">Add the query and `For Each` loop from this section to create a query that produces a sequence whose elements differ from the elements in the source.</span></span> <span data-ttu-id="97ebc-176">在以下示例中，源是一套`Student`返回对象，但每个对象只有一个成员︰ 其姓氏为 Garcia 的学生的名字。</span><span class="sxs-lookup"><span data-stu-id="97ebc-176">In the following example, the source is a collection of `Student` objects, but only one member of each object is returned: the first name of students whose last name is Garcia.</span></span> <span data-ttu-id="97ebc-177">因为`currentStudent.First`是一个字符串，返回的序列的数据类型`studentQuery3`是`IEnumerable(Of String)`，一个字符串序列。</span><span class="sxs-lookup"><span data-stu-id="97ebc-177">Because `currentStudent.First` is a string, the data type of the sequence returned by `studentQuery3` is `IEnumerable(Of String)`, a sequence of strings.</span></span> <span data-ttu-id="97ebc-178">如前面的示例中所示分配数据类型为`studentQuery3`保留以供编译器使用局部类型推理来确定的。</span><span class="sxs-lookup"><span data-stu-id="97ebc-178">As in earlier examples, the assignment of a data type for `studentQuery3` is left for the compiler to determine by using local type inference.</span></span>  
  
     <span data-ttu-id="97ebc-179">[!code-vb[VbLINQWalkthrough #&5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="97ebc-179">[!code-vb[VbLINQWalkthrough#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]</span></span>  
  
2.  <span data-ttu-id="97ebc-180">将鼠标指针停留在`studentQuery3`在您的代码以验证分配的类型是否为`IEnumerable(Of String)`。</span><span class="sxs-lookup"><span data-stu-id="97ebc-180">Rest the mouse pointer over `studentQuery3` in your code to verify that the assigned type is `IEnumerable(Of String)`.</span></span>  
  
3.  <span data-ttu-id="97ebc-181">生成并按 CTRL + F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="97ebc-181">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="97ebc-182">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="97ebc-182">Note the results in the console window.</span></span>  
  
#### <a name="to-create-an-anonymous-type-in-the-select-clause"></a><span data-ttu-id="97ebc-183">若要在 Select 子句中创建一个匿名类型</span><span class="sxs-lookup"><span data-stu-id="97ebc-183">To create an anonymous type in the Select clause</span></span>  
  
1.  <span data-ttu-id="97ebc-184">添加查询中使用的该部分以查看如何匿名类型中的代码。</span><span class="sxs-lookup"><span data-stu-id="97ebc-184">Add the code from this section to see how anonymous types are used in queries.</span></span> <span data-ttu-id="97ebc-185">如果您使用它们在查询中你想要从数据源而不是完整的记录返回多个字段 (`currentStudent`前面的示例中的记录) 或单个字段 (`First`前一节中)。</span><span class="sxs-lookup"><span data-stu-id="97ebc-185">You use them in queries when you want to return several fields from the data source rather than complete records (`currentStudent` records in previous examples) or single fields (`First` in the preceding section).</span></span> <span data-ttu-id="97ebc-186">而不是定义新的命名的类型，其中包含你想要在结果中包括的字段，指定在字段`Select`子句和编译器创建一个匿名类型与这些字段作为其属性。</span><span class="sxs-lookup"><span data-stu-id="97ebc-186">Instead of defining a new named type that contains the fields you want to include in the result, you specify the fields in the `Select` clause and the compiler creates an anonymous type with those fields as its properties.</span></span> <span data-ttu-id="97ebc-187">有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="97ebc-187">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="97ebc-188">下面的示例创建一个查询，返回的名称和其学术排名是介于 1 和 10，学术并按排列的上级的秩。</span><span class="sxs-lookup"><span data-stu-id="97ebc-188">The following example creates a query that returns the name and rank of seniors whose academic rank is between 1 and 10, in order of academic rank.</span></span> <span data-ttu-id="97ebc-189">在此示例中的一种`studentQuery4`必须推断，因为`Select`子句将返回一个匿名类型的实例和一个匿名类型已没有可用的名称。</span><span class="sxs-lookup"><span data-stu-id="97ebc-189">In this example, the type of `studentQuery4` must be inferred because the `Select` clause returns an instance of an anonymous type, and an anonymous type has no usable name.</span></span>  
  
     <span data-ttu-id="97ebc-190">[!code-vb[VbLINQWalkthrough #&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="97ebc-190">[!code-vb[VbLINQWalkthrough#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]</span></span>  
  
2.  <span data-ttu-id="97ebc-191">生成并按 CTRL + F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="97ebc-191">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="97ebc-192">请注意控制台窗口中的结果。</span><span class="sxs-lookup"><span data-stu-id="97ebc-192">Note the results in the console window.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="97ebc-193">其他示例</span><span class="sxs-lookup"><span data-stu-id="97ebc-193">Additional Examples</span></span>  
 <span data-ttu-id="97ebc-194">现在，您已了解基础知识，下面是其他示例来说明灵活的列表以及利用[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]查询。</span><span class="sxs-lookup"><span data-stu-id="97ebc-194">Now that you understand the basics, the following is a list of additional examples to illustrate the flexibility and power of [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries.</span></span> <span data-ttu-id="97ebc-195">每个示例的前面有其用途的简短说明。</span><span class="sxs-lookup"><span data-stu-id="97ebc-195">Each example is preceded by a brief description of what it does.</span></span> <span data-ttu-id="97ebc-196">将鼠标指针停留在每个查询，以查看推断出的类型的查询结果变量。</span><span class="sxs-lookup"><span data-stu-id="97ebc-196">Rest the mouse pointer over the query result variable for each query to see the inferred type.</span></span> <span data-ttu-id="97ebc-197">使用`For Each`循环，以产生的结果。</span><span class="sxs-lookup"><span data-stu-id="97ebc-197">Use a `For Each` loop to produce the results.</span></span>  
  
 <span data-ttu-id="97ebc-198">[!code-vb[VbLINQWalkthrough #&7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="97ebc-198">[!code-vb[VbLINQWalkthrough#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]</span></span>  
  
## <a name="additional-information"></a><span data-ttu-id="97ebc-199">其他信息</span><span class="sxs-lookup"><span data-stu-id="97ebc-199">Additional Information</span></span>  
 <span data-ttu-id="97ebc-200">您熟悉使用查询的基本概念后，你就可以读取的特定类型的文档和示例[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]您感兴趣的提供程序︰</span><span class="sxs-lookup"><span data-stu-id="97ebc-200">After you are familiar with the basic concepts of working with queries, you are ready to read the documentation and samples for the specific type of [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] provider that you are interested in:</span></span>  
  
 [<span data-ttu-id="97ebc-201">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="97ebc-201">LINQ to Objects</span></span>](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)  
  
 [<span data-ttu-id="97ebc-202">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="97ebc-202">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)  
  
 [<span data-ttu-id="97ebc-203">LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="97ebc-203">LINQ to XML</span></span>](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)  
  
 [<span data-ttu-id="97ebc-204">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="97ebc-204">LINQ to DataSet</span></span>](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)  
  
## <a name="see-also"></a><span data-ttu-id="97ebc-205">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97ebc-205">See Also</span></span>  
 <span data-ttu-id="97ebc-206">[语言集成查询 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="97ebc-206">[Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md) </span></span>  
<span data-ttu-id="97ebc-207"> [在 Visual Basic 中的 LINQ 入门](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="97ebc-207"> [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
<span data-ttu-id="97ebc-208"> [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="97ebc-208"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="97ebc-209"> [对象初始值设定项︰ 命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="97ebc-209"> [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span></span>  
<span data-ttu-id="97ebc-210"> [匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="97ebc-210"> [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span></span>  
<span data-ttu-id="97ebc-211"> [在 Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="97ebc-211"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="97ebc-212"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="97ebc-212"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="97ebc-213"> [查询](../../../../visual-basic/language-reference/queries/queries.md)</span><span class="sxs-lookup"><span data-stu-id="97ebc-213"> [Queries](../../../../visual-basic/language-reference/queries/queries.md)</span></span>
