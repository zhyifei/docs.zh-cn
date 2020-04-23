---
ms.openlocfilehash: b4499637cd5fff015335e0cdb3c6cf1c3ea6cff0
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "81637179"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a><span data-ttu-id="7cc49-101">身份验证：Newtonsoft.json 类型已替换</span><span class="sxs-lookup"><span data-stu-id="7cc49-101">Authentication: Newtonsoft.Json types replaced</span></span>

<span data-ttu-id="7cc49-102">在 ASP.NET Core 3.0 中，身份验证 API 中使用的 `Newtonsoft.Json` 类型已替换为 `System.Text.Json` 类型。</span><span class="sxs-lookup"><span data-stu-id="7cc49-102">In ASP.NET Core 3.0, `Newtonsoft.Json` types used in Authentication APIs have been replaced with `System.Text.Json` types.</span></span> <span data-ttu-id="7cc49-103">除以下情况外，身份验证包的基本使用不受影响：</span><span class="sxs-lookup"><span data-stu-id="7cc49-103">Except for the following cases, basic usage of the Authentication packages remains unaffected:</span></span>

* <span data-ttu-id="7cc49-104">派生自 OAuth 提供程序的类，例如来自 [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers) 的类。</span><span class="sxs-lookup"><span data-stu-id="7cc49-104">Classes derived from the OAuth providers, such as those from [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers).</span></span>
* <span data-ttu-id="7cc49-105">高级声明操作实现。</span><span class="sxs-lookup"><span data-stu-id="7cc49-105">Advanced claim manipulation implementations.</span></span>

<span data-ttu-id="7cc49-106">有关详细信息，请参阅 [dotnet/aspnetcore#7105](https://github.com/dotnet/aspnetcore/pull/7105)。</span><span class="sxs-lookup"><span data-stu-id="7cc49-106">For more information, see [dotnet/aspnetcore#7105](https://github.com/dotnet/aspnetcore/pull/7105).</span></span> <span data-ttu-id="7cc49-107">有关讨论，请参阅 [dotnet/aspnetcore#7289](https://github.com/dotnet/aspnetcore/issues/7289)。</span><span class="sxs-lookup"><span data-stu-id="7cc49-107">For discussion, see [dotnet/aspnetcore#7289](https://github.com/dotnet/aspnetcore/issues/7289).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7cc49-108">引入的版本</span><span class="sxs-lookup"><span data-stu-id="7cc49-108">Version introduced</span></span>

<span data-ttu-id="7cc49-109">3.0</span><span class="sxs-lookup"><span data-stu-id="7cc49-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7cc49-110">建议操作</span><span class="sxs-lookup"><span data-stu-id="7cc49-110">Recommended action</span></span>

<span data-ttu-id="7cc49-111">对于派生的 OAuth 实现，最常见的更改是将 `JObject.Parse` 替换为 `CreateTicketAsync` 重写中的 `JsonDocument.Parse`，如[本文](https://github.com/dotnet/aspnetcore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40)所示。</span><span class="sxs-lookup"><span data-stu-id="7cc49-111">For derived OAuth implementations, the most common change is to replace `JObject.Parse` with `JsonDocument.Parse` in the `CreateTicketAsync` override as shown [here](https://github.com/dotnet/aspnetcore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40).</span></span> <span data-ttu-id="7cc49-112">`JsonDocument` 可实现 `IDisposable`。</span><span class="sxs-lookup"><span data-stu-id="7cc49-112">`JsonDocument` implements `IDisposable`.</span></span>

<span data-ttu-id="7cc49-113">以下列表概述了已知更改：</span><span class="sxs-lookup"><span data-stu-id="7cc49-113">The following list outlines known changes:</span></span>

- <span data-ttu-id="7cc49-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> 变为 `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`。</span><span class="sxs-lookup"><span data-stu-id="7cc49-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> becomes `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`.</span></span> <span data-ttu-id="7cc49-115">`ClaimAction` 的所有派生的实现都受到类似的影响。</span><span class="sxs-lookup"><span data-stu-id="7cc49-115">All derived implementations of `ClaimAction` are similarly affected.</span></span>
- <span data-ttu-id="7cc49-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> 变为 `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`</span><span class="sxs-lookup"><span data-stu-id="7cc49-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="7cc49-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> 变为 `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`</span><span class="sxs-lookup"><span data-stu-id="7cc49-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="7cc49-118"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> 已移除一个旧构造函数，另一个将 `JObject` 替换为 `JsonElement`。</span><span class="sxs-lookup"><span data-stu-id="7cc49-118"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> has had one old constructor removed and the other replaced `JObject` with `JsonElement`.</span></span> <span data-ttu-id="7cc49-119">已更新 `User` 属性和 `RunClaimActions` 方法以使其匹配。</span><span class="sxs-lookup"><span data-stu-id="7cc49-119">The `User` property and `RunClaimActions` method have been updated to match.</span></span>
- <span data-ttu-id="7cc49-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> 现在接受类型为 `JsonDocument` 而非 `JObject` 的参数。</span><span class="sxs-lookup"><span data-stu-id="7cc49-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> now accepts a parameter of type `JsonDocument` instead of `JObject`.</span></span> <span data-ttu-id="7cc49-121">已更新 `Response` 属性以使其匹配。</span><span class="sxs-lookup"><span data-stu-id="7cc49-121">The `Response` property has been updated to match.</span></span> <span data-ttu-id="7cc49-122">`OAuthTokenResponse` 现在可处置，并将由 `OAuthHandler` 处置。</span><span class="sxs-lookup"><span data-stu-id="7cc49-122">`OAuthTokenResponse` is now disposable and will be disposed by `OAuthHandler`.</span></span> <span data-ttu-id="7cc49-123">替代 `ExchangeCodeAsync` 的派生的 OAuth 实现无需处置 `JsonDocument` 或 `OAuthTokenResponse`。</span><span class="sxs-lookup"><span data-stu-id="7cc49-123">Derived OAuth implementations overriding `ExchangeCodeAsync` don't need to dispose the `JsonDocument` or `OAuthTokenResponse`.</span></span>
- <span data-ttu-id="7cc49-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> 从 `JObject` 更改为 `JsonDocument`。</span><span class="sxs-lookup"><span data-stu-id="7cc49-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonDocument`.</span></span>
- <span data-ttu-id="7cc49-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> 从 `JObject` 更改为 `JsonElement`。</span><span class="sxs-lookup"><span data-stu-id="7cc49-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonElement`.</span></span>
- <span data-ttu-id="7cc49-126">[TwitterHandler.CreateTicketAsync(ClaimsIdentity,AuthenticationProperties,AccessToken,JObject)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.authentication.twitter.twitterhandler.createticketasync?view=aspnetcore-2.2#Microsoft_AspNetCore_Authentication_Twitter_TwitterHandler_CreateTicketAsync_System_Security_Claims_ClaimsIdentity_Microsoft_AspNetCore_Authentication_AuthenticationProperties_Microsoft_AspNetCore_Authentication_Twitter_AccessToken_Newtonsoft_Json_Linq_JObject_) 的最后一个参数从 `JObject` 更改为 `JsonElement`。</span><span class="sxs-lookup"><span data-stu-id="7cc49-126">The last parameter of [TwitterHandler.CreateTicketAsync(ClaimsIdentity,AuthenticationProperties,AccessToken,JObject)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.authentication.twitter.twitterhandler.createticketasync?view=aspnetcore-2.2#Microsoft_AspNetCore_Authentication_Twitter_TwitterHandler_CreateTicketAsync_System_Security_Claims_ClaimsIdentity_Microsoft_AspNetCore_Authentication_AuthenticationProperties_Microsoft_AspNetCore_Authentication_Twitter_AccessToken_Newtonsoft_Json_Linq_JObject_) changed from `JObject` to `JsonElement`.</span></span> <span data-ttu-id="7cc49-127">替换方法为 <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,System.Text.Json.JsonElement)?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="7cc49-127">The replacement method is <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,System.Text.Json.JsonElement)?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="7cc49-128">类别</span><span class="sxs-lookup"><span data-stu-id="7cc49-128">Category</span></span>

<span data-ttu-id="7cc49-129">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7cc49-129">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7cc49-130">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="7cc49-130">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Authentication.Facebook?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.MicrosoftAccount?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OAuth?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OpenIdConnect?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Twitter?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Facebook`
- `N:Microsoft.AspNetCore.Authentication.Google`
- `N:Microsoft.AspNetCore.Authentication.MicrosoftAccount`
- `N:Microsoft.AspNetCore.Authentication.OAuth`
- `N:Microsoft.AspNetCore.Authentication.OpenIdConnect`
- `N:Microsoft.AspNetCore.Authentication.Twitter`

-->
