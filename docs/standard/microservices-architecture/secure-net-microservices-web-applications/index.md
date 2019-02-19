---
title: 保护 .NET 微服务和 Web 应用程序
description: .NET 微服务和 Web 应用中的安全性 - 了解 ASP.NET Core Web 应用中的身份验证选项。
author: mjrousos
ms.author: wiwagn
ms.date: 10/19/2018
ms.openlocfilehash: e53e6a50c1fdfaff6839a0a1e328047562a47824
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2019
ms.locfileid: "56333491"
---
# <a name="make-secure-net-microservices-and-web-applications"></a><span data-ttu-id="ba062-103">确保 .NET 微服务和 Web 应用的安全性</span><span class="sxs-lookup"><span data-stu-id="ba062-103">Make secure .NET Microservices and Web Applications</span></span>

<span data-ttu-id="ba062-104">微服务和 Web 应用的安全性具有许多方面，该主题可能需要许多本此类书籍才能描述完，因此在本部分中，我们将重点介绍身份验证、授权和应用程序密钥。</span><span class="sxs-lookup"><span data-stu-id="ba062-104">There are so many aspects about security in microservices and web applications that the topic could easy take several books like this one so, in this section, we'll focus on authentication, authorization, and application secrets.</span></span>

## <a name="implement-authentication-in-net-microservices-and-web-applications"></a><span data-ttu-id="ba062-105">在 .NET 微服务和 Web 应用中实施身份验证</span><span class="sxs-lookup"><span data-stu-id="ba062-105">Implement authentication in .NET microservices and web applications</span></span>

<span data-ttu-id="ba062-106">通常有必要将服务发布的资源和 API 限制为特定受信任的用户或客户端。</span><span class="sxs-lookup"><span data-stu-id="ba062-106">It's often necessary for resources and APIs published by a service to be limited to certain trusted users or clients.</span></span> <span data-ttu-id="ba062-107">制定有关这些种类的 API 级别信任决策的第一步是身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba062-107">The first step to making these sorts of API-level trust decisions is authentication.</span></span> <span data-ttu-id="ba062-108">身份验证是可靠验证用户标识的流程。</span><span class="sxs-lookup"><span data-stu-id="ba062-108">Authentication is the process of reliably verify a user’s identity.</span></span>

<span data-ttu-id="ba062-109">在微服务方案中，通常会集中处理身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba062-109">In microservice scenarios, authentication is typically handled centrally.</span></span> <span data-ttu-id="ba062-110">如果使用 API 网关，则网关是一个进行身份验证的好方法，如图 9-1 所示。</span><span class="sxs-lookup"><span data-stu-id="ba062-110">If you're using an API Gateway, the gateway is a good place to authenticate, as shown in Figure 9-1.</span></span> <span data-ttu-id="ba062-111">如果使用此方法，请确保在不使用 API 网关的情况下，无法直接访问各个微服务，除非其他安全性措施已就绪，可对来自网关和其他位置的消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba062-111">If you use this approach, make sure that the individual microservices cannot be reached directly (without the API Gateway) unless additional security is in place to authenticate messages whether they come from the gateway or not.</span></span>

![当 API 网关集中身份验证时，它会在向微服务转发请求时添加用户信息。](./media/image1.png)

<span data-ttu-id="ba062-113">**图 9-1**。</span><span class="sxs-lookup"><span data-stu-id="ba062-113">**Figure 9-1**.</span></span> <span data-ttu-id="ba062-114">使用 API 网关进行集中身份验证</span><span class="sxs-lookup"><span data-stu-id="ba062-114">Centralized authentication with an API Gateway</span></span>

<span data-ttu-id="ba062-115">如果可以直接访问服务，则身份验证服务（如 Azure Active Directory）或充当安全令牌服务 (STS) 的专用身份验证微服务可用于对用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba062-115">If services can be accessed directly, an authentication service like Azure Active Directory or a dedicated authentication microservice acting as a security token service (STS) can be used to authenticate users.</span></span> <span data-ttu-id="ba062-116">通过安全令牌或 cookie 在服务之间共享信任决策。</span><span class="sxs-lookup"><span data-stu-id="ba062-116">Trust decisions are shared between services with security tokens or cookies.</span></span> <span data-ttu-id="ba062-117">（如有需要，可在 ASP.NET Core 中使用[数据保护服务](/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)，在应用程序之间共享这些令牌。）此模式如图 9-2 所示。</span><span class="sxs-lookup"><span data-stu-id="ba062-117">(These tokens can be shared between applications, if needed, in ASP.NET Core with [data protection services](/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications).) This pattern is illustrated in Figure 9-2.</span></span>

![直接访问微服务时，包含身份验证和授权的信任由微服务之间共享的专用微服务颁发的安全令牌处理。](./media/image2.png)

<span data-ttu-id="ba062-119">**图 9-2**。</span><span class="sxs-lookup"><span data-stu-id="ba062-119">**Figure 9-2**.</span></span> <span data-ttu-id="ba062-120">通过标识微服务进行的身份验证；使用授权令牌共享信任</span><span class="sxs-lookup"><span data-stu-id="ba062-120">Authentication by identity microservice; trust is shared using an authorization token</span></span>

### <a name="authenticate-with-aspnet-core-identity"></a><span data-ttu-id="ba062-121">使用 ASP.NET Core 标识进行身份验证</span><span class="sxs-lookup"><span data-stu-id="ba062-121">Authenticate with ASP.NET Core Identity</span></span>

<span data-ttu-id="ba062-122">在 ASP.NET Core 中用于标识应用程序用户的主要机制是 [ASP.NET Core 标识](/aspnet/core/security/authentication/identity)成员身份系统。</span><span class="sxs-lookup"><span data-stu-id="ba062-122">The primary mechanism in ASP.NET Core for identifying an application’s users is the [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) membership system.</span></span> <span data-ttu-id="ba062-123">ASP.NET Core 标识会将用户信息（包括登录信息、角色和声明）存储在由开发人员配置的数据存储中。</span><span class="sxs-lookup"><span data-stu-id="ba062-123">ASP.NET Core Identity stores user information (including sign-in information, roles, and claims) in a data store configured by the developer.</span></span> <span data-ttu-id="ba062-124">通常情况下，ASP.NET Core 标识数据存储是 `Microsoft.AspNetCore.Identity.EntityFrameworkCore` 包中提供的实体框架存储。</span><span class="sxs-lookup"><span data-stu-id="ba062-124">Typically, the ASP.NET Core Identity data store is an Entity Framework store provided in the `Microsoft.AspNetCore.Identity.EntityFrameworkCore` package.</span></span> <span data-ttu-id="ba062-125">但是，自定义存储或其他第三方包可用于将标识信息存储在 Azure 表存储、CosmosDB 或其他位置。</span><span class="sxs-lookup"><span data-stu-id="ba062-125">However, custom stores or other third-party packages can be used to store identity information in Azure Table Storage, CosmosDB, or other locations.</span></span>

<span data-ttu-id="ba062-126">下面的代码来自选中单个用户帐户身份验证的 ASP.NET Core Web 应用程序项目模板。</span><span class="sxs-lookup"><span data-stu-id="ba062-126">The following code is taken from the ASP.NET Core Web Application project template with individual user account authentication selected.</span></span> <span data-ttu-id="ba062-127">它演示如何使用 Startup.ConfigureServices 方法中的 EntityFramework.Core 配置 ASP.NET Core 标识。</span><span class="sxs-lookup"><span data-stu-id="ba062-127">It shows how to configure ASP.NET Core Identity using EntityFramework.Core in the Startup.ConfigureServices method.</span></span>

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

<span data-ttu-id="ba062-128">配置 ASP.NET Core 标识后，可以通过调用服务的 `Startup.Configure` 方法中的 app.UseIdentity，启用该标识。</span><span class="sxs-lookup"><span data-stu-id="ba062-128">Once ASP.NET Core Identity is configured, you enable it by calling app.UseIdentity in the service’s `Startup.Configure` method.</span></span>

<span data-ttu-id="ba062-129">使用 ASP.NET Core 标识可支持多个方案：</span><span class="sxs-lookup"><span data-stu-id="ba062-129">Using ASP.NET Core Identity enables several scenarios:</span></span>

- <span data-ttu-id="ba062-130">使用 UserManager 类型 (userManager.CreateAsync) 创建新用户信息。</span><span class="sxs-lookup"><span data-stu-id="ba062-130">Create new user information using the UserManager type (userManager.CreateAsync).</span></span>

- <span data-ttu-id="ba062-131">使用 SignInManager 类型对用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba062-131">Authenticate users using the SignInManager type.</span></span> <span data-ttu-id="ba062-132">可以使用 `signInManager.SignInAsync` 直接登录，或使用 `signInManager.PasswordSignInAsync` 确认用户密码正确并登录。</span><span class="sxs-lookup"><span data-stu-id="ba062-132">You can use `signInManager.SignInAsync` to sign in directly, or `signInManager.PasswordSignInAsync` to confirm the user’s password is correct and then sign them in.</span></span>

- <span data-ttu-id="ba062-133">根据存储在 cookie（由 ASP.NET Core 标识中间件读取）中的信息标识用户，这样浏览器的后续请求中将包括已登录用户的标识和声明。</span><span class="sxs-lookup"><span data-stu-id="ba062-133">Identify a user based on information stored in a cookie (which is read by ASP.NET Core Identity middleware) so that subsequent requests from a browser will include a signed-in user’s identity and claims.</span></span>

<span data-ttu-id="ba062-134">ASP.NET Core 标识还支持[双因素身份验证](/aspnet/core/security/authentication/2fa)。</span><span class="sxs-lookup"><span data-stu-id="ba062-134">ASP.NET Core Identity also supports [two-factor authentication](/aspnet/core/security/authentication/2fa).</span></span>

<span data-ttu-id="ba062-135">对于使用本地用户数据存储并使用 cookie 保留请求间的标识（对于 MVC Web 应用程序是常见的）的身份验证方案，ASP.NET Core 标识是推荐的解决方案。</span><span class="sxs-lookup"><span data-stu-id="ba062-135">For authentication scenarios that make use of a local user data store and that persist identity between requests using cookies (as is typical for MVC web applications), ASP.NET Core Identity is a recommended solution.</span></span>

### <a name="authenticate-with-external-providers"></a><span data-ttu-id="ba062-136">使用外部提供程序进行身份验证</span><span class="sxs-lookup"><span data-stu-id="ba062-136">Authenticate with external providers</span></span>

<span data-ttu-id="ba062-137">ASP.NET Core 还支持使用[外部身份验证提供程序](/aspnet/core/security/authentication/social/)，使用户通过 [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) 流登录。</span><span class="sxs-lookup"><span data-stu-id="ba062-137">ASP.NET Core also supports using [external authentication providers](/aspnet/core/security/authentication/social/) to let users sign in via [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) flows.</span></span> <span data-ttu-id="ba062-138">这意味着用户可从 Microsoft、Google、Facebook 或 Twitter 等提供程序中使用现有身份验证流程登录，并将这些标识与应用程序中的 ASP.NET Core 标识相关联。</span><span class="sxs-lookup"><span data-stu-id="ba062-138">This means that users can sign in using existing authentication processes from providers like Microsoft, Google, Facebook, or Twitter and associate those identities with an ASP.NET Core identity in your application.</span></span>

<span data-ttu-id="ba062-139">若要使用外部身份验证，请在应用程序的 HTTP 请求处理管道中包括相应的身份验证中间件。</span><span class="sxs-lookup"><span data-stu-id="ba062-139">To use external authentication, you include the appropriate authentication middleware in your application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="ba062-140">此中间件负责处理从身份验证提供程序返回 URI 路由的请求，捕获标识信息，并实现通过 SignInManager.GetExternalLoginInfo 方法提供该信息。</span><span class="sxs-lookup"><span data-stu-id="ba062-140">This middleware is responsible for handling requests to return URI routes from the authentication provider, capturing identity information, and making it available via the SignInManager.GetExternalLoginInfo method.</span></span>

<span data-ttu-id="ba062-141">下表显示常用的外部身份验证提供程序及其关联的 NuGet 包：</span><span class="sxs-lookup"><span data-stu-id="ba062-141">Popular external authentication providers and their associated NuGet packages are shown in the following table:</span></span>

| <span data-ttu-id="ba062-142">**提供程序**</span><span class="sxs-lookup"><span data-stu-id="ba062-142">**Provider**</span></span>  | <span data-ttu-id="ba062-143">**包**</span><span class="sxs-lookup"><span data-stu-id="ba062-143">**Package**</span></span>                                          |
| ------------- | ---------------------------------------------------- |
| <span data-ttu-id="ba062-144">**Microsoft**</span><span class="sxs-lookup"><span data-stu-id="ba062-144">**Microsoft**</span></span> | <span data-ttu-id="ba062-145">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span><span class="sxs-lookup"><span data-stu-id="ba062-145">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span></span> |
| <span data-ttu-id="ba062-146">**Google**</span><span class="sxs-lookup"><span data-stu-id="ba062-146">**Google**</span></span>    | <span data-ttu-id="ba062-147">**Microsoft.AspNetCore.Authentication.Google**</span><span class="sxs-lookup"><span data-stu-id="ba062-147">**Microsoft.AspNetCore.Authentication.Google**</span></span>           |
| <span data-ttu-id="ba062-148">**Facebook**</span><span class="sxs-lookup"><span data-stu-id="ba062-148">**Facebook**</span></span>  | <span data-ttu-id="ba062-149">**Microsoft.AspNetCore.Authentication.Facebook**</span><span class="sxs-lookup"><span data-stu-id="ba062-149">**Microsoft.AspNetCore.Authentication.Facebook**</span></span>         |
| <span data-ttu-id="ba062-150">**Twitter**</span><span class="sxs-lookup"><span data-stu-id="ba062-150">**Twitter**</span></span>   | <span data-ttu-id="ba062-151">**Microsoft.AspNetCore.Authentication.Twitter**</span><span class="sxs-lookup"><span data-stu-id="ba062-151">**Microsoft.AspNetCore.Authentication.Twitter**</span></span>          |

<span data-ttu-id="ba062-152">在所有情况下，中间件注册与 `Startup.Configure` 中的 `app.Use{ExternalProvider}Authentication` 类似的对注册方法的调用。</span><span class="sxs-lookup"><span data-stu-id="ba062-152">In all cases, the middleware is registered with a call to a registration method similar to `app.Use{ExternalProvider}Authentication` in `Startup.Configure`.</span></span> <span data-ttu-id="ba062-153">根据提供程序的需要，这些注册方法会采用包含应用程序 ID 和机密信息（例如密码）的选项对象。</span><span class="sxs-lookup"><span data-stu-id="ba062-153">These registration methods take an options object that contains an application ID and secret information (a password, for instance), as needed by the provider.</span></span> <span data-ttu-id="ba062-154">外部身份验证提供程序要求注册应用程序（如 [ASP.NET Core 文档](/aspnet/core/security/authentication/social/)所述），以便通知用户哪些应用程序正在请求访问其标识。</span><span class="sxs-lookup"><span data-stu-id="ba062-154">External authentication providers require the application to be registered (as explained in [ASP.NET Core documentation](/aspnet/core/security/authentication/social/)) so that they can inform the user what application is requesting access to their identity.</span></span>

<span data-ttu-id="ba062-155">在 `Startup.Configure` 中注册中间件后，即可提示用户通过任何控制器操作进行登录。</span><span class="sxs-lookup"><span data-stu-id="ba062-155">Once the middleware is registered in `Startup.Configure`, you can prompt users to sign in from any controller action.</span></span> <span data-ttu-id="ba062-156">若要执行此操作，可以创建 `AuthenticationProperties` 对象，其中包含身份验证提供程序的名称和重定向 URL。</span><span class="sxs-lookup"><span data-stu-id="ba062-156">To do this, you create an `AuthenticationProperties` object that includes the authentication provider’s name and a redirect URL.</span></span> <span data-ttu-id="ba062-157">随后，可返回一个传递 `AuthenticationProperties` 对象的质询响应。</span><span class="sxs-lookup"><span data-stu-id="ba062-157">You then return a Challenge response that passes the `AuthenticationProperties` object.</span></span> <span data-ttu-id="ba062-158">下面的代码显示此响应的示例。</span><span class="sxs-lookup"><span data-stu-id="ba062-158">The following code shows an example of this.</span></span>

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

<span data-ttu-id="ba062-159">redirectUrl 参数包括用户通过身份验证后，外部提供程序应重定向到的 URL。</span><span class="sxs-lookup"><span data-stu-id="ba062-159">The redirectUrl parameter includes the URL that the external provider should redirect to once the user has authenticated.</span></span> <span data-ttu-id="ba062-160">该 URL 应表示基于外部标识信息使用户登录的操作，如以下简化示例所示：</span><span class="sxs-lookup"><span data-stu-id="ba062-160">The URL should represent an action that will sign the user in based on external identity information, as in the following simplified example:</span></span>

```csharp
// Sign in the user with this external login provider if the user
// already has a login.
var result = await _signInManager.ExternalLoginSignInAsync(info.LoginProvider, info.ProviderKey, isPersistent: false);

if (result.Succeeded)
{
    return RedirectToLocal(returnUrl);
}
else
{
    ApplicationUser newUser = new ApplicationUser
    {
        // The user object can be constructed with claims from the
        // external authentication provider, combined with information
        // supplied by the user after they have authenticated with
        // the external provider.
        UserName = info.Principal.FindFirstValue(ClaimTypes.Name),
        Email = info.Principal.FindFirstValue(ClaimTypes.Email)
    };
    var identityResult = await _userManager.CreateAsync(newUser);
    if (identityResult.Succeeded)
    {
        identityResult = await _userManager.AddLoginAsync(newUser, info);
        if (identityResult.Succeeded)
        {
            await _signInManager.SignInAsync(newUser, isPersistent: false);
        }
        return RedirectToLocal(returnUrl);
    }
}
```

<span data-ttu-id="ba062-161">在 Visual Studio 中创建 ASP.NET 代码 Web 应用程序项目时，如果选择“单个用户帐户”身份验证选项，则使用外部提供程序进行登录所需的所有代码已在项目中，如图 9-3 所示。</span><span class="sxs-lookup"><span data-stu-id="ba062-161">If you choose the **Individual User Account** authentication option when you create the ASP.NET Code web application project in Visual Studio, all the code necessary to sign in with an external provider is already in the project, as shown in Figure 9-3.</span></span>

![新 ASP.NET Core Web 应用的对话框，突出显示用于更改身份验证的按钮。](./media/image3.png)

<span data-ttu-id="ba062-163">**图 9-3**。</span><span class="sxs-lookup"><span data-stu-id="ba062-163">**Figure 9-3**.</span></span> <span data-ttu-id="ba062-164">创建 Web 应用程序项目时，选择一个用于使用外部身份验证的选项</span><span class="sxs-lookup"><span data-stu-id="ba062-164">Selecting an option for using external authentication when creating a web application project</span></span>

<span data-ttu-id="ba062-165">除了之前列出的外部身份验证提供程序外，还提供第三方包，其中提供可用于使用多个外部身份验证提供程序的中间件。</span><span class="sxs-lookup"><span data-stu-id="ba062-165">In addition to the external authentication providers listed previously, third-party packages are available that provide middleware for using many more external authentication providers.</span></span> <span data-ttu-id="ba062-166">有关列表，请参阅 GitHub 上的 [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) 存储库。</span><span class="sxs-lookup"><span data-stu-id="ba062-166">For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repo on GitHub.</span></span>

<span data-ttu-id="ba062-167">也可以创建自己的外部身份验证中间件以满足一些特殊需求。</span><span class="sxs-lookup"><span data-stu-id="ba062-167">You can also create your own external authentication middleware to solve some special need.</span></span>

### <a name="authenticate-with-bearer-tokens"></a><span data-ttu-id="ba062-168">使用持有者令牌进行身份验证</span><span class="sxs-lookup"><span data-stu-id="ba062-168">Authenticate with bearer tokens</span></span>

<span data-ttu-id="ba062-169">使用 ASP.NET Core 标识（或标识加外部身份验证提供程序）进行身份验证，这适用于应在 cookie 中存储用户信息的许多 Web 应用程序方案。</span><span class="sxs-lookup"><span data-stu-id="ba062-169">Authenticating with ASP.NET Core Identity (or Identity plus external authentication providers) works well for many web application scenarios in which storing user information in a cookie is appropriate.</span></span> <span data-ttu-id="ba062-170">但是，在其他方案中，cookie 不是保留和传输数据的自然方式。</span><span class="sxs-lookup"><span data-stu-id="ba062-170">In other scenarios, though, cookies are not a natural means of persisting and transmitting data.</span></span>

<span data-ttu-id="ba062-171">例如，在公开 Single Page Application (SPA)、本机客户端、甚至是其他 Web API 可能访问的 RESTful 终结点的 ASP.NET Core Web API 中，通常需要改为使用持有者令牌身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba062-171">For example, in an ASP.NET Core Web API that exposes RESTful endpoints that might be accessed by Single Page Applications (SPAs), by native clients, or even by other Web APIs, you typically want to use bearer token authentication instead.</span></span> <span data-ttu-id="ba062-172">这些类型的应用程序不能与 cookie 配合使用，但可以轻松地检索持有者令牌，并将其包括在后续请求的授权标头中。</span><span class="sxs-lookup"><span data-stu-id="ba062-172">These types of applications do not work with cookies, but can easily retrieve a bearer token and include it in the authorization header of subsequent requests.</span></span> <span data-ttu-id="ba062-173">若要启用令牌身份验证，ASP.NET Core 支持几个用于使用 [OAuth 2.0](https://oauth.net/2/) 和 [OpenID Connect](https://openid.net/connect/) 的选项。</span><span class="sxs-lookup"><span data-stu-id="ba062-173">To enable token authentication, ASP.NET Core supports several options for using [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](https://openid.net/connect/).</span></span>

### <a name="authenticate-with-an-openid-connect-or-oauth-20-identity-provider"></a><span data-ttu-id="ba062-174">使用 OpenID Connect 或 OAuth 2.0 标识提供程序进行身份验证</span><span class="sxs-lookup"><span data-stu-id="ba062-174">Authenticate with an OpenID Connect or OAuth 2.0 Identity provider</span></span>

<span data-ttu-id="ba062-175">如果用户信息存储在 Azure Active Directory 或其他支持 OpenID Connect 或 OAuth 2.0 的标识解决方案中，则可以使用 Microsoft.AspNetCore.Authentication.OpenIdConnect 包，通过 OpenID Connect 工作流进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba062-175">If user information is stored in Azure Active Directory or another identity solution that supports OpenID Connect or OAuth 2.0, you can use the **Microsoft.AspNetCore.Authentication.OpenIdConnect** package to authenticate using the OpenID Connect workflow.</span></span> <span data-ttu-id="ba062-176">例如，如果要对 eShopOnContainers 中的 Identity.Api microservice 进行身份验证，ASP.NET Core Web 应用可以使用该包中的中间件，如 `Startup.cs` 中的以下简化示例所示：</span><span class="sxs-lookup"><span data-stu-id="ba062-176">For example, to authenticate to the Identity.Api microservice in eShopOnContainers, an ASP.NET Core web application can use middleware from that package as shown in the following simplified example in `Startup.cs`:</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseMvc();
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");
    var callBackUrl = Configuration.GetValue<string>("CallBackUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = OpenIdConnectDefaults.AuthenticationScheme;
    })
    .AddCookie()
    .AddOpenIdConnect(options =>
    {
        options.SignInScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.Authority = identityUrl;
        options.SignedOutRedirectUri = callBackUrl;
        options.ClientSecret = "secret";
        options.SaveTokens = true;
        options.GetClaimsFromUserInfoEndpoint = true;
        options.RequireHttpsMetadata = false;
        options.Scope.Add("openid");
        options.Scope.Add("profile");
        options.Scope.Add("orders");
        options.Scope.Add("basket");
        options.Scope.Add("marketing");
        options.Scope.Add("locations");
        options.Scope.Add("webshoppingagg");
        options.Scope.Add("orders.signalrhub");
    });
}
```

<span data-ttu-id="ba062-177">请注意，使用此工作流时，不需要 ASP.NET Core 标识中间件，因为所有的用户信息存储和身份验证均由标识服务处理。</span><span class="sxs-lookup"><span data-stu-id="ba062-177">Note that when you use this workflow, the ASP.NET Core Identity middleware is not needed, because all user information storage and authentication is handled by the Identity service.</span></span>

### <a name="issue-security-tokens-from-an-aspnet-core-service"></a><span data-ttu-id="ba062-178">从 ASP.NET Core 服务颁发安全令牌</span><span class="sxs-lookup"><span data-stu-id="ba062-178">Issue security tokens from an ASP.NET Core service</span></span>

<span data-ttu-id="ba062-179">如果希望为本地 ASP.NET Core 标识用户颁发安全令牌，而不是使用外部标识提供程序，可利用一些优秀的第三方库。</span><span class="sxs-lookup"><span data-stu-id="ba062-179">If you prefer to issue security tokens for local ASP.NET Core Identity users rather than using an external identity provider, you can take advantage of some good third-party libraries.</span></span>

<span data-ttu-id="ba062-180">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) 和 [OpenIddict](https://github.com/openiddict/openiddict-core) 是 OpenID Connect 提供程序，可轻松地与 ASP.NET Core 标识集成，使用户能够从 ASP.NET Core 服务颁发安全令牌。</span><span class="sxs-lookup"><span data-stu-id="ba062-180">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) and [OpenIddict](https://github.com/openiddict/openiddict-core) are OpenID Connect providers that integrate easily with ASP.NET Core Identity to let you issue security tokens from an ASP.NET Core service.</span></span> <span data-ttu-id="ba062-181">[IdentityServer4 文档](https://identityserver4.readthedocs.io/en/latest/)具有有关如何使用库的详细说明。</span><span class="sxs-lookup"><span data-stu-id="ba062-181">The [IdentityServer4 documentation](https://identityserver4.readthedocs.io/en/latest/) has in-depth instructions for using the library.</span></span> <span data-ttu-id="ba062-182">但是，使用 IdentityServer4 颁发令牌的基本步骤如下所示。</span><span class="sxs-lookup"><span data-stu-id="ba062-182">However, the basic steps to using IdentityServer4 to issue tokens are as follows.</span></span>

1. <span data-ttu-id="ba062-183">调用 Startup.Configure 方法中的 app.UseIdentityServer，将 IdentityServer4 添加到应用程序的 HTTP 请求处理管道。</span><span class="sxs-lookup"><span data-stu-id="ba062-183">You call app.UseIdentityServer in the Startup.Configure method to add IdentityServer4 to the application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="ba062-184">这使库能够为指向 OpenID Connect 和 OAuth2 终结点（如 /connect/token）的请求提供服务。</span><span class="sxs-lookup"><span data-stu-id="ba062-184">This lets the library serve requests to OpenID Connect and OAuth2 endpoints like /connect/token.</span></span>

2. <span data-ttu-id="ba062-185">通过调用 services.AddIdentityServer，配置 Startup.ConfigureServices 中的 IdentityServer4。</span><span class="sxs-lookup"><span data-stu-id="ba062-185">You configure IdentityServer4 in Startup.ConfigureServices by making a call to services.AddIdentityServer.</span></span>

3. <span data-ttu-id="ba062-186">通过设置以下数据，配置标识服务器：</span><span class="sxs-lookup"><span data-stu-id="ba062-186">You configure identity server by setting the following data:</span></span>

   - <span data-ttu-id="ba062-187">用于签名的[凭据](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html)。</span><span class="sxs-lookup"><span data-stu-id="ba062-187">The [credentials](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) to use for signing.</span></span>

   - <span data-ttu-id="ba062-188">用户可能会请求访问的[标识和 API 资源](https://identityserver4.readthedocs.io/en/latest/topics/resources.html)：</span><span class="sxs-lookup"><span data-stu-id="ba062-188">The [Identity and API resources](https://identityserver4.readthedocs.io/en/latest/topics/resources.html) that users might request access to:</span></span>

      - <span data-ttu-id="ba062-189">API 资源表示用户可通过访问令牌访问的受保护数据或功能。</span><span class="sxs-lookup"><span data-stu-id="ba062-189">API resources represent protected data or functionality that a user can access with an access token.</span></span> <span data-ttu-id="ba062-190">API 资源的一个示例是要求授权的 Web API（或 API 集）。</span><span class="sxs-lookup"><span data-stu-id="ba062-190">An example of an API resource would be a web API (or set of APIs) that requires authorization.</span></span>

      - <span data-ttu-id="ba062-191">标识资源表示提供给客户端进行用户识别的信息（声明）。</span><span class="sxs-lookup"><span data-stu-id="ba062-191">Identity resources represent information (claims) that are given to a client to identify a user.</span></span> <span data-ttu-id="ba062-192">声明可能包括用户名称、电子邮件地址等。</span><span class="sxs-lookup"><span data-stu-id="ba062-192">The claims might include the user name, email address, and so on.</span></span>

   - <span data-ttu-id="ba062-193">为请求令牌而连接的[客户端](https://identityserver4.readthedocs.io/en/latest/topics/clients.html)。</span><span class="sxs-lookup"><span data-stu-id="ba062-193">The [clients](https://identityserver4.readthedocs.io/en/latest/topics/clients.html) that will be connecting in order to request tokens.</span></span>

   - <span data-ttu-id="ba062-194">用户信息的存储机制，如 [ASP.NET Core 标识](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html)或一种替代方法。</span><span class="sxs-lookup"><span data-stu-id="ba062-194">The storage mechanism for user information, such as [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) or an alternative.</span></span>

<span data-ttu-id="ba062-195">为要使用的 IdentityServer4 指定客户端和资源时，可以将相应类型的 <xref:System.Collections.Generic.IEnumerable%601> 集合传递到采用内存中客户端或资源存储的方法中。</span><span class="sxs-lookup"><span data-stu-id="ba062-195">When you specify clients and resources for IdentityServer4 to use, you can pass an <xref:System.Collections.Generic.IEnumerable%601> collection of the appropriate type to methods that take in-memory client or resource stores.</span></span> <span data-ttu-id="ba062-196">或者对于更复杂的方案，可以通过依赖项注入提供客户端或资源提供程序类型。</span><span class="sxs-lookup"><span data-stu-id="ba062-196">Or for more complex scenarios, you can provide client or resource provider types via Dependency Injection.</span></span>

<span data-ttu-id="ba062-197">IdentityServer4 使用自定义 IClientStore 类型提供的内存中资源和客户端的示例配置可能类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="ba062-197">A sample configuration for IdentityServer4 to use in-memory resources and clients provided by a custom IClientStore type might look like the following example:</span></span>

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

### <a name="consume-security-tokens"></a><span data-ttu-id="ba062-198">使用安全令牌</span><span class="sxs-lookup"><span data-stu-id="ba062-198">Consume security tokens</span></span>

<span data-ttu-id="ba062-199">针对 OpenID Connect 终结点进行身份验证或自行颁发安全令牌会涵盖一些方案。</span><span class="sxs-lookup"><span data-stu-id="ba062-199">Authenticating against an OpenID Connect endpoint or issuing your own security tokens covers some scenarios.</span></span> <span data-ttu-id="ba062-200">但对于某个服务，如果它只需限制对具有由其他服务提供的有效安全令牌的用户的访问，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="ba062-200">But what about a service that simply needs to limit access to those users who have valid security tokens that were provided by a different service?</span></span>

<span data-ttu-id="ba062-201">对于这种情况，Microsoft.AspNetCore.Authentication.JwtBearer 包中提供处理 JWT 令牌的身份验证中间件。</span><span class="sxs-lookup"><span data-stu-id="ba062-201">For that scenario, authentication middleware that handles JWT tokens is available in the **Microsoft.AspNetCore.Authentication.JwtBearer** package.</span></span> <span data-ttu-id="ba062-202">JWT 代表“[JSON Web 令牌](https://tools.ietf.org/html/rfc7519)”，是适用于传递安全声明的通用安全令牌格式（由 RFC 7519 定义）。</span><span class="sxs-lookup"><span data-stu-id="ba062-202">JWT stands for "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" and is a common security token format (defined by RFC 7519) for communicating security claims.</span></span> <span data-ttu-id="ba062-203">如何通过中间件使用此类令牌的简化示例可能如以下代码片段（取自 eShopOnContainers 的 Ordering.Api 微服务）所示。</span><span class="sxs-lookup"><span data-stu-id="ba062-203">A simplified example of how to use middleware to consume such tokens might look like this code fragment, taken from the Ordering.Api microservice of eShopOnContainers.</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseMvc();
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");

    // Add Authentication services

    var identityUrl = configuration.GetValue<string>("IdentityUrl");

    services.AddAuthentication(options =>
    {
        options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;

    }).AddJwtBearer(options =>
    {
        options.Authority = identityUrl;
        options.RequireHttpsMetadata = false;
        options.Audience = "orders";
    });
}
```

<span data-ttu-id="ba062-204">此用法的参数包括：</span><span class="sxs-lookup"><span data-stu-id="ba062-204">The parameters in this usage are:</span></span>

- <span data-ttu-id="ba062-205">`Audience` 表示传入令牌的接收方或令牌授予访问权限的资源。</span><span class="sxs-lookup"><span data-stu-id="ba062-205">`Audience` represents the receiver of the incoming token or the resource that the token grants access to.</span></span> <span data-ttu-id="ba062-206">如果此参数中指定的值与令牌中的参数不匹配，则会拒绝该令牌。</span><span class="sxs-lookup"><span data-stu-id="ba062-206">If the value specified in this parameter does not match the parameter in the token, the token will be rejected.</span></span>

- <span data-ttu-id="ba062-207">`Authority` 是颁发令牌的身份验证服务器的地址。</span><span class="sxs-lookup"><span data-stu-id="ba062-207">`Authority` is the address of the token-issuing authentication server.</span></span> <span data-ttu-id="ba062-208">JWT 持有者身份验证中间件使用此 URI 获取可用于验证令牌签名的公钥。</span><span class="sxs-lookup"><span data-stu-id="ba062-208">The JWT bearer authentication middleware uses this URI to get the public key that can be used to validate the token's signature.</span></span> <span data-ttu-id="ba062-209">该中间件还确认令牌中的 `iss` 参数是否与此 URI 匹配。</span><span class="sxs-lookup"><span data-stu-id="ba062-209">The middleware also confirms that the `iss` parameter in the token matches this URI.</span></span>

<span data-ttu-id="ba062-210">另一个参数 `RequireHttpsMetadata` 用于测试目的；将此参数设置为 false，可在你没有证书的环境中进行测试。</span><span class="sxs-lookup"><span data-stu-id="ba062-210">Another parameter, `RequireHttpsMetadata`, is useful for testing purposes; you set this parameter to false so you can test in environments where you don't have certificates.</span></span> <span data-ttu-id="ba062-211">在实际部署中，JWT 持有者令牌应始终只能通过 HTTPS 传递。</span><span class="sxs-lookup"><span data-stu-id="ba062-211">In real-world deployments, JWT bearer tokens should always be passed only over HTTPS.</span></span>

<span data-ttu-id="ba062-212">此中间件准备就绪后，会自动从授权标头中提取 JWT 令牌。</span><span class="sxs-lookup"><span data-stu-id="ba062-212">With this middleware in place, JWT tokens are automatically extracted from authorization headers.</span></span> <span data-ttu-id="ba062-213">然后对其进行反序列化、验证（使用 `Audience` 和 `Authority` 参数的值），并将其存储为用户信息，稍后供 MVC 操作或授权筛选器引用。</span><span class="sxs-lookup"><span data-stu-id="ba062-213">They are then deserialized, validated (using the values in the `Audience` and `Authority` parameters), and stored as user information to be referenced later by MVC actions or authorization filters.</span></span>

<span data-ttu-id="ba062-214">JWT 持有者身份验证中间件还可以支持更高级的方案，例如颁发机构不可用时使用本地证书验证令牌。</span><span class="sxs-lookup"><span data-stu-id="ba062-214">The JWT bearer authentication middleware can also support more advanced scenarios, such as using a local certificate to validate a token if the authority is not available.</span></span> <span data-ttu-id="ba062-215">对于此情景，可以在 `JwtBearerOptions` 对象中指定 `TokenValidationParameters` 对象。</span><span class="sxs-lookup"><span data-stu-id="ba062-215">For this scenario, you can specify a `TokenValidationParameters` object in the `JwtBearerOptions` object.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ba062-216">其他资源</span><span class="sxs-lookup"><span data-stu-id="ba062-216">Additional resources</span></span>

- <span data-ttu-id="ba062-217">**在应用程序之间共享 cookie** \\</span><span class="sxs-lookup"><span data-stu-id="ba062-217">**Sharing cookies between applications** \\</span></span>
  [*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)

- <span data-ttu-id="ba062-218">**标识简介** \\</span><span class="sxs-lookup"><span data-stu-id="ba062-218">**Introduction to Identity** \\</span></span>
  [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](/aspnet/core/security/authentication/identity)

- <span data-ttu-id="ba062-219">**Rick Anderson。使用短信的双因素身份验证** \\</span><span class="sxs-lookup"><span data-stu-id="ba062-219">**Rick Anderson. Two-factor authentication with SMS** \\</span></span>
  [*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](/aspnet/core/security/authentication/2fa)

- <span data-ttu-id="ba062-220">**启用使用 Facebook、Google 和其他外部提供程序的身份验证** \\</span><span class="sxs-lookup"><span data-stu-id="ba062-220">**Enabling authentication using Facebook, Google and other external providers** \\</span></span>
  [*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](/aspnet/core/security/authentication/social/)

- <span data-ttu-id="ba062-221">**Michell Anicas。OAuth 2 简介** \\</span><span class="sxs-lookup"><span data-stu-id="ba062-221">**Michell Anicas. An Introduction to OAuth 2** \\</span></span>
  [*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)

- <span data-ttu-id="ba062-222">**AspNet.Security.OAuth.Providers**（ASP.NET OAuth 提供程序的 GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="ba062-222">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers.</span></span> \
  [*https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src*](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src)

- <span data-ttu-id="ba062-223">**Danny Strockis。将 Azure AD 集成到 ASP.NET Core Web 应用中** \\</span><span class="sxs-lookup"><span data-stu-id="ba062-223">**Danny Strockis. Integrating Azure AD into an ASP.NET Core web app** \\</span></span>
  [*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)

- <span data-ttu-id="ba062-224">**IdentityServer4。官方文档** \\</span><span class="sxs-lookup"><span data-stu-id="ba062-224">**IdentityServer4. Official documentation** \\</span></span>
  *<https://identityserver4.readthedocs.io/en/latest/>*

>[!div class="step-by-step"]
><span data-ttu-id="ba062-225">[上一页](../implement-resilient-applications/monitor-app-health.md)
>[下一页](authorization-net-microservices-web-applications.md)</span><span class="sxs-lookup"><span data-stu-id="ba062-225">[Previous](../implement-resilient-applications/monitor-app-health.md)
[Next](authorization-net-microservices-web-applications.md)</span></span>
