---
title: 内置配置
ms.date: 03/30/2017
ms.assetid: 34e85c9b-088d-4347-816c-0f77cb73ef2f
ms.openlocfilehash: e76c019d9fc1b416e6fa8175a70b5fd01d9ff53e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43867837"
---
# <a name="built-in-configuration"></a><span data-ttu-id="0cbb9-102">内置配置</span><span class="sxs-lookup"><span data-stu-id="0cbb9-102">Built-in Configuration</span></span>
<span data-ttu-id="0cbb9-103">此示例演示了 SQL 工作流实例存储的使用和配置。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-103">This sample demonstrates the use and configuration of the SQL workflow instance store.</span></span> <span data-ttu-id="0cbb9-104">SQL 工作流实例存储是基于 SQL 的实例存储实现。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-104">The SQL workflow instance store is a SQL-based implementation of an instance store.</span></span> <span data-ttu-id="0cbb9-105">它允许实例将状态保存到 SQL Server 或 SQL Server Express 数据库中以及从中加载状态。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-105">It allows an instance to save and load its state to and from a SQL Server or SQL Server Express database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0cbb9-106">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0cbb9-107">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="0cbb9-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0cbb9-108">如果此目录不存在，请转到 （下载页） 以下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-108">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0cbb9-109">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="0cbb9-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\BuiltInConfiguration`  
  
## <a name="sample-details"></a><span data-ttu-id="0cbb9-110">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="0cbb9-110">Sample Details</span></span>  
 <span data-ttu-id="0cbb9-111">此示例由一个实现计数服务的工作流构成。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-111">This sample consists of a workflow that implements a counting service.</span></span> <span data-ttu-id="0cbb9-112">在调用该服务的启动方法之后，该服务将从 0 计数到 59。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-112">Once the service's start method is invoked, the service counts from 0 to 59.</span></span> <span data-ttu-id="0cbb9-113">计数器将每 2 秒递增一次。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-113">The counter is incremented once every 2 seconds.</span></span> <span data-ttu-id="0cbb9-114">在每次计数之后，工作流将持久化。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-114">After each count, the workflow persists.</span></span>  
  
 <span data-ttu-id="0cbb9-115">计数工作流是通过工作流服务主机自承载的。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-115">The counting workflow is self-hosted by a workflow service host.</span></span> <span data-ttu-id="0cbb9-116">程序的 `Main` 方法创建一个可承载计数工作流的工作流服务主机的实例。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-116">The program's `Main` method creates an instance of the workflow service host that hosts the counting workflow.</span></span> <span data-ttu-id="0cbb9-117">它定义计数工作流可以到达的终结点。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-117">It defines the endpoints under which the counting workflow can be reached.</span></span> <span data-ttu-id="0cbb9-118">之后，它定义一个 SQL 工作流实例存储行为，用于配置 SQL 工作流实例存储。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-118">After that, it defines a SQL workflow instance store behavior, which is used to configure the SQL workflow instance store.</span></span> <span data-ttu-id="0cbb9-119">接下来，程序创建一个客户端，调用计数工作流的启动方法。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-119">Next, the program creates a client that calls the start method of the counting workflow.</span></span>  
  
 <span data-ttu-id="0cbb9-120">在程序启动之后，计数器自动开始计数。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-120">Once the program is started, the counter automatically starts counting.</span></span> <span data-ttu-id="0cbb9-121">请注意，加载该实例并配置 SQL 工作流实例存储可能需要花费几秒钟的时间。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-121">Note that it might take a few seconds to load the instance and configure the SQL workflow instance store.</span></span> <span data-ttu-id="0cbb9-122">有关工作流实例存储的详细信息，请参阅[SQL 工作流实例存储](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-122">For more information about the workflow instance store, see [SQL Workflow Instance Store](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span></span>  
  
 <span data-ttu-id="0cbb9-123">此示例由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="0cbb9-123">The sample consists of two parts:</span></span>  
  
1.  <span data-ttu-id="0cbb9-124">InstanceStore1 演示如何使用 C# 代码配置 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>（请参见 Program.cs）。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-124">InstanceStore1 shows how <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> is configured using C# code (see Program.cs).</span></span>  
  
2.  <span data-ttu-id="0cbb9-125">InstanceStore2 演示如何使用 XML 代码配置 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>（请参见 App.config）。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-125">InstanceStore2 shows how <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> is configured using XML (see App.config).</span></span>  
  
 <span data-ttu-id="0cbb9-126">以下设置可用于配置 SQL 工作流实例存储行为：</span><span class="sxs-lookup"><span data-stu-id="0cbb9-126">The following settings are available to configure the SQL Workflow Instance Store behavior:</span></span>  
  
-   <span data-ttu-id="0cbb9-127">设置 `HostLockRenewalPeriod`。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-127">Set the `HostLockRenewalPeriod`.</span></span> <span data-ttu-id="0cbb9-128">此时间定义主机续订它运行的实例的所有权锁的间隔。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-128">This time defines the interval with which the host renews the ownership lock of the instances it runs.</span></span> <span data-ttu-id="0cbb9-129">锁信息存储在实例存储中。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-129">The lock information is stored in the Instance Store.</span></span> <span data-ttu-id="0cbb9-130">如果在两个 `HostLockRenewalPeriod` 中定义的间隔内没有续订所有权，则认为已放弃该实例。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-130">If the ownership is not renewed for two of the intervals defined in `HostLockRenewalPeriod`, the instance is considered abandoned.</span></span> <span data-ttu-id="0cbb9-131">如果另一个 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 正在运行同一个工作流，并连接到同一个实例存储（在同一台计算机上或另一台计算机上），则它将恢复该实例。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-131">If another <xref:System.ServiceModel.Activities.WorkflowServiceHost> is running the same workflow and connected to the same instance store (either on the same computer or a different computer), it recovers that instance.</span></span> <span data-ttu-id="0cbb9-132">（实例恢复不属于此示例的范围。）</span><span class="sxs-lookup"><span data-stu-id="0cbb9-132">(Instance Recovery is out of scope for this sample.)</span></span>  
  
-   <span data-ttu-id="0cbb9-133">设置 `RunnableInstancesDetectionPeriod`。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-133">Set the `RunnableInstancesDetectionPeriod`.</span></span> <span data-ttu-id="0cbb9-134">此期限定义主机轮询已经可以运行的实例的间隔。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-134">This period defines the interval in which the host polls for instances that have become runnable.</span></span> <span data-ttu-id="0cbb9-135">如果发生以下任何事件，则实例可能会变成可运行的：</span><span class="sxs-lookup"><span data-stu-id="0cbb9-135">Instances may become runnable if any of the following events occur:</span></span>  
  
    -   <span data-ttu-id="0cbb9-136">持久计时器 (<xref:System.Activities.Statements.Delay>) 过期。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-136">A Durable Timer (<xref:System.Activities.Statements.Delay>) expires.</span></span>  
  
    -   <span data-ttu-id="0cbb9-137">另一个主机错过其 `HostLockRenewal` 信号（例如，由于计算机崩溃）并恢复实例。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-137">Another host misses its `HostLockRenewal` heartbeat (for example, due to a computer crash) and the instance is recovered.</span></span>  
  
-   <span data-ttu-id="0cbb9-138">设置 `InstanceCompletionAction`。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-138">Set the `InstanceCompletionAction`.</span></span> <span data-ttu-id="0cbb9-139">此属性如果设置为 `DeleteNothing`，则在实例存储中保持完整的实例，如果设置为 `DeleteAll`，则在完成时从存储中删除所有实例。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-139">This property, if set to `DeleteNothing`, keeps completed instances in the Instance Store; if set to `DeleteAll`, instances are deleted from the store upon completion.</span></span> <span data-ttu-id="0cbb9-140">请注意</span><span class="sxs-lookup"><span data-stu-id="0cbb9-140">Note that</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0cbb9-141">在计数完成之前通过按 Enter 终止主机并不会完成工作流实例。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-141">Terminating the host by pressing ENTER before the counting has completed does not complete the workflow instance.</span></span>  
  
-   <span data-ttu-id="0cbb9-142">设置 `InstanceLockedExceptionAction`。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-142">Set the `InstanceLockedExceptionAction`.</span></span> <span data-ttu-id="0cbb9-143">此设置定义主机在需要加载另一个主机锁定的实例时应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-143">This setting defines what a host should do if it wants to load an instance that is locked by another host.</span></span> <span data-ttu-id="0cbb9-144">存在下列选项：</span><span class="sxs-lookup"><span data-stu-id="0cbb9-144">The following options exist:</span></span>  
  
    -   <span data-ttu-id="0cbb9-145">如果设置为 `NoRetry`：不再次尝试加载，并将 `InstanceLockedException` 返回到主机。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-145">If set to `NoRetry`: Do not retry the load and return an `InstanceLockedException` to the host.</span></span>  
  
    -   <span data-ttu-id="0cbb9-146">如果设置为 `BasicRetry`：一直重试加载该实例。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-146">If set to `BasicRetry`: Keep retrying to load the instance.</span></span> <span data-ttu-id="0cbb9-147">按照一种简单的线性算法计划这些重试（例如，每 5 秒重试一次）。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-147">The retries are scheduled according to a simple linear algorithm (for example, retry every 5 seconds).</span></span>  
  
    -   <span data-ttu-id="0cbb9-148">如果设置为 `AggressiveRetry`：一直重试加载该实例。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-148">If set to `AggressiveRetry`: Keep retrying to load the instance.</span></span> <span data-ttu-id="0cbb9-149">按照一种主动的指数补偿算法计划这些重试。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-149">The retries are scheduled according to an aggressive exponential back-off algorithm.</span></span>  
  
-   <span data-ttu-id="0cbb9-150">设置编码选项。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-150">Set the Encoding option.</span></span> <span data-ttu-id="0cbb9-151">此设置定义实例状态在 SQL 工作流实例存储中的存储方式。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-151">This setting defines how the instance state is stored in the SQL Workflow Instance Store.</span></span> <span data-ttu-id="0cbb9-152">存在下列选项：</span><span class="sxs-lookup"><span data-stu-id="0cbb9-152">The following options exist:</span></span>  
  
    -   <span data-ttu-id="0cbb9-153">使用 GZip 压缩算法对实例状态进行压缩。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-153">The instance state is compressed using the GZip compression algorithm.</span></span>  
  
    -   <span data-ttu-id="0cbb9-154">不对实例状态进行压缩。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-154">The instance state is not compressed.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="0cbb9-155">使用此示例</span><span class="sxs-lookup"><span data-stu-id="0cbb9-155">To use this sample</span></span>  
  
1.  <span data-ttu-id="0cbb9-156">以管理员身份打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示（如果具有相应的权限）。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-156">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt as an Administrator if permissions are available.</span></span>  
  
2.  <span data-ttu-id="0cbb9-157">导航到示例目录 (\WF\Basic\Persistence\BuiltInConfiguration\CS)，然后运行 CreateInstanceStore.cmd。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-157">Navigate to the sample directory (\WF\Basic\Persistence\BuiltInConfiguration\CS) and run CreateInstanceStore.cmd.</span></span>  
  
3.  <span data-ttu-id="0cbb9-158">如果管理员权限不可用，则创建 SQL Server 登录。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-158">If Administrator privileges are not available, Create SQL Server login.</span></span> <span data-ttu-id="0cbb9-159">转到`Security`，**登录名**。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-159">Go to `Security`, **Logins**.</span></span> <span data-ttu-id="0cbb9-160">右键单击**登录名**并创建新的登录名。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-160">Right-click **Logins** and create a new login.</span></span>  
  
4.  <span data-ttu-id="0cbb9-161">向 SQL 角色添加您的 ACL 用户。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-161">Add your ACL user to SQL role.</span></span> <span data-ttu-id="0cbb9-162">打开**数据库**， **InstanceStore**，**安全**。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-162">Open **Databases**, **InstanceStore**, **Security**.</span></span> <span data-ttu-id="0cbb9-163">右键单击**用户**，然后选择**新用户**。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-163">Right-click **Users** and select **New users**.</span></span> <span data-ttu-id="0cbb9-164">设置**登录名**到上一步中创建的用户。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-164">Set the **Login name** to the user created in the previous step.</span></span> <span data-ttu-id="0cbb9-165">将用户添加到数据库角色成员身份**System.Activities.DurableInstancing.InstanceStoreUsers** （和其他人）。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-165">Add the user to the Database role membership **System.Activities.DurableInstancing.InstanceStoreUsers** (and others).</span></span> <span data-ttu-id="0cbb9-166">请注意，该用户可能已经存在（例如，用户 dbo）。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-166">Note that the user might exist already (for example, user dbo).</span></span>  
  
5.  <span data-ttu-id="0cbb9-167">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 InstanceStore.sln 文件，按 CTRL+SHIFT+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-167">Open the InstanceStore.sln file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="0cbb9-168">在中[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]，导航到示例的相应的 bin\debug 目录 (\WF\Basic\Persistence\BuiltInConfiguration\cs\InstanceStore(1 or 2)\bin\debug) 中，右击 InstanceStore.exe 并选择**以管理员身份运行**.</span><span class="sxs-lookup"><span data-stu-id="0cbb9-168">In [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], navigate to the sample’s appropriate bin\debug directory (\WF\Basic\Persistence\BuiltInConfiguration\cs\InstanceStore(1 or 2)\bin\debug), right click InstanceStore.exe and select **Run as administrator**.</span></span> <span data-ttu-id="0cbb9-169">必须使用管理特权来运行此示例，因为它要打开一个通道侦听器。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-169">This sample must be run with administrative privileges because it opens a channel listener.</span></span>  
  
7.  <span data-ttu-id="0cbb9-170">如果已在数据库（而不是 SQL Server Express 的本地安装）中创建实例存储，则必须更新示例中的数据库连接字符串（InstanceStore1 项目的 Program.cs 中的 `const string ConnectionString` 和 InstanceStore2 项目的 App.config 中的 `connectionString` 特性），并重新编译示例。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-170">If you created the instance store in a database other than a local installation of SQL Server Express you must update the database connection string (`const string ConnectionString` in Program.cs of the InstanceStore1 project, and the `connectionString` attribute in App.config of the InstanceStore2 project) in the sample and recompile the sample.</span></span>  
  
#### <a name="to-verify-the-sample-is-running-correctly"></a><span data-ttu-id="0cbb9-171">验证示例是否正常运行</span><span class="sxs-lookup"><span data-stu-id="0cbb9-171">To verify the sample is running correctly</span></span>  
  
1.  <span data-ttu-id="0cbb9-172">在此示例运行的过程中，启动 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-172">While the sample is running, start SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="0cbb9-173">在中**对象资源管理器**，选择**数据库**， **InstanceStore**，**表**，，然后**System.Activities.DurableInstancing.InstanceTable**。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-173">In the **Object Explorer**, select **Databases**, **InstanceStore**, **Tables**, and then **System.Activities.DurableInstancing.InstanceTable**.</span></span>  
  
3.  <span data-ttu-id="0cbb9-174">右键单击**InstanceTable** ，然后选择**选择前 1000年行**。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-174">Right click **InstanceTable** and select **Select Top 1000 Rows**.</span></span>  
  
4.  <span data-ttu-id="0cbb9-175">观察是否有新项，而且**锁定到期日**每隔 5 秒更改一次 (单击任务栏**Execute**按钮可刷新查询)。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-175">Observe that there is a new entry and that the **Lock Expiration** changes every 5 seconds, (click the taskbar’s **Execute** button to refresh the query).</span></span> <span data-ttu-id="0cbb9-176">这是设置的结果**宿主锁定续订期**为 5。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-176">This is a consequence of setting the **Host Lock Renewal Period** to 5.</span></span>  
  
5.  <span data-ttu-id="0cbb9-177">计数完成后，观察实例表中的项是否已移除。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-177">Observe after the counting completes, that the entry in the instance table is removed.</span></span> <span data-ttu-id="0cbb9-178">这是设置的结果**实例完成操作**到**DeleteAll**。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-178">This is a consequence of setting **Instance Completion Action** to **DeleteAll**.</span></span>  
  
6.  <span data-ttu-id="0cbb9-179">按 ENTER 以终止工作流主机应用程序，并观察是否**LockOwnersTable**被删除。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-179">Press ENTER to terminate the workflow host application and observe that the **LockOwnersTable** is deleted.</span></span>  
  
#### <a name="to-uninstall-the-sample"></a><span data-ttu-id="0cbb9-180">卸载此示例</span><span class="sxs-lookup"><span data-stu-id="0cbb9-180">To uninstall the sample</span></span>  
  
1.  <span data-ttu-id="0cbb9-181">在示例目录 (\WF\Basic\Persistence\BuiltInConfiguration) 中运行 RemoveInstanceStore.cmd。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-181">Run RemoveInstanceStore.cmd in the sample directory (\WF\Basic\Persistence\BuiltInConfiguration).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0cbb9-182">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-182">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0cbb9-183">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="0cbb9-183">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0cbb9-184">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="0cbb9-184">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0cbb9-185">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="0cbb9-185">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\BuiltInConfiguration`  
  
## <a name="see-also"></a><span data-ttu-id="0cbb9-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="0cbb9-186">See Also</span></span>  
 [<span data-ttu-id="0cbb9-187">AppFabric 承载和持久性示例</span><span class="sxs-lookup"><span data-stu-id="0cbb9-187">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
