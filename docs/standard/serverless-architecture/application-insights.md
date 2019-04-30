---
title: Application Insights-无服务器应用
description: Application Insights 是一个无服务器诊断平台，使开发人员能够检测、 会审和诊断 web 应用、 移动应用、 桌面应用程序和微服务中的问题。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: b4884d483de07c1c2077f7280b6b77c6059572c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051218"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="99c4d-103">使用 Application Insights 的遥测数据</span><span class="sxs-lookup"><span data-stu-id="99c4d-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="99c4d-104">[Application Insights](https://docs.microsoft.com/azure/application-insights)是一个无服务器诊断平台，使开发人员能够检测、 会审和诊断 web 应用、 移动应用、 桌面应用程序和微服务中的问题。</span><span class="sxs-lookup"><span data-stu-id="99c4d-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="99c4d-105">您可以启用 Application Insights 为函数应用只需通过在门户中扳动开关。</span><span class="sxs-lookup"><span data-stu-id="99c4d-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="99c4d-106">Application Insights 提供所有这些功能而无需配置服务器，或者设置您自己的数据库。</span><span class="sxs-lookup"><span data-stu-id="99c4d-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="99c4d-107">作为自动与您的应用程序集成的服务提供的所有 Application Insights 的功能。</span><span class="sxs-lookup"><span data-stu-id="99c4d-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![应用程序见解徽标](./media/application-insights-logo.png)

<span data-ttu-id="99c4d-109">将 Application Insights 添加到现有应用程序非常简单，只需作为将检测密钥添加到应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="99c4d-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="99c4d-110">使用 Application Insights，你可以：</span><span class="sxs-lookup"><span data-stu-id="99c4d-110">With Application Insights you can:</span></span>

* <span data-ttu-id="99c4d-111">创建自定义图表和警报基于指标，如函数调用数，运行一个函数和异常所需的时间</span><span class="sxs-lookup"><span data-stu-id="99c4d-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
* <span data-ttu-id="99c4d-112">分析故障和服务器异常</span><span class="sxs-lookup"><span data-stu-id="99c4d-112">Analyze failures and server exceptions</span></span>
* <span data-ttu-id="99c4d-113">操作通过钻取到性能和度量值来调用第三方依赖项所花费的时间</span><span class="sxs-lookup"><span data-stu-id="99c4d-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
* <span data-ttu-id="99c4d-114">监视托管函数应用的所有服务器上的 CPU 使用情况、 内存和费率</span><span class="sxs-lookup"><span data-stu-id="99c4d-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
* <span data-ttu-id="99c4d-115">查看指标，包括请求计数和延迟为函数应用的实时流</span><span class="sxs-lookup"><span data-stu-id="99c4d-115">View a live stream of metrics including request count and latency for your function apps</span></span>
* <span data-ttu-id="99c4d-116">使用[Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)要搜索，请查询，并对函数数据创建自定义图表</span><span class="sxs-lookup"><span data-stu-id="99c4d-116">Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![指标资源管理器](./media/metrics-explorer.png)

<span data-ttu-id="99c4d-118">除了内置的遥测数据，还有可能生成自定义遥测数据。</span><span class="sxs-lookup"><span data-stu-id="99c4d-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="99c4d-119">下面的代码段将创建使用设置为函数应用的检测密钥的自定义遥测客户端：</span><span class="sxs-lookup"><span data-stu-id="99c4d-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="99c4d-120">下面的代码度量值插入新行插入所需的时间长度[Azure 表存储](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)实例：</span><span class="sxs-lookup"><span data-stu-id="99c4d-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="99c4d-121">生成的性能图所示：</span><span class="sxs-lookup"><span data-stu-id="99c4d-121">The resulting performance graph is shown:</span></span>

![自定义遥测](./media/custom-telemetry.png)

<span data-ttu-id="99c4d-123">自定义遥测就会发现以插入新行的平均时间是 32.6 毫秒为单位。</span><span class="sxs-lookup"><span data-stu-id="99c4d-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="99c4d-124">Application Insights 提供强大而方便的方法来记录有关无服务器应用程序的详细遥测数据。</span><span class="sxs-lookup"><span data-stu-id="99c4d-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="99c4d-125">你可以完全控制的跟踪级别，提供的日志记录，它是。</span><span class="sxs-lookup"><span data-stu-id="99c4d-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="99c4d-126">你可以跟踪自定义统计信息，例如事件、 依赖项和页面视图。</span><span class="sxs-lookup"><span data-stu-id="99c4d-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="99c4d-127">最后，功能强大的分析，可以编写查询的重要提问并生成图表和高级的见解。</span><span class="sxs-lookup"><span data-stu-id="99c4d-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="99c4d-128">有关详细信息，请参阅[监视 Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)。</span><span class="sxs-lookup"><span data-stu-id="99c4d-128">For more information, see [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="99c4d-129">[上一页](azure-functions.md)
>[下一页](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="99c4d-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>