---
title: 查询支持
ms.date: 03/30/2017
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
ms.openlocfilehash: 30695fcd791a0d69c31a897068d69838c80c3957
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307946"
---
# <a name="support-for-queries"></a><span data-ttu-id="35d3d-102">查询支持</span><span class="sxs-lookup"><span data-stu-id="35d3d-102">Support for Queries</span></span>
<span data-ttu-id="35d3d-103">SQL 工作流实例存储中记录了存储区中的一组已知属性。</span><span class="sxs-lookup"><span data-stu-id="35d3d-103">The SQL Workflow Instance Store records a set of well-known properties in the store.</span></span> <span data-ttu-id="35d3d-104">用户可以根据这些属性查询实例。</span><span class="sxs-lookup"><span data-stu-id="35d3d-104">Users can query for instances based on these properties.</span></span> <span data-ttu-id="35d3d-105">下面的列表包含这些已知属性的一部分：</span><span class="sxs-lookup"><span data-stu-id="35d3d-105">The following list contains some of these well-known properties:</span></span>  
  
-   <span data-ttu-id="35d3d-106">**站点名称。**</span><span class="sxs-lookup"><span data-stu-id="35d3d-106">**Site Name.**</span></span> <span data-ttu-id="35d3d-107">包含服务的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="35d3d-107">Name of the Web site that contains the service.</span></span>  
  
-   <span data-ttu-id="35d3d-108">**相对应用程序路径。**</span><span class="sxs-lookup"><span data-stu-id="35d3d-108">**Relative Application Path.**</span></span> <span data-ttu-id="35d3d-109">应用程序相对于网站的路径。</span><span class="sxs-lookup"><span data-stu-id="35d3d-109">Path of the application relative to the Web site.</span></span>  
  
-   <span data-ttu-id="35d3d-110">**相对服务路径。**</span><span class="sxs-lookup"><span data-stu-id="35d3d-110">**Relative Service Path.**</span></span> <span data-ttu-id="35d3d-111">服务相对于应用程序的路径。</span><span class="sxs-lookup"><span data-stu-id="35d3d-111">Path of the service relative to the application.</span></span>  
  
-   <span data-ttu-id="35d3d-112">**服务名称。**</span><span class="sxs-lookup"><span data-stu-id="35d3d-112">**Service Name.**</span></span> <span data-ttu-id="35d3d-113">服务的名称。</span><span class="sxs-lookup"><span data-stu-id="35d3d-113">Name of the service.</span></span>  
  
-   <span data-ttu-id="35d3d-114">**服务 Namespace。**</span><span class="sxs-lookup"><span data-stu-id="35d3d-114">**Service Namespace.**</span></span> <span data-ttu-id="35d3d-115">服务使用的命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="35d3d-115">Name of the namespace that the service uses.</span></span>  
  
-   <span data-ttu-id="35d3d-116">**当前计算机。**</span><span class="sxs-lookup"><span data-stu-id="35d3d-116">**Current Machine.**</span></span>  
  
-   <span data-ttu-id="35d3d-117">**上一计算机**。</span><span class="sxs-lookup"><span data-stu-id="35d3d-117">**Last Machine**.</span></span> <span data-ttu-id="35d3d-118">上次运行工作流服务实例的计算机。</span><span class="sxs-lookup"><span data-stu-id="35d3d-118">The computer on which the workflow service instance ran the last time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35d3d-119">对于使用工作流服务主机的自承载方案，仅填充最后四个属性。</span><span class="sxs-lookup"><span data-stu-id="35d3d-119">For self-hosted scenarios using Workflow Service Host, only the last four properties are populated.</span></span> <span data-ttu-id="35d3d-120">对于工作流应用程序方案，仅填充最后一个属性。</span><span class="sxs-lookup"><span data-stu-id="35d3d-120">For Workflow Application scenarios, only the last property is populated.</span></span>  
  
 <span data-ttu-id="35d3d-121">工作流运行时为前三个属性提供值。</span><span class="sxs-lookup"><span data-stu-id="35d3d-121">The workflow runtime supplies values for the first three properties.</span></span> <span data-ttu-id="35d3d-122">工作流服务主机提供的值**挂起原因**属性。</span><span class="sxs-lookup"><span data-stu-id="35d3d-122">The workflow service host supplies the value for the **Suspend Reason** property.</span></span> <span data-ttu-id="35d3d-123">SQL 工作流实例存储自身提供值的**上次更新的计算机**属性。</span><span class="sxs-lookup"><span data-stu-id="35d3d-123">The SQL Workflow Instance Store itself supplies values for the **Last Updated Machine** property.</span></span>  
  
 <span data-ttu-id="35d3d-124">使用 SQL 工作流实例存储的功能还可以指定自定义属性，您可以在持久性数据库中存储这些属性的值并且在查询中使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="35d3d-124">The SQL Workflow Instance Store feature also lets you specify the custom properties for which you want to store the values in the persistence database and that you want to use in queries.</span></span> <span data-ttu-id="35d3d-125">有关自定义促销的详细信息，请参阅[存储扩展性](store-extensibility.md)。</span><span class="sxs-lookup"><span data-stu-id="35d3d-125">For more information about custom promotions, see [Store Extensibility](store-extensibility.md).</span></span>  
  
## <a name="views"></a><span data-ttu-id="35d3d-126">Views</span><span class="sxs-lookup"><span data-stu-id="35d3d-126">Views</span></span>  
 <span data-ttu-id="35d3d-127">实例存储区包含下列视图。</span><span class="sxs-lookup"><span data-stu-id="35d3d-127">The instance store contains the following views.</span></span> <span data-ttu-id="35d3d-128">请参阅[暂留数据库架构](persistence-database-schema.md)的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="35d3d-128">See [Persistence Database Schema](persistence-database-schema.md) for further details.</span></span>  
  
### <a name="the-instances-view"></a><span data-ttu-id="35d3d-129">Instances 视图</span><span class="sxs-lookup"><span data-stu-id="35d3d-129">The Instances View</span></span>  
 <span data-ttu-id="35d3d-130">Instances 视图包含下列字段：</span><span class="sxs-lookup"><span data-stu-id="35d3d-130">The Instances view contains the following fields:</span></span>  
  
1. <span data-ttu-id="35d3d-131">**Id**</span><span class="sxs-lookup"><span data-stu-id="35d3d-131">**Id**</span></span>  
  
2. <span data-ttu-id="35d3d-132">**PendingTimer**</span><span class="sxs-lookup"><span data-stu-id="35d3d-132">**PendingTimer**</span></span>  
  
3. <span data-ttu-id="35d3d-133">**CreationTime**</span><span class="sxs-lookup"><span data-stu-id="35d3d-133">**CreationTime**</span></span>  
  
4. <span data-ttu-id="35d3d-134">**LastUpdatedTime**</span><span class="sxs-lookup"><span data-stu-id="35d3d-134">**LastUpdatedTime**</span></span>  
  
5. <span data-ttu-id="35d3d-135">**ServiceDeploymentId**</span><span class="sxs-lookup"><span data-stu-id="35d3d-135">**ServiceDeploymentId**</span></span>  
  
6. <span data-ttu-id="35d3d-136">**SuspensionExceptionName**</span><span class="sxs-lookup"><span data-stu-id="35d3d-136">**SuspensionExceptionName**</span></span>  
  
7. <span data-ttu-id="35d3d-137">**SuspensionReason**</span><span class="sxs-lookup"><span data-stu-id="35d3d-137">**SuspensionReason**</span></span>  
  
8. <span data-ttu-id="35d3d-138">**ActiveBookmarks**</span><span class="sxs-lookup"><span data-stu-id="35d3d-138">**ActiveBookmarks**</span></span>  
  
9. <span data-ttu-id="35d3d-139">**CurrentMachine**</span><span class="sxs-lookup"><span data-stu-id="35d3d-139">**CurrentMachine**</span></span>  
  
10. <span data-ttu-id="35d3d-140">**LastMachine**</span><span class="sxs-lookup"><span data-stu-id="35d3d-140">**LastMachine**</span></span>  
  
11. <span data-ttu-id="35d3d-141">**ExecutionStatus**</span><span class="sxs-lookup"><span data-stu-id="35d3d-141">**ExecutionStatus**</span></span>  
  
12. <span data-ttu-id="35d3d-142">**IsInitialized**</span><span class="sxs-lookup"><span data-stu-id="35d3d-142">**IsInitialized**</span></span>  
  
13. <span data-ttu-id="35d3d-143">**IsSuspended**</span><span class="sxs-lookup"><span data-stu-id="35d3d-143">**IsSuspended**</span></span>  
  
14. <span data-ttu-id="35d3d-144">**IsCompleted**</span><span class="sxs-lookup"><span data-stu-id="35d3d-144">**IsCompleted**</span></span>  
  
15. <span data-ttu-id="35d3d-145">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="35d3d-145">**EncodingOption**</span></span>  
  
16. <span data-ttu-id="35d3d-146">**ReadWritePrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="35d3d-146">**ReadWritePrimitiveDataProperties**</span></span>  
  
17. <span data-ttu-id="35d3d-147">**WriteOnlyPrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="35d3d-147">**WriteOnlyPrimitiveDataProperties**</span></span>  
  
18. <span data-ttu-id="35d3d-148">**ReadWriteComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="35d3d-148">**ReadWriteComplexDataProperties**</span></span>  
  
19. <span data-ttu-id="35d3d-149">**WriteOnlyComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="35d3d-149">**WriteOnlyComplexDataProperties**</span></span>  
  
### <a name="the-servicedeployments-view"></a><span data-ttu-id="35d3d-150">ServiceDeployments 视图</span><span class="sxs-lookup"><span data-stu-id="35d3d-150">The ServiceDeployments view</span></span>  
 <span data-ttu-id="35d3d-151">ServiceDeployments 视图包含下列字段：</span><span class="sxs-lookup"><span data-stu-id="35d3d-151">The ServiceDeployments view contains the following fields:</span></span>  
  
1. <span data-ttu-id="35d3d-152">**SiteName**</span><span class="sxs-lookup"><span data-stu-id="35d3d-152">**SiteName**</span></span>  
  
2. <span data-ttu-id="35d3d-153">**RelativeServicePath**</span><span class="sxs-lookup"><span data-stu-id="35d3d-153">**RelativeServicePath**</span></span>  
  
3. <span data-ttu-id="35d3d-154">**RelativeApplicationPath**</span><span class="sxs-lookup"><span data-stu-id="35d3d-154">**RelativeApplicationPath**</span></span>  
  
4. <span data-ttu-id="35d3d-155">**ServiceName**</span><span class="sxs-lookup"><span data-stu-id="35d3d-155">**ServiceName**</span></span>  
  
5. <span data-ttu-id="35d3d-156">**ServiceNamespace**</span><span class="sxs-lookup"><span data-stu-id="35d3d-156">**ServiceNamespace**</span></span>  
  
### <a name="the-instancepromotedproperties-view"></a><span data-ttu-id="35d3d-157">InstancePromotedProperties 视图</span><span class="sxs-lookup"><span data-stu-id="35d3d-157">The InstancePromotedProperties view</span></span>  
 <span data-ttu-id="35d3d-158">InstancePromotedProperties 视图包含下列字段。</span><span class="sxs-lookup"><span data-stu-id="35d3d-158">The InstancePromotedProperties view contains the following fields.</span></span> <span data-ttu-id="35d3d-159">有关升级的属性的详细信息，请参阅[存储扩展性](store-extensibility.md)主题。</span><span class="sxs-lookup"><span data-stu-id="35d3d-159">For details on promoted properties, see the [Store Extensibility](store-extensibility.md) topic.</span></span>  
  
1. <span data-ttu-id="35d3d-160">**InstanceId**</span><span class="sxs-lookup"><span data-stu-id="35d3d-160">**InstanceId**</span></span>  
  
2. <span data-ttu-id="35d3d-161">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="35d3d-161">**EncodingOption**</span></span>  
  
3. <span data-ttu-id="35d3d-162">**PromotionName**</span><span class="sxs-lookup"><span data-stu-id="35d3d-162">**PromotionName**</span></span>  
  
4. <span data-ttu-id="35d3d-163">**Value #** (一系列中的字段**Value1**到**Value64**)。</span><span class="sxs-lookup"><span data-stu-id="35d3d-163">**Value#** (a range of fields from **Value1** to **Value64**).</span></span>
