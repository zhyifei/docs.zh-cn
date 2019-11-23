---
title: 模块、处理程序和中间件
description: 了解如何处理模块、处理程序和中间件的 HTTP 请求。
author: danroth27
ms.author: daroth
ms.date: 10/11/2019
ms.openlocfilehash: b0be6109b9226bddbb9cbe4cebf114fd2b2a6114
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2019
ms.locfileid: "73841203"
---
# <a name="modules-handlers-and-middleware"></a><span data-ttu-id="d79b8-103">模块、处理程序和中间件</span><span class="sxs-lookup"><span data-stu-id="d79b8-103">Modules, handlers, and middleware</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="d79b8-104">ASP.NET Core 应用基于一系列中间件构建。</span><span class="sxs-lookup"><span data-stu-id="d79b8-104">An ASP.NET Core app is built upon a series of middleware.</span></span> <span data-ttu-id="d79b8-105">中间件是一些处理程序，它们排列在管道中以处理请求和响应。</span><span class="sxs-lookup"><span data-stu-id="d79b8-105">Middlewares are handlers, which are arranged into a pipeline to handle requests and responses.</span></span> <span data-ttu-id="d79b8-106">在 Web 窗体应用程序中，HTTP 处理程序和模块解决了类似的问题。</span><span class="sxs-lookup"><span data-stu-id="d79b8-106">In a Web Forms app, HTTP handlers and modules solve similar problems.</span></span> <span data-ttu-id="d79b8-107">在 ASP.NET Core 中，模块、处理程序、 *Global.asax.cs*和应用程序生命周期替换为中间件。</span><span class="sxs-lookup"><span data-stu-id="d79b8-107">In ASP.NET Core, modules, handlers, *Global.asax.cs*, and the app life cycle are replaced with middleware.</span></span> <span data-ttu-id="d79b8-108">在本章中，你将了解 Blazor 应用上下文中的中间件。</span><span class="sxs-lookup"><span data-stu-id="d79b8-108">In this chapter, you'll learn what middleware in the context of a Blazor app.</span></span>

## <a name="overview"></a><span data-ttu-id="d79b8-109">概述</span><span class="sxs-lookup"><span data-stu-id="d79b8-109">Overview</span></span>

<span data-ttu-id="d79b8-110">ASP.NET Core 请求管道包含一系列请求委托，依次调用。</span><span class="sxs-lookup"><span data-stu-id="d79b8-110">The ASP.NET Core request pipeline consists of a sequence of request delegates, called one after the other.</span></span> <span data-ttu-id="d79b8-111">下图演示了这一概念。</span><span class="sxs-lookup"><span data-stu-id="d79b8-111">The following diagram demonstrates the concept.</span></span> <span data-ttu-id="d79b8-112">沿黑色箭头执行。</span><span class="sxs-lookup"><span data-stu-id="d79b8-112">The thread of execution follows the black arrows.</span></span>

![管道 (pipeline)](media/middleware/request-delegate-pipeline.png)

<span data-ttu-id="d79b8-114">前面的关系图缺少生命周期事件的概念。</span><span class="sxs-lookup"><span data-stu-id="d79b8-114">The preceding diagram lacks a concept of lifecycle events.</span></span> <span data-ttu-id="d79b8-115">此概念是处理 ASP.NET Web 窗体请求的基础。</span><span class="sxs-lookup"><span data-stu-id="d79b8-115">This concept is foundational to how ASP.NET Web Forms requests are handled.</span></span> <span data-ttu-id="d79b8-116">此系统使你可以更轻松地处理正在进行的过程，并允许在任意点插入中间件。</span><span class="sxs-lookup"><span data-stu-id="d79b8-116">This system makes it easier to reason about what process is occurring and allows middleware to be inserted at any point.</span></span> <span data-ttu-id="d79b8-117">中间件按其添加到请求管道中的顺序执行。</span><span class="sxs-lookup"><span data-stu-id="d79b8-117">Middleware executes in the order in which it's added to the request pipeline.</span></span> <span data-ttu-id="d79b8-118">它们还添加在代码中，而不是配置文件中，通常在*Startup.cs*中。</span><span class="sxs-lookup"><span data-stu-id="d79b8-118">They're also added in code instead of configuration files, usually in *Startup.cs*.</span></span>

## <a name="katana"></a><span data-ttu-id="d79b8-119">Katana</span><span class="sxs-lookup"><span data-stu-id="d79b8-119">Katana</span></span>

<span data-ttu-id="d79b8-120">熟悉 Katana 的读者在 ASP.NET Core 中感觉非常熟悉。</span><span class="sxs-lookup"><span data-stu-id="d79b8-120">Readers familiar with Katana will feel comfortable in ASP.NET Core.</span></span> <span data-ttu-id="d79b8-121">事实上，Katana 是从中派生 ASP.NET Core 的框架。</span><span class="sxs-lookup"><span data-stu-id="d79b8-121">In fact, Katana is a framework from which ASP.NET Core derives.</span></span> <span data-ttu-id="d79b8-122">它为 ASP.NET 1.x 引入了类似的中间件和管道模式。</span><span class="sxs-lookup"><span data-stu-id="d79b8-122">It introduced similar middleware and pipeline patterns for ASP.NET 4.x.</span></span> <span data-ttu-id="d79b8-123">为 Katana 设计的中间件可以改编为使用 ASP.NET Core 管道。</span><span class="sxs-lookup"><span data-stu-id="d79b8-123">Middleware designed for Katana can be adapted to work with the ASP.NET Core pipeline.</span></span>

## <a name="common-middleware"></a><span data-ttu-id="d79b8-124">常见中间件</span><span class="sxs-lookup"><span data-stu-id="d79b8-124">Common middleware</span></span>

<span data-ttu-id="d79b8-125">ASP.NET 4.x 包含许多模块。</span><span class="sxs-lookup"><span data-stu-id="d79b8-125">ASP.NET 4.x includes many modules.</span></span> <span data-ttu-id="d79b8-126">同样，ASP.NET Core 还提供了许多中间件组件。</span><span class="sxs-lookup"><span data-stu-id="d79b8-126">In a similar fashion, ASP.NET Core has many middleware components available as well.</span></span> <span data-ttu-id="d79b8-127">在某些情况下，可以使用 ASP.NET Core 的 IIS 模块。</span><span class="sxs-lookup"><span data-stu-id="d79b8-127">IIS modules may be used in some cases with ASP.NET Core.</span></span> <span data-ttu-id="d79b8-128">在其他情况下，可以使用本机 ASP.NET Core 中间件。</span><span class="sxs-lookup"><span data-stu-id="d79b8-128">In other cases, native ASP.NET Core middleware may be available.</span></span>

<span data-ttu-id="d79b8-129">下表列出了 ASP.NET Core 中的替换中间件和组件。</span><span class="sxs-lookup"><span data-stu-id="d79b8-129">The following table lists replacement middleware and components in ASP.NET Core.</span></span>

|<span data-ttu-id="d79b8-130">模块</span><span class="sxs-lookup"><span data-stu-id="d79b8-130">Module</span></span>                 |<span data-ttu-id="d79b8-131">ASP.NET 4.x 模块</span><span class="sxs-lookup"><span data-stu-id="d79b8-131">ASP.NET 4.x module</span></span>           |<span data-ttu-id="d79b8-132">ASP.NET Core 选项</span><span class="sxs-lookup"><span data-stu-id="d79b8-132">ASP.NET Core option</span></span>|
|-----------------------|-----------------------------|-------------------|
|<span data-ttu-id="d79b8-133">HTTP 错误</span><span class="sxs-lookup"><span data-stu-id="d79b8-133">HTTP errors</span></span>            |`CustomErrorModule`          |[<span data-ttu-id="d79b8-134">状态代码页中间件</span><span class="sxs-lookup"><span data-stu-id="d79b8-134">Status Code Pages Middleware</span></span>](/aspnet/core/fundamentals/error-handling#usestatuscodepages)|
|<span data-ttu-id="d79b8-135">默认文档</span><span class="sxs-lookup"><span data-stu-id="d79b8-135">Default document</span></span>       |`DefaultDocumentModule`      |[<span data-ttu-id="d79b8-136">默认文件中间件</span><span class="sxs-lookup"><span data-stu-id="d79b8-136">Default Files Middleware</span></span>](/aspnet/core/fundamentals/static-files#serve-a-default-document)|
|<span data-ttu-id="d79b8-137">目录浏览</span><span class="sxs-lookup"><span data-stu-id="d79b8-137">Directory browsing</span></span>     |`DirectoryListingModule`     |[<span data-ttu-id="d79b8-138">目录浏览中间件</span><span class="sxs-lookup"><span data-stu-id="d79b8-138">Directory Browsing Middleware</span></span>](/aspnet/core/fundamentals/static-files#enable-directory-browsing)|
|<span data-ttu-id="d79b8-139">动态压缩</span><span class="sxs-lookup"><span data-stu-id="d79b8-139">Dynamic compression</span></span>    |`DynamicCompressionModule`   |[<span data-ttu-id="d79b8-140">响应压缩中间件</span><span class="sxs-lookup"><span data-stu-id="d79b8-140">Response Compression Middleware</span></span>](/aspnet/core/performance/response-compression)|
|<span data-ttu-id="d79b8-141">失败请求跟踪</span><span class="sxs-lookup"><span data-stu-id="d79b8-141">Failed requests tracing</span></span>|`FailedRequestsTracingModule`|[<span data-ttu-id="d79b8-142">ASP.NET Core 日志记录</span><span class="sxs-lookup"><span data-stu-id="d79b8-142">ASP.NET Core Logging</span></span>](/aspnet/core/fundamentals/logging/index#tracesource-provider)|
|<span data-ttu-id="d79b8-143">文件缓存</span><span class="sxs-lookup"><span data-stu-id="d79b8-143">File caching</span></span>           |`FileCacheModule`            |[<span data-ttu-id="d79b8-144">响应缓存中间件</span><span class="sxs-lookup"><span data-stu-id="d79b8-144">Response Caching Middleware</span></span>](/aspnet/core/performance/caching/middleware)|
|<span data-ttu-id="d79b8-145">HTTP 缓存</span><span class="sxs-lookup"><span data-stu-id="d79b8-145">HTTP caching</span></span>           |`HttpCacheModule`            |[<span data-ttu-id="d79b8-146">响应缓存中间件</span><span class="sxs-lookup"><span data-stu-id="d79b8-146">Response Caching Middleware</span></span>](/aspnet/core/performance/caching/middleware)|
|<span data-ttu-id="d79b8-147">HTTP 日志记录</span><span class="sxs-lookup"><span data-stu-id="d79b8-147">HTTP logging</span></span>           |`HttpLoggingModule`          |[<span data-ttu-id="d79b8-148">ASP.NET Core 日志记录</span><span class="sxs-lookup"><span data-stu-id="d79b8-148">ASP.NET Core Logging</span></span>](/aspnet/core/fundamentals/logging/index)|
|<span data-ttu-id="d79b8-149">HTTP 重定向</span><span class="sxs-lookup"><span data-stu-id="d79b8-149">HTTP redirection</span></span>       |`HttpRedirectionModule`      |[<span data-ttu-id="d79b8-150">URL 重写中间件</span><span class="sxs-lookup"><span data-stu-id="d79b8-150">URL Rewriting Middleware</span></span>](/aspnet/core/fundamentals/url-rewriting)|
|<span data-ttu-id="d79b8-151">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="d79b8-151">ISAPI filters</span></span>          |`IsapiFilterModule`          |[<span data-ttu-id="d79b8-152">中间件</span><span class="sxs-lookup"><span data-stu-id="d79b8-152">Middleware</span></span>](/aspnet/core/fundamentals/middleware/index)|
|<span data-ttu-id="d79b8-153">ISAPI</span><span class="sxs-lookup"><span data-stu-id="d79b8-153">ISAPI</span></span>                  |`IsapiModule`                |[<span data-ttu-id="d79b8-154">中间件</span><span class="sxs-lookup"><span data-stu-id="d79b8-154">Middleware</span></span>](/aspnet/core/fundamentals/middleware/index)|
|<span data-ttu-id="d79b8-155">请求筛选</span><span class="sxs-lookup"><span data-stu-id="d79b8-155">Request filtering</span></span>      |`RequestFilteringModule`     |[<span data-ttu-id="d79b8-156">URL 重写中间件 IRule</span><span class="sxs-lookup"><span data-stu-id="d79b8-156">URL Rewriting Middleware IRule</span></span>](/aspnet/core/fundamentals/url-rewriting#irule-based-rule)|
|<span data-ttu-id="d79b8-157">URL 重写&#8224;</span><span class="sxs-lookup"><span data-stu-id="d79b8-157">URL rewriting&#8224;</span></span>   |`RewriteModule`              |[<span data-ttu-id="d79b8-158">URL 重写中间件</span><span class="sxs-lookup"><span data-stu-id="d79b8-158">URL Rewriting Middleware</span></span>](/aspnet/core/fundamentals/url-rewriting)|
|<span data-ttu-id="d79b8-159">静态压缩</span><span class="sxs-lookup"><span data-stu-id="d79b8-159">Static compression</span></span>     |`StaticCompressionModule`    |[<span data-ttu-id="d79b8-160">响应压缩中间件</span><span class="sxs-lookup"><span data-stu-id="d79b8-160">Response Compression Middleware</span></span>](/aspnet/core/performance/response-compression)|
|<span data-ttu-id="d79b8-161">静态内容</span><span class="sxs-lookup"><span data-stu-id="d79b8-161">Static content</span></span>         |`StaticFileModule`           |[<span data-ttu-id="d79b8-162">静态文件中间件</span><span class="sxs-lookup"><span data-stu-id="d79b8-162">Static File Middleware</span></span>](/aspnet/core/fundamentals/static-files)|
|<span data-ttu-id="d79b8-163">URL 身份验证</span><span class="sxs-lookup"><span data-stu-id="d79b8-163">URL authorization</span></span>      |`UrlAuthorizationModule`     |[<span data-ttu-id="d79b8-164">ASP.NET Core 标识</span><span class="sxs-lookup"><span data-stu-id="d79b8-164">ASP.NET Core Identity</span></span>](/aspnet/core/security/authentication/identity)|

<span data-ttu-id="d79b8-165">此列表并不详尽，但应了解两个框架之间存在的映射。</span><span class="sxs-lookup"><span data-stu-id="d79b8-165">This list isn't exhaustive but should give an idea of what mapping exists between the two frameworks.</span></span> <span data-ttu-id="d79b8-166">有关更详细的列表，请参阅[带有 ASP.NET Core 的 IIS 模块](/aspnet/core/host-and-deploy/iis/modules)。</span><span class="sxs-lookup"><span data-stu-id="d79b8-166">For a more detailed list, see [IIS modules with ASP.NET Core](/aspnet/core/host-and-deploy/iis/modules).</span></span>

## <a name="custom-middleware"></a><span data-ttu-id="d79b8-167">自定义中间件</span><span class="sxs-lookup"><span data-stu-id="d79b8-167">Custom middleware</span></span>

<span data-ttu-id="d79b8-168">内置中间件可能无法处理应用所需的所有方案。</span><span class="sxs-lookup"><span data-stu-id="d79b8-168">Built-in middleware may not handle all scenarios needed for an app.</span></span> <span data-ttu-id="d79b8-169">在这种情况下，创建自己的中间件是有意义的。</span><span class="sxs-lookup"><span data-stu-id="d79b8-169">In such cases, it makes sense to create your own middleware.</span></span> <span data-ttu-id="d79b8-170">定义中间件的方式有多种，最简单的方法是使用简单的委托。</span><span class="sxs-lookup"><span data-stu-id="d79b8-170">There are multiple ways of defining middleware, with the simplest being a simple delegate.</span></span> <span data-ttu-id="d79b8-171">请考虑以下中间件，它接受来自查询字符串的区域性请求：</span><span class="sxs-lookup"><span data-stu-id="d79b8-171">Consider the following middleware, which accepts a culture request from a query string:</span></span>

```csharp
public class Startup
{
    public void Configure(IApplicationBuilder app)
    {
        app.Use(async (context, next) =>
        {
            var cultureQuery = context.Request.Query["culture"];

            if (!string.IsNullOrWhiteSpace(cultureQuery))
            {
                var culture = new CultureInfo(cultureQuery);

                CultureInfo.CurrentCulture = culture;
                CultureInfo.CurrentUICulture = culture;
            }

            // Call the next delegate/middleware in the pipeline
            await next();
        });

        app.Run(async (context) =>
            await context.Response.WriteAsync(
                $"Hello {CultureInfo.CurrentCulture.DisplayName}"));
    }
}
```

<span data-ttu-id="d79b8-172">还可以通过实现 `IMiddleware` 接口或按中间件约定将中间件定义为类。</span><span class="sxs-lookup"><span data-stu-id="d79b8-172">Middleware can also be defined as class, either by implementing the `IMiddleware` interface or by following middleware convention.</span></span> <span data-ttu-id="d79b8-173">有关详细信息，请参阅[编写自定义 ASP.NET Core 中间件](/aspnet/core/fundamentals/middleware/write)。</span><span class="sxs-lookup"><span data-stu-id="d79b8-173">For more information, see [Write custom ASP.NET Core middleware](/aspnet/core/fundamentals/middleware/write).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d79b8-174">[上一页](data.md)
>[下一页](config.md)</span><span class="sxs-lookup"><span data-stu-id="d79b8-174">[Previous](data.md)
[Next](config.md)</span></span>
