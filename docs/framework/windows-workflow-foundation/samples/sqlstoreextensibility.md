---
title: SQLStoreExtensibility
ms.date: 03/30/2017
ms.assetid: 5da1b5a3-f144-41ba-b9c4-02818b28b15d
ms.openlocfilehash: f49d05244cf9f65a8e06f39c7e40391aaebd9f77
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47090157"
---
# <a name="sqlstoreextensibility"></a><span data-ttu-id="2c91c-102">SQLStoreExtensibility</span><span class="sxs-lookup"><span data-stu-id="2c91c-102">SQLStoreExtensibility</span></span>
<span data-ttu-id="2c91c-103">此示例演示了 SQL 工作流实例存储中的已提升属性的使用和配置。</span><span class="sxs-lookup"><span data-stu-id="2c91c-103">This sample demonstrates the use and configuration of promoted properties in the SQL workflow instance store.</span></span> <span data-ttu-id="2c91c-104">SQL 工作流实例存储是基于 SQL 的实例存储实现。</span><span class="sxs-lookup"><span data-stu-id="2c91c-104">The SQL workflow instance store is a SQL-based implementation of an instance store.</span></span> <span data-ttu-id="2c91c-105">利用此存储，实例可保存其状态，并将其状态加载到 SQL Server 或 SQL Server Express 数据库中以及从 SQL Server 或 SQL Server Express 数据库中加载其状态。</span><span class="sxs-lookup"><span data-stu-id="2c91c-105">It allows an instance to save its state and load its state to and from a SQL Server or SQL Server Express database.</span></span> <span data-ttu-id="2c91c-106">用户可使用存储扩展性功能来定义存储在示例存储中的属性。</span><span class="sxs-lookup"><span data-stu-id="2c91c-106">The store extensibility feature allows the user to define properties that are stored in the instance store.</span></span> <span data-ttu-id="2c91c-107">这些属性显示在已提升属性视图中，用户可利用该视图查询这些属性。</span><span class="sxs-lookup"><span data-stu-id="2c91c-107">These properties are displayed in a promoted properties view that allows the user to query for them.</span></span>  
  
 <span data-ttu-id="2c91c-108">此示例由一个实现计数服务的工作流构成。</span><span class="sxs-lookup"><span data-stu-id="2c91c-108">This sample consists of a workflow that implements a counting service.</span></span> <span data-ttu-id="2c91c-109">在调用该服务的启动方法之后，该服务将从 0 计数到 29。</span><span class="sxs-lookup"><span data-stu-id="2c91c-109">Once the service's start method is invoked, the service counts from 0 to 29.</span></span> <span data-ttu-id="2c91c-110">计数器将每 2 秒递增一次。</span><span class="sxs-lookup"><span data-stu-id="2c91c-110">The counter is incremented once every 2 seconds.</span></span> <span data-ttu-id="2c91c-111">在每次计数之后，工作流将持久化。</span><span class="sxs-lookup"><span data-stu-id="2c91c-111">After each count, the workflow persists.</span></span> <span data-ttu-id="2c91c-112">当前的计数器值将作为一个已提升属性存储在实例存储中。</span><span class="sxs-lookup"><span data-stu-id="2c91c-112">The current counter value is stored in the instance store as a promoted property.</span></span>  
  
 <span data-ttu-id="2c91c-113">计数工作流由工作流服务主机进行自承载。</span><span class="sxs-lookup"><span data-stu-id="2c91c-113">The Counting Workflow is self-hosted by a Workflow Service Host.</span></span> <span data-ttu-id="2c91c-114">该程序的 `Main` 方法将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2c91c-114">The program's `Main` method performs the following actions:</span></span>  
  
-   <span data-ttu-id="2c91c-115">创建一个工作流服务主机实例，它承载计数工作流并定义计数工作流可到达的终结点。</span><span class="sxs-lookup"><span data-stu-id="2c91c-115">Creates an instance of the Workflow Service Host that hosts the Counting Workflow and defines the endpoints under which the Counting Workflow can be reached.</span></span>  
  
-   <span data-ttu-id="2c91c-116">定义一个 SQL 工作流实例存储行为，该行为用于配置 SQL 工作流实例存储。</span><span class="sxs-lookup"><span data-stu-id="2c91c-116">Defines a SQL workflow instance store behavior, which is used to configure the SQL workflow instance store.</span></span> <span data-ttu-id="2c91c-117">指示存储将 `CountStatus` 视为已提升属性。</span><span class="sxs-lookup"><span data-stu-id="2c91c-117">The store is instructed to treat `CountStatus` as a promoted property.</span></span>  
  
-   <span data-ttu-id="2c91c-118">创建一个调用计数工作流的启动方法的客户端。</span><span class="sxs-lookup"><span data-stu-id="2c91c-118">Creates a client that calls the start method of the counting workflow.</span></span>  
  
 <span data-ttu-id="2c91c-119">在程序启动之后，计数器自动开始计数。</span><span class="sxs-lookup"><span data-stu-id="2c91c-119">Once the program is started, the counter automatically starts counting.</span></span> <span data-ttu-id="2c91c-120">请注意，加载该实例并配置 SQL 工作流实例存储可能需要花费几秒钟的时间。</span><span class="sxs-lookup"><span data-stu-id="2c91c-120">Note that it might take a few seconds to load the instance and configure the SQL workflow instance store.</span></span>  
  
 <span data-ttu-id="2c91c-121">若要将计数器值提升为自定义属性，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="2c91c-121">To promote the counter value as a custom property, the following steps must be taken:</span></span>  
  
1.  <span data-ttu-id="2c91c-122">类 `CounterStatus` 定义类型 <xref:System.Activities.Persistence.PersistenceParticipant> 的实例扩展，活动使用该实例扩展来提供状态变量。</span><span class="sxs-lookup"><span data-stu-id="2c91c-122">The class `CounterStatus` defines an instance extension of type <xref:System.Activities.Persistence.PersistenceParticipant>, which is used by activities to supply the state variables.</span></span> <span data-ttu-id="2c91c-123">将 `Count` 定义为只写值。</span><span class="sxs-lookup"><span data-stu-id="2c91c-123">`Count` is defined as a write-only value.</span></span> <span data-ttu-id="2c91c-124">当工作流实例到达某个持久性点时，该实例扩展会将 `Count` 属性保存到持久性数据集合中。</span><span class="sxs-lookup"><span data-stu-id="2c91c-124">When a workflow instance comes to a persistence point, the instance extension saves the `Count` property into the persistence data collection.</span></span>  
  
2.  <span data-ttu-id="2c91c-125">在创建实例存储时，将通过 `CountStatus` 方法定义一个新属性，即 `store.Promote()`。</span><span class="sxs-lookup"><span data-stu-id="2c91c-125">When creating the instance store, a new property, `CountStatus`, is defined through the `store.Promote()` method.</span></span>  
  
3.  <span data-ttu-id="2c91c-126">工作流的 `SaveCounter` 活动将当前计数器值分配给 `Count` 状态字段。</span><span class="sxs-lookup"><span data-stu-id="2c91c-126">The workflow's `SaveCounter` activity assigns the current counter value to the `Count` status field.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="2c91c-127">使用此示例</span><span class="sxs-lookup"><span data-stu-id="2c91c-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="2c91c-128">创建实例存储区数据库。</span><span class="sxs-lookup"><span data-stu-id="2c91c-128">Create the instance store database.</span></span>  
  
    1.  <span data-ttu-id="2c91c-129">打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="2c91c-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="2c91c-130">导航到示例目录 (\WF\Basic\Persistence\SqlStoreExtensibility\CS) 并在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符下运行 CreateInstanceStore.cmd。</span><span class="sxs-lookup"><span data-stu-id="2c91c-130">Navigate to the sample directory (\WF\Basic\Persistence\SqlStoreExtensibility\CS) and run CreateInstanceStore.cmd in the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
        > [!WARNING]
        >  <span data-ttu-id="2c91c-131">CreateInstanceStore.cmd 脚本尝试在 SQL Server 2008 Express 的默认实例上创建数据库。</span><span class="sxs-lookup"><span data-stu-id="2c91c-131">The CreateInstanceStore.cmd script attempts to create the database on the default instance of SQL Server 2008 Express.</span></span> <span data-ttu-id="2c91c-132">如果要在不同的实例上安装数据库，请修改脚本。</span><span class="sxs-lookup"><span data-stu-id="2c91c-132">If you want to install the database on a different instance, modify the script to do so.</span></span>  
  
2.  <span data-ttu-id="2c91c-133">打开 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 并加载 SqlStoreExtensibility.sln 解决方案，然后通过按 CTRL+SHIFT+B 生成它。</span><span class="sxs-lookup"><span data-stu-id="2c91c-133">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and load the SqlStoreExtensibility.sln solution and build it by pressing CTRL+SHIFT+B.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="2c91c-134">如果在 SQL Server 的非默认实例上安装了数据库，请在生成解决方案之前更新代码中的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="2c91c-134">If you installed the database on a non-default instance of SQL Server, update the connection string in the code prior to building the solution.</span></span>  
  
3.  <span data-ttu-id="2c91c-135">导航到项目的 bin 目录 (\WF\Basic\Persistence\SqlStoreExtensibility\bin\Debug) 中使用管理员特权运行该示例[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]中，右击 SqlStoreExtensibility.exe 并选择**以运行管理员**。</span><span class="sxs-lookup"><span data-stu-id="2c91c-135">Run the sample with administrator privileges by navigating to the project’s bin directory (\WF\Basic\Persistence\SqlStoreExtensibility\bin\Debug) in [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], right-clicking SqlStoreExtensibility.exe and selecting **Run as Administrator**.</span></span>  
  
### <a name="to-verify-the-sample-is-working-correctly"></a><span data-ttu-id="2c91c-136">验证此示例是否正常工作</span><span class="sxs-lookup"><span data-stu-id="2c91c-136">To verify the sample is working correctly</span></span>  
  
1.  <span data-ttu-id="2c91c-137">使用 SQL Server Management Studio 来选择查看实例表的内容**数据库**， **InstanceStore**，然后**System.ServiceModel.Activities.DurableInstancing.InstanceTable**在对象资源管理器，右键单击**System.ServiceModel.Activities.DurableInstancing.InstanceTable** ，然后选择**选择前 1000年行**。</span><span class="sxs-lookup"><span data-stu-id="2c91c-137">Use SQL Server Management Studio to view the contents of the instance table by selecting **Databases**, **InstanceStore**, and then **System.ServiceModel.Activities.DurableInstancing.InstanceTable** in the Object Explorer, right-click **System.ServiceModel.Activities.DurableInstancing.InstanceTable** and select **Select Top 1000 Rows**.</span></span> <span data-ttu-id="2c91c-138">有关 SQL Server Management Studio 的详细信息，请参阅[引入 SQL Server Management Studio](https://go.microsoft.com/fwlink/?LinkId=165645)</span><span class="sxs-lookup"><span data-stu-id="2c91c-138">For more information about SQL Server Management Studio, see [Introducing SQL Server Management Studio](https://go.microsoft.com/fwlink/?LinkId=165645)</span></span>  
  
2.  <span data-ttu-id="2c91c-139">观察列出的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="2c91c-139">Observe the workflow instances listed.</span></span>  
  
3.  <span data-ttu-id="2c91c-140">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符下，运行位于示例目录 (\WF\Basic\Persistence\SqlStoreExtensibility) 中的 QueryInstanceStore.cmd 脚本。</span><span class="sxs-lookup"><span data-stu-id="2c91c-140">In a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, run the QueryInstanceStore.cmd script located in the sample directory (\WF\Basic\Persistence\SqlStoreExtensibility).</span></span>  
  
4.  <span data-ttu-id="2c91c-141">观察下显示的计数器值**CountStatus**。</span><span class="sxs-lookup"><span data-stu-id="2c91c-141">Observe the counter value displayed under **CountStatus**.</span></span>  
  
5.  <span data-ttu-id="2c91c-142">运行脚本几次以查看**countstats**值的更改。</span><span class="sxs-lookup"><span data-stu-id="2c91c-142">Run the script a few times to see the **CountStats** value change.</span></span>  
  
6.  <span data-ttu-id="2c91c-143">按 Enter 以终止工作流应用程序。</span><span class="sxs-lookup"><span data-stu-id="2c91c-143">Press ENTER to terminate the workflow application.</span></span>  
  
### <a name="to-uninstall-the-sample"></a><span data-ttu-id="2c91c-144">卸载此示例</span><span class="sxs-lookup"><span data-stu-id="2c91c-144">To uninstall the sample</span></span>  
  
1.  <span data-ttu-id="2c91c-145">通过运行位于示例目录 (\WF\Basic\Persistence\SqlStoreExtensibility) 中的 RemoveInstanceStore.cmd 脚本来移除实例存储区数据库。</span><span class="sxs-lookup"><span data-stu-id="2c91c-145">Remove the instance store database by running the RemoveInstanceStore.cmd script located in the sample directory (\WF\Basic\Persistence\SqlStoreExtensibility).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2c91c-146">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="2c91c-146">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2c91c-147">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="2c91c-147">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2c91c-148">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="2c91c-148">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2c91c-149">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="2c91c-149">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\SQLStoreExtensibility`  
  
## <a name="see-also"></a><span data-ttu-id="2c91c-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c91c-150">See Also</span></span>  
 [<span data-ttu-id="2c91c-151">工作流暂留</span><span class="sxs-lookup"><span data-stu-id="2c91c-151">Workflow Persistence</span></span>](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)  
 [<span data-ttu-id="2c91c-152">工作流服务</span><span class="sxs-lookup"><span data-stu-id="2c91c-152">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="2c91c-153">AppFabric 承载和持久性示例</span><span class="sxs-lookup"><span data-stu-id="2c91c-153">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
