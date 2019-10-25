---
ms.openlocfilehash: 2945465bb6a3a362dc640641056712dffd73d559
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394263"
---
### <a name="authentication-httpcontextauthentication-property-removed"></a><span data-ttu-id="f677b-101">身份验证：已删除 HttpContext.Authentication 属性</span><span class="sxs-lookup"><span data-stu-id="f677b-101">Authentication: HttpContext.Authentication property removed</span></span>

<span data-ttu-id="f677b-102">已删除 `HttpContext` 上弃用的 `Authentication` 属性。</span><span class="sxs-lookup"><span data-stu-id="f677b-102">The deprecated `Authentication` property on `HttpContext` has been removed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f677b-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="f677b-103">Change description</span></span>

<span data-ttu-id="f677b-104">作为 [aspnet/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504) 的一部分，已删除 `HttpContext` 上弃用的 `Authentication` 属性。</span><span class="sxs-lookup"><span data-stu-id="f677b-104">As part of [aspnet/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504), the deprecated `Authentication` property on `HttpContext` has been removed.</span></span> <span data-ttu-id="f677b-105">从 2.0 开始，`Authentication` 属性已弃用。</span><span class="sxs-lookup"><span data-stu-id="f677b-105">The `Authentication` property has been deprecated since 2.0.</span></span> <span data-ttu-id="f677b-106">[迁移指南 ](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions)已发布，可使用此弃用属性将代码迁移到新的替换 API。</span><span class="sxs-lookup"><span data-stu-id="f677b-106">A [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) was published to migrate code using this deprecated property to the new replacement APIs.</span></span> <span data-ttu-id="f677b-107">在 commit [aspnet/AspNetCore@d7a7c65](https://github.com/aspnet/AspNetCore/commit/d7a7c65) 中移除了与旧 ASP.NET Core 1.x 身份验证堆栈相关的其余未使用的类/API。</span><span class="sxs-lookup"><span data-stu-id="f677b-107">The remaining unused classes / APIs related to the old ASP.NET Core 1.x authentication stack were removed in commit [aspnet/AspNetCore@d7a7c65](https://github.com/aspnet/AspNetCore/commit/d7a7c65).</span></span>

<span data-ttu-id="f677b-108">有关讨论，请参阅 [aspnet/AspNetCore#6533](https://github.com/aspnet/AspNetCore/issues/6533)。</span><span class="sxs-lookup"><span data-stu-id="f677b-108">For discussion, see [aspnet/AspNetCore#6533](https://github.com/aspnet/AspNetCore/issues/6533).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f677b-109">引入的版本</span><span class="sxs-lookup"><span data-stu-id="f677b-109">Version introduced</span></span>

<span data-ttu-id="f677b-110">3.0</span><span class="sxs-lookup"><span data-stu-id="f677b-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f677b-111">更改原因</span><span class="sxs-lookup"><span data-stu-id="f677b-111">Reason for change</span></span>

<span data-ttu-id="f677b-112">ASP.NET Core 1.0 API 已被 <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName> 中的扩展方法替换。</span><span class="sxs-lookup"><span data-stu-id="f677b-112">ASP.NET Core 1.0 APIs have been replaced by extension methods in <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f677b-113">建议的操作</span><span class="sxs-lookup"><span data-stu-id="f677b-113">Recommended action</span></span>

<span data-ttu-id="f677b-114">请参阅[迁移指南](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions)。</span><span class="sxs-lookup"><span data-stu-id="f677b-114">See the [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).</span></span>

#### <a name="category"></a><span data-ttu-id="f677b-115">类别</span><span class="sxs-lookup"><span data-stu-id="f677b-115">Category</span></span>

<span data-ttu-id="f677b-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f677b-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f677b-117">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="f677b-117">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpContext.Authentication?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler`
- `P:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext`
- `P:Microsoft.AspNetCore.Http.HttpContext.Authentication`

-->
