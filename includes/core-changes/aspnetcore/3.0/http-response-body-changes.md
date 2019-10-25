---
ms.openlocfilehash: 22ef5d0f91a4f61ca75203f677bcc14e91d77dc1
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394319"
---
### <a name="http-response-body-infrastructure-changes"></a><span data-ttu-id="81167-101">HTTP：响应正文基础结构更改</span><span class="sxs-lookup"><span data-stu-id="81167-101">HTTP: Response body infrastructure changes</span></span>

<span data-ttu-id="81167-102">支持 HTTP 响应正文的基础结构已发生更改。</span><span class="sxs-lookup"><span data-stu-id="81167-102">The infrastructure backing an HTTP response body has changed.</span></span> <span data-ttu-id="81167-103">如果直接使用 `HttpResponse`，则不需要进行任何代码更改。</span><span class="sxs-lookup"><span data-stu-id="81167-103">If you're using `HttpResponse` directly, you shouldn't need to make any code changes.</span></span> <span data-ttu-id="81167-104">如果要包装或替换 `HttpResponse.Body` 或访问 `HttpContext.Features`，请进行进一步了解。</span><span class="sxs-lookup"><span data-stu-id="81167-104">Read further if you're wrapping or replacing `HttpResponse.Body` or accessing `HttpContext.Features`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="81167-105">引入的版本</span><span class="sxs-lookup"><span data-stu-id="81167-105">Version introduced</span></span>

<span data-ttu-id="81167-106">3.0</span><span class="sxs-lookup"><span data-stu-id="81167-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="81167-107">旧行为</span><span class="sxs-lookup"><span data-stu-id="81167-107">Old behavior</span></span>

<span data-ttu-id="81167-108">有三个 API 与 HTTP 响应正文关联：</span><span class="sxs-lookup"><span data-stu-id="81167-108">There were three APIs associated with the HTTP response body:</span></span>

- `IHttpResponseFeature.Body`
- `IHttpSendFileFeature.SendFileAsync`
- `IHttpBufferingFeature.DisableResponseBuffering`

#### <a name="new-behavior"></a><span data-ttu-id="81167-109">新行为</span><span class="sxs-lookup"><span data-stu-id="81167-109">New behavior</span></span>

<span data-ttu-id="81167-110">如果替换 `HttpResponse.Body`，则它通过使用 `StreamResponseBodyFeature` 为所有预期的 API 提供默认实现，将整个 `IHttpResponseBodyFeature` 替换为给定流周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="81167-110">If you replace `HttpResponse.Body`, it replaces the entire `IHttpResponseBodyFeature` with a wrapper around your given stream using `StreamResponseBodyFeature` to provide default implementations for all of the expected APIs.</span></span> <span data-ttu-id="81167-111">重新设置回原始流会还原此更改。</span><span class="sxs-lookup"><span data-stu-id="81167-111">Setting back the original stream reverts this change.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="81167-112">更改原因</span><span class="sxs-lookup"><span data-stu-id="81167-112">Reason for change</span></span>

<span data-ttu-id="81167-113">动机是将响应正文 API 合并为单一新功能接口。</span><span class="sxs-lookup"><span data-stu-id="81167-113">The motivation is to combine the response body APIs into a single new feature interface.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="81167-114">建议的操作</span><span class="sxs-lookup"><span data-stu-id="81167-114">Recommended action</span></span>

<span data-ttu-id="81167-115">使用之前在其中使用 `IHttpResponseFeature.Body`、`IHttpSendFileFeature` 或 `IHttpBufferingFeature` 的 `IHttpResponseBodyFeature`。</span><span class="sxs-lookup"><span data-stu-id="81167-115">Use `IHttpResponseBodyFeature` where you previously were using `IHttpResponseFeature.Body`, `IHttpSendFileFeature`, or `IHttpBufferingFeature`.</span></span>

#### <a name="category"></a><span data-ttu-id="81167-116">类别</span><span class="sxs-lookup"><span data-stu-id="81167-116">Category</span></span>

<span data-ttu-id="81167-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="81167-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="81167-118">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="81167-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature?displayProperty=nameWithType>
 
<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature`
- `P:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body`
- `T:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature`

-->
