---
title: 演练：简单对象模型和查询 (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: c878e457-f715-46e4-a136-ff14d6c86018
ms.openlocfilehash: c6d00271f412829cb8e030c2b9a338f73327977b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724169"
---
# <a name="walkthrough-simple-object-model-and-query-visual-basic"></a><span data-ttu-id="12216-102">演练：简单对象模型和查询 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12216-102">Walkthrough: Simple Object Model and Query (Visual Basic)</span></span>
<span data-ttu-id="12216-103">本演练提供了复杂性最小的基本端对端 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 方案。</span><span class="sxs-lookup"><span data-stu-id="12216-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario with minimal complexities.</span></span> <span data-ttu-id="12216-104">您将创建一个可为示例 Northwind 数据库中的 Customers 表建模的实体类。</span><span class="sxs-lookup"><span data-stu-id="12216-104">You will create an entity class that models the Customers table in the sample Northwind database.</span></span> <span data-ttu-id="12216-105">然后您将创建一个简单查询，用于列出位于伦敦的客户。</span><span class="sxs-lookup"><span data-stu-id="12216-105">You will then create a simple query to list customers who are located in London.</span></span>  
  
 <span data-ttu-id="12216-106">本演练在设计上是面向代码的，以帮助说明 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 概念。</span><span class="sxs-lookup"><span data-stu-id="12216-106">This walkthrough is code-oriented by design to help show [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] concepts.</span></span> <span data-ttu-id="12216-107">一般来说，您会使用 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 来创建对象模型。</span><span class="sxs-lookup"><span data-stu-id="12216-107">Normally speaking, you would use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="12216-108">本演练是使用 Visual Basic 开发设置编写的。</span><span class="sxs-lookup"><span data-stu-id="12216-108">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="12216-109">系统必备</span><span class="sxs-lookup"><span data-stu-id="12216-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="12216-110">本演练使用专用文件夹（“c:\linqtest”）来保存文件。</span><span class="sxs-lookup"><span data-stu-id="12216-110">This walkthrough uses a dedicated folder ("c:\linqtest") to hold files.</span></span> <span data-ttu-id="12216-111">请在开始本演练前创建此文件夹。</span><span class="sxs-lookup"><span data-stu-id="12216-111">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="12216-112">本演练需要 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="12216-112">This walkthrough requires the Northwind sample database.</span></span> <span data-ttu-id="12216-113">如果您的开发计算机上没有此数据库，您可以从 Microsoft 下载网站下载它。</span><span class="sxs-lookup"><span data-stu-id="12216-113">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="12216-114">有关说明，请参阅[下载示例数据库](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="12216-114">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="12216-115">下载此数据库后，请将文件复制到 c:\linqtest 文件夹。</span><span class="sxs-lookup"><span data-stu-id="12216-115">After you have downloaded the database, copy the file to the c:\linqtest folder.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="12216-116">概述</span><span class="sxs-lookup"><span data-stu-id="12216-116">Overview</span></span>  
 <span data-ttu-id="12216-117">本演练由六项主要任务组成：</span><span class="sxs-lookup"><span data-stu-id="12216-117">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="12216-118">创建[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Visual Studio 中的解决方案。</span><span class="sxs-lookup"><span data-stu-id="12216-118">Creating a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
-   <span data-ttu-id="12216-119">将类映射到数据库表。</span><span class="sxs-lookup"><span data-stu-id="12216-119">Mapping a class to a database table.</span></span>  
  
-   <span data-ttu-id="12216-120">指定类中的属性表示数据库列。</span><span class="sxs-lookup"><span data-stu-id="12216-120">Designating properties on the class to represent database columns.</span></span>  
  
-   <span data-ttu-id="12216-121">指定到 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="12216-121">Specifying the connection to the Northwind database.</span></span>  
  
-   <span data-ttu-id="12216-122">创建针对该数据库运行的简单查询。</span><span class="sxs-lookup"><span data-stu-id="12216-122">Creating a simple query to run against the database.</span></span>  
  
-   <span data-ttu-id="12216-123">执行查询并观察结果。</span><span class="sxs-lookup"><span data-stu-id="12216-123">Executing the query and observing the results.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="12216-124">创建 LINQ to SQL 解决方案</span><span class="sxs-lookup"><span data-stu-id="12216-124">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="12216-125">在此第一个任务中，创建一个包含必要的引用，生成并运行的 Visual Studio 解决方案[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="12216-125">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="12216-126">创建 LINQ to SQL 解决方案</span><span class="sxs-lookup"><span data-stu-id="12216-126">To create a LINQ to SQL solution</span></span>  
  
1.  <span data-ttu-id="12216-127">在“文件”菜单上，单击“新建项目”。</span><span class="sxs-lookup"><span data-stu-id="12216-127">On the **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="12216-128">在中**项目类型**窗格**新项目**对话框中，单击**Visual Basic**。</span><span class="sxs-lookup"><span data-stu-id="12216-128">In the **Project types** pane of the **New Project** dialog box, click **Visual Basic**.</span></span>  
  
3.  <span data-ttu-id="12216-129">在“模板”窗格中，单击“控制台应用程序”。</span><span class="sxs-lookup"><span data-stu-id="12216-129">In the **Templates** pane, click **Console Application**.</span></span>  
  
4.  <span data-ttu-id="12216-130">在中**名称**框中，键入**LinqConsoleApp**。</span><span class="sxs-lookup"><span data-stu-id="12216-130">In the **Name** box, type **LinqConsoleApp**.</span></span>  
  
5.  <span data-ttu-id="12216-131">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="12216-131">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="12216-132">添加 LINQ 引用和指令</span><span class="sxs-lookup"><span data-stu-id="12216-132">Adding LINQ References and Directives</span></span>  
 <span data-ttu-id="12216-133">本演练用到默认情况下您的项目中可能未安装的程序集。</span><span class="sxs-lookup"><span data-stu-id="12216-133">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="12216-134">如果`System.Data.Linq`不作为项目中引用列出 (单击**显示所有文件**中**解决方案资源管理器**展开**引用**节点)，请按照中所述添加它以下步骤。</span><span class="sxs-lookup"><span data-stu-id="12216-134">If `System.Data.Linq` is not listed as a reference in your project (click **Show All Files** in **Solution Explorer** and expand the **References** node), add it, as explained in the following steps.</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="12216-135">添加 System.Data.Linq</span><span class="sxs-lookup"><span data-stu-id="12216-135">To add System.Data.Linq</span></span>  
  
1.  <span data-ttu-id="12216-136">在中**解决方案资源管理器**，右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="12216-136">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="12216-137">在中**添加引用**对话框中，单击 **.NET**，单击 System.Data.Linq 程序集，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="12216-137">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="12216-138">此程序集即被添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="12216-138">The assembly is added to the project.</span></span>  
  
3.  <span data-ttu-id="12216-139">另外，请在**添加引用**对话框中，单击 **.NET**中，滚动到并单击 System.Windows.Forms，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="12216-139">Also in the **Add Reference** dialog box, click **.NET**, scroll to and click System.Windows.Forms, and then click **OK**.</span></span>  
  
     <span data-ttu-id="12216-140">此程序集（支持本演练中的消息框）即被添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="12216-140">This assembly, which supports the message box in the walkthrough, is added to the project.</span></span>  
  
4.  <span data-ttu-id="12216-141">在 `Module1` 上方添加以下指令：</span><span class="sxs-lookup"><span data-stu-id="12216-141">Add the following directives above `Module1`:</span></span>  
  
     [!code-vb[DLinqWalk1VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#1)]  
  
## <a name="mapping-a-class-to-a-database-table"></a><span data-ttu-id="12216-142">将类映射到数据库表</span><span class="sxs-lookup"><span data-stu-id="12216-142">Mapping a Class to a Database Table</span></span>  
 <span data-ttu-id="12216-143">在此步骤中，您将创建一个类，并将其映射到数据库表。</span><span class="sxs-lookup"><span data-stu-id="12216-143">In this step, you create a class and map it to a database table.</span></span> <span data-ttu-id="12216-144">此类的类称为*实体类*。</span><span class="sxs-lookup"><span data-stu-id="12216-144">Such a class is termed an *entity class*.</span></span> <span data-ttu-id="12216-145">请注意，只需添加 <xref:System.Data.Linq.Mapping.TableAttribute> 属性即可完成映射。</span><span class="sxs-lookup"><span data-stu-id="12216-145">Note that the mapping is accomplished by just adding the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span> <span data-ttu-id="12216-146"><xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> 属性指定数据库中的表的名称。</span><span class="sxs-lookup"><span data-stu-id="12216-146">The <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property specifies the name of the table in the database.</span></span>  
  
#### <a name="to-create-an-entity-class-and-map-it-to-a-database-table"></a><span data-ttu-id="12216-147">创建一个实体类并将其映射到数据库表</span><span class="sxs-lookup"><span data-stu-id="12216-147">To create an entity class and map it to a database table</span></span>  
  
-   <span data-ttu-id="12216-148">将下面的代码键入或粘贴到 `Sub Main` 上方紧靠它的 Module1.vb 中。</span><span class="sxs-lookup"><span data-stu-id="12216-148">Type or paste the following code into Module1.vb immediately above `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk1VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#2)]  
  
## <a name="designating-properties-on-the-class-to-represent-database-columns"></a><span data-ttu-id="12216-149">指定类中的属性表示数据库列</span><span class="sxs-lookup"><span data-stu-id="12216-149">Designating Properties on the Class to Represent Database Columns</span></span>  
 <span data-ttu-id="12216-150">在此步骤中，您要完成几项任务。</span><span class="sxs-lookup"><span data-stu-id="12216-150">In this step, you accomplish several tasks.</span></span>  
  
-   <span data-ttu-id="12216-151">您要使用 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute) 指定实体类中的 `CustomerID` 和 `City` 属性 (Property) 表示数据库表中的列。</span><span class="sxs-lookup"><span data-stu-id="12216-151">You use the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate `CustomerID` and `City` properties on the entity class as representing columns in the database table.</span></span>  
  
-   <span data-ttu-id="12216-152">您要指定 `CustomerID` 属性表示数据库中的主键列。</span><span class="sxs-lookup"><span data-stu-id="12216-152">You designate the `CustomerID` property as representing a primary key column in the database.</span></span>  
  
-   <span data-ttu-id="12216-153">您要指定 `_CustomerID` 和 `_City` 字段用作私有存储字段。</span><span class="sxs-lookup"><span data-stu-id="12216-153">You designate `_CustomerID` and `_City` fields for private storage.</span></span> <span data-ttu-id="12216-154">然后，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 就可以直接存储和检索值，而不用使用可能包含业务逻辑的公共访问器。</span><span class="sxs-lookup"><span data-stu-id="12216-154">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can then store and retrieve values directly, instead of using public accessors that might include business logic.</span></span>  
  
#### <a name="to-represent-characteristics-of-two-database-columns"></a><span data-ttu-id="12216-155">表示两个数据库列的特性</span><span class="sxs-lookup"><span data-stu-id="12216-155">To represent characteristics of two database columns</span></span>  
  
-   <span data-ttu-id="12216-156">将下面的代码键入或粘贴到 `End Class` 前面紧靠它的 Module1.vb 中。</span><span class="sxs-lookup"><span data-stu-id="12216-156">Type or paste the following code into Module1.vb just before `End Class`:</span></span>  
  
     [!code-vb[DLinqWalk1VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#3)]  
  
## <a name="specifying-the-connection-to-the-northwind-database"></a><span data-ttu-id="12216-157">指定到 Northwind 数据库的连接</span><span class="sxs-lookup"><span data-stu-id="12216-157">Specifying the Connection to the Northwind Database</span></span>  
 <span data-ttu-id="12216-158">在此步骤中，要使用 <xref:System.Data.Linq.DataContext> 对象在您基于代码的数据结构和数据库本身之间建立连接。</span><span class="sxs-lookup"><span data-stu-id="12216-158">In this step you use a <xref:System.Data.Linq.DataContext> object to establish a connection between your code-based data structures and the database itself.</span></span> <span data-ttu-id="12216-159"><xref:System.Data.Linq.DataContext> 是您从数据库中检索对象和提交更改的主要通道。</span><span class="sxs-lookup"><span data-stu-id="12216-159">The <xref:System.Data.Linq.DataContext> is the main channel through which you retrieve objects from the database and submit changes.</span></span>  
  
 <span data-ttu-id="12216-160">您还需声明 `Table(Of Customer)`，用作您针对数据库中 Customers 表的查询的逻辑、类型化表。</span><span class="sxs-lookup"><span data-stu-id="12216-160">You also declare a `Table(Of Customer)` to act as the logical, typed table for your queries against the Customers table in the database.</span></span> <span data-ttu-id="12216-161">您将在后续步骤中创建和执行这些查询。</span><span class="sxs-lookup"><span data-stu-id="12216-161">You will create and execute these queries in later steps.</span></span>  
  
#### <a name="to-specify-the-database-connection"></a><span data-ttu-id="12216-162">指定数据库连接</span><span class="sxs-lookup"><span data-stu-id="12216-162">To specify the database connection</span></span>  
  
-   <span data-ttu-id="12216-163">将下面的代码键入或粘贴到 `Sub Main` 方法中。</span><span class="sxs-lookup"><span data-stu-id="12216-163">Type or paste the following code into the `Sub Main` method.</span></span>  
  
     <span data-ttu-id="12216-164">请注意，假定 `northwnd.mdf` 文件位于 linqtest 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="12216-164">Note that the `northwnd.mdf` file is assumed to be in the linqtest folder.</span></span> <span data-ttu-id="12216-165">有关更多信息，请参见本演练前面部分的“先决条件”一节。</span><span class="sxs-lookup"><span data-stu-id="12216-165">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
     [!code-vb[DLinqWalk1VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#4)]  
  
## <a name="creating-a-simple-query"></a><span data-ttu-id="12216-166">创建简单查询</span><span class="sxs-lookup"><span data-stu-id="12216-166">Creating a Simple Query</span></span>  
 <span data-ttu-id="12216-167">在此步骤中，您将创建一个查询，查找数据库中的 Customers 表内的哪些客户位于伦敦。</span><span class="sxs-lookup"><span data-stu-id="12216-167">In this step, you create a query to find which customers in the database Customers table are located in London.</span></span> <span data-ttu-id="12216-168">此步骤中的查询代码只描述查询。</span><span class="sxs-lookup"><span data-stu-id="12216-168">The query code in this step just describes the query.</span></span> <span data-ttu-id="12216-169">它不执行查询。</span><span class="sxs-lookup"><span data-stu-id="12216-169">It does not execute it.</span></span> <span data-ttu-id="12216-170">这种方法称为*延迟执行*。</span><span class="sxs-lookup"><span data-stu-id="12216-170">This approach is known as *deferred execution*.</span></span> <span data-ttu-id="12216-171">有关详细信息，请参阅 [LINQ 查询简介 (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="12216-171">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="12216-172">您还将生成一个日志输出，显示 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 生成的 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="12216-172">You will also produce a log output to show the SQL commands that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates.</span></span> <span data-ttu-id="12216-173">此日志记录功能（使用 <xref:System.Data.Linq.DataContext.Log%2A>）对调试有帮助，并有助于确定发送给数据库的命令是否准确地表示您的查询。</span><span class="sxs-lookup"><span data-stu-id="12216-173">This logging feature (which uses <xref:System.Data.Linq.DataContext.Log%2A>) is helpful in debugging, and in determining that the commands being sent to the database accurately represent your query.</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="12216-174">创建简单查询</span><span class="sxs-lookup"><span data-stu-id="12216-174">To create a simple query</span></span>  
  
-   <span data-ttu-id="12216-175">将下面的代码键入或粘贴到 `Sub Main` 声明之后的 `Table(Of Customer)` 方法中：</span><span class="sxs-lookup"><span data-stu-id="12216-175">Type or paste the following code into the `Sub Main` method after the `Table(Of Customer)` declaration:</span></span>  
  
     [!code-vb[DLinqWalk1AVB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#5)]  
  
## <a name="executing-the-query"></a><span data-ttu-id="12216-176">执行查询</span><span class="sxs-lookup"><span data-stu-id="12216-176">Executing the Query</span></span>  
 <span data-ttu-id="12216-177">在此步骤中，您将实际执行查询。</span><span class="sxs-lookup"><span data-stu-id="12216-177">In this step, you actually execute the query.</span></span> <span data-ttu-id="12216-178">您在前面步骤中创建的查询表达式只有在需要结果时才会进行计算。</span><span class="sxs-lookup"><span data-stu-id="12216-178">The query expressions you created in the previous steps are not evaluated until the results are needed.</span></span> <span data-ttu-id="12216-179">当您开始 `For Each` 迭代时，将对数据库执行 SQL 命令，并将对象具体化。</span><span class="sxs-lookup"><span data-stu-id="12216-179">When you begin the `For Each` iteration, a SQL command is executed against the database and objects are materialized.</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="12216-180">执行查询</span><span class="sxs-lookup"><span data-stu-id="12216-180">To execute the query</span></span>  
  
1.  <span data-ttu-id="12216-181">将下面的代码键入或粘贴到 `Sub Main` 方法的结尾（在查询说明之后）：</span><span class="sxs-lookup"><span data-stu-id="12216-181">Type or paste the following code at the end of the `Sub Main` method (after the query description):</span></span>  
  
     [!code-vb[DLinqWalk1AVB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#6)]  
  
2.  <span data-ttu-id="12216-182">按 F5 调试该应用程序。</span><span class="sxs-lookup"><span data-stu-id="12216-182">Press F5 to debug the application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="12216-183">如果你的应用程序产生运行时错误，请参阅疑难解答一节[通过演练学习](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)。</span><span class="sxs-lookup"><span data-stu-id="12216-183">If your application generates a run-time error, see the Troubleshooting section of [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
     <span data-ttu-id="12216-184">消息框会显示一个包含六个客户的列表。</span><span class="sxs-lookup"><span data-stu-id="12216-184">The message box displays a list of six customers.</span></span> <span data-ttu-id="12216-185">控制台窗口会显示生成的 SQL 代码。</span><span class="sxs-lookup"><span data-stu-id="12216-185">The Console window displays the generated SQL code.</span></span>  
  
3.  <span data-ttu-id="12216-186">单击“确定”，关闭该消息框。</span><span class="sxs-lookup"><span data-stu-id="12216-186">Click **OK** to dismiss the message box.</span></span>  
  
     <span data-ttu-id="12216-187">应用程序即会关闭。</span><span class="sxs-lookup"><span data-stu-id="12216-187">The application closes.</span></span>  
  
4.  <span data-ttu-id="12216-188">在“文件”菜单上，单击“全部保存”。</span><span class="sxs-lookup"><span data-stu-id="12216-188">On the **File** menu, click **Save All**.</span></span>  
  
     <span data-ttu-id="12216-189">如果您要继续下一演练，您将需要此应用程序。</span><span class="sxs-lookup"><span data-stu-id="12216-189">You will need this application if you continue with the next walkthrough.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="12216-190">后续步骤</span><span class="sxs-lookup"><span data-stu-id="12216-190">Next Steps</span></span>  
 <span data-ttu-id="12216-191">[演练：跨关系查询 (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md)主题将继续本演练结束的位置。</span><span class="sxs-lookup"><span data-stu-id="12216-191">The [Walkthrough: Querying Across Relationships (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md) topic continues where this walkthrough ends.</span></span> <span data-ttu-id="12216-192">跨关系查询演练演示了如何[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]可以跨表查询，类似于*联接*关系数据库中。</span><span class="sxs-lookup"><span data-stu-id="12216-192">The Querying Across Relationships walkthrough demonstrates how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can query across tables, similar to *joins* in a relational database.</span></span>  
  
 <span data-ttu-id="12216-193">如果您希望进行“跨关系进行查询”演练，请务必保存您刚完成的演练的解决方案，这是一项必备条件。</span><span class="sxs-lookup"><span data-stu-id="12216-193">If you want to do the Querying Across Relationships walkthrough, make sure to save the solution for the walkthrough you have just completed, which is a prerequisite.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12216-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="12216-194">See also</span></span>
- [<span data-ttu-id="12216-195">通过演练学习</span><span class="sxs-lookup"><span data-stu-id="12216-195">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
