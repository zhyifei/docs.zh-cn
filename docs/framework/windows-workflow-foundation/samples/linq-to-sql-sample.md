---
title: "LINQ to SQL 示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f39db9e-0e62-42c9-8c98-bb8b54cec98c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 06273f3ac7dd159adac4c058a23c187f44417d94
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-sql-sample"></a><span data-ttu-id="e501a-102">LINQ to SQL 示例</span><span class="sxs-lookup"><span data-stu-id="e501a-102">LINQ to SQL Sample</span></span>
<span data-ttu-id="e501a-103">此示例演示如何创建活动以使用 LINQ to SQL 查询 SQL Server 数据库的表中的实体。</span><span class="sxs-lookup"><span data-stu-id="e501a-103">This sample demonstrates how to create an activity to use LINQ to SQL query entities from tables in SQL Server databases.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e501a-104">您的计算机上可能已安装 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="e501a-104">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples may already be installed on your machine.</span></span> <span data-ttu-id="e501a-105">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="e501a-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardspace`  
>   
>  <span data-ttu-id="e501a-106">如果该目录不存在，请单击此页顶部的下载示例链接。</span><span class="sxs-lookup"><span data-stu-id="e501a-106">If this directory does not exist, click the download sample link at the top of this page.</span></span> <span data-ttu-id="e501a-107">请注意，此链接将下载和安装所有 [!INCLUDE[wf1](../../../../includes/wf1-md.md)]、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 和 [!INCLUDE[infocard](../../../../includes/infocard-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="e501a-107">Note that this link downloads and installs all of the [!INCLUDE[wf1](../../../../includes/wf1-md.md)], [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], and [!INCLUDE[infocard](../../../../includes/infocard-md.md)] samples.</span></span> <span data-ttu-id="e501a-108">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="e501a-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardSpace\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## <a name="activity-details-for-findinsqltable"></a><span data-ttu-id="e501a-109">FindInSqlTable 的活动详细信息</span><span class="sxs-lookup"><span data-stu-id="e501a-109">Activity details for FindInSqlTable</span></span>  
 <span data-ttu-id="e501a-110">此活动允许用户使用 LINQ to SQL 查询数据库的表中的实体。</span><span class="sxs-lookup"><span data-stu-id="e501a-110">This activity allows users to query entities from tables in a database using LINQ to SQL.</span></span> <span data-ttu-id="e501a-111">此活动的用户还可以提供 lambda 表达式形式的 LINQ 谓词来筛选结果。</span><span class="sxs-lookup"><span data-stu-id="e501a-111">Users of the activity can also provide a LINQ predicate in the form of a lambda expression to filter the results.</span></span> <span data-ttu-id="e501a-112">如果未提供谓词，则返回整个表。</span><span class="sxs-lookup"><span data-stu-id="e501a-112">If no predicate is provided, the entire table is returned.</span></span> <span data-ttu-id="e501a-113">下表详述了此活动的属性和返回值。</span><span class="sxs-lookup"><span data-stu-id="e501a-113">The following table details the property and return values for the activity.</span></span>  
  
|<span data-ttu-id="e501a-114">属性或返回值</span><span class="sxs-lookup"><span data-stu-id="e501a-114">Property or Return Value</span></span>|<span data-ttu-id="e501a-115">描述</span><span class="sxs-lookup"><span data-stu-id="e501a-115">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="e501a-116">`Collection` 属性</span><span class="sxs-lookup"><span data-stu-id="e501a-116">`Collection` property</span></span>|<span data-ttu-id="e501a-117">必需属性，用于指定源集合。</span><span class="sxs-lookup"><span data-stu-id="e501a-117">A required property that specifies the source collection.</span></span>|  
|<span data-ttu-id="e501a-118">`Predicate` 属性</span><span class="sxs-lookup"><span data-stu-id="e501a-118">`Predicate` property</span></span>|<span data-ttu-id="e501a-119">必需属性，用于指定 lambda 表达式形式的集合筛选器。</span><span class="sxs-lookup"><span data-stu-id="e501a-119">A required property that specifies the filter for the collection in the form of a lambda expression.</span></span>|  
|<span data-ttu-id="e501a-120">返回值</span><span class="sxs-lookup"><span data-stu-id="e501a-120">Return Value</span></span>|<span data-ttu-id="e501a-121">经过筛选的集合。</span><span class="sxs-lookup"><span data-stu-id="e501a-121">The filtered collection.</span></span>|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a><span data-ttu-id="e501a-122">使用自定义活动的代码示例</span><span class="sxs-lookup"><span data-stu-id="e501a-122">Code Sample that uses the Custom Activity</span></span>  
 <span data-ttu-id="e501a-123">下面的代码示例使用 `FindInSqlTable` 自定义活动，在名为 `Employee` 的 SQL Server 表中查找所有 `Role` 列等于 `SDE` 的行。</span><span class="sxs-lookup"><span data-stu-id="e501a-123">The following code example uses the `FindInSqlTable` custom activity to find all rows in a SQL Server table named `Employee` where the `Role` column is equal to `SDE`.</span></span>  
  
```csharp  
new FindInSqlTable<Employee>   
{  
    ConnectionString = @"Data Source=.\SQLExpress;Initial Catalog=LinqToSqlSample;Integrated Security=True",                          
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(emp => emp.Role.Equals("SDE"))),  
    Result = new OutArgument<IList<Employee>>(employees)  
},  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="e501a-124">使用此示例</span><span class="sxs-lookup"><span data-stu-id="e501a-124">To use this sample</span></span>  
  
1.  <span data-ttu-id="e501a-125">打开命令提示。</span><span class="sxs-lookup"><span data-stu-id="e501a-125">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="e501a-126">导航到包含此示例的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e501a-126">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="e501a-127">运行 Setup.cmd 命令文件。</span><span class="sxs-lookup"><span data-stu-id="e501a-127">Run the Setup.cmd command file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e501a-128">Setup.cmd 脚本尝试将此示例数据库安装在您本地计算机上的 SQL Server Express 中。</span><span class="sxs-lookup"><span data-stu-id="e501a-128">The Setup.cmd script attempts to install the sample database in your local machine SQL Server Express.</span></span> <span data-ttu-id="e501a-129">如果您需要在其他 SQL Server 实例中安装它，请编辑 Setup.cmd。</span><span class="sxs-lookup"><span data-stu-id="e501a-129">If you want to install it in other SQL server instance, edit Setup.cmd.</span></span>  
  
     <span data-ttu-id="e501a-130">Setup.cmd 脚本执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e501a-130">The Setup.cmd script does the following actions.:</span></span>  
  
    -   <span data-ttu-id="e501a-131">创建一个名为 LinqToSqlSample 的数据库。</span><span class="sxs-lookup"><span data-stu-id="e501a-131">Creates a database called LinqToSqlSample.</span></span>  
  
    -   <span data-ttu-id="e501a-132">创建一个 Roles 表。</span><span class="sxs-lookup"><span data-stu-id="e501a-132">Creates a Roles table.</span></span>  
  
    -   <span data-ttu-id="e501a-133">创建一个 Employees 表。</span><span class="sxs-lookup"><span data-stu-id="e501a-133">Creates an Employees table.</span></span>  
  
    -   <span data-ttu-id="e501a-134">将 3 个记录插入到 Roles 表中。</span><span class="sxs-lookup"><span data-stu-id="e501a-134">Inserts 3 records into the Roles table.</span></span>  
  
    -   <span data-ttu-id="e501a-135">将 12 个记录插入到 Employees 表中。</span><span class="sxs-lookup"><span data-stu-id="e501a-135">Inserts 12 records into the Employees table.</span></span>  
  
4.  <span data-ttu-id="e501a-136">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 LinqToSQL.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="e501a-136">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LinqToSQL.sln solution file.</span></span>  
  
5.  <span data-ttu-id="e501a-137">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="e501a-137">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="e501a-138">若要运行解决方案，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="e501a-138">To run the solution, press F5.</span></span>  
  
#### <a name="to-uninstall-the-linqtosql-sample-database"></a><span data-ttu-id="e501a-139">卸载 LinqToSql 示例数据库</span><span class="sxs-lookup"><span data-stu-id="e501a-139">To uninstall the LinqToSql sample database</span></span>  
  
1.  <span data-ttu-id="e501a-140">打开命令提示。</span><span class="sxs-lookup"><span data-stu-id="e501a-140">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="e501a-141">导航到包含此示例的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e501a-141">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="e501a-142">运行 Cleanup.cmd 命令文件。</span><span class="sxs-lookup"><span data-stu-id="e501a-142">Run the Cleanup.cmd command file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e501a-143">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="e501a-143">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e501a-144">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="e501a-144">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e501a-145">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="e501a-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e501a-146">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="e501a-146">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Liiinq\LinqToSql`  
  
## <a name="see-also"></a><span data-ttu-id="e501a-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="e501a-147">See Also</span></span>  
 [<span data-ttu-id="e501a-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e501a-148">LINQ to SQL</span></span>](http://go.microsoft.com/fwlink/?LinkId=150376)  
 [<span data-ttu-id="e501a-149">入门 (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="e501a-149">Getting Started (LINQ to SQL)</span></span>](http://go.microsoft.com/fwlink/?LinkId=150377)
