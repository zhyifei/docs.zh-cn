---
ms.openlocfilehash: c634c43e72d345721f2d8f2e9f45760e927a86ab
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394250"
---
### <a name="authentication-google-deprecated-and-replaced"></a><span data-ttu-id="61f85-101">身份验证：Google+ 已弃用并被替换</span><span class="sxs-lookup"><span data-stu-id="61f85-101">Authentication: Google+ deprecated and replaced</span></span>

<span data-ttu-id="61f85-102">Google 早在 2019 年 1 月 28 日就开始[关闭](https://developers.google.com/+/api-shutdown)对应用使用 Google + 登录。</span><span class="sxs-lookup"><span data-stu-id="61f85-102">Google is starting to [shut down](https://developers.google.com/+/api-shutdown) Google+ Sign-in for apps as early as January 28, 2019.</span></span>

#### <a name="change-description"></a><span data-ttu-id="61f85-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="61f85-103">Change description</span></span>

<span data-ttu-id="61f85-104">ASP.NET 4.x 和 ASP.NET Core 已使用 Google + 登录 API 在 Web 应用中对 Google 帐户用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="61f85-104">ASP.NET 4.x and ASP.NET Core have been using the Google+ Sign-in APIs to authenticate Google account users in web apps.</span></span> <span data-ttu-id="61f85-105">受影响的 NuGet 包为 [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/)（对于 ASP.NET Core）和 [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/)（对于具有 ASP.NET Web Forms 和 MVC 的 `Microsoft.Owin`）。</span><span class="sxs-lookup"><span data-stu-id="61f85-105">The affected NuGet packages are [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/) for ASP.NET Core and [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/) for `Microsoft.Owin` with ASP.NET Web Forms and MVC.</span></span>

<span data-ttu-id="61f85-106">Google 的替代 API 使用不同的数据源和格式。</span><span class="sxs-lookup"><span data-stu-id="61f85-106">Google's replacement APIs use a different data source and format.</span></span> <span data-ttu-id="61f85-107">下面提供的缓解措施和解决方案说明存在结构性更改。</span><span class="sxs-lookup"><span data-stu-id="61f85-107">The mitigations and solutions provided below account for the structural changes.</span></span> <span data-ttu-id="61f85-108">应用应验证数据本身是否仍然满足其需求。</span><span class="sxs-lookup"><span data-stu-id="61f85-108">Apps should verify the data itself still satisfies their requirements.</span></span> <span data-ttu-id="61f85-109">例如，名称、电子邮件地址、配置文件链接和个人资料照片的值可能与以前稍有不同。</span><span class="sxs-lookup"><span data-stu-id="61f85-109">For example, names, email addresses, profile links, and profile photos may provide subtly different values than before.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="61f85-110">引入的版本</span><span class="sxs-lookup"><span data-stu-id="61f85-110">Version introduced</span></span>

<span data-ttu-id="61f85-111">所有版本。</span><span class="sxs-lookup"><span data-stu-id="61f85-111">All versions.</span></span> <span data-ttu-id="61f85-112">此更改是 ASP.NET Core 的外部更改。</span><span class="sxs-lookup"><span data-stu-id="61f85-112">This change is external to ASP.NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="61f85-113">建议的操作</span><span class="sxs-lookup"><span data-stu-id="61f85-113">Recommended action</span></span>

##### <a name="owin-with-aspnet-web-forms-and-mvc"></a><span data-ttu-id="61f85-114">包含 ASP.NET Web Forms 和 MVC 的 Owin</span><span class="sxs-lookup"><span data-stu-id="61f85-114">Owin with ASP.NET Web Forms and MVC</span></span>

<span data-ttu-id="61f85-115">针对 `Microsoft.Owin` 3.1.0 和更高版本，[本文](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635)概述了临时的缓解措施。</span><span class="sxs-lookup"><span data-stu-id="61f85-115">For `Microsoft.Owin` 3.1.0 and later, a temporary mitigation is outlined [here](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635).</span></span> <span data-ttu-id="61f85-116">应用应通过缓解措施来完成测试，以检查数据格式的更改。</span><span class="sxs-lookup"><span data-stu-id="61f85-116">Apps should complete testing with the mitigation to check for changes in the data format.</span></span> <span data-ttu-id="61f85-117">计划发布 `Microsoft.Owin` 4.0.1，并提供一个修补程序。</span><span class="sxs-lookup"><span data-stu-id="61f85-117">There are plans to release `Microsoft.Owin` 4.0.1 with a fix.</span></span> <span data-ttu-id="61f85-118">使用任何较低版本的应用都应更新到版本 4.0.1。</span><span class="sxs-lookup"><span data-stu-id="61f85-118">Apps using any prior version should update to version 4.0.1.</span></span>

##### <a name="aspnet-core-1x"></a><span data-ttu-id="61f85-119">ASP.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="61f85-119">ASP.NET Core 1.x</span></span>

<span data-ttu-id="61f85-120">[包含 ASP.NET Web Form 和MVC 的 Owin](#owin-with-aspnet-web-forms-and-mvc)的缓解措施可应用于 ASP.NET Core 1.x。</span><span class="sxs-lookup"><span data-stu-id="61f85-120">The mitigation in [Owin with ASP.NET Web Forms and MVC](#owin-with-aspnet-web-forms-and-mvc) can be adapted to ASP.NET Core 1.x.</span></span> <span data-ttu-id="61f85-121">未计划 NuGet 包修补程序，因为 1.x 已处于[生命周期结束](https://dotnet.microsoft.com/platform/support-policy)状态。</span><span class="sxs-lookup"><span data-stu-id="61f85-121">NuGet package patches aren't planned because 1.x has reached [end of life](https://dotnet.microsoft.com/platform/support-policy) status.</span></span>

##### <a name="aspnet-core-2x"></a><span data-ttu-id="61f85-122">ASP.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="61f85-122">ASP.NET Core 2.x</span></span>

<span data-ttu-id="61f85-123">对于 `Microsoft.AspNetCore.Authentication.Google` 版本 2.x，请将对 `Startup.ConfigureServices` 中 `AddGoogle` 的现有调用替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="61f85-123">For `Microsoft.AspNetCore.Authentication.Google` version 2.x, replace your existing call to `AddGoogle` in `Startup.ConfigureServices` with the following code:</span></span>

```csharp
.AddGoogle(o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.UserInformationEndpoint = "https://www.googleapis.com/oauth2/v2/userinfo";
    o.ClaimActions.Clear();
    o.ClaimActions.MapJsonKey(ClaimTypes.NameIdentifier, "id");
    o.ClaimActions.MapJsonKey(ClaimTypes.Name, "name");
    o.ClaimActions.MapJsonKey(ClaimTypes.GivenName, "given_name");
    o.ClaimActions.MapJsonKey(ClaimTypes.Surname, "family_name");
    o.ClaimActions.MapJsonKey("urn:google:profile", "link");
    o.ClaimActions.MapJsonKey(ClaimTypes.Email, "email");
});
```

<span data-ttu-id="61f85-124">2 月 2.1 和 2.2 修补程序将前面的重新配置合并为新的默认配置。</span><span class="sxs-lookup"><span data-stu-id="61f85-124">The February 2.1 and 2.2 patches incorporated the preceding reconfiguration as the new default.</span></span> <span data-ttu-id="61f85-125">不会为 ASP.NET Core 2.0 计划任何修补程序，因为它的[生命周期已经结束](https://dotnet.microsoft.com/platform/support-policy)。</span><span class="sxs-lookup"><span data-stu-id="61f85-125">No patch is planned for ASP.NET Core 2.0 since it has reached [end of life](https://dotnet.microsoft.com/platform/support-policy).</span></span>

##### <a name="aspnet-core-30"></a><span data-ttu-id="61f85-126">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="61f85-126">ASP.NET Core 3.0</span></span>

<span data-ttu-id="61f85-127">为 ASP.NET Core 2.x 提供的缓解措施也可用于 ASP.NET Core 3.0。</span><span class="sxs-lookup"><span data-stu-id="61f85-127">The mitigation given for ASP.NET Core 2.x can also be used for ASP.NET Core 3.0.</span></span> <span data-ttu-id="61f85-128">未来的 3.0 预览版中，可能会删除 `Microsoft.AspNetCore.Authentication.Google` 包。</span><span class="sxs-lookup"><span data-stu-id="61f85-128">In future 3.0 previews, the `Microsoft.AspNetCore.Authentication.Google` package may be removed.</span></span> <span data-ttu-id="61f85-129">改为将用户定向到 `Microsoft.AspNetCore.Authentication.OpenIdConnect`。</span><span class="sxs-lookup"><span data-stu-id="61f85-129">Users would be directed to `Microsoft.AspNetCore.Authentication.OpenIdConnect` instead.</span></span> <span data-ttu-id="61f85-130">以下代码演示了如何在 `Startup.ConfigureServices` 中将 `AddGoogle` 替换为 `AddOpenIdConnect`。</span><span class="sxs-lookup"><span data-stu-id="61f85-130">The following code shows how to replace `AddGoogle` with `AddOpenIdConnect` in `Startup.ConfigureServices`.</span></span> <span data-ttu-id="61f85-131">此替换可以用于 ASP.NET Core 2.0 及更高版本，并且可以根据需要应用于 ASP.NET Core 1.x。</span><span class="sxs-lookup"><span data-stu-id="61f85-131">This replacement can be used with ASP.NET Core 2.0 and later and can be adapted for ASP.NET Core 1.x as needed.</span></span>

```csharp
.AddOpenIdConnect("Google", o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.Authority = "https://accounts.google.com";
    o.ResponseType = OpenIdConnectResponseType.Code;
    o.CallbackPath = "/signin-google"; // Or register the default "/sigin-oidc"
    o.Scope.Add("email");
});
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();
```

#### <a name="category"></a><span data-ttu-id="61f85-132">类别</span><span class="sxs-lookup"><span data-stu-id="61f85-132">Category</span></span>

<span data-ttu-id="61f85-133">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="61f85-133">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="61f85-134">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="61f85-134">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=fullName>

<!-- 

#### Affected APIs

`N:Microsoft.AspNetCore.Authentication.Google`

-->
