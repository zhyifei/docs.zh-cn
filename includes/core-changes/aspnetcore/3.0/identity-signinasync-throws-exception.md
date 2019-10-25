---
ms.openlocfilehash: 6679e38aefa7d61ce430dc5375ff3b35c641ea27
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394214"
---
### <a name="identity-signinasync-throws-exception-for-unauthenticated-identity"></a><span data-ttu-id="b2964-101">标识：对于未经身份验证的标识，SignInAsync 会引发异常</span><span class="sxs-lookup"><span data-stu-id="b2964-101">Identity: SignInAsync throws exception for unauthenticated identity</span></span>

<span data-ttu-id="b2964-102">默认情况下，`SignInAsync` 会为其中 `IsAuthenticated` 为 `false` 的主体/标识引发异常。</span><span class="sxs-lookup"><span data-stu-id="b2964-102">By default, `SignInAsync` throws an exception for principals / identities in which `IsAuthenticated` is `false`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b2964-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="b2964-103">Version introduced</span></span>

<span data-ttu-id="b2964-104">3.0</span><span class="sxs-lookup"><span data-stu-id="b2964-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b2964-105">旧行为</span><span class="sxs-lookup"><span data-stu-id="b2964-105">Old behavior</span></span>

<span data-ttu-id="b2964-106">`SignInAsync` 接受任何主体/标识，包括其中 `IsAuthenticated` 为 `false` 的标识。</span><span class="sxs-lookup"><span data-stu-id="b2964-106">`SignInAsync` accepts any principals / identities, including identities in which `IsAuthenticated` is `false`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b2964-107">新行为</span><span class="sxs-lookup"><span data-stu-id="b2964-107">New behavior</span></span>

<span data-ttu-id="b2964-108">默认情况下，`SignInAsync` 会为其中 `IsAuthenticated` 为 `false` 的主体/标识引发异常。</span><span class="sxs-lookup"><span data-stu-id="b2964-108">By default, `SignInAsync` throws an exception for principals / identities in which `IsAuthenticated` is `false`.</span></span> <span data-ttu-id="b2964-109">有一个新的标志可禁止显示此行为，但默认行为已更改。</span><span class="sxs-lookup"><span data-stu-id="b2964-109">There's a new flag to suppress this behavior, but the default behavior has changed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b2964-110">更改原因</span><span class="sxs-lookup"><span data-stu-id="b2964-110">Reason for change</span></span>

<span data-ttu-id="b2964-111">旧行为是有问题的，因为在默认情况下，`[Authorize]`  /  `RequireAuthenticatedUser()` 拒绝了这些主体。</span><span class="sxs-lookup"><span data-stu-id="b2964-111">The old behavior was problematic because, by default, these principals were rejected by `[Authorize]` / `RequireAuthenticatedUser()`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b2964-112">建议的操作</span><span class="sxs-lookup"><span data-stu-id="b2964-112">Recommended action</span></span>

<span data-ttu-id="b2964-113">在 ASP.NET Core 3.0 预览版 6 中，`AuthenticationOptions` 上有 `RequireAuthenticatedSignIn` 标记，默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="b2964-113">In ASP.NET Core 3.0 Preview 6, there's a `RequireAuthenticatedSignIn` flag on `AuthenticationOptions` that is `true` by default.</span></span> <span data-ttu-id="b2964-114">将此标志设置为 `false` 以还原旧行为。</span><span class="sxs-lookup"><span data-stu-id="b2964-114">Set this flag to `false` to restore the old behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="b2964-115">类别</span><span class="sxs-lookup"><span data-stu-id="b2964-115">Category</span></span>

<span data-ttu-id="b2964-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2964-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b2964-117">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="b2964-117">Affected APIs</span></span>

<span data-ttu-id="b2964-118">无</span><span class="sxs-lookup"><span data-stu-id="b2964-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
