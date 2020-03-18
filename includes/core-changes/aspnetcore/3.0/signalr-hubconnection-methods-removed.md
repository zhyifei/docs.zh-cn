---
ms.openlocfilehash: de06825f1031d05bc83183a83bae165e2f9512ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901995"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a><span data-ttu-id="e847e-101">SignalR：已删除 HubConnection ResetSendPing 和 ResetTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="e847e-101">SignalR: HubConnection ResetSendPing and ResetTimeout methods removed</span></span>

<span data-ttu-id="e847e-102">已从 SignalR `HubConnection` API 中删除了 `ResetSendPing` 和 `ResetTimeout` 方法。</span><span class="sxs-lookup"><span data-stu-id="e847e-102">The `ResetSendPing` and `ResetTimeout` methods were removed from the SignalR `HubConnection` API.</span></span> <span data-ttu-id="e847e-103">这些方法最初仅供内部使用，但已在 ASP.NET Core 2.2 中公开。</span><span class="sxs-lookup"><span data-stu-id="e847e-103">These methods were originally intended only for internal use but were made public in ASP.NET Core 2.2.</span></span> <span data-ttu-id="e847e-104">从 ASP.NET Core 3.0 预览版 4 开始，这些方法将不可用。</span><span class="sxs-lookup"><span data-stu-id="e847e-104">These methods won't be available starting in the ASP.NET Core 3.0 Preview 4 release.</span></span> <span data-ttu-id="e847e-105">有关讨论，请参阅 [dotnet/aspnetcore#8543](https://github.com/dotnet/aspnetcore/issues/8543)。</span><span class="sxs-lookup"><span data-stu-id="e847e-105">For discussion, see [dotnet/aspnetcore#8543](https://github.com/dotnet/aspnetcore/issues/8543).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e847e-106">引入的版本</span><span class="sxs-lookup"><span data-stu-id="e847e-106">Version introduced</span></span>

<span data-ttu-id="e847e-107">3.0</span><span class="sxs-lookup"><span data-stu-id="e847e-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e847e-108">旧行为</span><span class="sxs-lookup"><span data-stu-id="e847e-108">Old behavior</span></span>

<span data-ttu-id="e847e-109">API 可用。</span><span class="sxs-lookup"><span data-stu-id="e847e-109">APIs were available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="e847e-110">新行为</span><span class="sxs-lookup"><span data-stu-id="e847e-110">New behavior</span></span>

<span data-ttu-id="e847e-111">API 已删除。</span><span class="sxs-lookup"><span data-stu-id="e847e-111">APIs are removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e847e-112">更改原因</span><span class="sxs-lookup"><span data-stu-id="e847e-112">Reason for change</span></span>

<span data-ttu-id="e847e-113">这些方法最初仅供内部使用，但已在 ASP.NET Core 2.2 中公开。</span><span class="sxs-lookup"><span data-stu-id="e847e-113">These methods were originally intended only for internal use but were made public in ASP.NET Core 2.2.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e847e-114">建议操作</span><span class="sxs-lookup"><span data-stu-id="e847e-114">Recommended action</span></span>

<span data-ttu-id="e847e-115">不要使用这些方法。</span><span class="sxs-lookup"><span data-stu-id="e847e-115">Don't use these methods.</span></span>

#### <a name="category"></a><span data-ttu-id="e847e-116">类别</span><span class="sxs-lookup"><span data-stu-id="e847e-116">Category</span></span>

<span data-ttu-id="e847e-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e847e-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e847e-118">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="e847e-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing`
- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout`

-->
