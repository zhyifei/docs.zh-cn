---
title: "演练：使用 BatchBlock 和 BatchedJoinBlock 提高效率"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, improving efficiency
ms.assetid: 5beb4983-80c2-4f60-8c51-a07f9fd94cb3
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bc74b4acc5b29395c05e7c8302caefeb51718282
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency"></a><span data-ttu-id="663a0-102">演练：使用 BatchBlock 和 BatchedJoinBlock 提高效率</span><span class="sxs-lookup"><span data-stu-id="663a0-102">Walkthrough: Using BatchBlock and BatchedJoinBlock to Improve Efficiency</span></span>
<span data-ttu-id="663a0-103">TPL 数据流库提供<xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType>和<xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType>类，以使你可以接收和缓冲，来自一个或多个源的数据，然后传播该缓冲数据作为一个集合。</span><span class="sxs-lookup"><span data-stu-id="663a0-103">The TPL Dataflow Library provides the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType> classes so that you can receive and buffer data from one or more sources and then propagate out that buffered data as one collection.</span></span> <span data-ttu-id="663a0-104">从一个或多个来源中收集数据，然后以批处理方式处理多个数据元素时，此批处理机制非常有用。</span><span class="sxs-lookup"><span data-stu-id="663a0-104">This batching mechanism is useful when you collect data from one or more sources and then process multiple data elements as a batch.</span></span> <span data-ttu-id="663a0-105">例如，考虑使用数据流将记录插入数据库的应用程序。</span><span class="sxs-lookup"><span data-stu-id="663a0-105">For example, consider an application that uses dataflow to insert records into a database.</span></span> <span data-ttu-id="663a0-106">此操作可能更有效，如果多个项按顺序插入而不是一次一个地一次。</span><span class="sxs-lookup"><span data-stu-id="663a0-106">This operation can be more efficient if multiple items are inserted at the same time instead of one at a time sequentially.</span></span> <span data-ttu-id="663a0-107">本文档介绍如何使用<xref:System.Threading.Tasks.Dataflow.BatchBlock%601>类来改善此类数据库的效率的插入操作。</span><span class="sxs-lookup"><span data-stu-id="663a0-107">This document describes how to use the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class to improve the efficiency of such database insert operations.</span></span> <span data-ttu-id="663a0-108">它还介绍了如何使用<xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602>类获取的结果和发生时程序从数据库中读取的任何异常。</span><span class="sxs-lookup"><span data-stu-id="663a0-108">It also describes how to use the <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> class to capture both the results and any exceptions that occur when the program reads from a database.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="663a0-109">TPL 数据流库（<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 命名空间）不是随 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 一起分发的。</span><span class="sxs-lookup"><span data-stu-id="663a0-109">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="663a0-110">若要安装<xref:System.Threading.Tasks.Dataflow>命名空间中，打开你的项目中[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]，选择**管理 NuGet 包**从项目菜单，然后联机搜索`Microsoft.Tpl.Dataflow`包。</span><span class="sxs-lookup"><span data-stu-id="663a0-110">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="663a0-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="663a0-111">Prerequisites</span></span>  
  
1.  <span data-ttu-id="663a0-112">读取中的联接块部分[数据流](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)之前在开始本演练，请记录。</span><span class="sxs-lookup"><span data-stu-id="663a0-112">Read the Join Blocks section in the [Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) document before you start this walkthrough.</span></span>  
  
2.  <span data-ttu-id="663a0-113">确保你有 Northwind 数据库，Northwind.sdf，可在你的计算机上的副本。</span><span class="sxs-lookup"><span data-stu-id="663a0-113">Ensure that you have a copy of the Northwind database, Northwind.sdf, available on your computer.</span></span> <span data-ttu-id="663a0-114">此文件通常位于文件夹 %程序 Files%\Microsoft SQL Server Compact Edition\v3.5\Samples\\。</span><span class="sxs-lookup"><span data-stu-id="663a0-114">This file is typically located in the folder %Program Files%\Microsoft SQL Server Compact Edition\v3.5\Samples\\.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="663a0-115">在某些版本的 Windows 中，你无法连接到 Northwind.sdf 如果[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]在非管理员模式下运行。</span><span class="sxs-lookup"><span data-stu-id="663a0-115">In some versions of Windows, you cannot connect to Northwind.sdf if [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] is running in a non-administrator mode.</span></span> <span data-ttu-id="663a0-116">若要连接到 Northwind.sdf，启动[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]或[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]中的命令提示符**以管理员身份运行**模式。</span><span class="sxs-lookup"><span data-stu-id="663a0-116">To connect to Northwind.sdf, start [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] command prompt in the **Run as administrator** mode.</span></span>  
  
 <span data-ttu-id="663a0-117">本演练包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="663a0-117">This walkthrough contains the following sections:</span></span>  
  
-   [<span data-ttu-id="663a0-118">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="663a0-118">Creating the Console Application</span></span>](#creating)  
  
-   [<span data-ttu-id="663a0-119">定义 Employee 类</span><span class="sxs-lookup"><span data-stu-id="663a0-119">Defining the Employee Class</span></span>](#employeeClass)  
  
-   [<span data-ttu-id="663a0-120">定义员工数据库操作</span><span class="sxs-lookup"><span data-stu-id="663a0-120">Defining Employee Database Operations</span></span>](#operations)  
  
-   [<span data-ttu-id="663a0-121">向数据库添加员工数据，而无需使用缓冲</span><span class="sxs-lookup"><span data-stu-id="663a0-121">Adding Employee Data to the Database without Using Buffering</span></span>](#nonBuffering)  
  
-   [<span data-ttu-id="663a0-122">使用缓冲员工数据添加到数据库</span><span class="sxs-lookup"><span data-stu-id="663a0-122">Using Buffering to Add Employee Data to the Database</span></span>](#buffering)  
  
-   [<span data-ttu-id="663a0-123">使用缓冲的联接以从数据库中读取雇员数据</span><span class="sxs-lookup"><span data-stu-id="663a0-123">Using Buffered Join to Read Employee Data from the Database</span></span>](#bufferedJoin)  
  
-   [<span data-ttu-id="663a0-124">完整示例</span><span class="sxs-lookup"><span data-stu-id="663a0-124">The Complete Example</span></span>](#complete)  
  
<a name="creating"></a>   
## <a name="creating-the-console-application"></a><span data-ttu-id="663a0-125">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="663a0-125">Creating the Console Application</span></span>  
  
<a name="consoleApp"></a>   
1.  <span data-ttu-id="663a0-126">在[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]，创建 Visual C# 或 Visual Basic**控制台应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="663a0-126">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], create a Visual C# or Visual Basic **Console Application** project.</span></span> <span data-ttu-id="663a0-127">在本文档中，该项目名为 `DataflowBatchDatabase`。</span><span class="sxs-lookup"><span data-stu-id="663a0-127">In this document, the project is named `DataflowBatchDatabase`.</span></span>  
  
2.  <span data-ttu-id="663a0-128">在项目中，添加对 System.Data.SqlServerCe.dll 的引用和对 System.Threading.Tasks.Dataflow.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="663a0-128">In your project, add a reference to System.Data.SqlServerCe.dll and a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
3.  <span data-ttu-id="663a0-129">确保 Form1.cs (对于 Form1.vb [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 包含以下`using`(`Imports`中[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 语句。</span><span class="sxs-lookup"><span data-stu-id="663a0-129">Ensure that Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contains the following `using` (`Imports` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) statements.</span></span>  
  
     [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
     [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]  
  
4.  <span data-ttu-id="663a0-130">将以下数据成员添加到 `Program` 类。</span><span class="sxs-lookup"><span data-stu-id="663a0-130">Add the following data members to the `Program` class.</span></span>  
  
     [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
     [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]  
  
<a name="employeeClass"></a>   
## <a name="defining-the-employee-class"></a><span data-ttu-id="663a0-131">定义 Employee 类</span><span class="sxs-lookup"><span data-stu-id="663a0-131">Defining the Employee Class</span></span>  
 <span data-ttu-id="663a0-132">将添加到`Program`类`Employee`类。</span><span class="sxs-lookup"><span data-stu-id="663a0-132">Add to the `Program` class the `Employee` class.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
 [!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]  
  
 <span data-ttu-id="663a0-133">`Employee`类包含三个属性， `EmployeeID`， `LastName`，和`FirstName`。</span><span class="sxs-lookup"><span data-stu-id="663a0-133">The `Employee` class contains three properties, `EmployeeID`, `LastName`, and `FirstName`.</span></span> <span data-ttu-id="663a0-134">这些属性对应于`Employee ID`， `Last Name`，和`First Name`中的列`Employees`Northwind 数据库中的表。</span><span class="sxs-lookup"><span data-stu-id="663a0-134">These properties correspond to the `Employee ID`, `Last Name`, and `First Name` columns in the `Employees` table in the Northwind database.</span></span> <span data-ttu-id="663a0-135">对于本演示，`Employee`类还定义`Random`方法，创建`Employee`具有其属性的随机值的对象。</span><span class="sxs-lookup"><span data-stu-id="663a0-135">For this demonstration, the `Employee` class also defines the `Random` method, which creates an `Employee` object that has random values for its properties.</span></span>  
  
<a name="operations"></a>   
## <a name="defining-employee-database-operations"></a><span data-ttu-id="663a0-136">定义员工数据库操作</span><span class="sxs-lookup"><span data-stu-id="663a0-136">Defining Employee Database Operations</span></span>  
 <span data-ttu-id="663a0-137">将添加到`Program`类`InsertEmployees`， `GetEmployeeCount`，和`GetEmployeeID`方法。</span><span class="sxs-lookup"><span data-stu-id="663a0-137">Add to the `Program` class the `InsertEmployees`, `GetEmployeeCount`, and `GetEmployeeID` methods.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
 [!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]  
  
 <span data-ttu-id="663a0-138">`InsertEmployees`方法向数据库添加新雇员记录。</span><span class="sxs-lookup"><span data-stu-id="663a0-138">The `InsertEmployees` method adds new employee records to the database.</span></span> <span data-ttu-id="663a0-139">`GetEmployeeCount`方法检索中的条目数`Employees`表。</span><span class="sxs-lookup"><span data-stu-id="663a0-139">The `GetEmployeeCount` method retrieves the number of entries in the `Employees` table.</span></span> <span data-ttu-id="663a0-140">`GetEmployeeID`方法检索具有所提供的名称的第一个员工的标识符。</span><span class="sxs-lookup"><span data-stu-id="663a0-140">The `GetEmployeeID` method retrieves the identifier of the first employee that has the provided name.</span></span> <span data-ttu-id="663a0-141">每个这些方法采用包含到 Northwind 数据库的连接字符串，并使用中的功能`System.Data.SqlServerCe`命名空间与数据库进行通信。</span><span class="sxs-lookup"><span data-stu-id="663a0-141">Each of these methods takes a connection string to the Northwind database and uses functionality in the `System.Data.SqlServerCe` namespace to communicate with the database.</span></span>  
  
<a name="nonBuffering"></a>   
## <a name="adding-employee-data-to-the-database-without-using-buffering"></a><span data-ttu-id="663a0-142">向数据库添加员工数据，而无需使用缓冲</span><span class="sxs-lookup"><span data-stu-id="663a0-142">Adding Employee Data to the Database Without Using Buffering</span></span>  
 <span data-ttu-id="663a0-143">将添加到`Program`类`AddEmployees`和`PostRandomEmployees`方法。</span><span class="sxs-lookup"><span data-stu-id="663a0-143">Add to the `Program` class the `AddEmployees` and `PostRandomEmployees` methods.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
 [!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]  
  
 <span data-ttu-id="663a0-144">`AddEmployees`方法将随机员工数据添加到数据库，通过使用数据流。</span><span class="sxs-lookup"><span data-stu-id="663a0-144">The `AddEmployees` method adds random employee data to the database by using dataflow.</span></span> <span data-ttu-id="663a0-145">它将创建<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>调用的对象`InsertEmployees`方法将员工条目添加到数据库。</span><span class="sxs-lookup"><span data-stu-id="663a0-145">It creates an <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object that calls the `InsertEmployees` method to add an employee entry to the database.</span></span> <span data-ttu-id="663a0-146">`AddEmployees`方法然后调用`PostRandomEmployees`方法发布多个`Employee`对象添加到<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>对象。</span><span class="sxs-lookup"><span data-stu-id="663a0-146">The `AddEmployees` method then calls the `PostRandomEmployees` method to post multiple `Employee` objects to the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="663a0-147">`AddEmployees`方法然后等待所有插入操作来完成。</span><span class="sxs-lookup"><span data-stu-id="663a0-147">The `AddEmployees` method then waits for all insert operations to finish.</span></span>  
  
<a name="buffering"></a>   
## <a name="using-buffering-to-add-employee-data-to-the-database"></a><span data-ttu-id="663a0-148">使用缓冲员工数据添加到数据库</span><span class="sxs-lookup"><span data-stu-id="663a0-148">Using Buffering to Add Employee Data to the Database</span></span>  
 <span data-ttu-id="663a0-149">将添加到`Program`类`AddEmployeesBatched`方法。</span><span class="sxs-lookup"><span data-stu-id="663a0-149">Add to the `Program` class the `AddEmployeesBatched` method.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
 [!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]  
  
 <span data-ttu-id="663a0-150">此方法类似于`AddEmployees`，只不过它还使用<xref:System.Threading.Tasks.Dataflow.BatchBlock%601>类的数据进行缓冲多个`Employee`对象发送这些对象附加到之前<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>对象。</span><span class="sxs-lookup"><span data-stu-id="663a0-150">This method resembles `AddEmployees`, except that it also uses the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class to buffer multiple `Employee` objects before it sends those objects to the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="663a0-151">因为<xref:System.Threading.Tasks.Dataflow.BatchBlock%601>类作为一个集合，传播多个元素<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>修改对象操作的数组`Employee`对象。</span><span class="sxs-lookup"><span data-stu-id="663a0-151">Because the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class propagates out multiple elements as a collection, the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object is modified to act on an array of `Employee` objects.</span></span> <span data-ttu-id="663a0-152">作为 in`AddEmployees`方法，`AddEmployeesBatched`调用`PostRandomEmployees`方法发布多个`Employee`对象; 但是，`AddEmployeesBatched`发送到这些对象<xref:System.Threading.Tasks.Dataflow.BatchBlock%601>对象。</span><span class="sxs-lookup"><span data-stu-id="663a0-152">As in the `AddEmployees` method, `AddEmployeesBatched` calls the `PostRandomEmployees` method to post multiple `Employee` objects; however, `AddEmployeesBatched` posts these objects to the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> object.</span></span> <span data-ttu-id="663a0-153">`AddEmployeesBatched`方法也等待所有插入操作来完成。</span><span class="sxs-lookup"><span data-stu-id="663a0-153">The `AddEmployeesBatched`  method also waits for all insert operations to finish.</span></span>  
  
<a name="bufferedJoin"></a>   
## <a name="using-buffered-join-to-read-employee-data-from-the-database"></a><span data-ttu-id="663a0-154">使用缓冲的联接以从数据库中读取雇员数据</span><span class="sxs-lookup"><span data-stu-id="663a0-154">Using Buffered Join to Read Employee Data from the Database</span></span>  
 <span data-ttu-id="663a0-155">将添加到`Program`类`GetRandomEmployees`方法。</span><span class="sxs-lookup"><span data-stu-id="663a0-155">Add to the `Program` class the `GetRandomEmployees` method.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
 [!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]  
  
 <span data-ttu-id="663a0-156">此方法将打印到控制台的随机员工有关的信息。</span><span class="sxs-lookup"><span data-stu-id="663a0-156">This method prints information about random employees to the console.</span></span> <span data-ttu-id="663a0-157">它会创建多个随机`Employee`对象，并调用`GetEmployeeID`方法来检索每个对象的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="663a0-157">It creates several random `Employee` objects and calls the `GetEmployeeID` method to retrieve the unique identifier for each object.</span></span> <span data-ttu-id="663a0-158">因为`GetEmployeeID`方法引发异常，如果没有具有给定的第一个和最后一个名称，没有匹配员工`GetRandomEmployees`方法使用<xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602>类来存储`Employee`对象以便成功调用`GetEmployeeID`和<xref:System.Exception?displayProperty=nameWithType>失败的调用的对象。</span><span class="sxs-lookup"><span data-stu-id="663a0-158">Because the `GetEmployeeID` method throws an exception if there is no matching employee with the given first and last names, the `GetRandomEmployees` method uses the <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> class to store `Employee` objects for successful calls to `GetEmployeeID` and <xref:System.Exception?displayProperty=nameWithType> objects for calls that fail.</span></span> <span data-ttu-id="663a0-159"><xref:System.Threading.Tasks.Dataflow.ActionBlock%601>对象在此示例中，也用作上<xref:System.Tuple%602>对象包含一系列的`Employee`对象和列表<xref:System.Exception>对象。</span><span class="sxs-lookup"><span data-stu-id="663a0-159">The <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object in this example acts on a <xref:System.Tuple%602> object that holds a list of `Employee` objects and a list of <xref:System.Exception> objects.</span></span> <span data-ttu-id="663a0-160"><xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602>对象传播此数据时收到的总和`Employee`和<xref:System.Exception>对象计数等于批大小。</span><span class="sxs-lookup"><span data-stu-id="663a0-160">The <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> object propagates out this data when the sum of the received `Employee` and <xref:System.Exception> object counts equals the batch size.</span></span>  
  
<a name="complete"></a>   
## <a name="the-complete-example"></a><span data-ttu-id="663a0-161">完整示例</span><span class="sxs-lookup"><span data-stu-id="663a0-161">The Complete Example</span></span>  
 <span data-ttu-id="663a0-162">以下示例显示了完整的代码。</span><span class="sxs-lookup"><span data-stu-id="663a0-162">The following example shows the complete code.</span></span> <span data-ttu-id="663a0-163">`Main`方法比较执行与执行非批处理数据库插入操作的时间的批处理的数据库插入所需的时间。</span><span class="sxs-lookup"><span data-stu-id="663a0-163">The `Main` method compares the time that is required to perform batched database insertions versus the time to perform non-batched database insertions.</span></span> <span data-ttu-id="663a0-164">它还演示了利用缓冲的联接可以从数据库读取员工数据，还报告错误。</span><span class="sxs-lookup"><span data-stu-id="663a0-164">It also demonstrates the use of buffered join to read employee data from the database and also report errors.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
 [!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="663a0-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="663a0-165">See Also</span></span>  
 [<span data-ttu-id="663a0-166">数据流</span><span class="sxs-lookup"><span data-stu-id="663a0-166">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
