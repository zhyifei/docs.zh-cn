---
title: SQL 跟踪
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: 72bfcaac2903b3e7fa5679422ad4feaa79e93211
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243175"
---
# <a name="sql-tracking"></a><span data-ttu-id="a3047-102">SQL 跟踪</span><span class="sxs-lookup"><span data-stu-id="a3047-102">SQL tracking</span></span>

<span data-ttu-id="a3047-103">此示例演示如何编写将跟踪记录写入 SQL 数据库的自定义 SQL 跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="a3047-103">This sample demonstrates how to write a custom SQL tracking participant that writes tracking records to a SQL database.</span></span> <span data-ttu-id="a3047-104">Windows 工作流基础 （WF） 提供工作流跟踪，以深入了解工作流实例的执行。</span><span class="sxs-lookup"><span data-stu-id="a3047-104">Windows Workflow Foundation (WF) provides workflow tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="a3047-105">跟踪运行时在工作流执行过程中会发出工作流跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="a3047-105">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> <span data-ttu-id="a3047-106">有关工作流跟踪的详细信息，请参阅[工作流跟踪和跟踪](../workflow-tracking-and-tracing.md)。</span><span class="sxs-lookup"><span data-stu-id="a3047-106">For more information about workflow tracking, see [Workflow Tracking and Tracing](../workflow-tracking-and-tracing.md).</span></span>

## <a name="use-the-sample"></a><span data-ttu-id="a3047-107">使用示例</span><span class="sxs-lookup"><span data-stu-id="a3047-107">Use the sample</span></span>

1. <span data-ttu-id="a3047-108">确认您已安装 SQL Server 2008、 SQL Server 2008 Express 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="a3047-108">Verify you have SQL Server 2008, SQL Server 2008 Express or newer installed.</span></span> <span data-ttu-id="a3047-109">与示例打包在一起的脚本假定在您的本地计算机上使用 SQL Express 实例。</span><span class="sxs-lookup"><span data-stu-id="a3047-109">The scripts packaged with the sample assume the use of a SQL Express instance on your local computer.</span></span> <span data-ttu-id="a3047-110">如果您安装了不同的实例，请在运行此示例之前修改与数据库相关的脚本。</span><span class="sxs-lookup"><span data-stu-id="a3047-110">If you have a different instance please modify the database-related scripts before running the sample.</span></span>

2. <span data-ttu-id="a3047-111">通过在脚本目录 (\WF\Basic\Tracking\SqlTracking\CS\Scripts) 中运行 Trackingsetup.cmd 来创建 SQL Server 跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="a3047-111">Create the SQL Server tracking database by running Trackingsetup.cmd in the scripts directory (\WF\Basic\Tracking\SqlTracking\CS\Scripts).</span></span> <span data-ttu-id="a3047-112">这会创建一个名为 TrackingSample 的数据库。</span><span class="sxs-lookup"><span data-stu-id="a3047-112">This creates a database called TrackingSample.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a3047-113">脚本将在 SQL Express 的默认实例上创建该数据库。</span><span class="sxs-lookup"><span data-stu-id="a3047-113">The script creates the database on the default instance of SQL Express.</span></span> <span data-ttu-id="a3047-114">如果您想在不同的数据库实例上安装该数据库，请编辑 Trackingsetup.cmd 脚本。</span><span class="sxs-lookup"><span data-stu-id="a3047-114">If you want to install it on a different database instance, edit the Trackingsetup.cmd script.</span></span>

3. <span data-ttu-id="a3047-115">在视觉工作室 2010 中打开 SqlTrackingSample.sln。</span><span class="sxs-lookup"><span data-stu-id="a3047-115">Open SqlTrackingSample.sln in Visual Studio 2010.</span></span>

4. <span data-ttu-id="a3047-116">按**Ctrl**+**移位**+**B**可构建解决方案。</span><span class="sxs-lookup"><span data-stu-id="a3047-116">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

5. <span data-ttu-id="a3047-117">按 **F5** 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3047-117">Press **F5** to run the application.</span></span>

   <span data-ttu-id="a3047-118">浏览器窗口打开和显示侦听应用程序的目录。</span><span class="sxs-lookup"><span data-stu-id="a3047-118">The browser window opens and shows the directory listing for the application.</span></span>

6. <span data-ttu-id="a3047-119">在浏览器中，单击 StockPriceService.xamlx。</span><span class="sxs-lookup"><span data-stu-id="a3047-119">In the browser, click StockPriceService.xamlx.</span></span>

7. <span data-ttu-id="a3047-120">浏览器显示 StockPriceService 页，其中包含本地服务 WSDL 地址。</span><span class="sxs-lookup"><span data-stu-id="a3047-120">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="a3047-121">复制此地址。</span><span class="sxs-lookup"><span data-stu-id="a3047-121">Copy this address.</span></span>

   <span data-ttu-id="a3047-122">本地服务 WSDL 地址的一个`http://localhost:65193/StockPriceService.xamlx?wsdl`示例是 。</span><span class="sxs-lookup"><span data-stu-id="a3047-122">An example of the local service WSDL address is `http://localhost:65193/StockPriceService.xamlx?wsdl`.</span></span>

8. <span data-ttu-id="a3047-123">使用文件资源管理器运行 WCF 测试客户端 （WcfTestClient.exe）。</span><span class="sxs-lookup"><span data-stu-id="a3047-123">Using File Explorer, run the WCF test client (WcfTestClient.exe).</span></span> <span data-ttu-id="a3047-124">它位于*微软视觉工作室 10.0_Common7_IDE 目录中*。</span><span class="sxs-lookup"><span data-stu-id="a3047-124">It's located in the *Microsoft Visual Studio 10.0\Common7\IDE directory*.</span></span>

9. <span data-ttu-id="a3047-125">在 WCF 测试客户端中，单击 **"文件**"菜单并选择"**添加服务**"。</span><span class="sxs-lookup"><span data-stu-id="a3047-125">In the WCF test client, click the **File** menu and select **Add Service**.</span></span> <span data-ttu-id="a3047-126">将本地服务地址粘贴到文本框中。</span><span class="sxs-lookup"><span data-stu-id="a3047-126">Paste the local service address in the textbox.</span></span> <span data-ttu-id="a3047-127">单击 **“确定”**，关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="a3047-127">Click **OK** to close the dialog.</span></span>

10. <span data-ttu-id="a3047-128">在 WCF 测试客户端中，双击**GetStockPrice**。</span><span class="sxs-lookup"><span data-stu-id="a3047-128">In the WCF test client, double click **GetStockPrice**.</span></span> <span data-ttu-id="a3047-129">这将打开需要`GetStockPrice`一个参数的操作，键入值`Contoso`并单击 **"调用**"。</span><span class="sxs-lookup"><span data-stu-id="a3047-129">This opens the `GetStockPrice` operation that takes one parameter, type in the value `Contoso` and click **Invoke**.</span></span>

11. <span data-ttu-id="a3047-130">发出的跟踪记录将写入一个 SQL 数据库中。</span><span class="sxs-lookup"><span data-stu-id="a3047-130">The emitted tracking records are written to a SQL database.</span></span> <span data-ttu-id="a3047-131">若要查看跟踪记录，请在 SQL Management Studio 中打开 TrackingSample 数据库，然后导航到表。</span><span class="sxs-lookup"><span data-stu-id="a3047-131">To view the tracking records, open the TrackingSample database in SQL Management Studio and navigate to the tables.</span></span> <span data-ttu-id="a3047-132">对表运行一个选择查询，将显示存储在相关表中的跟踪记录内的数据。</span><span class="sxs-lookup"><span data-stu-id="a3047-132">Running a select query on the tables displays the data within the tracking records stored in the respective tables.</span></span>

   <span data-ttu-id="a3047-133">有关 SQL 服务器管理工作室的详细信息，请参阅[介绍 SQL 服务器管理工作室](/sql/ssms/sql-server-management-studio-ssms)。</span><span class="sxs-lookup"><span data-stu-id="a3047-133">For more information about SQL Server Management Studio, see [Introducing SQL Server Management Studio](/sql/ssms/sql-server-management-studio-ssms).</span></span> <span data-ttu-id="a3047-134">[在此处](https://aka.ms/ssmsfullsetup)下载 SQL 服务器管理工作室。</span><span class="sxs-lookup"><span data-stu-id="a3047-134">Download SQL Server Management Studio [here](https://aka.ms/ssmsfullsetup).</span></span>

## <a name="uninstall-the-sample"></a><span data-ttu-id="a3047-135">卸载示例</span><span class="sxs-lookup"><span data-stu-id="a3047-135">Uninstall the sample</span></span>

1. <span data-ttu-id="a3047-136">在示例目录中运行跟踪清理.cmd 脚本 *（\WF_基本\跟踪\Sql 跟踪*）。</span><span class="sxs-lookup"><span data-stu-id="a3047-136">Run theTrackingcleanup.cmd script in the sample directory (*\WF\Basic\Tracking\SqlTracking*).</span></span>

    > [!NOTE]
    > <span data-ttu-id="a3047-137">Trackingcleanup.cmd 将尝试删除本地计算机 SQL Express 中的数据库。</span><span class="sxs-lookup"><span data-stu-id="a3047-137">The Trackingcleanup.cmd attempts to delete the database in your local computer SQL Express.</span></span> <span data-ttu-id="a3047-138">如果您使用的是其他 SQL Server 实例，请编辑 Trackingcleanup.cmd。</span><span class="sxs-lookup"><span data-stu-id="a3047-138">If you are using another SQL server instance, edit Trackingcleanup.cmd.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3047-139">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="a3047-139">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a3047-140">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="a3047-140">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="a3047-141">如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。</span><span class="sxs-lookup"><span data-stu-id="a3047-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a3047-142">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="a3047-142">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`

## <a name="see-also"></a><span data-ttu-id="a3047-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3047-143">See also</span></span>

- <span data-ttu-id="a3047-144">[AppFabric 监视示例](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="a3047-144">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
