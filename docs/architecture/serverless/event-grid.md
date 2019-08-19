---
title: Azure 事件网格-无服务器应用
description: Azure 事件网格是一种无服务器解决方案, 用于在每个事件的每个服务上进行大规模的事件传递和路由。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4970130ede0c96c645129ee6c8c7d54cb1114042
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577570"
---
# <a name="event-grid"></a>事件网格

[Azure 事件网格](/azure/event-grid/overview)为基于事件的应用程序提供无服务器基础结构。 你可以从任何源发布到事件网格, 并从任何平台使用消息。 事件网格还提供对 Azure 资源中的事件的内置支持, 以简化与应用程序的集成。 例如, 你可以订阅 blob 存储事件, 以在上传文件时通知应用。 然后, 应用程序可以发布由其他云或本地应用程序使用的自定义事件网格消息。 生成事件网格是为了可靠地处理大规模。 您可以获得发布和订阅消息的好处, 而无需设置所需的基础结构。

![事件网格徽标](./media/event-grid-logo.png)

事件网格的主要功能包括:

* 完全托管的事件路由。
* 大规模实时事件交付。
* Azure 内部和外部的广泛覆盖面。

## <a name="scenarios"></a>方案

事件网格解决了几种不同的情况。 本部分介绍三个最常见的部分。

### <a name="ops-automation"></a>Ops 自动化

![Ops 自动化](./media/ops-automation.png)

通过在预配基础结构时通知[Azure 自动化](https://docs.microsoft.com/azure/automation), 事件网格可帮助加快自动化并简化策略强制执行。

### <a name="application-integration"></a>应用程序集成

![应用程序集成](./media/app-integration.png)

您可以使用事件网格将您的应用程序连接到其他服务。 使用标准 HTTP 协议, 甚至可以轻松修改旧应用, 以便发布事件网格消息。 Web 挂钩适用于其他服务和平台使用事件网格消息。

### <a name="serverless-apps"></a>无服务器应用

![无服务器应用](./media/serverless-apps.png)

事件网格可以触发 Azure Functions、逻辑应用或您自己的自定义代码。 使用事件网格的主要好处是在事件发生时使用*推送*机制来发送消息。 推送体系结构消耗的资源更少, 并且比*轮询*机制更好。 轮询必须定期检查更新。

## <a name="event-grid-vs-other-azure-messaging-services"></a>事件网格与其他 Azure 消息传递服务

Azure 提供了多种消息服务, 包括[事件中心](https://docs.microsoft.com/azure/event-hubs)和[服务总线](https://docs.microsoft.com/azure/service-bus-messaging)。 每个设计用于处理一组特定用例。 下图对服务之间的差异进行了高级概述。

![Azure 消息传送比较](./media/azure-messaging-services.png)

有关更深入的比较, 请参阅[比较消息传递服务](https://docs.microsoft.com/azure/event-grid/compare-messaging-services)。

## <a name="performance-targets"></a>性能目标

使用事件网格, 可以利用以下性能保证:

* 亚秒级中的端到端延迟。
* 99.99% 的可用性。
* 每个区域每秒10000000事件。
* 100000000每个区域订阅。
* 50-ms 发布服务器延迟。
* 24小时重试, 并在1天窗口中以指数方式重试以保证送达。
* 透明的区域故障转移。

## <a name="event-grid-schema"></a>事件网格架构

事件网格使用标准架构来包装自定义事件。 架构类似于包装自定义数据元素的信封。 下面是事件网格消息示例:

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

除`data`属性外, 消息的所有内容都是标准的。 你可以检查消息, 并使用`eventType`和`dataVersion`来反序列化有效负载部分。

## <a name="azure-resources"></a>Azure 资源

使用事件网格的主要好处是 Azure 生成的自动消息。 在 Azure 中, 资源自动发布到允许你订阅各种事件的*主题*。 下表列出了可自动使用的资源类型、消息类型和事件。

| Azure 资源 | 事件类型 | 描述 |
| -------------- | ---------- | ----------- |
| Azure 订阅 | Microsoft.Resources.ResourceWriteSuccess | 当资源创建或更新操作成功时引发。 |
| | Microsoft.Resources.ResourceWriteFailure | 当资源创建或更新操作失败时引发。 |
| | Microsoft.Resources.ResourceWriteCancel | 在取消资源创建或更新操作时引发。 |
|  | Microsoft.Resources.ResourceDeleteSuccess | 在资源删除操作成功时引发。 |
|  | Microsoft.Resources.ResourceDeleteFailure | 在资源删除操作失败时引发。 |
| | Microsoft.Resources.ResourceDeleteCancel | 在取消资源删除操作时引发。 取消模板部署时发生此事件。 |
| Blob 存储 | Microsoft.Storage.BlobCreated | 创建 blob 时引发。 |
| | Microsoft.Storage.BlobDeleted | 删除 blob 时引发。 |
| 事件中心 | Microsoft.EventHub.CaptureFileCreated | 创建捕获文件时引发。
| IoT 中心 | Microsoft.Devices.DeviceCreated | 当设备注册到 IoT 中心时发布。 |
| | Microsoft.Devices.DeviceDeleted | 从 IoT 中心删除设备时发布。 |
| 资源组 | Microsoft.Resources.ResourceWriteSuccess | 当资源创建或更新操作成功时引发。 |
| | Microsoft.Resources.ResourceWriteFailure | 当资源创建或更新操作失败时引发。 |
| | Microsoft.Resources.ResourceWriteCancel | 在取消资源创建或更新操作时引发。 |
| | Microsoft.Resources.ResourceDeleteSuccess | 在资源删除操作成功时引发。 |
| | Microsoft.Resources.ResourceDeleteFailure | 在资源删除操作失败时引发。 |
| | Microsoft.Resources.ResourceDeleteCancel | 在取消资源删除操作时引发。 取消模板部署时发生此事件。 |

有关详细信息, 请参阅[Azure 事件网格事件架构](https://docs.microsoft.com/azure/event-grid/event-schema)。

你可以从任何类型的应用程序 (甚至是在本地运行的应用程序) 访问事件网格。

## <a name="conclusion"></a>结束语

在本章中, 你了解了由 Azure Functions、逻辑应用和事件网格组成的 Azure 无服务器平台。 你可以使用这些资源来构建完全无服务器的应用程序体系结构, 或创建与其他云资源和本地服务器交互的混合解决方案。 与无服务器数据平台 (如[AZURE SQL](https://docs.microsoft.com/azure/sql-database)或[CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction)) 结合使用, 可以构建完全托管的云本机应用程序。

## <a name="recommended-resources"></a>推荐的资源

* [应用服务计划](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
* [Application Insights](https://docs.microsoft.com/azure/application-insights)
* [Application Insights 分析](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
* [Microsoft利用无服务器 Azure Functions 将你的应用引入云](https://channel9.msdn.com/events/Connect/2017/E102)
* [Azure 事件网格](https://docs.microsoft.com/azure/event-grid/overview)
* [Azure 事件网格事件架构](https://docs.microsoft.com/azure/event-grid/event-schema)
* [Azure 事件中心](https://docs.microsoft.com/azure/event-hubs)
* [Azure Functions 文档](https://docs.microsoft.com/azure/azure-functions)
* [Azure Functions 触发器和绑定概念](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
* [Azure 逻辑应用](https://docs.microsoft.com/azure/logic-apps)
* [Azure 服务总线](https://docs.microsoft.com/azure/service-bus-messaging)
* [Azure 表存储](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
* [比较函数1.x 和2。x](https://docs.microsoft.com/azure/azure-functions/functions-versions)
* [通过 Azure 本地数据网关连接到本地数据源](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
* [在 Azure 门户中创建第一个函数](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
* [使用 Azure CLI 创建第一个函数](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
* [使用 Visual Studio 创建第一个函数](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
* [函数支持的语言](https://docs.microsoft.com/azure/azure-functions/supported-languages)
* [监视 Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)
* [使用 Azure Functions 代理](https://docs.microsoft.com/azure/azure-functions/functions-proxies)

>[!div class="step-by-step"]
>[上一页](logic-apps.md)
>[下一页](durable-azure-functions.md)
