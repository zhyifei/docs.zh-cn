---
ms.openlocfilehash: c861d61cbbe8075db4b17a702e863336ea621f2b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198357"
---
### <a name="http-synchronous-io-disabled-in-all-servers"></a><span data-ttu-id="86f2d-101">HTTP：所有服务器均禁用同步 IO</span><span class="sxs-lookup"><span data-stu-id="86f2d-101">HTTP: Synchronous IO disabled in all servers</span></span>

<span data-ttu-id="86f2d-102">从 ASP.NET Core 3.0 开始，默认将禁用同步服务器操作。</span><span class="sxs-lookup"><span data-stu-id="86f2d-102">Starting with ASP.NET Core 3.0, synchronous server operations are disabled by default.</span></span>

#### <a name="change-description"></a><span data-ttu-id="86f2d-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="86f2d-103">Change description</span></span>

<span data-ttu-id="86f2d-104">`AllowSynchronousIO` 是每台服务器中包含的一个选项，用于启用或禁用同步 IO API，如 `HttpRequest.Body.Read`、`HttpResponse.Body.Write` 和 `Stream.Flush`。</span><span class="sxs-lookup"><span data-stu-id="86f2d-104">`AllowSynchronousIO` is an option in each server that enables or disables synchronous IO APIs like `HttpRequest.Body.Read`, `HttpResponse.Body.Write`, and `Stream.Flush`.</span></span> <span data-ttu-id="86f2d-105">这些 API 长期以来一直是线程不足和应用挂起的根源。</span><span class="sxs-lookup"><span data-stu-id="86f2d-105">These APIs have long been a source of thread starvation and app hangs.</span></span> <span data-ttu-id="86f2d-106">从 ASP.NET Core 3.0 预览版 3 开始，默认将禁用这些同步操作。</span><span class="sxs-lookup"><span data-stu-id="86f2d-106">Starting in ASP.NET Core 3.0 Preview 3, these synchronous operations are disabled by default.</span></span>

<span data-ttu-id="86f2d-107">受影响的服务器：</span><span class="sxs-lookup"><span data-stu-id="86f2d-107">Affected servers:</span></span>

- <span data-ttu-id="86f2d-108">Kestrel</span><span class="sxs-lookup"><span data-stu-id="86f2d-108">Kestrel</span></span>
- <span data-ttu-id="86f2d-109">HttpSys</span><span class="sxs-lookup"><span data-stu-id="86f2d-109">HttpSys</span></span>
- <span data-ttu-id="86f2d-110">IIS（进程内）</span><span class="sxs-lookup"><span data-stu-id="86f2d-110">IIS in-process</span></span>
- <span data-ttu-id="86f2d-111">TestServer</span><span class="sxs-lookup"><span data-stu-id="86f2d-111">TestServer</span></span>

<span data-ttu-id="86f2d-112">错误应如下所示：</span><span class="sxs-lookup"><span data-stu-id="86f2d-112">Expect errors similar to:</span></span>

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

<span data-ttu-id="86f2d-113">每台服务器都有一个 `AllowSynchronousIO` 选项，该选项控制此行为，且它们的默认值当前为 `false`。</span><span class="sxs-lookup"><span data-stu-id="86f2d-113">Each server has an `AllowSynchronousIO` option that controls this behavior and the default for all of them is now `false`.</span></span>

<span data-ttu-id="86f2d-114">作为一种临时缓解措施，还可以根据每个请求重写该行为。</span><span class="sxs-lookup"><span data-stu-id="86f2d-114">The behavior can also be overridden on a per-request basis as a temporary mitigation.</span></span> <span data-ttu-id="86f2d-115">例如:</span><span class="sxs-lookup"><span data-stu-id="86f2d-115">For example:</span></span>

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

<span data-ttu-id="86f2d-116">如果调用 `Dispose` 中同步 API 的 `TextWriter` 或另一个流出现问题，请改为调用新的 `DisposeAsync` API。</span><span class="sxs-lookup"><span data-stu-id="86f2d-116">If you have trouble with a `TextWriter` or another stream calling a synchronous API in `Dispose`, call the new `DisposeAsync` API instead.</span></span>

<span data-ttu-id="86f2d-117">有关讨论，请参阅 [aspnet/AspNetCore#7644](https://github.com/aspnet/AspNetCore/issues/7644)。</span><span class="sxs-lookup"><span data-stu-id="86f2d-117">For discussion, see [aspnet/AspNetCore#7644](https://github.com/aspnet/AspNetCore/issues/7644).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="86f2d-118">引入的版本</span><span class="sxs-lookup"><span data-stu-id="86f2d-118">Version introduced</span></span>

<span data-ttu-id="86f2d-119">3.0</span><span class="sxs-lookup"><span data-stu-id="86f2d-119">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="86f2d-120">旧行为</span><span class="sxs-lookup"><span data-stu-id="86f2d-120">Old behavior</span></span>

<span data-ttu-id="86f2d-121">默认情况下允许 `HttpRequest.Body.Read`、`HttpResponse.Body.Write` 和 `Stream.Flush`。</span><span class="sxs-lookup"><span data-stu-id="86f2d-121">`HttpRequest.Body.Read`, `HttpResponse.Body.Write`, and `Stream.Flush` were allowed by default.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="86f2d-122">新行为</span><span class="sxs-lookup"><span data-stu-id="86f2d-122">New behavior</span></span>

<span data-ttu-id="86f2d-123">默认情况下，不允许使用这些同步 API：</span><span class="sxs-lookup"><span data-stu-id="86f2d-123">These synchronous APIs are disallowed by default:</span></span>

<span data-ttu-id="86f2d-124">错误应如下所示：</span><span class="sxs-lookup"><span data-stu-id="86f2d-124">Expect errors similar to:</span></span>

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

#### <a name="reason-for-change"></a><span data-ttu-id="86f2d-125">更改原因</span><span class="sxs-lookup"><span data-stu-id="86f2d-125">Reason for change</span></span>

<span data-ttu-id="86f2d-126">这些同步 API 长期以来一直是线程不足和应用挂起的根源。</span><span class="sxs-lookup"><span data-stu-id="86f2d-126">These synchronous APIs have long been a source of thread starvation and app hangs.</span></span> <span data-ttu-id="86f2d-127">从 ASP.NET Core 3.0 预览版 3 开始，默认将禁用同步操作。</span><span class="sxs-lookup"><span data-stu-id="86f2d-127">Starting in ASP.NET Core 3.0 Preview 3, the synchronous operations are disabled by default.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="86f2d-128">建议的操作</span><span class="sxs-lookup"><span data-stu-id="86f2d-128">Recommended action</span></span>

<span data-ttu-id="86f2d-129">使用这些方法的异步版本。</span><span class="sxs-lookup"><span data-stu-id="86f2d-129">Use the asynchronous versions of the methods.</span></span> <span data-ttu-id="86f2d-130">作为一种临时缓解措施，还可以根据每个请求重写该行为。</span><span class="sxs-lookup"><span data-stu-id="86f2d-130">The behavior can also be overridden on a per-request basis as a temporary mitigation.</span></span>

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

#### <a name="category"></a><span data-ttu-id="86f2d-131">类别</span><span class="sxs-lookup"><span data-stu-id="86f2d-131">Category</span></span>

<span data-ttu-id="86f2d-132">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="86f2d-132">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="86f2d-133">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="86f2d-133">Affected APIs</span></span>

- <xref:System.IO.Stream.Flush%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.IO.Stream.Flush`
- `Overload:System.IO.Stream.Read`
- `Overload:System.IO.Stream.Write`

-->
