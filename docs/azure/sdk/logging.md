---
title: 使用 .NET 的 Azure SDK 进行日志记录
description: 了解如何使用 .NET 客户端库的 Azure SDK 启用日志记录
ms.date: 03/20/2020
ms.custom: azure-sdk-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: b277045a60ef5cc065d77dad84878872dedc963e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433222"
---
# <a name="logging-with-the-azure-sdk-for-net"></a>使用 .NET 的 Azure SDK 进行日志记录

.NET 客户端库的[Azure SDK](https://azure.microsoft.com/downloads/)包括记录客户端库操作的能力。 这允许您监视客户端库对 Azure 服务执行的 I/O 请求和响应。 通常，日志用于调试或诊断通信问题。 本文介绍了使用 .NET 的 Azure SDK 启用日志记录的三种方法：

- 登录到控制台窗口
- 登录到 .NET 诊断跟踪
- 配置自定义日志记录

> [!IMPORTANT]
> 本文适用于使用最新版本的 Azure SDK 的客户端库。 要查看是否支持库，请参阅[Azure SDK 最新版本](https://azure.github.io/azure-sdk/releases/latest/index.html)的列表。 如果应用程序使用的是 Azure SDK 客户端库的旧版本，请参阅适用的服务文档中的特定说明。

## <a name="log-information"></a>记录信息

SDK 会记录以下信息，对参数查询和标头值进行清理以删除个人数据。

HTTP 请求日志条目：

- 唯一 ID
- HTTP 方法
- URI
- 传出请求标头

HTTP 响应日志条目：

- I/O 操作的持续时间（已过的时间）
- 请求 ID
- HTTP 状态代码
- HTTP 原因短语
- 响应标头
- 错误信息（如果适用）

对于请求和响应内容：

- 内容流作为文本或字节，具体取决于内容类型标头。
     > [!注* 默认情况下禁用内容日志记录。 要启用它，在`Diagnostics.IsLoggingContentEnabled``true`中`ClientOptions`设置为 。

事件日志通常以以下三个级别之一输出：

- 请求和响应事件的信息
- 错误警告
- 详细邮件和内容日志记录的冗长

## <a name="enable-logging-with-built-in-methods"></a>使用内置方法启用日志记录

.NET 客户端的 Azure SDK 通过[`EventSource`类](/dotnet/api/system.diagnostics.tracing.eventsource)将事件记录到 Windows 事件跟踪 （ETW），这是 .NET 的典型情况。 事件源允许您在应用程序代码中使用结构化日志记录，但性能开销最小。 要访问这些事件日志，您需要注册事件侦听器。

SDK 包括`Azure.Core.Diagnostics.AzureEventSourceListener`类（在 Azure.Core NuGet 包中定义），其中包含两个静态方法，可简化 .NET 应用程序的全面`CreateConsoleLogger`日志记录`CreateTraceLogger`：和 。 这些方法采用指定日志级别的可选参数。

### <a name="log-to-the-console-window"></a>登录到控制台窗口

.NET 客户端库的 Azure SDK 的核心原则是简化实时查看全面日志的能力。 该方法`CreateConsoleLogger`允许您使用一行代码将日志发送到控制台窗口：

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a>登录到诊断跟踪

如果实现跟踪侦听器，则可以使用 方法`CreateTraceLogger`登录到标准 .NET 事件跟踪机制 （）。[`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing) 有关 .NET 中事件跟踪的详细信息，请参阅[跟踪侦听器](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners)。 此示例指定详细日志级别：

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a>配置自定义日志记录

如上所述，您需要注册事件侦听器才能从 .NET 的 Azure SDK 接收日志消息。 如果不想使用上面简化的方法实现全面日志记录，则可以构造`AzureEventSourceListener`类的实例，并传递您编写的回调函数。 此方法将收到日志消息，您可以处理所需的日志消息。 此外，在构造实例时，可以指定要包括的日志级别。

下面的示例创建一个事件侦听器，该侦听器使用自定义消息登录到控制台，并筛选到级别详细内容的 Azure 核心事件。

```csharp
using AzureEventSourceListener listener = new AzureEventSourceListener((e, message) =>
    {
        // Only log messages from Azure-Core event source
        if (e.EventSource.Name == "Azure-Core")
        {
            Console.WriteLine($"{DateTime.Now} {message}");
        }
    },
    level: EventLevel.Verbose);
```

## <a name="next-steps"></a>后续步骤

- [为 Azure 应用服务中的应用启用诊断日志记录](https://docs.microsoft.com/azure/app-service/troubleshoot-diagnostic-logs)
- 查看[Azure 安全日志记录和审核](https://docs.microsoft.com/azure/security/fundamentals/log-audit)选项
- 了解如何使用 Azure[平台日志](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)
- 阅读有关[.NET 核心日志记录和跟踪的更多内容](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)
