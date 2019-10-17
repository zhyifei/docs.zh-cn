---
title: Application Insights-无服务器应用
description: Application Insights 是一种无服务器诊断平台，使开发人员能够检测、会审和诊断 web 应用、移动应用、桌面应用和微服务中的问题。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7c1013ac029645a2da44aaf1c3b6ba74ca3f3dde
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522744"
---
# <a name="telemetry-with-application-insights"></a>具有 Application Insights 的遥测

[Application Insights](https://docs.microsoft.com/azure/application-insights)是一种无服务器诊断平台，使开发人员能够检测、会审和诊断 web 应用、移动应用、桌面应用和微服务中的问题。 只需在门户中翻转交换机，就可以打开函数应用 Application Insights。 Application Insights 提供所有这些功能，而无需配置服务器或设置自己的数据库。 所有 Application Insights 功能都作为服务提供，可自动与你的应用集成。

![Application Insights 徽标](./media/application-insights-logo.png)

向现有应用程序添加 Application Insights 与将检测密钥添加到应用程序的设置一样简单。 通过 Application Insights 您可以：

- 基于诸如函数调用数、运行函数所用的时间、异常等指标创建自定义图表和警报
- 分析失败和服务器异常
- 按操作深化性能并测量调用第三方依赖项所用的时间
- 监视托管函数应用的所有服务器上的 CPU 使用情况、内存和速率
- 查看实时指标，包括函数应用的请求计数和延迟
- 使用[分析](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)搜索、查询和创建对函数数据的自定义图表

![指标资源管理器](./media/metrics-explorer.png)

除了内置遥测，还可以生成自定义遥测。 以下代码片段使用为函数应用设置的检测密钥来创建自定义遥测客户端：

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

以下代码测量将新行插入[Azure 表存储](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)实例所花费的时间：

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

将显示生成的性能图：

![自定义遥测](./media/custom-telemetry.png)

自定义遥测显示插入新行的平均时间为32.6 毫秒。

Application Insights 提供了一种强大而方便的方法来记录有关无服务器应用程序的详细遥测数据。 你可以完全控制所提供的跟踪和日志记录级别。 可以跟踪自定义统计信息，如事件、依赖项和页面视图。 最后，利用强大的分析功能，您可以编写查询来询问重要问题并生成图表和高级见解。

有关详细信息，请参阅[Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)。

>[!div class="step-by-step"]
>[上一页](azure-functions.md)
>[下一页](logic-apps.md)
