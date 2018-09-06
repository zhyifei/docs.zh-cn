---
title: 属性提升活动
ms.date: 03/30/2017
ms.assetid: 802196b7-1159-4c05-b41b-d3bfdfcc88d9
ms.openlocfilehash: 6e059a0d344e6c62833feaa890c459c141a49673
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43747049"
---
# <a name="property-promotion-activity"></a><span data-ttu-id="d7611-102">属性提升活动</span><span class="sxs-lookup"><span data-stu-id="d7611-102">Property Promotion Activity</span></span>
<span data-ttu-id="d7611-103">本示例提供了将 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 提升功能直接集成到工作流创作体验的端到端解决方案。</span><span class="sxs-lookup"><span data-stu-id="d7611-103">This sample provides an end-to-end solution that integrates the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Promotion feature directly into the workflow authoring experience.</span></span> <span data-ttu-id="d7611-104">提供了一组用于简化对提升功能的使用的配置元素、工作流活动和工作流扩展。</span><span class="sxs-lookup"><span data-stu-id="d7611-104">A collection of configuration elements, workflow activities, and workflow extensions that simplify the use of the Promotion feature are provided.</span></span> <span data-ttu-id="d7611-105">此外，该示例包含一个演示如何使用此集合的简单工作流。</span><span class="sxs-lookup"><span data-stu-id="d7611-105">Additionally, the sample contains a simple workflow that demonstrates how to use this collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7611-106">提供的示例仅供教学使用。</span><span class="sxs-lookup"><span data-stu-id="d7611-106">Samples are provided for educational purposes only.</span></span> <span data-ttu-id="d7611-107">这些示例不是针对生产环境设计的，也没有在生产环境中进行测试。</span><span class="sxs-lookup"><span data-stu-id="d7611-107">They are not intended for a production environment, and have not been tested in a production environment.</span></span> <span data-ttu-id="d7611-108">对于这些示例，Microsoft 不提供相关的技术支持。</span><span class="sxs-lookup"><span data-stu-id="d7611-108">Microsoft does not provide technical support for these samples.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d7611-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="d7611-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="d7611-110">已初始化的 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 数据库</span><span class="sxs-lookup"><span data-stu-id="d7611-110">An initialized <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> database</span></span>  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]  
  
## <a name="sample-projects"></a><span data-ttu-id="d7611-111">示例项目</span><span class="sxs-lookup"><span data-stu-id="d7611-111">Sample Projects</span></span>  
  
-   <span data-ttu-id="d7611-112">**PropertyPromotionActivity**项目包含与特定于升级的配置元素、 工作流活动和工作流扩展相关的文件。</span><span class="sxs-lookup"><span data-stu-id="d7611-112">The **PropertyPromotionActivity** project contains files pertaining to the promotion-specific configuration elements, workflow activities, and workflow extensions.</span></span>  
  
-   <span data-ttu-id="d7611-113">**CounterServiceApplication**项目包含一个使用的示例工作流**SqlWorkflowInstanceStorePromotion**项目。</span><span class="sxs-lookup"><span data-stu-id="d7611-113">The **CounterServiceApplication** project contains a sample workflow that uses the **SqlWorkflowInstanceStorePromotion** project.</span></span>  
  
-   <span data-ttu-id="d7611-114">一个必须对 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 数据库运行的 SQL 脚本 (PropertyPromotionActivitySQLSample.sql)。</span><span class="sxs-lookup"><span data-stu-id="d7611-114">A SQL script (PropertyPromotionActivitySQLSample.sql) that must be run against the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> database.</span></span>  
  
-   <span data-ttu-id="d7611-115">一个链接两个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 项目的解决方案文件 (`PropertyPromotionActivity.sln`)</span><span class="sxs-lookup"><span data-stu-id="d7611-115">A solution file that links the two [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] projects (`PropertyPromotionActivity.sln`)</span></span>  
  
## <a name="to-set-up-and-run-the-sample"></a><span data-ttu-id="d7611-116">设置和运行示例</span><span class="sxs-lookup"><span data-stu-id="d7611-116">To set up and run the sample</span></span>  
  
1.  <span data-ttu-id="d7611-117">初始化工作流持久性数据库。</span><span class="sxs-lookup"><span data-stu-id="d7611-117">Initialize a workflow persistence database.</span></span>  
  
    1.  <span data-ttu-id="d7611-118">导航到示例目录 (\WF\Basic\Persistence\PropertyPromotionActivity)，然后运行 CreateInstanceStore.cmd。</span><span class="sxs-lookup"><span data-stu-id="d7611-118">Navigate to the sample directory (\WF\Basic\Persistence\PropertyPromotionActivity) and run CreateInstanceStore.cmd.</span></span>  
  
    2.  <span data-ttu-id="d7611-119">如果管理员权限不可用，则创建 SQL Server 登录。</span><span class="sxs-lookup"><span data-stu-id="d7611-119">If Administrator privileges are not available, create a SQL Server login.</span></span> <span data-ttu-id="d7611-120">在 SQL Server Management Studio 中，转到**安全**，**登录名**。</span><span class="sxs-lookup"><span data-stu-id="d7611-120">In SQL Server Management Studio, go to **Security**, **Logins**.</span></span> <span data-ttu-id="d7611-121">右键单击**登录名**并创建新的登录名。</span><span class="sxs-lookup"><span data-stu-id="d7611-121">Right-click **Logins** and create a new login.</span></span> <span data-ttu-id="d7611-122">将 ACL 用户添加到 SQL 角色中，通过打开**数据库**， **InstanceStore**，**安全**。</span><span class="sxs-lookup"><span data-stu-id="d7611-122">Add your ACL user to the SQL role by opening **Databases**, **InstanceStore**, **Security**.</span></span> <span data-ttu-id="d7611-123">右键单击**用户**，然后选择**新用户**。</span><span class="sxs-lookup"><span data-stu-id="d7611-123">Right-click **Users** and select **New user**.</span></span> <span data-ttu-id="d7611-124">设置**登录名**到上面创建的用户。</span><span class="sxs-lookup"><span data-stu-id="d7611-124">Set the **Login name** to the user created above.</span></span> <span data-ttu-id="d7611-125">将该用户添加到数据库角色成员 System.Activities.DurableInstancing.InstanceStoreUsers（以及其他成员）。</span><span class="sxs-lookup"><span data-stu-id="d7611-125">Add the user to the Database role membership System.Activities.DurableInstancing.InstanceStoreUsers (and others).</span></span> <span data-ttu-id="d7611-126">请注意，该用户可能已经存在（例如，用户 dbo）。</span><span class="sxs-lookup"><span data-stu-id="d7611-126">Note that the user might exist already (for example, user dbo).</span></span>  
  
2.  <span data-ttu-id="d7611-127">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开解决方案文件 PropertyPromotionActivity.sln。</span><span class="sxs-lookup"><span data-stu-id="d7611-127">Open the PropertyPromotionActivity.sln solution file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="d7611-128">如果已在 SQL Server Express 本地安装之外的数据库中创建实例存储区，则必须更新数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="d7611-128">If you created the instance store in a database other than a local installation of SQL Server Express, then you must update the database connection string.</span></span> <span data-ttu-id="d7611-129">下的 App.config 文件**CounterServiceApplication**的值设置`connectionString`特性，可以在`sqlWorkflowInstanceStorePromotion`节点，使其指向已初始化的持久性数据库步骤 1 中。</span><span class="sxs-lookup"><span data-stu-id="d7611-129">Alter the App.config file under the **CounterServiceApplication** by setting the value of the `connectionString` attribute on the `sqlWorkflowInstanceStorePromotion` node so that it points to the persistence database that was initialized in step 1.</span></span>  
  
4.  <span data-ttu-id="d7611-130">生成和运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="d7611-130">Build and run the solution.</span></span> <span data-ttu-id="d7611-131">这将启动计数器 WF 服务并自动启动一个工作流实例。</span><span class="sxs-lookup"><span data-stu-id="d7611-131">This will start the Counter WF service and automatically start a workflow instance.</span></span>  
  
5.  <span data-ttu-id="d7611-132">快速选择持久性数据库中的 [dbo].[CounterService] 视图中的所有行（步骤 1 中通过运行 CreateInstanceStore.cmd 添加了此视图）。</span><span class="sxs-lookup"><span data-stu-id="d7611-132">Quickly select all the rows in the [dbo].[CounterService] view in your persistence database (this view was added by running CreateInstanceStore.cmd in step 1).</span></span> <span data-ttu-id="d7611-133">您将看到与下面的内容类似的结果集：</span><span class="sxs-lookup"><span data-stu-id="d7611-133">You will see a result set similar to the following:</span></span>  
  
    |<span data-ttu-id="d7611-134">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d7611-134">InstanceId</span></span>|<span data-ttu-id="d7611-135">CounterValue</span><span class="sxs-lookup"><span data-stu-id="d7611-135">CounterValue</span></span>|<span data-ttu-id="d7611-136">CounterValueLastUpdated</span><span class="sxs-lookup"><span data-stu-id="d7611-136">CounterValueLastUpdated</span></span>|  
    |----------------|------------------|-----------------------------|  
    |<span data-ttu-id="d7611-137">2FA2C302-929E-4C0D-8C25-768A3DA20CE5</span><span class="sxs-lookup"><span data-stu-id="d7611-137">2FA2C302-929E-4C0D-8C25-768A3DA20CE5</span></span>|<span data-ttu-id="d7611-138">12</span><span class="sxs-lookup"><span data-stu-id="d7611-138">12</span></span>|<span data-ttu-id="d7611-139">2010-02-18 22:48:01.740</span><span class="sxs-lookup"><span data-stu-id="d7611-139">2010-02-18 22:48:01.740</span></span>|  
  
     <span data-ttu-id="d7611-140">在连续刷新视图时，您会发现，CounterValue 和 CounterValueLastUpdated 将每两秒更改一次。</span><span class="sxs-lookup"><span data-stu-id="d7611-140">As you keep refreshing the view, you will notice that CounterValue and CounterValueLastUpdated change every two seconds.</span></span> <span data-ttu-id="d7611-141">这是计数器自行更新的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="d7611-141">This is the interval at which the counter updates itself.</span></span> <span data-ttu-id="d7611-142">CounterValue 和 CounterValueLastUpdated 表示此工作流的已提升属性。</span><span class="sxs-lookup"><span data-stu-id="d7611-142">CounterValue and CounterValueLastUpdated represent promoted properties for this workflow.</span></span>  
  
## <a name="to-remove-the-sample"></a><span data-ttu-id="d7611-143">移除示例</span><span class="sxs-lookup"><span data-stu-id="d7611-143">To remove the sample</span></span>  
  
-   <span data-ttu-id="d7611-144">在示例目录 (\WF\Basic\Persistence\PropertyPromotionActivity) 中运行 RemoveInstanceStore.cmd。</span><span class="sxs-lookup"><span data-stu-id="d7611-144">Run RemoveInstanceStore.cmd in the sample directory (\WF\Basic\Persistence\PropertyPromotionActivity).</span></span>  
  
## <a name="understanding-this-sample"></a><span data-ttu-id="d7611-145">了解此示例</span><span class="sxs-lookup"><span data-stu-id="d7611-145">Understanding This Sample</span></span>  
 <span data-ttu-id="d7611-146">此示例包含两个项目和一个 SQL 文件：</span><span class="sxs-lookup"><span data-stu-id="d7611-146">The sample contains two projects and an SQL file:</span></span>  
  
-   <span data-ttu-id="d7611-147">**CounterServiceApplication**是一个承载简单计数器 WF 服务的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="d7611-147">**CounterServiceApplication** is a console application that hosts a simple Counter WF service.</span></span> <span data-ttu-id="d7611-148">在通过 `Start` 终结点接收单向消息后，工作流将从 0 计数到 29，并每两秒递增一个计数器变量。</span><span class="sxs-lookup"><span data-stu-id="d7611-148">Upon receiving a one-way message through the `Start` endpoint, the workflow counts from 0 to 29, incrementing a counter variable every two seconds.</span></span> <span data-ttu-id="d7611-149">在每个计数器递增后，工作流将保留，并将在 [dbo].[CounterService] 视图中更新已提升的属性。</span><span class="sxs-lookup"><span data-stu-id="d7611-149">After every counter increment, the workflow persists, and the promoted properties are updated in the [dbo].[CounterService] view.</span></span> <span data-ttu-id="d7611-150">在运行控制台应用程序时，它会承载 WF 服务并向 `Start` 终结点发送一条消息，由此创建计数器 WF 实例。</span><span class="sxs-lookup"><span data-stu-id="d7611-150">When the console application is run, it hosts the WF service and sends a message to the `Start` endpoint, creating a Counter WF instance.</span></span>  
  
-   <span data-ttu-id="d7611-151">**PropertyPromotionActivity**是一个包含配置元素、 工作流活动和工作流扩展的类库， **CounterServiceApplication**使用。</span><span class="sxs-lookup"><span data-stu-id="d7611-151">**PropertyPromotionActivity** is a class library that contains the configuration elements, workflow activities, and workflow extensions that the **CounterServiceApplication** uses.</span></span>  
  
-   <span data-ttu-id="d7611-152">**PropertyPromotionActivitySQLSample.sql**创建，并将视图 [dbo]。 [CounterService] 到数据库。</span><span class="sxs-lookup"><span data-stu-id="d7611-152">**PropertyPromotionActivitySQLSample.sql** creates and adds the view [dbo].[CounterService] to the database.</span></span>  
  
### <a name="counterserviceapplication"></a><span data-ttu-id="d7611-153">CounterServiceApplication</span><span class="sxs-lookup"><span data-stu-id="d7611-153">CounterServiceApplication</span></span>  
  
#### <a name="using-the-sqlworkflowinstancestorepromotion-configuration-element"></a><span data-ttu-id="d7611-154">使用 SqlWorkflowInstanceStorePromotion 配置元素</span><span class="sxs-lookup"><span data-stu-id="d7611-154">Using the SqlWorkflowInstanceStorePromotion Configuration Element</span></span>  
 <span data-ttu-id="d7611-155">`SqlWorkflowInstanceStorePromotion` 配置元素继承自 `SqlWorkflowInstanceStore` 配置元素，但添加了一个称作 `promotionSets` 的附加配置元素。</span><span class="sxs-lookup"><span data-stu-id="d7611-155">The `SqlWorkflowInstanceStorePromotion` configuration element inherits from the `SqlWorkflowInstanceStore` configuration element, but adds an additional configuration element called `promotionSets`.</span></span> <span data-ttu-id="d7611-156">使用 `promotionSets` 元素，用户可通过配置指定提升的属性。</span><span class="sxs-lookup"><span data-stu-id="d7611-156">The `promotionSets` element enables the user to specify promoted properties through configuration.</span></span> <span data-ttu-id="d7611-157">这是由此示例使用的配置文件：</span><span class="sxs-lookup"><span data-stu-id="d7611-157">This is the configuration file that is used by the sample:</span></span>  
  
```xml  
<sqlWorkflowInstanceStorePromotion connectionString ="Data Source=.;Initial Catalog=SqlWorkflowInstanceStoreTest;Integrated Security=True;">  
  <promotionSets>  
    <promotionSet name="CounterService">  
      <promotedValue propertyName="Count"/>  
      <promotedValue propertyName="LastIncrementedAt"/>  
    </promotionSet>  
  </promotionSets>  
</sqlWorkflowInstanceStorePromotion>  
```  
  
 <span data-ttu-id="d7611-158">检查 [dbo].[CounterService] 视图的定义。</span><span class="sxs-lookup"><span data-stu-id="d7611-158">Examine the definition for the [dbo].[CounterService] view.</span></span>  
  
```sql  
create view [dbo].[CounterService] as  
      select [InstanceId],  
 [Value1] as [CounterValue],  
 [Value2] as [CounterValueLastUpdated]  
      from [System.Activities.DurableInstancing].[InstancePromotedProperties]  
      where [PromotionName] = 'CounterService'  
go  
```  
  
 <span data-ttu-id="d7611-159">当工作流实例保留时，将在配置中定义的每个 `InstancePromotedProperties` 的 `PromotionSet` 视图中插入一行。</span><span class="sxs-lookup"><span data-stu-id="d7611-159">When a workflow instance persists, a row is inserted into the `InstancePromotedProperties` view for each `PromotionSet` defined in the configuration.</span></span> <span data-ttu-id="d7611-160">此行包含 `PromotionSet` 的所有已提升的属性（一个列对应一个已提升的属性）。</span><span class="sxs-lookup"><span data-stu-id="d7611-160">This row contains all the promoted properties of the `PromotionSet` (one promoted property per column).</span></span> <span data-ttu-id="d7611-161">此 `PromotionSet` 由元组 `InstanceId, PromotionName` 进行键控。</span><span class="sxs-lookup"><span data-stu-id="d7611-161">This `PromotionSet` is keyed by the tuple: `InstanceId, PromotionName`.</span></span> <span data-ttu-id="d7611-162">此示例中具有一个配置中定义的 `PromotionSet`，其 name 属性为 `CounterService`。</span><span class="sxs-lookup"><span data-stu-id="d7611-162">In this sample, we have one `PromotionSet` defined in configuration whose name attribute is `CounterService`.</span></span> <span data-ttu-id="d7611-163">请注意，`PromotionName` 列值与 `PromotionSet` 元素的 name 属性的相等程度。</span><span class="sxs-lookup"><span data-stu-id="d7611-163">Note how the `PromotionName` column value is equal to the name attribute of the `PromotionSet` element.</span></span>  
  
 <span data-ttu-id="d7611-164">`promotedValue` 元素的顺序与已提升的属性在 `InstancePromotedProperties` 视图中的位置有关。</span><span class="sxs-lookup"><span data-stu-id="d7611-164">The order of the `promotedValue` elements correlates with the placement of the promoted properties in the `InstancePromotedProperties` view.</span></span> <span data-ttu-id="d7611-165">`Count` 是第一个 `promotedValue` 元素。</span><span class="sxs-lookup"><span data-stu-id="d7611-165">`Count` is the first `promotedValue` element.</span></span> <span data-ttu-id="d7611-166">因此，它将映射到 `Value1` 视图中的 `InstancePromotedProperties` 列。</span><span class="sxs-lookup"><span data-stu-id="d7611-166">As a result, it is mapped to the `Value1` column in the `InstancePromotedProperties` view.</span></span> <span data-ttu-id="d7611-167">`LastIncrementedAt` 是第二个 `promotedValue` 元素。</span><span class="sxs-lookup"><span data-stu-id="d7611-167">`LastIncrementedAt` is the second `promotedValue` element.</span></span> <span data-ttu-id="d7611-168">因此，它将映射到 `Value2` 视图中的 `InstancePromotedProperties` 列。</span><span class="sxs-lookup"><span data-stu-id="d7611-168">As a result, it is mapped to the `Value2` column in the `InstancePromotedProperties` view.</span></span>  
  
#### <a name="using-the-promotevalue-activity"></a><span data-ttu-id="d7611-169">使用 PromoteValue 活动</span><span class="sxs-lookup"><span data-stu-id="d7611-169">Using the PromoteValue Activity</span></span>  
 <span data-ttu-id="d7611-170">检查 Windows Workflow Foundation 设计器中的 CounterService.xamlx 文件。</span><span class="sxs-lookup"><span data-stu-id="d7611-170">Examine the CounterService.xamlx file in the Windows Workflow Foundation Designer.</span></span> <span data-ttu-id="d7611-171">请注意，WF 定义中包含两个特殊活动：`PromoteValue<DateTime>` 和 `PromoteValue<Int32>`。</span><span class="sxs-lookup"><span data-stu-id="d7611-171">Notice that there are two special activities in the WF definition: `PromoteValue<DateTime>` and `PromoteValue<Int32>`.</span></span>  
  
 <span data-ttu-id="d7611-172">`PromoteValue<Int32>` 活动的 `Name` 成员已定义为 `Count`。</span><span class="sxs-lookup"><span data-stu-id="d7611-172">The `PromoteValue<Int32>` activity has its `Name` member defined as `Count`.</span></span> <span data-ttu-id="d7611-173">这与配置中的第一个 `promotedValue` 元素匹配，并且其 `Value` 已定义为 `Counter` 工作流变量。</span><span class="sxs-lookup"><span data-stu-id="d7611-173">This matches with the first `promotedValue` element in the configuration, and has its `Value` defined as the `Counter` workflow variable.</span></span> <span data-ttu-id="d7611-174">当工作流保留时，`Counter` 工作流变量将作为已提升的属性保留到 `Value1` 视图的 `InstancePromotedProperties` 列中。</span><span class="sxs-lookup"><span data-stu-id="d7611-174">When the workflow persists, the `Counter` workflow variable is persisted as a promoted property into the `Value1` column of the `InstancePromotedProperties` view.</span></span>  
  
 <span data-ttu-id="d7611-175">`PromoteValue<DateTime>` 活动的 `Name` 成员已定义为 `LastIncrementedAt`。</span><span class="sxs-lookup"><span data-stu-id="d7611-175">The `PromoteValue<DateTime>` activity has its `Name` member defined as `LastIncrementedAt`.</span></span> <span data-ttu-id="d7611-176">这与配置中的第二个 `promotedValue` 元素匹配，并且其 `Value` 已定义为 `TimeLastIncremented` 工作流变量。</span><span class="sxs-lookup"><span data-stu-id="d7611-176">This matches with the second `promotedValue` element in the configuration, and has its `Value` defined as the `TimeLastIncremented` workflow variable.</span></span> <span data-ttu-id="d7611-177">这意味着，当工作流保留时，`TimeLastIncremented` 工作流变量的值将作为已提升的属性保留到 `Value2` 视图的 `InstancePromotedProperties` 列中。</span><span class="sxs-lookup"><span data-stu-id="d7611-177">This means that when the workflow persists, the value for the `TimeLastIncremented` workflow variable will be persisted as a promoted property into the `Value2` column of the `InstancePromotedProperties` view.</span></span>  
  
 <span data-ttu-id="d7611-178">请注意，`PromotedValue` 活动还具有一个称作 `ClearExistingPromotedData` 的 Boolean 成员。</span><span class="sxs-lookup"><span data-stu-id="d7611-178">Note that the `PromotedValue` activity also has a Boolean member called `ClearExistingPromotedData`.</span></span> <span data-ttu-id="d7611-179">在将此成员设置为 `true` 时，将清除工作流中该点之前的所有已提升的属性值。</span><span class="sxs-lookup"><span data-stu-id="d7611-179">When this member is set to `true`, this clears all the promoted property values up to that point in the workflow.</span></span> <span data-ttu-id="d7611-180">例如，如果将 Sequence 活动定义为如下内容：</span><span class="sxs-lookup"><span data-stu-id="d7611-180">For example, if a Sequence activity is defined as follows:</span></span>  
  
1.  <span data-ttu-id="d7611-181">PromoteValue {名称 ="计数"，值 = 3}</span><span class="sxs-lookup"><span data-stu-id="d7611-181">PromoteValue { Name = "Count", Value = 3}</span></span>  
  
2.  <span data-ttu-id="d7611-182">PromoteValue {名称 ="LastIncrementedAt"，值 = 1-1-2000年}</span><span class="sxs-lookup"><span data-stu-id="d7611-182">PromoteValue {Name = "LastIncrementedAt", Value = 1-1-2000 }</span></span>  
  
3.  <span data-ttu-id="d7611-183">持久</span><span class="sxs-lookup"><span data-stu-id="d7611-183">Persist</span></span>  
  
4.  <span data-ttu-id="d7611-184">PromoteValue {名称 ="计数"，值 = 4，ClearExistingPromotedData = true}</span><span class="sxs-lookup"><span data-stu-id="d7611-184">PromoteValue {Name = "Count", Value = 4, ClearExistingPromotedData = true}</span></span>  
  
5.  <span data-ttu-id="d7611-185">持久</span><span class="sxs-lookup"><span data-stu-id="d7611-185">Persist</span></span>  
  
 <span data-ttu-id="d7611-186">在第二次保留时，`Count` 的已提升的值将为 4。</span><span class="sxs-lookup"><span data-stu-id="d7611-186">On the second persist, the promoted value for `Count` will be 4.</span></span> <span data-ttu-id="d7611-187">但是，已提升的值`LastIncrementedAt`将为`NULL`。</span><span class="sxs-lookup"><span data-stu-id="d7611-187">However, the promoted value for `LastIncrementedAt` will be `NULL`.</span></span> <span data-ttu-id="d7611-188">如果步骤 4 中未将 `ClearExistingPromotedData` 设置为 `true`，则在第二次保留之后，Count 的已提升的值将为 4。</span><span class="sxs-lookup"><span data-stu-id="d7611-188">If `ClearExistingPromotedData` was not set to `true` for step 4, then after the second persist, the promoted value for Count would be 4.</span></span> <span data-ttu-id="d7611-189">因此，`LastIncrementedAt` 的已提升的值仍将为 1-1-2000。</span><span class="sxs-lookup"><span data-stu-id="d7611-189">As a result, the promoted value for `LastIncrementedAt` would still be 1-1-2000.</span></span>  
  
### <a name="propertypromotionactivity"></a><span data-ttu-id="d7611-190">PropertyPromotionActivity</span><span class="sxs-lookup"><span data-stu-id="d7611-190">PropertyPromotionActivity</span></span>  
 <span data-ttu-id="d7611-191">此类库包含以下用于简化对 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 提升功能的使用的公共类。</span><span class="sxs-lookup"><span data-stu-id="d7611-191">This class library contains the following public classes to simplify use of the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Promotion feature.</span></span>  
  
#### <a name="promotevalue-class"></a><span data-ttu-id="d7611-192">PromoteValue 类</span><span class="sxs-lookup"><span data-stu-id="d7611-192">PromoteValue Class</span></span>  
 <span data-ttu-id="d7611-193">此类可提升一个属性。</span><span class="sxs-lookup"><span data-stu-id="d7611-193">This class promotes one property.</span></span> <span data-ttu-id="d7611-194">已提升的属性的名称应与配置中的 `promotedValue` 元素的 name 属性匹配。</span><span class="sxs-lookup"><span data-stu-id="d7611-194">The name of the promoted property should match a name attribute of a `promotedValue` element in the configuration.</span></span> <span data-ttu-id="d7611-195">可在工作流设计器中使用此活动。</span><span class="sxs-lookup"><span data-stu-id="d7611-195">This activity can be used in the Workflow Designer.</span></span> <span data-ttu-id="d7611-196">有关示例用法，请参见 CounterServiceApplication。</span><span class="sxs-lookup"><span data-stu-id="d7611-196">See the CounterServiceApplication for an example usage.</span></span>  
  
```csharp  
public class PromoteValue<T> : CodeActivity  
{  
    public PromoteValue()  
    {  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public string Name { get; set; }  
    public InArgument<T> Value { get; set; }  
}  
```  
  
 <span data-ttu-id="d7611-197">ClearExistingPromotedData (Bool)</span><span class="sxs-lookup"><span data-stu-id="d7611-197">ClearExistingPromotedData (Bool)</span></span>  
 <span data-ttu-id="d7611-198">清除在此活动之前已提升的所有值。</span><span class="sxs-lookup"><span data-stu-id="d7611-198">Clears all values that were promoted before this activity.</span></span>  
  
 <span data-ttu-id="d7611-199">Name (string)</span><span class="sxs-lookup"><span data-stu-id="d7611-199">Name (string)</span></span>  
 <span data-ttu-id="d7611-200">表示此属性的名称。</span><span class="sxs-lookup"><span data-stu-id="d7611-200">The name that represents this property.</span></span> <span data-ttu-id="d7611-201">这应与匹配的 name 属性\<promotedValue > 配置中的元素。</span><span class="sxs-lookup"><span data-stu-id="d7611-201">This should match the name attribute of a \<promotedValue> element in the configuration.</span></span>  
  
 <span data-ttu-id="d7611-202">值 (InArgument\<T >)</span><span class="sxs-lookup"><span data-stu-id="d7611-202">Value (InArgument\<T>)</span></span>  
 <span data-ttu-id="d7611-203">要存储在列中的变量/值。</span><span class="sxs-lookup"><span data-stu-id="d7611-203">The variable / value that you want to store in the column.</span></span>  
  
#### <a name="promotevalues-class"></a><span data-ttu-id="d7611-204">PromoteValues 类</span><span class="sxs-lookup"><span data-stu-id="d7611-204">PromoteValues Class</span></span>  
 <span data-ttu-id="d7611-205">提升多个属性。</span><span class="sxs-lookup"><span data-stu-id="d7611-205">Promotes multiple properties.</span></span> <span data-ttu-id="d7611-206">已提升的属性的名称应与配置中的 `promotedValue` 元素中的所有 name 属性匹配。</span><span class="sxs-lookup"><span data-stu-id="d7611-206">The names of the promoted properties should match all name attributes in the `promotedValue` elements in the configuration.</span></span> <span data-ttu-id="d7611-207">用法与 `PromoteValue` 活动相似，只不过可同时提升多个属性。</span><span class="sxs-lookup"><span data-stu-id="d7611-207">Usage is similar to the `PromoteValue` activity, except for the fact that multiple properties can be promoted at the same time.</span></span> <span data-ttu-id="d7611-208">无法在工作流设计器中使用此活动。</span><span class="sxs-lookup"><span data-stu-id="d7611-208">This activity cannot be used in the Workflow Designer.</span></span>  
  
```  
public class PromoteValues : CodeActivity  
{  
    public PromoteValues()  
    {  
        this.ValuesToPromote = new Dictionary<string, InArgument>();  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public IDictionary<string, InArgument> ValuesToPromote { get; set; }  
}  
```  
  
#### <a name="sqlworkflowinstancestorepromotionbehavior"></a><span data-ttu-id="d7611-209">SqlWorkflowInstanceStorePromotionBehavior</span><span class="sxs-lookup"><span data-stu-id="d7611-209">SqlWorkflowInstanceStorePromotionBehavior</span></span>  
 <span data-ttu-id="d7611-210">派生自 `SqlWorkflowInstanceStoreBehavior`。</span><span class="sxs-lookup"><span data-stu-id="d7611-210">Derives from `SqlWorkflowInstanceStoreBehavior`.</span></span> <span data-ttu-id="d7611-211">此派生类会将自定义持久性参与者（也是此库的一部分）添加为工作流扩展。</span><span class="sxs-lookup"><span data-stu-id="d7611-211">This derived class adds a custom persistence participant (also a part of this library) as a workflow extension.</span></span> <span data-ttu-id="d7611-212">前两个工作流活动的实现依赖于此自定义持久性参与者。</span><span class="sxs-lookup"><span data-stu-id="d7611-212">The implementation of the previous two workflow activities relies on this custom persistence participant.</span></span>  
  
```  
public class SqlWorkflowInstanceStorePromotionBehavior :  
             SqlWorkflowInstanceStoreBehavior, IServiceBehavior  
{  
        public void Promote(string name, IEnumerable<string> promoteAsSqlVariant,  
                            IEnumerable<string> promoteAsBinary)  
  
}  
```  
  
 <span data-ttu-id="d7611-213">此类库还包含 `ConfigurationElement` 的 `SqlWorkflowInstanceStorePromotionElement` 实现和前面的提升活动所使用的自定义持久性参与者。</span><span class="sxs-lookup"><span data-stu-id="d7611-213">This class library also contains the `ConfigurationElement` implementation for the `SqlWorkflowInstanceStorePromotionElement` and a custom persistence participant used by the previous promotion activities.</span></span>  
  
### <a name="propertypromotionactivitysqlsample"></a><span data-ttu-id="d7611-214">PropertyPromotionActivitySQLSample</span><span class="sxs-lookup"><span data-stu-id="d7611-214">PropertyPromotionActivitySQLSample</span></span>  
 <span data-ttu-id="d7611-215">此 SQL 文件会创建 `[dbo].[CounterService]` 视图以及用于查询具有 CounterService 提升集的所有实例的 `[InstancePromotedProperties]` 视图。</span><span class="sxs-lookup"><span data-stu-id="d7611-215">This SQL file creates a `[dbo].[CounterService]` view in addition to the `[InstancePromotedProperties]` view for querying all instances that have a CounterService Promotion set.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d7611-216">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="d7611-216">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d7611-217">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="d7611-217">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d7611-218">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="d7611-218">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d7611-219">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="d7611-219">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\PropertyPromotionActivity`  
  
## <a name="see-also"></a><span data-ttu-id="d7611-220">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7611-220">See Also</span></span>  
 [<span data-ttu-id="d7611-221">AppFabric 承载和持久性示例</span><span class="sxs-lookup"><span data-stu-id="d7611-221">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
