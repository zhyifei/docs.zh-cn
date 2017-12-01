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
# <a name="walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency"></a>演练：使用 BatchBlock 和 BatchedJoinBlock 提高效率
TPL 数据流库提供<xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType>和<xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType>类，以使你可以接收和缓冲，来自一个或多个源的数据，然后传播该缓冲数据作为一个集合。 从一个或多个来源中收集数据，然后以批处理方式处理多个数据元素时，此批处理机制非常有用。 例如，考虑使用数据流将记录插入数据库的应用程序。 此操作可能更有效，如果多个项按顺序插入而不是一次一个地一次。 本文档介绍如何使用<xref:System.Threading.Tasks.Dataflow.BatchBlock%601>类来改善此类数据库的效率的插入操作。 它还介绍了如何使用<xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602>类获取的结果和发生时程序从数据库中读取的任何异常。  
  
> [!TIP]
>  TPL 数据流库（<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 命名空间）不是随 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 一起分发的。 若要安装<xref:System.Threading.Tasks.Dataflow>命名空间中，打开你的项目中[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]，选择**管理 NuGet 包**从项目菜单，然后联机搜索`Microsoft.Tpl.Dataflow`包。  
  
## <a name="prerequisites"></a>先决条件  
  
1.  读取中的联接块部分[数据流](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)之前在开始本演练，请记录。  
  
2.  确保你有 Northwind 数据库，Northwind.sdf，可在你的计算机上的副本。 此文件通常位于文件夹 %程序 Files%\Microsoft SQL Server Compact Edition\v3.5\Samples\\。  
  
    > [!IMPORTANT]
    >  在某些版本的 Windows 中，你无法连接到 Northwind.sdf 如果[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]在非管理员模式下运行。 若要连接到 Northwind.sdf，启动[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]或[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]中的命令提示符**以管理员身份运行**模式。  
  
 本演练包含以下各节：  
  
-   [创建控制台应用程序](#creating)  
  
-   [定义 Employee 类](#employeeClass)  
  
-   [定义员工数据库操作](#operations)  
  
-   [向数据库添加员工数据，而无需使用缓冲](#nonBuffering)  
  
-   [使用缓冲员工数据添加到数据库](#buffering)  
  
-   [使用缓冲的联接以从数据库中读取雇员数据](#bufferedJoin)  
  
-   [完整示例](#complete)  
  
<a name="creating"></a>   
## <a name="creating-the-console-application"></a>创建控制台应用程序  
  
<a name="consoleApp"></a>   
1.  在[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]，创建 Visual C# 或 Visual Basic**控制台应用程序**项目。 在本文档中，该项目名为 `DataflowBatchDatabase`。  
  
2.  在项目中，添加对 System.Data.SqlServerCe.dll 的引用和对 System.Threading.Tasks.Dataflow.dll 的引用。  
  
3.  确保 Form1.cs (对于 Form1.vb [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 包含以下`using`(`Imports`中[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 语句。  
  
     [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
     [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]  
  
4.  将以下数据成员添加到 `Program` 类。  
  
     [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
     [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]  
  
<a name="employeeClass"></a>   
## <a name="defining-the-employee-class"></a>定义 Employee 类  
 将添加到`Program`类`Employee`类。  
  
 [!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
 [!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]  
  
 `Employee`类包含三个属性， `EmployeeID`， `LastName`，和`FirstName`。 这些属性对应于`Employee ID`， `Last Name`，和`First Name`中的列`Employees`Northwind 数据库中的表。 对于本演示，`Employee`类还定义`Random`方法，创建`Employee`具有其属性的随机值的对象。  
  
<a name="operations"></a>   
## <a name="defining-employee-database-operations"></a>定义员工数据库操作  
 将添加到`Program`类`InsertEmployees`， `GetEmployeeCount`，和`GetEmployeeID`方法。  
  
 [!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
 [!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]  
  
 `InsertEmployees`方法向数据库添加新雇员记录。 `GetEmployeeCount`方法检索中的条目数`Employees`表。 `GetEmployeeID`方法检索具有所提供的名称的第一个员工的标识符。 每个这些方法采用包含到 Northwind 数据库的连接字符串，并使用中的功能`System.Data.SqlServerCe`命名空间与数据库进行通信。  
  
<a name="nonBuffering"></a>   
## <a name="adding-employee-data-to-the-database-without-using-buffering"></a>向数据库添加员工数据，而无需使用缓冲  
 将添加到`Program`类`AddEmployees`和`PostRandomEmployees`方法。  
  
 [!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
 [!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]  
  
 `AddEmployees`方法将随机员工数据添加到数据库，通过使用数据流。 它将创建<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>调用的对象`InsertEmployees`方法将员工条目添加到数据库。 `AddEmployees`方法然后调用`PostRandomEmployees`方法发布多个`Employee`对象添加到<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>对象。 `AddEmployees`方法然后等待所有插入操作来完成。  
  
<a name="buffering"></a>   
## <a name="using-buffering-to-add-employee-data-to-the-database"></a>使用缓冲员工数据添加到数据库  
 将添加到`Program`类`AddEmployeesBatched`方法。  
  
 [!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
 [!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]  
  
 此方法类似于`AddEmployees`，只不过它还使用<xref:System.Threading.Tasks.Dataflow.BatchBlock%601>类的数据进行缓冲多个`Employee`对象发送这些对象附加到之前<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>对象。 因为<xref:System.Threading.Tasks.Dataflow.BatchBlock%601>类作为一个集合，传播多个元素<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>修改对象操作的数组`Employee`对象。 作为 in`AddEmployees`方法，`AddEmployeesBatched`调用`PostRandomEmployees`方法发布多个`Employee`对象; 但是，`AddEmployeesBatched`发送到这些对象<xref:System.Threading.Tasks.Dataflow.BatchBlock%601>对象。 `AddEmployeesBatched`方法也等待所有插入操作来完成。  
  
<a name="bufferedJoin"></a>   
## <a name="using-buffered-join-to-read-employee-data-from-the-database"></a>使用缓冲的联接以从数据库中读取雇员数据  
 将添加到`Program`类`GetRandomEmployees`方法。  
  
 [!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
 [!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]  
  
 此方法将打印到控制台的随机员工有关的信息。 它会创建多个随机`Employee`对象，并调用`GetEmployeeID`方法来检索每个对象的唯一标识符。 因为`GetEmployeeID`方法引发异常，如果没有具有给定的第一个和最后一个名称，没有匹配员工`GetRandomEmployees`方法使用<xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602>类来存储`Employee`对象以便成功调用`GetEmployeeID`和<xref:System.Exception?displayProperty=nameWithType>失败的调用的对象。 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>对象在此示例中，也用作上<xref:System.Tuple%602>对象包含一系列的`Employee`对象和列表<xref:System.Exception>对象。 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602>对象传播此数据时收到的总和`Employee`和<xref:System.Exception>对象计数等于批大小。  
  
<a name="complete"></a>   
## <a name="the-complete-example"></a>完整示例  
 以下示例显示了完整的代码。 `Main`方法比较执行与执行非批处理数据库插入操作的时间的批处理的数据库插入所需的时间。 它还演示了利用缓冲的联接可以从数据库读取员工数据，还报告错误。  
  
 [!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
 [!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]  
  
## <a name="see-also"></a>另请参阅  
 [数据流](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
