---
ms.openlocfilehash: 80d4bbbfe52ab9685d7ca54f21b80d4b1773da22
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859638"
---
### <a name="webclientcancelasync-doesnt-always-cancel-immediately"></a><span data-ttu-id="086ef-101">WebClient.CancelAsync 并不总是立即取消</span><span class="sxs-lookup"><span data-stu-id="086ef-101">WebClient.CancelAsync doesn't always cancel immediately</span></span>

<span data-ttu-id="086ef-102">自 .NET Core 2.0 起，如果响应已开始提取，则调用 <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> 不会立即取消请求。</span><span class="sxs-lookup"><span data-stu-id="086ef-102">Starting in .NET Core 2.0, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> doesn't cancel the request immediately if the response has started to fetch.</span></span>

#### <a name="change-description"></a><span data-ttu-id="086ef-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="086ef-103">Change description</span></span>

<span data-ttu-id="086ef-104">以前，调用 <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> 会立即取消请求。</span><span class="sxs-lookup"><span data-stu-id="086ef-104">Previously, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> canceled the request immediately.</span></span> <span data-ttu-id="086ef-105">自 .NET Core 2.0 起，只有当响应尚未开始提取时，调用 <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> 才会立即取消请求。</span><span class="sxs-lookup"><span data-stu-id="086ef-105">Starting in .NET Core 2.0, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> cancels the request immediately only if the response hasn't started fetching.</span></span> <span data-ttu-id="086ef-106">如果响应已开始提取，则只有在读取完整响应之后才会取消请求。</span><span class="sxs-lookup"><span data-stu-id="086ef-106">If the response has started to fetch, the request is cancelled only after a complete response is read.</span></span>

<span data-ttu-id="086ef-107">此更改已实现，因为 <xref:System.Net.WebClient> API 已弃用，取而代之的是 <xref:System.Net.Http.HttpClient>。</span><span class="sxs-lookup"><span data-stu-id="086ef-107">This change was implemented because the <xref:System.Net.WebClient> API is deprecated in favor of <xref:System.Net.Http.HttpClient>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="086ef-108">引入的版本</span><span class="sxs-lookup"><span data-stu-id="086ef-108">Version introduced</span></span>

<span data-ttu-id="086ef-109">2.0</span><span class="sxs-lookup"><span data-stu-id="086ef-109">2.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="086ef-110">建议操作</span><span class="sxs-lookup"><span data-stu-id="086ef-110">Recommended action</span></span>

<span data-ttu-id="086ef-111">使用 <xref:System.Net.Http.HttpClient?displayProperty=fullName> 类，而不是已弃用的 <xref:System.Net.WebClient?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="086ef-111">Use the <xref:System.Net.Http.HttpClient?displayProperty=fullName> class instead of <xref:System.Net.WebClient?displayProperty=fullName>, which is deprecated.</span></span>

#### <a name="category"></a><span data-ttu-id="086ef-112">类别</span><span class="sxs-lookup"><span data-stu-id="086ef-112">Category</span></span>

<span data-ttu-id="086ef-113">网络</span><span class="sxs-lookup"><span data-stu-id="086ef-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="086ef-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="086ef-114">Affected APIs</span></span>

- <xref:System.Net.WebClient.CancelAsync?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.WebClient.CancelAsync`

-->
