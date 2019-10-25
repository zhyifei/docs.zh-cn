---
ms.openlocfilehash: ae5a5fbf97ed4a03de7d35b9d5d5ca8de3aebc39
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394233"
---
### <a name="caching-responsecaching-pubternal-types-changed-to-internal"></a><span data-ttu-id="4cdb8-101">缓存：ResponseCaching“Pubternal”类型已更改为内部</span><span class="sxs-lookup"><span data-stu-id="4cdb8-101">Caching: ResponseCaching "pubternal" types changed to internal</span></span>

<span data-ttu-id="4cdb8-102">在 ASP.NET Core 3.0 中，`ResponseCaching` 中的“pubternal”类型已更改为 `internal`。</span><span class="sxs-lookup"><span data-stu-id="4cdb8-102">In ASP.NET Core 3.0, "pubternal" types in `ResponseCaching` have been changed to `internal`.</span></span>

<span data-ttu-id="4cdb8-103">此外，`IResponseCachingPolicyProvider` 和 `IResponseCachingKeyProvider` 的默认实现不再作为 `AddResponseCaching` 方法的一部分添加到服务。</span><span class="sxs-lookup"><span data-stu-id="4cdb8-103">In addition, default implementations of `IResponseCachingPolicyProvider` and `IResponseCachingKeyProvider` are no longer added to services as part of the `AddResponseCaching` method.</span></span>

#### <a name="change-description"></a><span data-ttu-id="4cdb8-104">更改描述</span><span class="sxs-lookup"><span data-stu-id="4cdb8-104">Change description</span></span>

<span data-ttu-id="4cdb8-105">在 ASP.NET Core 中，“pubternal”类型声明为 `public`，但驻留在后缀为 `.Internal` 的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="4cdb8-105">In ASP.NET Core, "pubternal" types are declared as `public` but reside in a namespace suffixed with `.Internal`.</span></span> <span data-ttu-id="4cdb8-106">尽管这些类型为 public，但它们没有支持策略，可能会发生中断性变更。</span><span class="sxs-lookup"><span data-stu-id="4cdb8-106">While these types are public, they have no support policy and are subject to breaking changes.</span></span> <span data-ttu-id="4cdb8-107">遗憾的是，经常会意外使用这些类型，导致对这些项目做出中断性变更，并使维护框架的能力受到限制。</span><span class="sxs-lookup"><span data-stu-id="4cdb8-107">Unfortunately, accidental use of these types has been common, resulting in breaking changes to these projects and limiting the ability to maintain the framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4cdb8-108">引入的版本</span><span class="sxs-lookup"><span data-stu-id="4cdb8-108">Version introduced</span></span>

<span data-ttu-id="4cdb8-109">3.0</span><span class="sxs-lookup"><span data-stu-id="4cdb8-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="4cdb8-110">旧行为</span><span class="sxs-lookup"><span data-stu-id="4cdb8-110">Old behavior</span></span>

<span data-ttu-id="4cdb8-111">这些类型公开可见，但不受支持。</span><span class="sxs-lookup"><span data-stu-id="4cdb8-111">These types were publicly visible, but unsupported.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="4cdb8-112">新行为</span><span class="sxs-lookup"><span data-stu-id="4cdb8-112">New behavior</span></span>

<span data-ttu-id="4cdb8-113">这些类型现在为 `internal`。</span><span class="sxs-lookup"><span data-stu-id="4cdb8-113">These types are now `internal`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="4cdb8-114">更改原因</span><span class="sxs-lookup"><span data-stu-id="4cdb8-114">Reason for change</span></span>

<span data-ttu-id="4cdb8-115">`internal` 范围更好地反映了不受支持的策略。</span><span class="sxs-lookup"><span data-stu-id="4cdb8-115">The `internal` scope better reflects the unsupported policy.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4cdb8-116">建议的操作</span><span class="sxs-lookup"><span data-stu-id="4cdb8-116">Recommended action</span></span>

<span data-ttu-id="4cdb8-117">复制应用或库使用的类型。</span><span class="sxs-lookup"><span data-stu-id="4cdb8-117">Copy types that are used by your app or library.</span></span>

#### <a name="category"></a><span data-ttu-id="4cdb8-118">类别</span><span class="sxs-lookup"><span data-stu-id="4cdb8-118">Category</span></span>

<span data-ttu-id="4cdb8-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4cdb8-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4cdb8-120">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="4cdb8-120">Affected APIs</span></span>

- `Microsoft.AspNetCore.ResponseCaching.Internal.CachedResponse`
- `Microsoft.AspNetCore.ResponseCaching.Internal.CachedVaryByRules`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCacheEntry`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider`
- `Microsoft.AspNetCore.ResponseCaching.Internal.MemoryResponseCache`
- `Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingContext`
- `Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingKeyProvider`
- `Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingPolicyProvider`
- <xref:Microsoft.AspNetCore.ResponseCaching.ResponseCachingMiddleware.%23ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.ResponseCaching.ResponseCachingOptions},Microsoft.Extensions.Logging.ILoggerFactory,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.ResponseCaching.Internal.CachedResponse`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.CachedVaryByRules`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCacheEntry`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.MemoryResponseCache`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingContext`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingKeyProvider`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingPolicyProvider`
- `M:Microsoft.AspNetCore.ResponseCaching.ResponseCachingMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.ResponseCaching.ResponseCachingOptions},Microsoft.Extensions.Logging.ILoggerFactory,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider)",
"nameWithType": "ResponseCachingMiddleware.ResponseCachingMiddleware(RequestDelegate, IOptions<ResponseCachingOptions>, ILoggerFactory, IResponseCachingPolicyProvider, IResponseCache, IResponseCachingKeyProvider)`

-->
