---
ms.openlocfilehash: acef6d7177ee5ad7e18dc8ba1e383d6f76263623
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394442"
---
### <a name="signalr-javascript-client-package-name-changed"></a><span data-ttu-id="57d87-101">SignalR：已更改 JavaScript 客户端包名称</span><span class="sxs-lookup"><span data-stu-id="57d87-101">SignalR: JavaScript client package name changed</span></span>

<span data-ttu-id="57d87-102">在 ASP.NET Core 3.0 预览版 7 中，SignalR JavaScript 客户端包名称从 `@aspnet/signalr` 更改为 `@microsoft/signalr`。</span><span class="sxs-lookup"><span data-stu-id="57d87-102">In ASP.NET Core 3.0 Preview 7, the SignalR JavaScript client package name changed from `@aspnet/signalr` to `@microsoft/signalr`.</span></span> <span data-ttu-id="57d87-103">由于 Azure SignalR 服务，名称更改反映了 SignalR 不只是在 ASP.NET Core 应用中有用这一事实。</span><span class="sxs-lookup"><span data-stu-id="57d87-103">The name change reflects the fact that SignalR is useful in more than just ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

<span data-ttu-id="57d87-104">若要对此更改做出反应，请更改 package.json  文件、`require` 语句和 ECMAScript `import` 语句中的引用。</span><span class="sxs-lookup"><span data-stu-id="57d87-104">To react to this change, change references in your *package.json* files, `require` statements, and ECMAScript `import` statements.</span></span> <span data-ttu-id="57d87-105">在此重命名过程中，不会更改 API。</span><span class="sxs-lookup"><span data-stu-id="57d87-105">No API will change as part of this rename.</span></span>

<span data-ttu-id="57d87-106">有关讨论，请参阅 [aspnet/AspNetCore#11637](https://github.com/aspnet/AspNetCore/issues/11637)。</span><span class="sxs-lookup"><span data-stu-id="57d87-106">For discussion, see [aspnet/AspNetCore#11637](https://github.com/aspnet/AspNetCore/issues/11637).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="57d87-107">引入的版本</span><span class="sxs-lookup"><span data-stu-id="57d87-107">Version introduced</span></span>

<span data-ttu-id="57d87-108">3.0</span><span class="sxs-lookup"><span data-stu-id="57d87-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="57d87-109">旧行为</span><span class="sxs-lookup"><span data-stu-id="57d87-109">Old behavior</span></span>

<span data-ttu-id="57d87-110">客户端包以前命名为 `@aspnet/signalr`。</span><span class="sxs-lookup"><span data-stu-id="57d87-110">The client package was named `@aspnet/signalr`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="57d87-111">新行为</span><span class="sxs-lookup"><span data-stu-id="57d87-111">New behavior</span></span>

<span data-ttu-id="57d87-112">客户端包现在命名为 `@microsoft/signalr`。</span><span class="sxs-lookup"><span data-stu-id="57d87-112">The client package is named `@microsoft/signalr`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="57d87-113">更改原因</span><span class="sxs-lookup"><span data-stu-id="57d87-113">Reason for change</span></span>

<span data-ttu-id="57d87-114">由于 Azure SignalR 服务，名称更改阐明了 SignalR 在 ASP.NET Core 应用之外也很有用。</span><span class="sxs-lookup"><span data-stu-id="57d87-114">The name change clarifies that SignalR is useful beyond ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="57d87-115">建议的操作</span><span class="sxs-lookup"><span data-stu-id="57d87-115">Recommended action</span></span>

<span data-ttu-id="57d87-116">切换到新包 `@microsoft/signalr`。</span><span class="sxs-lookup"><span data-stu-id="57d87-116">Switch to the new package `@microsoft/signalr`.</span></span>

#### <a name="category"></a><span data-ttu-id="57d87-117">类别</span><span class="sxs-lookup"><span data-stu-id="57d87-117">Category</span></span>

<span data-ttu-id="57d87-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="57d87-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="57d87-119">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="57d87-119">Affected APIs</span></span>

<span data-ttu-id="57d87-120">无</span><span class="sxs-lookup"><span data-stu-id="57d87-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
