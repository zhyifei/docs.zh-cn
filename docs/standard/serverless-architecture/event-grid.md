---
title: Azure 事件网格的无服务器应用
description: Azure 事件网格是可靠事件交付和支付每个事件模型上大规模地路由的无服务器解决方案。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4970130ede0c96c645129ee6c8c7d54cb1114042
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212178"
---
# <a name="event-grid"></a><span data-ttu-id="80a90-103">事件网格</span><span class="sxs-lookup"><span data-stu-id="80a90-103">Event Grid</span></span>

<span data-ttu-id="80a90-104">[Azure 事件网格](/azure/event-grid/overview)为基于事件的应用程序提供无服务器基础结构。</span><span class="sxs-lookup"><span data-stu-id="80a90-104">[Azure Event Grid](/azure/event-grid/overview) provides serverless infrastructure for event-based applications.</span></span> <span data-ttu-id="80a90-105">可以从任何源发布到事件网格，并使用从任何平台的消息。</span><span class="sxs-lookup"><span data-stu-id="80a90-105">You can publish to Event Grid from any source and consume messages from any platform.</span></span> <span data-ttu-id="80a90-106">事件网格还提供来自 Azure 资源，以简化您的应用程序与集成的事件的内置支持。</span><span class="sxs-lookup"><span data-stu-id="80a90-106">Event Grid also has built-in support for events from Azure resources to streamline integration with your applications.</span></span> <span data-ttu-id="80a90-107">例如，您可以订阅 blob 存储事件，以在文件上传时通知您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="80a90-107">For example, you can subscribe to blob storage events to notify your app when a file is uploaded.</span></span> <span data-ttu-id="80a90-108">你的应用程序然后可以将发布供其他云或本地应用程序的自定义事件网格消息。</span><span class="sxs-lookup"><span data-stu-id="80a90-108">Your application can then publish a custom event grid message that is consumed by other cloud or on-premises applications.</span></span> <span data-ttu-id="80a90-109">事件网格旨在可靠地处理很大的规模。</span><span class="sxs-lookup"><span data-stu-id="80a90-109">Event Grid was built to reliably handle massive scale.</span></span> <span data-ttu-id="80a90-110">获取发布和订阅消息，而不必设置必要的基础结构的开销的优势。</span><span class="sxs-lookup"><span data-stu-id="80a90-110">You get the benefits of publishing and subscribing to messages without the overhead of setting up the necessary infrastructure.</span></span>

![事件网格徽标](./media/event-grid-logo.png)

<span data-ttu-id="80a90-112">事件网格的主要功能包括：</span><span class="sxs-lookup"><span data-stu-id="80a90-112">The major features of event grid include:</span></span>

* <span data-ttu-id="80a90-113">完全托管的事件路由。</span><span class="sxs-lookup"><span data-stu-id="80a90-113">Fully managed event routing.</span></span>
* <span data-ttu-id="80a90-114">附近大规模实时事件交付。</span><span class="sxs-lookup"><span data-stu-id="80a90-114">Near real-time event delivery at scale.</span></span>
* <span data-ttu-id="80a90-115">内部和外部 Azure 广泛覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="80a90-115">Broad coverage both inside and outside of Azure.</span></span>

## <a name="scenarios"></a><span data-ttu-id="80a90-116">方案</span><span class="sxs-lookup"><span data-stu-id="80a90-116">Scenarios</span></span>

<span data-ttu-id="80a90-117">事件网格解决了几个不同的方案。</span><span class="sxs-lookup"><span data-stu-id="80a90-117">Event Grid addresses several different scenarios.</span></span> <span data-ttu-id="80a90-118">本部分介绍了三个最常见的。</span><span class="sxs-lookup"><span data-stu-id="80a90-118">This section covers three of the most common ones.</span></span>

### <a name="ops-automation"></a><span data-ttu-id="80a90-119">运维自动化</span><span class="sxs-lookup"><span data-stu-id="80a90-119">Ops automation</span></span>

![运维自动化](./media/ops-automation.png)

<span data-ttu-id="80a90-121">事件网格可以帮助速度自动化和简化策略执行通知[Azure 自动化](https://docs.microsoft.com/azure/automation)基础结构预配时。</span><span class="sxs-lookup"><span data-stu-id="80a90-121">Event Grid can help speed automation and simplify policy enforcement by notifying [Azure Automation](https://docs.microsoft.com/azure/automation) when infrastructure is provisioned.</span></span>

### <a name="application-integration"></a><span data-ttu-id="80a90-122">应用程序集成</span><span class="sxs-lookup"><span data-stu-id="80a90-122">Application integration</span></span>

![应用程序集成](./media/app-integration.png)

<span data-ttu-id="80a90-124">事件网格可用于将应用连接到其他服务。</span><span class="sxs-lookup"><span data-stu-id="80a90-124">You can use Event Grid to connect your app to other services.</span></span> <span data-ttu-id="80a90-125">使用标准 HTTP 协议，甚至旧版应用可以轻松地修改发布事件网格消息。</span><span class="sxs-lookup"><span data-stu-id="80a90-125">Using standard HTTP protocols, even legacy apps can be easily modified to publish Event Grid messages.</span></span> <span data-ttu-id="80a90-126">Web 挂钩是适用于其他服务和平台使用事件网格的消息。</span><span class="sxs-lookup"><span data-stu-id="80a90-126">Web hooks are available for other services and platforms to consume Event Grid messages.</span></span>

### <a name="serverless-apps"></a><span data-ttu-id="80a90-127">无服务器应用</span><span class="sxs-lookup"><span data-stu-id="80a90-127">Serverless apps</span></span>

![无服务器应用](./media/serverless-apps.png)

<span data-ttu-id="80a90-129">事件网格可以触发 Azure Functions、 逻辑应用或你自己的自定义代码。</span><span class="sxs-lookup"><span data-stu-id="80a90-129">Event Grid can trigger Azure Functions, Logic Apps, or your own custom code.</span></span> <span data-ttu-id="80a90-130">使用事件网格的主要优点是，它使用*推送*事件发生时发送消息的机制。</span><span class="sxs-lookup"><span data-stu-id="80a90-130">A major benefit of using Event Grid is that it uses a *push* mechanism to send messages when events occur.</span></span> <span data-ttu-id="80a90-131">推送体系结构会占用较少的资源和伸缩性优于*轮询*机制。</span><span class="sxs-lookup"><span data-stu-id="80a90-131">The push architecture consumes fewer resources and scales better than *polling* mechanisms.</span></span> <span data-ttu-id="80a90-132">轮询必须检查固定时间间隔上的更新。</span><span class="sxs-lookup"><span data-stu-id="80a90-132">Polling must check for updates on a regular interval.</span></span>

## <a name="event-grid-vs-other-azure-messaging-services"></a><span data-ttu-id="80a90-133">事件网格与其他 Azure 消息传送服务</span><span class="sxs-lookup"><span data-stu-id="80a90-133">Event Grid vs. other Azure messaging services</span></span>

<span data-ttu-id="80a90-134">Azure 提供了多个消息传送服务，包括[事件中心](https://docs.microsoft.com/azure/event-hubs)并[服务总线](https://docs.microsoft.com/azure/service-bus-messaging)。</span><span class="sxs-lookup"><span data-stu-id="80a90-134">Azure provides several messaging services, including [Event Hubs](https://docs.microsoft.com/azure/event-hubs) and [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging).</span></span> <span data-ttu-id="80a90-135">每个旨在解决一组特定的用例。</span><span class="sxs-lookup"><span data-stu-id="80a90-135">Each is designed to address a specific set of use cases.</span></span> <span data-ttu-id="80a90-136">下图提供了在服务之间的差异的高级概述。</span><span class="sxs-lookup"><span data-stu-id="80a90-136">The following diagram provides a high-level overview of the differences between the services.</span></span>

![Azure 消息传递的比较](./media/azure-messaging-services.png)

<span data-ttu-id="80a90-138">有关更深入比较，请参阅[比较消息服务](https://docs.microsoft.com/azure/event-grid/compare-messaging-services)。</span><span class="sxs-lookup"><span data-stu-id="80a90-138">For a more in-depth comparison, see [Compare messaging services](https://docs.microsoft.com/azure/event-grid/compare-messaging-services).</span></span>

## <a name="performance-targets"></a><span data-ttu-id="80a90-139">性能目标</span><span class="sxs-lookup"><span data-stu-id="80a90-139">Performance targets</span></span>

<span data-ttu-id="80a90-140">使用事件网格可以充分利用以下性能可保证：</span><span class="sxs-lookup"><span data-stu-id="80a90-140">Using Event Grid you can take advantage of the following performance guarantees:</span></span>

* <span data-ttu-id="80a90-141">次秒级的端到端延迟在第 99 个百分点值。</span><span class="sxs-lookup"><span data-stu-id="80a90-141">Subsecond end-to-end latency in the 99th percentile.</span></span>
* <span data-ttu-id="80a90-142">99.99%的可用性。</span><span class="sxs-lookup"><span data-stu-id="80a90-142">99.99% availability.</span></span>
* <span data-ttu-id="80a90-143">每个区域每秒 10 万个事件。</span><span class="sxs-lookup"><span data-stu-id="80a90-143">10 million events per second per region.</span></span>
* <span data-ttu-id="80a90-144">每个区域 100 万个订阅。</span><span class="sxs-lookup"><span data-stu-id="80a90-144">100 million subscriptions per region.</span></span>
* <span data-ttu-id="80a90-145">发布服务器 50 毫秒的延迟。</span><span class="sxs-lookup"><span data-stu-id="80a90-145">50-ms publisher latency.</span></span>
* <span data-ttu-id="80a90-146">使用指数回退的 1 天的时间窗口中的有保证传递的 24 小时重试。</span><span class="sxs-lookup"><span data-stu-id="80a90-146">24-hour retry with exponential back-off for guaranteed delivery in the 1-day window.</span></span>
* <span data-ttu-id="80a90-147">透明区域故障转移。</span><span class="sxs-lookup"><span data-stu-id="80a90-147">Transparent regional failover.</span></span>

## <a name="event-grid-schema"></a><span data-ttu-id="80a90-148">事件网格架构</span><span class="sxs-lookup"><span data-stu-id="80a90-148">Event Grid schema</span></span>

<span data-ttu-id="80a90-149">事件网格使用的标准架构来包装自定义事件。</span><span class="sxs-lookup"><span data-stu-id="80a90-149">Event Grid uses a standard schema to wrap custom events.</span></span> <span data-ttu-id="80a90-150">架构就像自定义数据元素进行包装的信封。</span><span class="sxs-lookup"><span data-stu-id="80a90-150">The schema is like an envelope that wraps your custom data element.</span></span> <span data-ttu-id="80a90-151">下面是示例事件网格消息：</span><span class="sxs-lookup"><span data-stu-id="80a90-151">Here is an example Event Grid message:</span></span>

```json
[{
    "id": "03e24f21-a955-43cc-8921-1f61a6081ce0",
    "eventType": "myCustomEvent",
    "subject": "foo/bar/12",
    "eventTime": "2018-09-22T10:36:01+00:00",
    "data": {
        "favoriteColor": "blue",
        "favoriteAnimal": "panther",
        "favoritePlanet": "Jupiter"
    },
    "dataVersion": "1.0"
}]
```

<span data-ttu-id="80a90-152">有关消息的所有内容都是除标准`data`属性。</span><span class="sxs-lookup"><span data-stu-id="80a90-152">Everything about the message is standard except the `data` property.</span></span> <span data-ttu-id="80a90-153">可以检查消息，并使用`eventType`和`dataVersion`进行反序列化有效负载的自定义部分。</span><span class="sxs-lookup"><span data-stu-id="80a90-153">You can inspect the message and use the `eventType` and `dataVersion` to de-serialize the custom portion of the payload.</span></span>

## <a name="azure-resources"></a><span data-ttu-id="80a90-154">Azure 资源</span><span class="sxs-lookup"><span data-stu-id="80a90-154">Azure resources</span></span>

<span data-ttu-id="80a90-155">使用事件网格的主要优点是由 Azure 生成的自动消息。</span><span class="sxs-lookup"><span data-stu-id="80a90-155">A major benefit of using Event Grid is the automatic messages produced by Azure.</span></span> <span data-ttu-id="80a90-156">在 Azure 中，资源会自动将发布到*主题*，可以有多个事件订阅。</span><span class="sxs-lookup"><span data-stu-id="80a90-156">In Azure, resources automatically publish to a *topic* that allows you to subscribe for various events.</span></span> <span data-ttu-id="80a90-157">下表列出了资源类型、 消息类型和事件将自动应用。</span><span class="sxs-lookup"><span data-stu-id="80a90-157">The following table lists the resource types, message types, and events that are available automatically.</span></span>

| <span data-ttu-id="80a90-158">Azure 资源</span><span class="sxs-lookup"><span data-stu-id="80a90-158">Azure resource</span></span> | <span data-ttu-id="80a90-159">事件类型</span><span class="sxs-lookup"><span data-stu-id="80a90-159">Event type</span></span> | <span data-ttu-id="80a90-160">描述</span><span class="sxs-lookup"><span data-stu-id="80a90-160">Description</span></span> |
| -------------- | ---------- | ----------- |
| <span data-ttu-id="80a90-161">Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="80a90-161">Azure subscription</span></span> | <span data-ttu-id="80a90-162">Microsoft.Resources.ResourceWriteSuccess</span><span class="sxs-lookup"><span data-stu-id="80a90-162">Microsoft.Resources.ResourceWriteSuccess</span></span> | <span data-ttu-id="80a90-163">引发时资源创建或更新操作成功。</span><span class="sxs-lookup"><span data-stu-id="80a90-163">Raised when a resource create or update operation succeeds.</span></span> |
| | <span data-ttu-id="80a90-164">Microsoft.Resources.ResourceWriteFailure</span><span class="sxs-lookup"><span data-stu-id="80a90-164">Microsoft.Resources.ResourceWriteFailure</span></span> | <span data-ttu-id="80a90-165">在资源创建或更新操作失败时引发。</span><span class="sxs-lookup"><span data-stu-id="80a90-165">Raised when a resource create or update operation fails.</span></span> |
| | <span data-ttu-id="80a90-166">Microsoft.Resources.ResourceWriteCancel</span><span class="sxs-lookup"><span data-stu-id="80a90-166">Microsoft.Resources.ResourceWriteCancel</span></span> | <span data-ttu-id="80a90-167">引发时资源创建或更新操作已取消。</span><span class="sxs-lookup"><span data-stu-id="80a90-167">Raised when a resource create or update operation is canceled.</span></span> |
|  | <span data-ttu-id="80a90-168">Microsoft.Resources.ResourceDeleteSuccess</span><span class="sxs-lookup"><span data-stu-id="80a90-168">Microsoft.Resources.ResourceDeleteSuccess</span></span> | <span data-ttu-id="80a90-169">当资源删除操作成功时引发。</span><span class="sxs-lookup"><span data-stu-id="80a90-169">Raised when a resource delete operation succeeds.</span></span> |
|  | <span data-ttu-id="80a90-170">Microsoft.Resources.ResourceDeleteFailure</span><span class="sxs-lookup"><span data-stu-id="80a90-170">Microsoft.Resources.ResourceDeleteFailure</span></span> | <span data-ttu-id="80a90-171">当资源删除操作失败时引发。</span><span class="sxs-lookup"><span data-stu-id="80a90-171">Raised when a resource delete operation fails.</span></span> |
| | <span data-ttu-id="80a90-172">Microsoft.Resources.ResourceDeleteCancel</span><span class="sxs-lookup"><span data-stu-id="80a90-172">Microsoft.Resources.ResourceDeleteCancel</span></span> | <span data-ttu-id="80a90-173">取消资源删除操作时引发。</span><span class="sxs-lookup"><span data-stu-id="80a90-173">Raised when a resource delete operation is canceled.</span></span> <span data-ttu-id="80a90-174">取消模板部署时会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="80a90-174">This event happens when a template deployment is canceled.</span></span> |
| <span data-ttu-id="80a90-175">Blob 存储</span><span class="sxs-lookup"><span data-stu-id="80a90-175">Blob storage</span></span> | <span data-ttu-id="80a90-176">Microsoft.Storage.BlobCreated</span><span class="sxs-lookup"><span data-stu-id="80a90-176">Microsoft.Storage.BlobCreated</span></span> | <span data-ttu-id="80a90-177">创建 blob 时引发。</span><span class="sxs-lookup"><span data-stu-id="80a90-177">Raised when a blob is created.</span></span> |
| | <span data-ttu-id="80a90-178">Microsoft.Storage.BlobDeleted</span><span class="sxs-lookup"><span data-stu-id="80a90-178">Microsoft.Storage.BlobDeleted</span></span> | <span data-ttu-id="80a90-179">删除 blob 时引发。</span><span class="sxs-lookup"><span data-stu-id="80a90-179">Raised when a blob is deleted.</span></span> |
| <span data-ttu-id="80a90-180">事件中心</span><span class="sxs-lookup"><span data-stu-id="80a90-180">Event hubs</span></span> | <span data-ttu-id="80a90-181">Microsoft.EventHub.CaptureFileCreated</span><span class="sxs-lookup"><span data-stu-id="80a90-181">Microsoft.EventHub.CaptureFileCreated</span></span> | <span data-ttu-id="80a90-182">创建捕获文件时引发。</span><span class="sxs-lookup"><span data-stu-id="80a90-182">Raised when a capture file is created.</span></span>
| <span data-ttu-id="80a90-183">IoT 中心</span><span class="sxs-lookup"><span data-stu-id="80a90-183">IoT Hub</span></span> | <span data-ttu-id="80a90-184">Microsoft.Devices.DeviceCreated</span><span class="sxs-lookup"><span data-stu-id="80a90-184">Microsoft.Devices.DeviceCreated</span></span> | <span data-ttu-id="80a90-185">发布到 IoT 中心注册设备。</span><span class="sxs-lookup"><span data-stu-id="80a90-185">Published when a device is registered to an IoT hub.</span></span> |
| | <span data-ttu-id="80a90-186">Microsoft.Devices.DeviceDeleted</span><span class="sxs-lookup"><span data-stu-id="80a90-186">Microsoft.Devices.DeviceDeleted</span></span> | <span data-ttu-id="80a90-187">当设备从 IoT 中心删除时发布。</span><span class="sxs-lookup"><span data-stu-id="80a90-187">Published when a device is deleted from an IoT hub.</span></span> |
| <span data-ttu-id="80a90-188">资源组</span><span class="sxs-lookup"><span data-stu-id="80a90-188">Resource groups</span></span> | <span data-ttu-id="80a90-189">Microsoft.Resources.ResourceWriteSuccess</span><span class="sxs-lookup"><span data-stu-id="80a90-189">Microsoft.Resources.ResourceWriteSuccess</span></span> | <span data-ttu-id="80a90-190">引发时资源创建或更新操作成功。</span><span class="sxs-lookup"><span data-stu-id="80a90-190">Raised when a resource create or update operation succeeds.</span></span> |
| | <span data-ttu-id="80a90-191">Microsoft.Resources.ResourceWriteFailure</span><span class="sxs-lookup"><span data-stu-id="80a90-191">Microsoft.Resources.ResourceWriteFailure</span></span> | <span data-ttu-id="80a90-192">在资源创建或更新操作失败时引发。</span><span class="sxs-lookup"><span data-stu-id="80a90-192">Raised when a resource create or update operation fails.</span></span> |
| | <span data-ttu-id="80a90-193">Microsoft.Resources.ResourceWriteCancel</span><span class="sxs-lookup"><span data-stu-id="80a90-193">Microsoft.Resources.ResourceWriteCancel</span></span> | <span data-ttu-id="80a90-194">引发时资源创建或更新操作已取消。</span><span class="sxs-lookup"><span data-stu-id="80a90-194">Raised when a resource create or update operation is canceled.</span></span> |
| | <span data-ttu-id="80a90-195">Microsoft.Resources.ResourceDeleteSuccess</span><span class="sxs-lookup"><span data-stu-id="80a90-195">Microsoft.Resources.ResourceDeleteSuccess</span></span> | <span data-ttu-id="80a90-196">当资源删除操作成功时引发。</span><span class="sxs-lookup"><span data-stu-id="80a90-196">Raised when a resource delete operation succeeds.</span></span> |
| | <span data-ttu-id="80a90-197">Microsoft.Resources.ResourceDeleteFailure</span><span class="sxs-lookup"><span data-stu-id="80a90-197">Microsoft.Resources.ResourceDeleteFailure</span></span> | <span data-ttu-id="80a90-198">当资源删除操作失败时引发。</span><span class="sxs-lookup"><span data-stu-id="80a90-198">Raised when a resource delete operation fails.</span></span> |
| | <span data-ttu-id="80a90-199">Microsoft.Resources.ResourceDeleteCancel</span><span class="sxs-lookup"><span data-stu-id="80a90-199">Microsoft.Resources.ResourceDeleteCancel</span></span> | <span data-ttu-id="80a90-200">取消资源删除操作时引发。</span><span class="sxs-lookup"><span data-stu-id="80a90-200">Raised when a resource delete operation is canceled.</span></span> <span data-ttu-id="80a90-201">取消模板部署时会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="80a90-201">This event happens when a template deployment is canceled.</span></span> |

<span data-ttu-id="80a90-202">有关详细信息，请参阅[Azure 事件网格事件架构](https://docs.microsoft.com/azure/event-grid/event-schema)。</span><span class="sxs-lookup"><span data-stu-id="80a90-202">For more information, see [Azure Event Grid event schema](https://docs.microsoft.com/azure/event-grid/event-schema).</span></span>

<span data-ttu-id="80a90-203">可以从任何类型的应用程序，甚至是在本地运行的一个来访问事件网格。</span><span class="sxs-lookup"><span data-stu-id="80a90-203">You can access Event Grid from any type of application, even one that runs on-premises.</span></span>

## <a name="conclusion"></a><span data-ttu-id="80a90-204">结束语</span><span class="sxs-lookup"><span data-stu-id="80a90-204">Conclusion</span></span>

<span data-ttu-id="80a90-205">在这一章中您学习了有关 Azure 无服务器平台，其中包含 Azure Functions、 逻辑应用和事件网格。</span><span class="sxs-lookup"><span data-stu-id="80a90-205">In this chapter you learned about the Azure serverless platform that is composed of Azure Functions, Logic Apps, and Event Grid.</span></span> <span data-ttu-id="80a90-206">您可以使用这些资源生成一个完全无服务器应用程序体系结构，或创建与其他云资源进行交互和本地服务器上的混合解决方案。</span><span class="sxs-lookup"><span data-stu-id="80a90-206">You can use these resources to build an entirely serverless app architecture, or create a hybrid solution that interacts with other cloud resources and on-premises servers.</span></span> <span data-ttu-id="80a90-207">如结合无服务器的数据平台[Azure SQL](https://docs.microsoft.com/azure/sql-database)或[CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction)，可以生成完全托管的云本机应用程序。</span><span class="sxs-lookup"><span data-stu-id="80a90-207">Combined with a serverless data platform such as [Azure SQL](https://docs.microsoft.com/azure/sql-database) or [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction), you can build fully managed cloud native applications.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="80a90-208">推荐的资源</span><span class="sxs-lookup"><span data-stu-id="80a90-208">Recommended resources</span></span>

* [<span data-ttu-id="80a90-209">应用服务计划</span><span class="sxs-lookup"><span data-stu-id="80a90-209">App service plans</span></span>](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
* [<span data-ttu-id="80a90-210">Application Insights</span><span class="sxs-lookup"><span data-stu-id="80a90-210">Application Insights</span></span>](https://docs.microsoft.com/azure/application-insights)
* [<span data-ttu-id="80a90-211">Application Insights 分析</span><span class="sxs-lookup"><span data-stu-id="80a90-211">Application Insights Analytics</span></span>](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
* [<span data-ttu-id="80a90-212">Azure:将应用迁移到使用无服务器 Azure Functions 在云中</span><span class="sxs-lookup"><span data-stu-id="80a90-212">Azure: Bring your app to the cloud with serverless Azure Functions</span></span>](https://channel9.msdn.com/events/Connect/2017/E102)
* [<span data-ttu-id="80a90-213">Azure 事件网格</span><span class="sxs-lookup"><span data-stu-id="80a90-213">Azure Event Grid</span></span>](https://docs.microsoft.com/azure/event-grid/overview)
* [<span data-ttu-id="80a90-214">Azure 事件网格事件架构</span><span class="sxs-lookup"><span data-stu-id="80a90-214">Azure Event Grid event schema</span></span>](https://docs.microsoft.com/azure/event-grid/event-schema)
* [<span data-ttu-id="80a90-215">Azure 事件中心</span><span class="sxs-lookup"><span data-stu-id="80a90-215">Azure Event Hubs</span></span>](https://docs.microsoft.com/azure/event-hubs)
* [<span data-ttu-id="80a90-216">Azure Functions 文档</span><span class="sxs-lookup"><span data-stu-id="80a90-216">Azure Functions documentation</span></span>](https://docs.microsoft.com/azure/azure-functions)
* [<span data-ttu-id="80a90-217">Azure Functions 触发器和绑定概念</span><span class="sxs-lookup"><span data-stu-id="80a90-217">Azure Functions triggers and bindings concepts</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
* [<span data-ttu-id="80a90-218">Azure 逻辑应用</span><span class="sxs-lookup"><span data-stu-id="80a90-218">Azure Logic Apps</span></span>](https://docs.microsoft.com/azure/logic-apps)
* [<span data-ttu-id="80a90-219">Azure 服务总线</span><span class="sxs-lookup"><span data-stu-id="80a90-219">Azure Service Bus</span></span>](https://docs.microsoft.com/azure/service-bus-messaging)
* [<span data-ttu-id="80a90-220">Azure 表存储</span><span class="sxs-lookup"><span data-stu-id="80a90-220">Azure Table Storage</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
* [<span data-ttu-id="80a90-221">比较函数 1.x 和 2.x</span><span class="sxs-lookup"><span data-stu-id="80a90-221">Compare functions 1.x and 2.x</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-versions)
* [<span data-ttu-id="80a90-222">连接到使用 Azure 本地数据网关的本地数据源</span><span class="sxs-lookup"><span data-stu-id="80a90-222">Connecting to on-premises data sources with Azure On-premises Data Gateway</span></span>](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
* [<span data-ttu-id="80a90-223">在 Azure 门户中创建第一个函数</span><span class="sxs-lookup"><span data-stu-id="80a90-223">Create your first function in the Azure portal</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
* [<span data-ttu-id="80a90-224">创建使用 Azure CLI 将第一个函数</span><span class="sxs-lookup"><span data-stu-id="80a90-224">Create your first function using the Azure CLI</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
* [<span data-ttu-id="80a90-225">创建第一个函数使用 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="80a90-225">Create your first function using Visual Studio</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
* [<span data-ttu-id="80a90-226">函数支持的语言</span><span class="sxs-lookup"><span data-stu-id="80a90-226">Functions supported languages</span></span>](https://docs.microsoft.com/azure/azure-functions/supported-languages)
* [<span data-ttu-id="80a90-227">监视 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="80a90-227">Monitor Azure Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)
* [<span data-ttu-id="80a90-228">使用 Azure Functions 代理</span><span class="sxs-lookup"><span data-stu-id="80a90-228">Work with Azure Functions Proxies</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-proxies)

>[!div class="step-by-step"]
><span data-ttu-id="80a90-229">[上一页](logic-apps.md)
>[下一页](durable-azure-functions.md)</span><span class="sxs-lookup"><span data-stu-id="80a90-229">[Previous](logic-apps.md)
[Next](durable-azure-functions.md)</span></span>
