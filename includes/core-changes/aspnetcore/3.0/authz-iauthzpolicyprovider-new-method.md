---
ms.openlocfilehash: 74b989a2413d2192f7cf5208e400eaed879ea096
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198356"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a><span data-ttu-id="ec9cb-101">Authorization:IAuthorizationPolicyProvider 实现需要新方法</span><span class="sxs-lookup"><span data-stu-id="ec9cb-101">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>

<span data-ttu-id="ec9cb-102">在 ASP.NET Core 3.0 中，已将一个新 `GetFallbackPolicyAsync` 方法添加到 `IAuthorizationPolicyProvider`。</span><span class="sxs-lookup"><span data-stu-id="ec9cb-102">In ASP.NET Core 3.0, a new `GetFallbackPolicyAsync` method was added to `IAuthorizationPolicyProvider`.</span></span> <span data-ttu-id="ec9cb-103">当未指定策略时，授权中间件会使用此回退策略。</span><span class="sxs-lookup"><span data-stu-id="ec9cb-103">This fallback policy is used by the authorization middleware when no policy is specified.</span></span>

<span data-ttu-id="ec9cb-104">有关详细信息，请参阅 [aspnet/AspNetCore # 9759](https://github.com/aspnet/AspNetCore/pull/9759)。</span><span class="sxs-lookup"><span data-stu-id="ec9cb-104">For more information, see [aspnet/AspNetCore#9759](https://github.com/aspnet/AspNetCore/pull/9759).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ec9cb-105">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ec9cb-105">Version introduced</span></span>

<span data-ttu-id="ec9cb-106">3.0</span><span class="sxs-lookup"><span data-stu-id="ec9cb-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ec9cb-107">旧行为</span><span class="sxs-lookup"><span data-stu-id="ec9cb-107">Old behavior</span></span>

<span data-ttu-id="ec9cb-108">`IAuthorizationPolicyProvider` 的实现不需要 `GetFallbackPolicyAsync` 方法。</span><span class="sxs-lookup"><span data-stu-id="ec9cb-108">Implementations of `IAuthorizationPolicyProvider` didn't require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ec9cb-109">新行为</span><span class="sxs-lookup"><span data-stu-id="ec9cb-109">New behavior</span></span>

<span data-ttu-id="ec9cb-110">`IAuthorizationPolicyProvider` 的实现需要 `GetFallbackPolicyAsync` 方法。</span><span class="sxs-lookup"><span data-stu-id="ec9cb-110">Implementations of `IAuthorizationPolicyProvider` require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ec9cb-111">更改原因</span><span class="sxs-lookup"><span data-stu-id="ec9cb-111">Reason for change</span></span>

<span data-ttu-id="ec9cb-112">如果未指定策略，则新 `AuthorizationMiddleware` 需要使用新方法。</span><span class="sxs-lookup"><span data-stu-id="ec9cb-112">A new method was needed for the new `AuthorizationMiddleware` to use when no policy is specified.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ec9cb-113">建议的操作</span><span class="sxs-lookup"><span data-stu-id="ec9cb-113">Recommended action</span></span>

<span data-ttu-id="ec9cb-114">将 `GetFallbackPolicyAsync` 方法添加到 `IAuthorizationPolicyProvider` 的实现。</span><span class="sxs-lookup"><span data-stu-id="ec9cb-114">Add the `GetFallbackPolicyAsync` method to your implementations of `IAuthorizationPolicyProvider`.</span></span>

#### <a name="category"></a><span data-ttu-id="ec9cb-115">类别</span><span class="sxs-lookup"><span data-stu-id="ec9cb-115">Category</span></span>

<span data-ttu-id="ec9cb-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ec9cb-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ec9cb-117">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="ec9cb-117">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
