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
# <a name="logging-with-the-azure-sdk-for-net"></a><span data-ttu-id="c8fb9-103">使用 .NET 的 Azure SDK 进行日志记录</span><span class="sxs-lookup"><span data-stu-id="c8fb9-103">Logging with the Azure SDK for .NET</span></span>

<span data-ttu-id="c8fb9-104">.NET 客户端库的[Azure SDK](https://azure.microsoft.com/downloads/)包括记录客户端库操作的能力。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-104">The [Azure SDK](https://azure.microsoft.com/downloads/) for .NET client libraries includes the ability to log client library operations.</span></span> <span data-ttu-id="c8fb9-105">这允许您监视客户端库对 Azure 服务执行的 I/O 请求和响应。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-105">This allows you to monitor I/O requests and responses that client libraries are making to Azure services.</span></span> <span data-ttu-id="c8fb9-106">通常，日志用于调试或诊断通信问题。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-106">Typically, the logs are used to debug or diagnose communication issues.</span></span> <span data-ttu-id="c8fb9-107">本文介绍了使用 .NET 的 Azure SDK 启用日志记录的三种方法：</span><span class="sxs-lookup"><span data-stu-id="c8fb9-107">This article describes three approaches to enable logging with the Azure SDK for .NET:</span></span>

- <span data-ttu-id="c8fb9-108">登录到控制台窗口</span><span class="sxs-lookup"><span data-stu-id="c8fb9-108">Log to the console window</span></span>
- <span data-ttu-id="c8fb9-109">登录到 .NET 诊断跟踪</span><span class="sxs-lookup"><span data-stu-id="c8fb9-109">Log to .NET diagnostics traces</span></span>
- <span data-ttu-id="c8fb9-110">配置自定义日志记录</span><span class="sxs-lookup"><span data-stu-id="c8fb9-110">Configure custom logging</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8fb9-111">本文适用于使用最新版本的 Azure SDK 的客户端库。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-111">This article applies to client libraries that use the most recent versions of the Azure SDK for .NET.</span></span> <span data-ttu-id="c8fb9-112">要查看是否支持库，请参阅[Azure SDK 最新版本](https://azure.github.io/azure-sdk/releases/latest/index.html)的列表。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-112">To see if a library is supported, refer to the list of [Azure SDK latest releases](https://azure.github.io/azure-sdk/releases/latest/index.html).</span></span> <span data-ttu-id="c8fb9-113">如果应用程序使用的是 Azure SDK 客户端库的旧版本，请参阅适用的服务文档中的特定说明。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-113">If your application is using an older version of the Azure SDK client libraries, refer to specific instructions in the applicable service documentation.</span></span>

## <a name="log-information"></a><span data-ttu-id="c8fb9-114">记录信息</span><span class="sxs-lookup"><span data-stu-id="c8fb9-114">Log information</span></span>

<span data-ttu-id="c8fb9-115">SDK 会记录以下信息，对参数查询和标头值进行清理以删除个人数据。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-115">The SDK logs the following information, sanitizing parameter query and header values to remove personal data.</span></span>

<span data-ttu-id="c8fb9-116">HTTP 请求日志条目：</span><span class="sxs-lookup"><span data-stu-id="c8fb9-116">HTTP request log entry:</span></span>

- <span data-ttu-id="c8fb9-117">唯一 ID</span><span class="sxs-lookup"><span data-stu-id="c8fb9-117">Unique ID</span></span>
- <span data-ttu-id="c8fb9-118">HTTP 方法</span><span class="sxs-lookup"><span data-stu-id="c8fb9-118">HTTP method</span></span>
- <span data-ttu-id="c8fb9-119">URI</span><span class="sxs-lookup"><span data-stu-id="c8fb9-119">URI</span></span>
- <span data-ttu-id="c8fb9-120">传出请求标头</span><span class="sxs-lookup"><span data-stu-id="c8fb9-120">Outgoing request headers</span></span>

<span data-ttu-id="c8fb9-121">HTTP 响应日志条目：</span><span class="sxs-lookup"><span data-stu-id="c8fb9-121">HTTP response log entry:</span></span>

- <span data-ttu-id="c8fb9-122">I/O 操作的持续时间（已过的时间）</span><span class="sxs-lookup"><span data-stu-id="c8fb9-122">Duration of I/O operation (time elapsed)</span></span>
- <span data-ttu-id="c8fb9-123">请求 ID</span><span class="sxs-lookup"><span data-stu-id="c8fb9-123">Request ID</span></span>
- <span data-ttu-id="c8fb9-124">HTTP 状态代码</span><span class="sxs-lookup"><span data-stu-id="c8fb9-124">HTTP status code</span></span>
- <span data-ttu-id="c8fb9-125">HTTP 原因短语</span><span class="sxs-lookup"><span data-stu-id="c8fb9-125">HTTP reason phrase</span></span>
- <span data-ttu-id="c8fb9-126">响应标头</span><span class="sxs-lookup"><span data-stu-id="c8fb9-126">Response headers</span></span>
- <span data-ttu-id="c8fb9-127">错误信息（如果适用）</span><span class="sxs-lookup"><span data-stu-id="c8fb9-127">Error information, when applicable</span></span>

<span data-ttu-id="c8fb9-128">对于请求和响应内容：</span><span class="sxs-lookup"><span data-stu-id="c8fb9-128">For request and response content:</span></span>

- <span data-ttu-id="c8fb9-129">内容流作为文本或字节，具体取决于内容类型标头。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-129">Content stream as text or bytes depending on the Content-Type header.</span></span>
     > <span data-ttu-id="c8fb9-130">[!注\* 默认情况下禁用内容日志记录。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-130">[!NOTE} Content logging is disabled by default.</span></span> <span data-ttu-id="c8fb9-131">要启用它，在`Diagnostics.IsLoggingContentEnabled``true`中`ClientOptions`设置为 。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-131">To enable it, set `Diagnostics.IsLoggingContentEnabled` to `true` in `ClientOptions`.</span></span>

<span data-ttu-id="c8fb9-132">事件日志通常以以下三个级别之一输出：</span><span class="sxs-lookup"><span data-stu-id="c8fb9-132">Event logs are output usually at one of these three levels:</span></span>

- <span data-ttu-id="c8fb9-133">请求和响应事件的信息</span><span class="sxs-lookup"><span data-stu-id="c8fb9-133">Informational for request and response events</span></span>
- <span data-ttu-id="c8fb9-134">错误警告</span><span class="sxs-lookup"><span data-stu-id="c8fb9-134">Warning for errors</span></span>
- <span data-ttu-id="c8fb9-135">详细邮件和内容日志记录的冗长</span><span class="sxs-lookup"><span data-stu-id="c8fb9-135">Verbose for detailed messages and content logging</span></span>

## <a name="enable-logging-with-built-in-methods"></a><span data-ttu-id="c8fb9-136">使用内置方法启用日志记录</span><span class="sxs-lookup"><span data-stu-id="c8fb9-136">Enable logging with built-in methods</span></span>

<span data-ttu-id="c8fb9-137">.NET 客户端的 Azure SDK 通过[`EventSource`类](/dotnet/api/system.diagnostics.tracing.eventsource)将事件记录到 Windows 事件跟踪 （ETW），这是 .NET 的典型情况。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-137">The Azure SDK for .NET client libraries log events to Event Tracing for Windows (ETW) via the [`EventSource` class](/dotnet/api/system.diagnostics.tracing.eventsource), which is typical for .NET.</span></span> <span data-ttu-id="c8fb9-138">事件源允许您在应用程序代码中使用结构化日志记录，但性能开销最小。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-138">Event sources allow you to use structured logging in your application code with a minimal performance overhead.</span></span> <span data-ttu-id="c8fb9-139">要访问这些事件日志，您需要注册事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-139">To gain access to these event logs, you need to register event listeners.</span></span>

<span data-ttu-id="c8fb9-140">SDK 包括`Azure.Core.Diagnostics.AzureEventSourceListener`类（在 Azure.Core NuGet 包中定义），其中包含两个静态方法，可简化 .NET 应用程序的全面`CreateConsoleLogger`日志记录`CreateTraceLogger`：和 。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-140">The SDK includes the `Azure.Core.Diagnostics.AzureEventSourceListener` class (defined in the Azure.Core NuGet package), which contains two static methods that simplify comprehensive logging for your .NET application: `CreateConsoleLogger` and `CreateTraceLogger`.</span></span> <span data-ttu-id="c8fb9-141">这些方法采用指定日志级别的可选参数。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-141">These methods take an optional parameter that specifies a log level.</span></span>

### <a name="log-to-the-console-window"></a><span data-ttu-id="c8fb9-142">登录到控制台窗口</span><span class="sxs-lookup"><span data-stu-id="c8fb9-142">Log to the console window</span></span>

<span data-ttu-id="c8fb9-143">.NET 客户端库的 Azure SDK 的核心原则是简化实时查看全面日志的能力。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-143">A core tenet of the Azure SDK for .NET client libraries is to simplify the ability to view comprehensive logs in real time.</span></span> <span data-ttu-id="c8fb9-144">该方法`CreateConsoleLogger`允许您使用一行代码将日志发送到控制台窗口：</span><span class="sxs-lookup"><span data-stu-id="c8fb9-144">The `CreateConsoleLogger` method allows you to send logs to the console window with a single line of code:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a><span data-ttu-id="c8fb9-145">登录到诊断跟踪</span><span class="sxs-lookup"><span data-stu-id="c8fb9-145">Log to diagnostic traces</span></span>

<span data-ttu-id="c8fb9-146">如果实现跟踪侦听器，则可以使用 方法`CreateTraceLogger`登录到标准 .NET 事件跟踪机制 （）。[`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)</span><span class="sxs-lookup"><span data-stu-id="c8fb9-146">If you implement trace listeners, you can use the `CreateTraceLogger` method to log to the standard .NET event tracing mechanism ([`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)).</span></span> <span data-ttu-id="c8fb9-147">有关 .NET 中事件跟踪的详细信息，请参阅[跟踪侦听器](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners)。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-147">For more information on event tracing in .NET, see [Trace Listeners](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners).</span></span> <span data-ttu-id="c8fb9-148">此示例指定详细日志级别：</span><span class="sxs-lookup"><span data-stu-id="c8fb9-148">This example specifies a log level of verbose:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a><span data-ttu-id="c8fb9-149">配置自定义日志记录</span><span class="sxs-lookup"><span data-stu-id="c8fb9-149">Configure custom logging</span></span>

<span data-ttu-id="c8fb9-150">如上所述，您需要注册事件侦听器才能从 .NET 的 Azure SDK 接收日志消息。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-150">As mentioned above, you need to register event listeners to receive log messages from the Azure SDK for .NET.</span></span> <span data-ttu-id="c8fb9-151">如果不想使用上面简化的方法实现全面日志记录，则可以构造`AzureEventSourceListener`类的实例，并传递您编写的回调函数。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-151">If you don’t want to implement comprehensive logging using one the simplified methods above, you can construct an instance of the `AzureEventSourceListener` class and pass it a callback function that you write.</span></span> <span data-ttu-id="c8fb9-152">此方法将收到日志消息，您可以处理所需的日志消息。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-152">This method will receive log messages that you can process however you need to.</span></span> <span data-ttu-id="c8fb9-153">此外，在构造实例时，可以指定要包括的日志级别。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-153">In addition, when you construct the instance, you can specify the log levels to include.</span></span>

<span data-ttu-id="c8fb9-154">下面的示例创建一个事件侦听器，该侦听器使用自定义消息登录到控制台，并筛选到级别详细内容的 Azure 核心事件。</span><span class="sxs-lookup"><span data-stu-id="c8fb9-154">The following example creates an event listener that logs to the console with a custom message, and is filtered to Azure core events of the level verbose.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="c8fb9-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c8fb9-155">Next steps</span></span>

- [<span data-ttu-id="c8fb9-156">为 Azure 应用服务中的应用启用诊断日志记录</span><span class="sxs-lookup"><span data-stu-id="c8fb9-156">Enable diagnostics logging for apps in Azure App Service</span></span>](https://docs.microsoft.com/azure/app-service/troubleshoot-diagnostic-logs)
- <span data-ttu-id="c8fb9-157">查看[Azure 安全日志记录和审核](https://docs.microsoft.com/azure/security/fundamentals/log-audit)选项</span><span class="sxs-lookup"><span data-stu-id="c8fb9-157">Review [Azure security logging and auditing](https://docs.microsoft.com/azure/security/fundamentals/log-audit) options</span></span>
- <span data-ttu-id="c8fb9-158">了解如何使用 Azure[平台日志](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)</span><span class="sxs-lookup"><span data-stu-id="c8fb9-158">Learn how to work with [Azure platform logs](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)</span></span>
- <span data-ttu-id="c8fb9-159">阅读有关[.NET 核心日志记录和跟踪的更多内容](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)</span><span class="sxs-lookup"><span data-stu-id="c8fb9-159">Read more about [.NET Core logging and tracing](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)</span></span>
