---
title: 应用程序性能管理-适用于 WCF 开发人员的 gRPC
description: ASP.NET Core gRPC 应用程序的日志记录、指标和跟踪。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 6ba67fd069e7efc232f912e50c0e283facb79e9c
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841683"
---
# <a name="application-performance-management"></a>应用程序性能管理

在 Kubernetes 等新式生产环境中，能够监视应用程序以确保它们以最佳状态运行非常重要。 类似于日志记录和指标的问题从未太重要。 ASP.NET Core （包括 gRPC）对生成和管理日志消息和指标数据以及*跟踪*数据具有一流支持。 本部分将更详细地探讨这些方面。

## <a name="logging-vs-metrics"></a>日志记录 vs 指标

在查看实现细节之前，必须了解日志记录和指标之间的差异。

日志记录与文本消息相关，这些文本消息记录了有关系统中所发生内容的详细信息。 日志消息可能包含异常数据，如堆栈跟踪或提供消息上下文的结构化数据。 日志记录输出通常写入到可搜索的文本存储。

度量值是指设计为使用面板中的图表和图形进行聚合并显示的数字数据，它提供了应用程序整体运行状况和性能的视图。 指标数据还可用于在超过阈值时触发自动警报。 以下列表显示了指标数据的一些示例：

- 处理请求所用的时间。
- 服务实例每秒处理的请求数。
- 实例上失败的请求数。

## <a name="logging-in-aspnet-core-grpc"></a>ASP.NET Core gRPC 中的日志记录

ASP.NET Core 提供对日志记录的内置支持，采用的形式为：[记录](https://www.nuget.org/packages/Microsoft.Extensions.Logging)NuGet 包。 此库的核心部分随 Web SDK 一起提供，因此不需要手动安装它。 默认情况下，日志消息会写入标准输出（"控制台"）和任何附加的调试器。 若要将日志写入永久性外部数据存储，你可能需要导入[可选的日志记录接收器包](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0#third-party-logging-providers)。

ASP.NET Core gRPC 框架将详细的诊断日志记录消息写入此日志记录框架，以便可以将其与应用程序的消息一起进行处理/存储。

### <a name="produce-log-messages"></a>生成日志消息

日志记录扩展会自动注册 ASP.NET Core 的依赖项注入系统，因此，你可以将记录器指定为 gRPC 服务类型上的构造函数参数。

```csharp
public class StockData : Stocks.StocksBase
{
    private readonly ILogger<StockData> _logger;

    public StockData(ILogger<StockData> logger)
    {
        _logger = logger;
    }
}
```

与请求、异常等有关的许多日志消息由 ASP.NET Core 和 gRPC 框架组件提供。 添加自己的日志消息，提供有关应用程序逻辑的详细信息和上下文，而不是更低级别的问题。

有关编写日志消息和可用日志记录接收器和目标的详细信息，请参阅[在 .Net Core 中进行日志记录和 ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0)一文。

## <a name="metrics-in-aspnet-core-grpc"></a>ASP.NET Core gRPC 中的指标

.NET Core 运行时提供一组用于发出和观察指标的组件，其中包括诸如 <xref:System.Diagnostics.Tracing.EventSource> 和 <xref:System.Diagnostics.Tracing.EventCounter> 类的 Api。 这些 Api 可用于发出基本数值数据，外部进程可使用这些数据，如[dotnet 全局工具](https://github.com/dotnet/diagnostics/blob/master/documentation/dotnet-counters-instructions.md)或 Windows 事件跟踪。 有关在自己的代码中使用 `EventCounter` 的详细信息，请参阅[EventCounter 简介](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md)教程。

对于更高级的度量值，以及将指标数据写入更广泛的数据存储，有一个称为 "[应用指标](https://www.app-metrics.io)" 的优秀开源项目。 此库套件提供了一组广泛的类型来检测你的代码。 它还提供了用于将指标写入不同类型目标的包，这些目标包括时间序列数据库，如 Prometheus 和 InfluxDB、 [Azure 应用程序 Insights](https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview)等。 [AspNetCore](https://www.nuget.org/packages/App.Metrics.AspNetCore.Mvc/) NuGet 包甚至添加了一组综合的基本指标，这些指标是通过与 ASP.NET Core 框架的集成自动生成的，而网站提供了用于使用[Grafana](https://grafana.com/)可视化平台显示这些指标的[模板](https://www.app-metrics.io/samples/grafana/)。

有关应用指标的详细信息和文档，请参阅[app-metrics.io](https://app-metrics.io)网站。

### <a name="produce-metrics"></a>生成指标

大多数指标平台支持5种基本类型的指标，如下表所示：

| 度量值类型 | 描述 |
| ----------- | ----------- |
| 计数器     | 跟踪发生某些情况（如请求、错误等）的频率。 |
| 衡量       | 记录随时间变化的单个值，如活动连接。 |
| 而言   | 度量跨任意限制的值的分布。 例如，直方图可以跟踪数据集的大小，计算包含多少 < 10 个记录，多少11-100 和101-1000，以及 > 1000 条记录。 |
| 进度表       | 度量事件在不同时间范围内的发生速率。 |
| 计时器       | 跟踪事件的持续时间以及事件发生的速率（以直方图形式存储）。 |

使用*应用指标*，可通过依赖关系注入获取 `IMetrics` 接口，并用于记录 gRPC 服务的任何指标。 下面的示例演示如何计算一段时间内发出的 `Get` 请求数：

```csharp
public class StockData : Stocks.StocksBase
{
    private static readonly CounterOptions GetRequestCounter = new CounterOptions
    {
        Name = "StockData_Get_Requests",
        MeasurementUnit = Unit.Calls
    };

    private readonly IStockRepository _repository;
    private readonly IMetrics _metrics;

    public StockData(IStockRepository repository, IMetrics metrics)
    {
        _repository = repository;
        _metrics = metrics;
    }

    public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
    {
        _metrics.Measure.Counter.Increment(GetRequestCounter);

        // Serve request...
    }
}
```

### <a name="store-and-visualize-metrics-data"></a>存储和可视化指标数据

存储度量值数据的最佳方式是在时序*数据库*中，这是一个专用的数据存储，用于记录用时间戳标记的数值数据系列。 这些数据库最常见的是[Prometheus](https://prometheus.io/)和[InfluxDB](https://www.influxdata.com/products/influxdb-overview/)。 Microsoft Azure 还通过[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview)服务提供专用的度量值存储。

用于可视化度量数据的当前走向解决方案是[Grafana](https://grafana.com)，可与各种存储提供程序（包括 Azure Monitor、InfluxDB 和 Prometheus）配合使用。 下图显示了一个示例 Grafana 仪表板，该仪表板显示运行 StockData 示例的 Linkerd service 网格中的指标：

![Grafana 仪表板](media/application-performance-management/grafana-screenshot.png)

### <a name="metrics-based-alerting"></a>基于指标的警报

度量值数据的数值性质意味着它非常适合用于驱动警报系统，并在某个值超出某些定义的容差时通知开发人员或支持工程师。 已提到的平台都通过各种选项（包括电子邮件、短信或仪表板中的可视化效果）提供警报支持。

## <a name="distributed-tracing"></a>分布式跟踪

*分布式跟踪*是一种相对较新的监视开发，它怀疑于不断使用微服务和分布式体系结构。 来自客户端浏览器、应用程序或设备的单个请求可能分为多个步骤和子请求，并涉及到跨网络使用许多服务。 这使得难以将日志消息和指标与触发它们的特定请求关联起来。 分布式跟踪将标识符应用于允许日志和指标与特定操作相关联的请求。 这类似于[WCF 的端到端跟踪](https://docs.microsoft.com/dotnet/framework/wcf/diagnostics/tracing/end-to-end-tracing)，但应用于多个平台。

尽管它仍是一个 nascent 的技术领域，但分布式跟踪在受欢迎程度上迅速增长，现在正在经历标准化过程。 云本机计算基础创建了[开放跟踪标准](https://opentracing.io)，尝试为使用后端（如[JAEGER](https://www.jaegertracing.io/)和[弹性 APM](https://www.elastic.co/products/apm)）提供与供应商无关的库。 同时，Google 创建了[OpenCensus 项目](https://opencensus.io/)来处理相同的一组问题。 这两个项目现在正在合并到一个新项目[OpenTelemetry](https://opentelemetry.io)中，该项目旨在成为未来的行业标准。

### <a name="how-distributed-tracing-works"></a>分布式跟踪的工作原理

分布式跟踪基于*跨越*的概念：已命名的计时操作，这些操作是单个*跟踪*的一部分，这可能涉及在系统的多个节点上进行处理。 当启动新操作时，将使用唯一标识符创建跟踪。 对于每个子操作，会使用其自己的标识符和跟踪标识符来创建一个跨度。 当请求在系统中传递时，各组件可以创建包括其*父*范围的标识符的*子*范围。 一个范围包含一个*上下文*，其中包含跟踪和范围标识符，以及键/值对（称为*行李*）形式的有用数据。

### <a name="distributed-tracing-with-diagnosticsource"></a>用 DiagnosticSource 进行分布式跟踪

.NET Core 有一个内部模块，该模块适用于分布式跟踪和跨越： [DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md#diagnosticsource-users-guide)。 除了提供一种在一个进程内生成和使用诊断的简单方法，`DiagnosticSource` 模块具有活动的概念，该*活动*实际上是分布式跟踪的实现或跟踪内的跨度。 模块的内部机制负责父子活动（包括分配标识符）。 有关使用 `Activity` 类型的详细信息，请参阅[GitHub 上的活动用户指南](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/ActivityUserGuide.md#activity-user-guide)

由于 DiagnosticSource 是核心框架的一部分，因此它受多个核心组件（包括 <xref:System.Net.Http.HttpClient>、Entity Framework Core 和 ASP.NET Core）的支持，包括 gRPC 框架中的显式支持。 当 ASP.NET Core 收到请求时，它将检查与[W3C 跟踪上下文](https://www.w3.org/TR/trace-context)标准匹配的一对 HTTP 标头。 如果找到了标头，则使用标识值和标头中的上下文启动活动。 如果未找到任何标头，则会启动一个活动，其中生成的标识值与标准格式匹配。 在此活动的生存期内，由框架或应用程序代码生成的任何诊断，都可以用 trace 和 span 标识符进行标记。 `HttpClient` 支持通过检查每个请求的当前活动并自动将跟踪标头添加到传出请求，进一步扩展了此功能。

ASP.NET Core gRPC 客户端和服务器库包括对 DiagnosticSource 和活动的显式支持，并将创建活动并自动应用和使用标头信息。

> [!NOTE]
> 仅当*侦听器*使用诊断信息时，才会发生这种情况。 如果没有侦听器，则不会写入任何诊断，也不会创建任何活动。

### <a name="add-your-own-diagnosticsources-and-activities"></a>添加自己的 DiagnosticSources 和活动

尽管 ASP.NET Core 会自动生成良好的数据量（包括 gRPC）以及 Entity Framework Core 和 `HttpClient`，但你可能希望在应用程序代码中添加自己的诊断或创建显式范围。 有关如何实现自己的诊断的详细信息，请参阅[DiagnosticSource 用户指南](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md#instrumenting-with-diagnosticsourcediagnosticlistener)和[活动用户指南](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/ActivityUserGuide.md#activity-usage)。

### <a name="store-distributed-trace-data"></a>存储分布式跟踪数据

撰写 OpenTelemetry 项目时仍处于早期阶段，并且只有 alpha 质量的包可用于 .NET 应用程序。 OpenTracing 项目提供更成熟的库，但它们会在将来被 OpenTelemetry 库取代。

下面介绍了 OpenTracing API。 如果希望在应用程序中使用较新的 OpenTelemetry API，请参阅[GitHub 上的 OpenTelemetry .NET SDK 存储库](https://github.com/open-telemetry/opentelemetry-dotnet)。

#### <a name="use-the-opentracing-package-to-store-distributed-trace-data"></a>使用 OpenTracing 包存储分布式跟踪数据

支持所有 OpenTracing 相容后端的[OpenTracing NuGet 包](https://www.nuget.org/packages/OpenTracing/)（可独立于 `DiagnosticSource`）使用。 还有一个来自 OpenTracing API 贡献项目的其他包[OpenTracing. Contrib NetCore](https://www.nuget.org/packages/OpenTracing.Contrib.NetCore/)，它添加一个 `DiagnosticSource` 侦听器，并自动将事件和活动写入后端。 启用此包非常简单，只是从 NuGet 安装它并将其作为服务添加到 `Startup` 类中。

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddOpenTracing();
    }
}
```

OpenTracing 包是抽象层，因此它需要特定于后端的实现。 OpenTracing API 实现适用于以下开源后端。

| “属性” | Package | 网站 |
| ---- | ------- | -------- |
| Jaeger | [Jaeger](https://www.nuget.org/packages/Jaeger/) | [jaegertracing.io](https://jaegertracing.io) |
| 弹性 APM | [NetCoreAll](https://www.nuget.org/packages/Elastic.Apm.NetCoreAll/) | [elastic.co/products/apm](https://www.elastic.co/products/apm) |

有关适用于 .net 的 OpenTracing API 的详细信息，请参阅 GitHub 上的[OpenTracing C# ](https://github.com/opentracing/opentracing-csharp)和[OpenTracing C#Contrib/.NET Core](https://github.com/opentracing-contrib/csharp-netcore)存储库。

>[!div class="step-by-step"]
>[上一页](load-balancing.md)
>[下一页](appendix.md)
