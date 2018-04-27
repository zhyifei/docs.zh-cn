---
title: SQL 跟踪
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2eeb5cf57e6efac77de4a76fe8131189273d5438
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="sql-tracking"></a><span data-ttu-id="7eacf-102">SQL 跟踪</span><span class="sxs-lookup"><span data-stu-id="7eacf-102">SQL Tracking</span></span>
<span data-ttu-id="7eacf-103">此示例演示如何编写一个自定义 SQL 跟踪参与者，该参与者将跟踪记录写入到一个 SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="7eacf-103">This sample demonstrates how to write a custom SQL tracking participant, that writes tracking records to a SQL database.</span></span> <span data-ttu-id="7eacf-104">Windows Workflow Foundation (WF) 提供工作流跟踪以查看工作流实例的执行。</span><span class="sxs-lookup"><span data-stu-id="7eacf-104">Windows Workflow Foundation (WF) provides workflow tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="7eacf-105">跟踪运行时在工作流执行过程中会发出工作流跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="7eacf-105">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7eacf-106"> 工作流跟踪，请参阅[工作流跟踪](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)。</span><span class="sxs-lookup"><span data-stu-id="7eacf-106"> workflow tracking, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="7eacf-107">使用此示例</span><span class="sxs-lookup"><span data-stu-id="7eacf-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="7eacf-108">确认您已安装 SQL Server 2008、 SQL Server 2008 Express 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="7eacf-108">Verify you have SQL Server 2008, SQL Server 2008 Express or newer installed.</span></span> <span data-ttu-id="7eacf-109">与示例打包在一起的脚本假定在您的本地计算机上使用 SQL Express 实例。</span><span class="sxs-lookup"><span data-stu-id="7eacf-109">The scripts packaged with the sample assume the use of a SQL Express instance on your local computer.</span></span> <span data-ttu-id="7eacf-110">如果您安装了不同的实例，请在运行此示例之前修改与数据库相关的脚本。</span><span class="sxs-lookup"><span data-stu-id="7eacf-110">If you have a different instance please modify the database-related scripts before running the sample.</span></span>  
  
2.  <span data-ttu-id="7eacf-111">通过在脚本目录 (\WF\Basic\Tracking\SqlTracking\CS\Scripts) 中运行 Trackingsetup.cmd 来创建 SQL Server 跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="7eacf-111">Create the SQL Server tracking database by running Trackingsetup.cmd in the scripts directory (\WF\Basic\Tracking\SqlTracking\CS\Scripts).</span></span> <span data-ttu-id="7eacf-112">这会创建一个名为 TrackingSample 的数据库。</span><span class="sxs-lookup"><span data-stu-id="7eacf-112">This creates a database called TrackingSample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7eacf-113">脚本将在 SQL Express 的默认实例上创建该数据库。</span><span class="sxs-lookup"><span data-stu-id="7eacf-113">The script creates the database on the default instance of SQL Express.</span></span> <span data-ttu-id="7eacf-114">如果您想在不同的数据库实例上安装该数据库，请编辑 Trackingsetup.cmd 脚本。</span><span class="sxs-lookup"><span data-stu-id="7eacf-114">If you want to install it on a different database instance, edit the Trackingsetup.cmd script.</span></span>  
  
3.  <span data-ttu-id="7eacf-115">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 SqlTrackingSample.sln。</span><span class="sxs-lookup"><span data-stu-id="7eacf-115">Open SqlTrackingSample.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
4.  <span data-ttu-id="7eacf-116">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="7eacf-116">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
5.  <span data-ttu-id="7eacf-117">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="7eacf-117">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="7eacf-118">浏览器窗口打开和显示侦听应用程序的目录。</span><span class="sxs-lookup"><span data-stu-id="7eacf-118">The browser window opens and shows the directory listing for the application.</span></span>  
  
6.  <span data-ttu-id="7eacf-119">在浏览器中，单击 StockPriceService.xamlx。</span><span class="sxs-lookup"><span data-stu-id="7eacf-119">In the browser, click StockPriceService.xamlx.</span></span>  
  
7.  <span data-ttu-id="7eacf-120">浏览器显示 StockPriceService 页，其中包含本地服务 WSDL 地址。</span><span class="sxs-lookup"><span data-stu-id="7eacf-120">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="7eacf-121">复制此地址。</span><span class="sxs-lookup"><span data-stu-id="7eacf-121">Copy this address.</span></span>  
  
     <span data-ttu-id="7eacf-122">本地服务 WSDL 地址的一个示例是http://localhost:65193/StockPriceService.xamlx?wsdl。</span><span class="sxs-lookup"><span data-stu-id="7eacf-122">An example of the local service WSDL address is http://localhost:65193/StockPriceService.xamlx?wsdl.</span></span>  
  
8.  <span data-ttu-id="7eacf-123">使用 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]，运行 WCF 测试客户端 (WcfTestClient.exe)。</span><span class="sxs-lookup"><span data-stu-id="7eacf-123">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], run the WCF test client (WcfTestClient.exe).</span></span> <span data-ttu-id="7eacf-124">它位于 Microsoft Visual Studio 10.0\Common7\IDE 目录下。</span><span class="sxs-lookup"><span data-stu-id="7eacf-124">It is located in the Microsoft Visual Studio 10.0\Common7\IDE directory.</span></span>  
  
9. <span data-ttu-id="7eacf-125">在 WCF 测试客户端中，单击**文件**菜单，然后选择**添加服务**。</span><span class="sxs-lookup"><span data-stu-id="7eacf-125">In the WCF test client, click the **File** menu and select **Add Service**.</span></span> <span data-ttu-id="7eacf-126">将本地服务地址粘贴到文本框中。</span><span class="sxs-lookup"><span data-stu-id="7eacf-126">Paste the local service address in the textbox.</span></span> <span data-ttu-id="7eacf-127">单击**确定**关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="7eacf-127">Click **OK** to close the dialog.</span></span>  
  
10. <span data-ttu-id="7eacf-128">在 WCF 测试客户端中，双击**GetStockPrice**。</span><span class="sxs-lookup"><span data-stu-id="7eacf-128">In the WCF test client, double click **GetStockPrice**.</span></span> <span data-ttu-id="7eacf-129">这将打开`GetStockPrice`采用一个参数，值中的类型的操作`Contoso`单击**Invoke**。</span><span class="sxs-lookup"><span data-stu-id="7eacf-129">This opens the `GetStockPrice` operation that takes one parameter, type in the value `Contoso` and click **Invoke**.</span></span>  
  
11. <span data-ttu-id="7eacf-130">发出的跟踪记录将写入一个 SQL 数据库中。</span><span class="sxs-lookup"><span data-stu-id="7eacf-130">The emitted tracking records are written to a SQL database.</span></span> <span data-ttu-id="7eacf-131">若要查看跟踪记录，请在 SQL Management Studio 中打开 TrackingSample 数据库，然后导航到表。</span><span class="sxs-lookup"><span data-stu-id="7eacf-131">To view the tracking records, open the TrackingSample database in SQL Management Studio and navigate to the tables.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7eacf-132"> SQL Server Management Studio，请参阅[SQL Server Management Studio 简介](http://go.microsoft.com/fwlink/?LinkId=165645)。</span><span class="sxs-lookup"><span data-stu-id="7eacf-132"> SQL Server Management Studio, see [Introducing SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645).</span></span> <span data-ttu-id="7eacf-133">可以下载 SQL Server 2008 Management Studio Express[此处](http://go.microsoft.com/fwlink/?LinkId=180520)。</span><span class="sxs-lookup"><span data-stu-id="7eacf-133">SQL Server 2008 Management Studio Express can be downloaded [here](http://go.microsoft.com/fwlink/?LinkId=180520).</span></span> <span data-ttu-id="7eacf-134">对表运行一个选择查询，将显示存储在相关表中的跟踪记录内的数据。</span><span class="sxs-lookup"><span data-stu-id="7eacf-134">Running a select query on the tables displays the data within the tracking records stored in the respective tables.</span></span>  
  
#### <a name="to-uninstall-the-sample"></a><span data-ttu-id="7eacf-135">卸载此示例</span><span class="sxs-lookup"><span data-stu-id="7eacf-135">To uninstall the sample</span></span>  
  
1.  <span data-ttu-id="7eacf-136">在示例目录 (\WF\Basic\Tracking\SqlTracking) 中运行 Trackingcleanup.cmd 脚本。</span><span class="sxs-lookup"><span data-stu-id="7eacf-136">Run theTrackingcleanup.cmd script in the sample directory (\WF\Basic\Tracking\SqlTracking).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7eacf-137">Trackingcleanup.cmd 将尝试删除本地计算机 SQL Express 中的数据库。</span><span class="sxs-lookup"><span data-stu-id="7eacf-137">The Trackingcleanup.cmd attempts to delete the database in your local computer SQL Express.</span></span> <span data-ttu-id="7eacf-138">如果您使用的是其他 SQL Server 实例，请编辑 Trackingcleanup.cmd。</span><span class="sxs-lookup"><span data-stu-id="7eacf-138">If you are using another SQL server instance, edit Trackingcleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7eacf-139">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="7eacf-139">The samples may already be installed on your computer.</span></span> <span data-ttu-id="7eacf-140">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="7eacf-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7eacf-141">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="7eacf-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7eacf-142">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="7eacf-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## <a name="see-also"></a><span data-ttu-id="7eacf-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="7eacf-143">See Also</span></span>  
 [<span data-ttu-id="7eacf-144">AppFabric 监视示例</span><span class="sxs-lookup"><span data-stu-id="7eacf-144">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
