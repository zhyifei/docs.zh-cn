---
ms.openlocfilehash: b0e1d6d720a1c9b827fb4585606e64b545d395d7
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393886"
---
### <a name="kestrel-request-trailer-headers-moved-to-new-collection"></a><span data-ttu-id="83d5d-101">Kestrel：请求尾部标头已移动到新集合</span><span class="sxs-lookup"><span data-stu-id="83d5d-101">Kestrel: Request trailer headers moved to new collection</span></span>

<span data-ttu-id="83d5d-102">在以前的版本中，当读取请求正文直到结尾时，Kestrel 会将 HTTP/1.1 分块尾部标头添加到请求标头集合中。</span><span class="sxs-lookup"><span data-stu-id="83d5d-102">In prior versions, Kestrel added HTTP/1.1 chunked trailer headers into the request headers collection when the request body was read to the end.</span></span> <span data-ttu-id="83d5d-103">此行为将引发对标头和尾部之间存在不明确性的担忧。</span><span class="sxs-lookup"><span data-stu-id="83d5d-103">This behavior caused concerns about ambiguity between headers and trailers.</span></span> <span data-ttu-id="83d5d-104">因此，做出了将尾部移动到新集合的决定。</span><span class="sxs-lookup"><span data-stu-id="83d5d-104">The decision was made to move the trailers to a new collection.</span></span>

<span data-ttu-id="83d5d-105">HTTP/2 请求尾部在 ASP.NET Core 2.2 中不可用，但现在可用于 ASP.NET Core 3.0 的此新集合。</span><span class="sxs-lookup"><span data-stu-id="83d5d-105">HTTP/2 request trailers were unavailable in ASP.NET Core 2.2 but are now also available in this new collection in ASP.NET Core 3.0.</span></span>

<span data-ttu-id="83d5d-106">添加了新的请求扩展方法以访问这些尾部。</span><span class="sxs-lookup"><span data-stu-id="83d5d-106">New request extension methods have been added to access these trailers.</span></span>

<span data-ttu-id="83d5d-107">读取整个请求正文后，HTTP/1.1 尾部即可用。</span><span class="sxs-lookup"><span data-stu-id="83d5d-107">HTTP/1.1 trailers are available once the entire request body has been read.</span></span>

<span data-ttu-id="83d5d-108">从客户端收到 HTTP/2 尾部后，这些尾部即可用。</span><span class="sxs-lookup"><span data-stu-id="83d5d-108">HTTP/2 trailers are available once they're received from the client.</span></span> <span data-ttu-id="83d5d-109">客户端将不会发生尾部，直到整个请求正文至少已由服务器缓冲。</span><span class="sxs-lookup"><span data-stu-id="83d5d-109">The client won't send the trailers until the entire request body has been at least buffered by the server.</span></span> <span data-ttu-id="83d5d-110">可能需要读取请求正文，以释放缓冲区空间。</span><span class="sxs-lookup"><span data-stu-id="83d5d-110">You may need to read the request body to free up buffer space.</span></span> <span data-ttu-id="83d5d-111">如果读取请求正文直到结尾，则尾部始终可用。</span><span class="sxs-lookup"><span data-stu-id="83d5d-111">Trailers are always available if you read the request body to the end.</span></span> <span data-ttu-id="83d5d-112">尾部标记正文的结尾。</span><span class="sxs-lookup"><span data-stu-id="83d5d-112">The trailers mark the end of the body.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="83d5d-113">引入的版本</span><span class="sxs-lookup"><span data-stu-id="83d5d-113">Version introduced</span></span>

<span data-ttu-id="83d5d-114">3.0</span><span class="sxs-lookup"><span data-stu-id="83d5d-114">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="83d5d-115">旧行为</span><span class="sxs-lookup"><span data-stu-id="83d5d-115">Old behavior</span></span>

<span data-ttu-id="83d5d-116">请求尾部标头将添加到 `HttpRequest.Headers` 集合中。</span><span class="sxs-lookup"><span data-stu-id="83d5d-116">Request trailer headers would be added to the `HttpRequest.Headers` collection.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="83d5d-117">新行为</span><span class="sxs-lookup"><span data-stu-id="83d5d-117">New behavior</span></span>

<span data-ttu-id="83d5d-118">请求尾部标头在  `HttpRequest.Headers` 集合中不存在。</span><span class="sxs-lookup"><span data-stu-id="83d5d-118">Request trailer headers **aren't present** in the `HttpRequest.Headers` collection.</span></span> <span data-ttu-id="83d5d-119">在 `HttpRequest` 上使用以下扩展方法来访问它们：</span><span class="sxs-lookup"><span data-stu-id="83d5d-119">Use the following extension methods on `HttpRequest` to access them:</span></span>

- <span data-ttu-id="83d5d-120">`GetDeclaredTrailers()` - 获取列出了正文后应具有的尾部的请求“尾部”标头。</span><span class="sxs-lookup"><span data-stu-id="83d5d-120">`GetDeclaredTrailers()` - Gets the request "Trailer" header that lists which trailers to expect after the body.</span></span>
- <span data-ttu-id="83d5d-121">`SupportsTrailers()` - 指示请求是否支持接收尾部标头。</span><span class="sxs-lookup"><span data-stu-id="83d5d-121">`SupportsTrailers()` - Indicates if the request supports receiving trailer headers.</span></span>
- <span data-ttu-id="83d5d-122">`CheckTrailersAvailable()` - 确定请求是否支持尾部以及是否可读取。</span><span class="sxs-lookup"><span data-stu-id="83d5d-122">`CheckTrailersAvailable()` - Determines if the request supports trailers and if they're available for reading.</span></span>
- <span data-ttu-id="83d5d-123">`GetTrailer(string trailerName)` - 从响应获取请求的尾随标头。</span><span class="sxs-lookup"><span data-stu-id="83d5d-123">`GetTrailer(string trailerName)` - Gets the requested trailing header from the response.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="83d5d-124">更改原因</span><span class="sxs-lookup"><span data-stu-id="83d5d-124">Reason for change</span></span>

<span data-ttu-id="83d5d-125">在 gRPC 等方案中，尾部是关键功能。</span><span class="sxs-lookup"><span data-stu-id="83d5d-125">Trailers are a key feature in scenarios like gRPC.</span></span> <span data-ttu-id="83d5d-126">将尾部合并到请求标头会使用户感到困惑。</span><span class="sxs-lookup"><span data-stu-id="83d5d-126">Merging the trailers in to request headers was confusing to users.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="83d5d-127">建议的操作</span><span class="sxs-lookup"><span data-stu-id="83d5d-127">Recommended action</span></span>

<span data-ttu-id="83d5d-128">在 `HttpRequest` 上使用尾部相关扩展方法访问尾部。</span><span class="sxs-lookup"><span data-stu-id="83d5d-128">Use the trailer-related extension methods on `HttpRequest` to access trailers.</span></span>

#### <a name="category"></a><span data-ttu-id="83d5d-129">类别</span><span class="sxs-lookup"><span data-stu-id="83d5d-129">Category</span></span>

<span data-ttu-id="83d5d-130">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="83d5d-130">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="83d5d-131">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="83d5d-131">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.HttpRequest.Headers?displayProperty=nameWithType>

<!--

#### Affected APIs

`P:Microsoft.AspNetCore.Http.HttpRequest.Headers`

-->
