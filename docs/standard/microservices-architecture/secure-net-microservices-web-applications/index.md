---
title: 保护 .NET 微服务和 Web 应用程序
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 保护 .NET 微服务和 Web 应用程序
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 0e55a68432dfd44c7a73ae51512f50d481ae100c
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "37937028"
---
# <a name="securing-net-microservices-and-web-applications"></a><span data-ttu-id="81630-103">保护 .NET 微服务和 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="81630-103">Securing .NET Microservices and Web Applications</span></span>

<span data-ttu-id="81630-104">通常有必要将服务公开的资源和 API 限制为特定受信任的用户或客户端。</span><span class="sxs-lookup"><span data-stu-id="81630-104">It is often necessary for resources and APIs exposed by a service to be limited to certain trusted users or clients.</span></span> <span data-ttu-id="81630-105">制定有关这些种类的 API 级别信任决策的第一步是身份验证。</span><span class="sxs-lookup"><span data-stu-id="81630-105">The first step to making these sorts of API-level trust decisions is authentication.</span></span> <span data-ttu-id="81630-106">身份验证是可靠判断用户标识的流程。</span><span class="sxs-lookup"><span data-stu-id="81630-106">Authentication is the process of reliably ascertaining a user’s identity.</span></span>

<span data-ttu-id="81630-107">在微服务方案中，通常会集中处理身份验证。</span><span class="sxs-lookup"><span data-stu-id="81630-107">In microservice scenarios, authentication is typically handled centrally.</span></span> <span data-ttu-id="81630-108">如果使用 API 网关，则网关是一个进行身份验证的好方法，如图 11-1 所示。</span><span class="sxs-lookup"><span data-stu-id="81630-108">If you are using an API Gateway, the gateway is a good place to authenticate, as shown in Figure 11-1.</span></span> <span data-ttu-id="81630-109">如果使用此方法，请确保在不使用 API 网关的情况下，无法直接访问各个微服务，除非其他安全性措施已就绪，可对来自网关和其他位置的消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="81630-109">If you use this approach, make sure that the individual microservices cannot be reached directly (without the API Gateway) unless additional security is in place to authenticate messages whether they come from the gateway or not.</span></span>

![](./media/image1.png)

<span data-ttu-id="81630-110">图 11-1。</span><span class="sxs-lookup"><span data-stu-id="81630-110">**Figure 11-1**.</span></span> <span data-ttu-id="81630-111">使用 API 网关进行集中身份验证</span><span class="sxs-lookup"><span data-stu-id="81630-111">Centralized authentication with an API Gateway</span></span>

<span data-ttu-id="81630-112">如果可以直接访问服务，则身份验证服务（如 Azure Active Directory）或充当安全令牌服务 (STS) 的专用身份验证微服务可用于对用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="81630-112">If services can be accessed directly, an authentication service like Azure Active Directory or a dedicated authentication microservice acting as a security token service (STS) can be used to authenticate users.</span></span> <span data-ttu-id="81630-113">通过安全令牌或 cookie 在服务之间共享信任决策。</span><span class="sxs-lookup"><span data-stu-id="81630-113">Trust decisions are shared between services with security tokens or cookies.</span></span> <span data-ttu-id="81630-114">（如有需要，可在 ASP.NET Core 中使用[数据保护服务](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)，在应用程序之间共享这些内容。）此模式如图 11-2 所示。</span><span class="sxs-lookup"><span data-stu-id="81630-114">(These can be shared between applications, if needed, in ASP.NET Core with [data protection services](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications).) This pattern is illustrated in Figure 11-2.</span></span>

![](./media/image2.png)

<span data-ttu-id="81630-115">图 11-2。</span><span class="sxs-lookup"><span data-stu-id="81630-115">**Figure 11-2**.</span></span> <span data-ttu-id="81630-116">通过标识微服务进行的身份验证；使用授权令牌共享信任</span><span class="sxs-lookup"><span data-stu-id="81630-116">Authentication by identity microservice; trust is shared using an authorization token</span></span>

## <a name="authenticating-using-aspnet-core-identity"></a><span data-ttu-id="81630-117">使用 ASP.NET Core 标识进行身份验证</span><span class="sxs-lookup"><span data-stu-id="81630-117">Authenticating using ASP.NET Core Identity</span></span>

<span data-ttu-id="81630-118">在 ASP.NET Core 中用于标识应用程序用户的主要机制是 [ASP.NET Core 标识](https://docs.microsoft.com/aspnet/core/security/authentication/identity)成员身份系统。</span><span class="sxs-lookup"><span data-stu-id="81630-118">The primary mechanism in ASP.NET Core for identifying an application’s users is the [ASP.NET Core Identity](https://docs.microsoft.com/aspnet/core/security/authentication/identity) membership system.</span></span> <span data-ttu-id="81630-119">ASP.NET Core 标识会将用户信息（包括登录信息、角色和声明）存储在由开发人员配置的数据存储中。</span><span class="sxs-lookup"><span data-stu-id="81630-119">ASP.NET Core Identity stores user information (including sign-in information, roles, and claims) in a data store configured by the developer.</span></span> <span data-ttu-id="81630-120">通常情况下，ASP.NET Core 标识数据存储是 Microsoft.AspNetCore.Identity.EntityFrameworkCore 包中提供的实体框架存储。</span><span class="sxs-lookup"><span data-stu-id="81630-120">Typically, the ASP.NET Core Identity data store is an Entity Framework store provided in the Microsoft.AspNetCore.Identity.EntityFrameworkCore package.</span></span> <span data-ttu-id="81630-121">但是，自定义存储或其他第三方包可用于将标识信息存储在 Azure 表存储、CosmosDB 或其他位置。</span><span class="sxs-lookup"><span data-stu-id="81630-121">However, custom stores or other third-party packages can be used to store identity information in Azure Table Storage, DocumentDB, or other locations.</span></span>

<span data-ttu-id="81630-122">下面的代码来自选中单个用户帐户身份验证的 ASP.NET Core Web 应用程序项目模板。</span><span class="sxs-lookup"><span data-stu-id="81630-122">The following code is taken from the ASP.NET Core Web Application project template with individual user account authentication selected.</span></span> <span data-ttu-id="81630-123">它演示如何使用 Startup.ConfigureServices 方法中的 EntityFramework.Core 配置 ASP.NET Core 标识。</span><span class="sxs-lookup"><span data-stu-id="81630-123">It shows how to configure ASP.NET Core Identity using EntityFramework.Core in the Startup.ConfigureServices method.</span></span>

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

<span data-ttu-id="81630-124">配置 ASP.NET Core 标识后，可以通过调用服务的 Startup.Configure 方法中的 app.UseIdentity，启用该标识。</span><span class="sxs-lookup"><span data-stu-id="81630-124">Once ASP.NET Core Identity is configured, you enable it by calling app.UseIdentity in the service’s Startup.Configure method.</span></span>

<span data-ttu-id="81630-125">使用 ASP.NET Core 标识可支持多个方案：</span><span class="sxs-lookup"><span data-stu-id="81630-125">Using ASP.NET Core Identity enables several scenarios:</span></span>

-   <span data-ttu-id="81630-126">使用 UserManager 类型 (userManager.CreateAsync) 创建新用户信息。</span><span class="sxs-lookup"><span data-stu-id="81630-126">Create new user information using the UserManager type (userManager.CreateAsync).</span></span>

-   <span data-ttu-id="81630-127">使用 SignInManager 类型对用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="81630-127">Authenticate users using the SignInManager type.</span></span> <span data-ttu-id="81630-128">可以使用 signInManager.SignInAsync 直接登录，或者使用 signInManager.PasswordSignInAsync 确认用户的密码正确无误，然后登录。</span><span class="sxs-lookup"><span data-stu-id="81630-128">You can use signInManager.SignInAsync to sign in directly, or signInManager.PasswordSignInAsync to confirm the user’s password is correct and then sign them in.</span></span>

-   <span data-ttu-id="81630-129">根据存储在 cookie（由 ASP.NET Core 标识中间件读取）中的信息标识用户，这样浏览器的后续请求中将包括已登录用户的标识和声明。</span><span class="sxs-lookup"><span data-stu-id="81630-129">Identify a user based on information stored in a cookie (which is read by ASP.NET Core Identity middleware) so that subsequent requests from a browser will include a signed-in user’s identity and claims.</span></span>

<span data-ttu-id="81630-130">ASP.NET Core 标识还支持[双因素身份验证](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)。</span><span class="sxs-lookup"><span data-stu-id="81630-130">ASP.NET Core Identity also supports [two-factor authentication](https://docs.microsoft.com/aspnet/core/security/authentication/2fa).</span></span>

<span data-ttu-id="81630-131">对于使用本地用户数据存储并使用 cookie 保留请求间的标识（对于 MVC Web 应用程序是常见的）的身份验证方案，ASP.NET Core 标识是推荐的解决方案。</span><span class="sxs-lookup"><span data-stu-id="81630-131">For authentication scenarios that make use of a local user data store and that persist identity between requests using cookies (as is typical for MVC web applications), ASP.NET Core Identity is a recommended solution.</span></span>

## <a name="authenticating-using-external-providers"></a><span data-ttu-id="81630-132">使用外部提供程序进行身份验证</span><span class="sxs-lookup"><span data-stu-id="81630-132">Authenticating using external providers</span></span>

<span data-ttu-id="81630-133">ASP.NET Core 还支持使用[外部身份验证提供程序](https://docs.microsoft.com/aspnet/core/security/authentication/social/)，使用户通过 [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) 流登录。</span><span class="sxs-lookup"><span data-stu-id="81630-133">ASP.NET Core also supports using [external authentication providers](https://docs.microsoft.com/aspnet/core/security/authentication/social/) to let users log in via [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) flows.</span></span> <span data-ttu-id="81630-134">这意味着用户可从 Microsoft、Google、Facebook 或 Twitter 等提供程序中使用现有身份验证流程登录，并将这些标识与应用程序中的 ASP.NET Core 标识相关联。</span><span class="sxs-lookup"><span data-stu-id="81630-134">This means that users can log in using existing authentication processes from providers like Microsoft, Google, Facebook, or Twitter and associate those identities with an ASP.NET Core identity in your application.</span></span>

<span data-ttu-id="81630-135">若要使用外部身份验证，请在应用程序的 HTTP 请求处理管道中包括相应的身份验证中间件。</span><span class="sxs-lookup"><span data-stu-id="81630-135">To use external authentication, you include the appropriate authentication middleware in your application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="81630-136">此中间件负责处理从身份验证提供程序返回 URI 路由的请求，捕获标识信息，并实现通过 SignInManager.GetExternalLoginInfo 方法提供该信息。</span><span class="sxs-lookup"><span data-stu-id="81630-136">This middleware is responsible for handling requests to return URI routes from the authentication provider, capturing identity information, and making it available via the SignInManager.GetExternalLoginInfo method.</span></span>

<span data-ttu-id="81630-137">下面显示常用的外部身份验证提供程序及其关联的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="81630-137">Popular external authentication providers and their associated NuGet packages are shown below.</span></span>

<span data-ttu-id="81630-138">**Microsoft：** Microsoft.AspNetCore.Authentication.MicrosoftAccount</span><span class="sxs-lookup"><span data-stu-id="81630-138">**Microsoft:** Microsoft.AspNetCore.Authentication.MicrosoftAccount</span></span>

<span data-ttu-id="81630-139">**Google：** Microsoft.AspNetCore.Authentication.Google</span><span class="sxs-lookup"><span data-stu-id="81630-139">**Google:** Microsoft.AspNetCore.Authentication.Google</span></span>

<span data-ttu-id="81630-140">**Facebook：** Microsoft.AspNetCore.Authentication.Facebook</span><span class="sxs-lookup"><span data-stu-id="81630-140">**Facebook:** Microsoft.AspNetCore.Authentication.Facebook</span></span>

<span data-ttu-id="81630-141">**Twitter：** Microsoft.AspNetCore.Authentication.Twitter</span><span class="sxs-lookup"><span data-stu-id="81630-141">**Twitter:** Microsoft.AspNetCore.Authentication.Twitter</span></span>

<span data-ttu-id="81630-142">在所有情况下，中间件都会向类似于 Startup.Configure 中的 app.Use{ExternalProvider}Authentication 的注册方法调用注册。</span><span class="sxs-lookup"><span data-stu-id="81630-142">In all cases, the middleware is registered with a call to a registration method similar to app.Use{ExternalProvider}Authentication in Startup.Configure.</span></span> <span data-ttu-id="81630-143">根据提供程序的需要，这些注册方法会采用包含应用程序 ID 和机密信息（例如密码）的选项对象。</span><span class="sxs-lookup"><span data-stu-id="81630-143">These registration methods take an options object that contains an application ID and secret information (a password, for instance), as needed by the provider.</span></span> <span data-ttu-id="81630-144">外部身份验证提供程序要求注册应用程序（如 [ASP.NET Core 文档](https://docs.microsoft.com/aspnet/core/security/authentication/social/)所述），以便通知用户哪些应用程序正在请求访问其标识。</span><span class="sxs-lookup"><span data-stu-id="81630-144">External authentication providers require the application to be registered (as explained in [ASP.NET Core documentation](https://docs.microsoft.com/aspnet/core/security/authentication/social/)) so that they can inform the user what application is requesting access to their identity.</span></span>

<span data-ttu-id="81630-145">在 Startup.Configure 中注册中间件后，即可提示用户通过任何控制器操作进行登录。</span><span class="sxs-lookup"><span data-stu-id="81630-145">Once the middleware is registered in Startup.Configure, you can prompt users to log in from any controller action.</span></span> <span data-ttu-id="81630-146">若要执行此操作，可以创建 AuthenticationProperties 对象，其中包含身份验证提供程序的名称和重定向 URL。</span><span class="sxs-lookup"><span data-stu-id="81630-146">To do this, you create an AuthenticationProperties object that includes the authentication provider’s name and a redirect URL.</span></span> <span data-ttu-id="81630-147">随后，可返回一个传递 AuthenticationProperties 对象的质询响应。</span><span class="sxs-lookup"><span data-stu-id="81630-147">You then return a Challenge response that passes the AuthenticationProperties object.</span></span> <span data-ttu-id="81630-148">下面的代码显示此响应的示例。</span><span class="sxs-lookup"><span data-stu-id="81630-148">The following code shows an example of this.</span></span>

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

<span data-ttu-id="81630-149">redirectUrl 参数包括用户通过身份验证后，外部提供程序应重定向到的 URL。</span><span class="sxs-lookup"><span data-stu-id="81630-149">The redirectUrl parameter includes the URL that the external provider should redirect to once the user has authenticated.</span></span> <span data-ttu-id="81630-150">该 URL 应表示基于外部标识信息使用户登录的操作，如以下简化示例所示：</span><span class="sxs-lookup"><span data-stu-id="81630-150">The URL should represent an action that will sign the user in based on external identity information, as in the following simplified example:</span></span>

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

<span data-ttu-id="81630-151">在 Visual Studio 中创建 ASP.NET 代码 Web 应用程序项目时，如果选择“单个用户帐户”身份验证选项，则使用外部提供程序进行登录所需的所有代码已在项目中，如图 11-3 所示。</span><span class="sxs-lookup"><span data-stu-id="81630-151">If you choose the **Individual User Account** authentication option when you create the ASP.NET Code web application project in Visual Studio, all the code necessary to sign in with an external provider is already in the project, as shown in Figure 11-3.</span></span>

![https://msdnshared.blob.core.windows.net/media/2016/10/new-web-app.png](./media/image3.png)

<span data-ttu-id="81630-152">图 11-3。</span><span class="sxs-lookup"><span data-stu-id="81630-152">**Figure 11-3**.</span></span> <span data-ttu-id="81630-153">创建 Web 应用程序项目时，选择一个用于使用外部身份验证的选项</span><span class="sxs-lookup"><span data-stu-id="81630-153">Selecting an option for using external authentication when creating a web application project</span></span>

<span data-ttu-id="81630-154">除了之前列出的外部身份验证提供程序外，还提供第三方包，其中提供可用于使用多个外部身份验证提供程序的中间件。</span><span class="sxs-lookup"><span data-stu-id="81630-154">In addition to the external authentication providers listed previously, third-party packages are available that provide middleware for using many more external authentication providers.</span></span> <span data-ttu-id="81630-155">有关列表，请参阅 GitHub 上的 [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) 存储库。</span><span class="sxs-lookup"><span data-stu-id="81630-155">For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repo on GitHub.</span></span>

<span data-ttu-id="81630-156">当然，也可自行创建外部身份验证中间件。</span><span class="sxs-lookup"><span data-stu-id="81630-156">It is also possible, of course, to create your own external authentication middleware.</span></span>

## <a name="authenticating-with-bearer-tokens"></a><span data-ttu-id="81630-157">使用持有者令牌进行身份验证</span><span class="sxs-lookup"><span data-stu-id="81630-157">Authenticating with bearer tokens</span></span>

<span data-ttu-id="81630-158">使用 ASP.NET Core 标识（或标识加外部身份验证提供程序）进行身份验证，这适用于应在 cookie 中存储用户信息的许多 Web 应用程序方案。</span><span class="sxs-lookup"><span data-stu-id="81630-158">Authenticating with ASP.NET Core Identity (or Identity plus external authentication providers) works well for many web application scenarios in which storing user information in a cookie is appropriate.</span></span> <span data-ttu-id="81630-159">但是，在其他方案中，cookie 不是保留和传输数据的自然方式。</span><span class="sxs-lookup"><span data-stu-id="81630-159">In other scenarios, though, cookies are not a natural means of persisting and transmitting data.</span></span>

<span data-ttu-id="81630-160">例如，在公开 Single Page Application (SPA)、本机客户端、甚至是其他 Web API 可能访问的 RESTful 终结点的 ASP.NET Core Web API 中，通常需要改为使用持有者令牌身份验证。</span><span class="sxs-lookup"><span data-stu-id="81630-160">For example, in an ASP.NET Core Web API that exposes RESTful endpoints that might be accessed by Single Page Applications (SPAs), by native clients, or even by other Web APIs, you typically want to use bearer token authentication instead.</span></span> <span data-ttu-id="81630-161">这些类型的应用程序不能与 cookie 配合使用，但可以轻松地检索持有者令牌，并将其包括在后续请求的授权标头中。</span><span class="sxs-lookup"><span data-stu-id="81630-161">These types of applications do not work with cookies, but can easily retrieve a bearer token and include it in the authorization header of subsequent requests.</span></span> <span data-ttu-id="81630-162">若要启用令牌身份验证，ASP.NET Core 支持几个用于使用 [OAuth 2.0](https://oauth.net/2/) 和 [OpenID Connect](https://openid.net/connect/) 的选项。</span><span class="sxs-lookup"><span data-stu-id="81630-162">To enable token authentication, ASP.NET Core supports several options for using [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](https://openid.net/connect/).</span></span>

## <a name="authenticating-with-an-openid-connect-or-oauth-20-identity-provider"></a><span data-ttu-id="81630-163">使用 OpenID Connect 或 OAuth 2.0 标识提供程序进行身份验证</span><span class="sxs-lookup"><span data-stu-id="81630-163">Authenticating with an OpenID Connect or OAuth 2.0 Identity provider</span></span>

<span data-ttu-id="81630-164">如果用户信息存储在 Azure Active Directory 或其他支持 OpenID Connect 或 OAuth 2.0 的标识解决方案中，则可以使用 Microsoft.AspNetCore.Authentication.OpenIdConnect 包，通过 OpenID Connect 工作流进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="81630-164">If user information is stored in Azure Active Directory or another identity solution that supports OpenID Connect or OAuth 2.0, you can use the Microsoft.AspNetCore.Authentication.OpenIdConnect package to authenticate using the OpenID Connect workflow.</span></span> <span data-ttu-id="81630-165">例如，若要[针对 Azure Active Directory 进行身份验证](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)，ASP.NET Core Web 应用程序可以使用来自该包的中间件，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="81630-165">For example, to [authenticate against Azure Active Directory](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/), an ASP.NET Core web application can use middleware from that package as shown in the following example:</span></span>

```csharp
// Configure the OWIN pipeline to use OpenID Connect auth
app.UseOpenIdConnectAuthentication(new OpenIdConnectOptions
{
    ClientId = Configuration["AzureAD:ClientId"],
    Authority = String.Format(Configuration["AzureAd:AadInstance"],
    Configuration["AzureAd:Tenant"]),
    ResponseType = OpenIdConnectResponseType.IdToken,
    PostLogoutRedirectUri = Configuration["AzureAd:PostLogoutRedirectUri"]
});
```

<span data-ttu-id="81630-166">配置值是应用程序[注册为 Azure AD 客户端](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad)时创建的 Azure Active Directory 值。</span><span class="sxs-lookup"><span data-stu-id="81630-166">The configuration values are Azure Active Directory values that are created when your application is [registered as an Azure AD client](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad).</span></span> <span data-ttu-id="81630-167">单个客户端 ID 可以在一个应用程序的多个微服务间共享，前提是它们都需要通过 Azure Active Directory 对用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="81630-167">A single client ID can be shared among multiple microservices in an application if they all need to authenticate users authenticated via Azure Active Directory.</span></span>

<span data-ttu-id="81630-168">请注意，使用此工作流时，不需要 ASP.NET Core 标识中间件，因为所有的用户信息存储和身份验证均由 Azure Active Directory 处理。</span><span class="sxs-lookup"><span data-stu-id="81630-168">Note that when you use this workflow, the ASP.NET Core Identity middleware is not needed, because all user information storage and authentication is handled by Azure Active Directory.</span></span>

## <a name="issuing-security-tokens-from-an-aspnet-core-service"></a><span data-ttu-id="81630-169">从 ASP.NET Core 服务颁发安全令牌</span><span class="sxs-lookup"><span data-stu-id="81630-169">Issuing security tokens from an ASP.NET Core service</span></span>

<span data-ttu-id="81630-170">如果希望为本地 ASP.NET Core 标识用户颁发安全令牌，而不是使用外部标识提供程序，可利用一些优秀的第三方库。</span><span class="sxs-lookup"><span data-stu-id="81630-170">If you prefer to issue security tokens for local ASP.NET Core Identity users rather than using an external identity provider, you can take advantage of some good third-party libraries.</span></span>

<span data-ttu-id="81630-171">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) 和 [OpenIddict](https://github.com/openiddict/openiddict-core) 是 OpenID Connect 提供程序，可轻松地与 ASP.NET Core 标识集成，使用户能够从 ASP.NET Core 服务颁发安全令牌。</span><span class="sxs-lookup"><span data-stu-id="81630-171">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) and [OpenIddict](https://github.com/openiddict/openiddict-core) are OpenID Connect providers that integrate easily with ASP.NET Core Identity to let you issue security tokens from an ASP.NET Core service.</span></span> <span data-ttu-id="81630-172">[IdentityServer4 文档](https://identityserver4.readthedocs.io/en/release/)具有有关如何使用库的详细说明。</span><span class="sxs-lookup"><span data-stu-id="81630-172">The [IdentityServer4 documentation](https://identityserver4.readthedocs.io/en/release/) has in-depth instructions for using the library.</span></span> <span data-ttu-id="81630-173">但是，使用 IdentityServer4 颁发令牌的基本步骤如下所示。</span><span class="sxs-lookup"><span data-stu-id="81630-173">However, the basic steps to using IdentityServer4 to issue tokens are as follows.</span></span>

1.  <span data-ttu-id="81630-174">调用 Startup.Configure 方法中的 app.UseIdentityServer，将 IdentityServer4 添加到应用程序的 HTTP 请求处理管道。</span><span class="sxs-lookup"><span data-stu-id="81630-174">You call app.UseIdentityServer in the Startup.Configure method to add IdentityServer4 to the application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="81630-175">这使库能够为指向 OpenID Connect 和 OAuth2 终结点（如 /connect/token）的请求提供服务。</span><span class="sxs-lookup"><span data-stu-id="81630-175">This lets the library serve requests to OpenID Connect and OAuth2 endpoints like /connect/token.</span></span>

2.  <span data-ttu-id="81630-176">通过调用 services.AddIdentityServer，配置 Startup.ConfigureServices 中的 IdentityServer4。</span><span class="sxs-lookup"><span data-stu-id="81630-176">You configure IdentityServer4 in Startup.ConfigureServices by making a call to services.AddIdentityServer.</span></span>

3.  <span data-ttu-id="81630-177">通过提供以下数据，配置标识服务器：</span><span class="sxs-lookup"><span data-stu-id="81630-177">You configure identity server by providing the following data:</span></span>

-   <span data-ttu-id="81630-178">用于签名的[凭据](https://identityserver4.readthedocs.io/en/release/topics/crypto.html)。</span><span class="sxs-lookup"><span data-stu-id="81630-178">The [credentials](https://identityserver4.readthedocs.io/en/release/topics/crypto.html) to use for signing.</span></span>

-   <span data-ttu-id="81630-179">用户可能会请求访问的[标识和 API 资源](https://identityserver4.readthedocs.io/en/release/topics/resources.html)：</span><span class="sxs-lookup"><span data-stu-id="81630-179">The [Identity and API resources](https://identityserver4.readthedocs.io/en/release/topics/resources.html) that users might request access to:</span></span>

<!-- -->

-   <span data-ttu-id="81630-180">API 资源表示用户可通过访问令牌访问的受保护数据或功能。</span><span class="sxs-lookup"><span data-stu-id="81630-180">API resources represent protected data or functionality that a user can access with an access token.</span></span> <span data-ttu-id="81630-181">API 资源的一个示例是要求授权的 Web API（或 API 集）。</span><span class="sxs-lookup"><span data-stu-id="81630-181">An example of an API resource would be a web API (or set of APIs) that requires authorization.</span></span>

-   <span data-ttu-id="81630-182">标识资源表示提供给客户端进行用户识别的信息（声明）。</span><span class="sxs-lookup"><span data-stu-id="81630-182">Identity resources represent information (claims) that are given to a client to identify a user.</span></span> <span data-ttu-id="81630-183">声明可能包括用户名称、电子邮件地址等。</span><span class="sxs-lookup"><span data-stu-id="81630-183">The claims might include the user name, email address, and so on.</span></span>

<!-- -->

-   <span data-ttu-id="81630-184">为请求令牌而连接的[客户端](https://identityserver4.readthedocs.io/en/release/topics/clients.html)。</span><span class="sxs-lookup"><span data-stu-id="81630-184">The [clients](https://identityserver4.readthedocs.io/en/release/topics/clients.html) that will be connecting in order to request tokens.</span></span>

-   <span data-ttu-id="81630-185">用户信息的存储机制，如 [ASP.NET Core 标识](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html)或一种替代方法。</span><span class="sxs-lookup"><span data-stu-id="81630-185">The storage mechanism for user information, such as [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html) or an alternative.</span></span>

<span data-ttu-id="81630-186">为要使用的 IdentityServer4 指定客户端和资源时，可以将相应类型的 IEnumerable&lt;T&gt; 集合传递到采用内存中客户端或资源存储的方法中。</span><span class="sxs-lookup"><span data-stu-id="81630-186">When you specify clients and resources for IdentityServer4 to use, you can pass an IEnumerable&lt;T&gt; collection of the appropriate type to methods that take in-memory client or resource stores.</span></span> <span data-ttu-id="81630-187">或者对于更复杂的方案，可以通过依赖项注入提供客户端或资源提供程序类型。</span><span class="sxs-lookup"><span data-stu-id="81630-187">Or for more complex scenarios, you can provide client or resource provider types via Dependency Injection.</span></span>

<span data-ttu-id="81630-188">IdentityServer4 使用自定义 IClientStore 类型提供的内存中资源和客户端的示例配置可能类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="81630-188">A sample configuration for IdentityServer4 to use in-memory resources and clients provided by a custom IClientStore type might look like the following example:</span></span>

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

## <a name="consuming-security-tokens"></a><span data-ttu-id="81630-189">使用安全令牌</span><span class="sxs-lookup"><span data-stu-id="81630-189">Consuming security tokens</span></span>

<span data-ttu-id="81630-190">针对 OpenID Connect 终结点进行身份验证或自行颁发安全令牌会涵盖一些方案。</span><span class="sxs-lookup"><span data-stu-id="81630-190">Authenticating against an OpenID Connect endpoint or issuing your own security tokens covers some scenarios.</span></span> <span data-ttu-id="81630-191">但对于某个服务，如果它只需限制对具有由其他服务提供的有效安全令牌的用户的访问，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="81630-191">But what about a service that simply needs to limit access to those users who have valid security tokens that were provided by a different service?</span></span>

<span data-ttu-id="81630-192">对于这种情况，Microsoft.AspNetCore.Authentication.JwtBearer 包中提供处理 JWT 令牌的身份验证中间件。</span><span class="sxs-lookup"><span data-stu-id="81630-192">For that scenario, authentication middleware that handles JWT tokens is available in the Microsoft.AspNetCore.Authentication.JwtBearer package.</span></span> <span data-ttu-id="81630-193">JWT 代表“[JSON Web 令牌](https://tools.ietf.org/html/rfc7519)”，是适用于传递安全声明的通用安全令牌格式（由 RFC 7519 定义）。</span><span class="sxs-lookup"><span data-stu-id="81630-193">JWT stands for "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" and is a common security token format (defined by RFC 7519) for communicating security claims.</span></span> <span data-ttu-id="81630-194">有关如何通过中间件使用此类令牌的简单示例可能类似于以下示例。</span><span class="sxs-lookup"><span data-stu-id="81630-194">A simple example of how to use middleware to consume such tokens might look like the following example.</span></span> <span data-ttu-id="81630-195">此代码必须位于 ASP.NET Core MVC 中间件 (app.UseMvc) 调用之前。</span><span class="sxs-lookup"><span data-stu-id="81630-195">This code must precede calls to ASP.NET Core MVC middleware (app.UseMvc).</span></span>

```csharp
app.UseJwtBearerAuthentication(new JwtBearerOptions()
{
    Audience = "http://localhost:5001/",
    Authority = "http://localhost:5000/",
    AutomaticAuthenticate = true
});
```

<span data-ttu-id="81630-196">此用法的参数包括：</span><span class="sxs-lookup"><span data-stu-id="81630-196">The parameters in this usage are:</span></span>

-   <span data-ttu-id="81630-197">Audience 表示传入令牌的接收方或令牌授予访问权限的资源。</span><span class="sxs-lookup"><span data-stu-id="81630-197">Audience represents the receiver of the incoming token or the resource that the token grants access to.</span></span> <span data-ttu-id="81630-198">如果此参数中指定的值与令牌中的 aud 参数不匹配，则会拒绝该令牌。</span><span class="sxs-lookup"><span data-stu-id="81630-198">If the value specified in this parameter does not match the aud parameter in the token, the token will be rejected.</span></span>

-   <span data-ttu-id="81630-199">Authority 是颁发令牌的身份验证服务器的地址。</span><span class="sxs-lookup"><span data-stu-id="81630-199">Authority is the address of the token-issuing authentication server.</span></span> <span data-ttu-id="81630-200">JWT 持有者身份验证中间件使用此 URI 获取可用于验证令牌签名的公钥。</span><span class="sxs-lookup"><span data-stu-id="81630-200">The JWT bearer authentication middleware uses this URI to get the public key that can be used to validate the token's signature.</span></span> <span data-ttu-id="81630-201">该中间件还确认令牌中的 iss 参数是否与此 URI 匹配。</span><span class="sxs-lookup"><span data-stu-id="81630-201">The middleware also confirms that the iss parameter in the token matches this URI.</span></span>

-   <span data-ttu-id="81630-202">AutomaticAuthenticate 是布尔值，指示令牌定义的用户是否应自动登录。</span><span class="sxs-lookup"><span data-stu-id="81630-202">AutomaticAuthenticate is a Boolean value that indicates whether the user defined by the token should be automatically signed in.</span></span>

<span data-ttu-id="81630-203">在此示例中未使用另一个参数 RequireHttpsMetadata。</span><span class="sxs-lookup"><span data-stu-id="81630-203">Another parameter, RequireHttpsMetadata, is not used in this example.</span></span> <span data-ttu-id="81630-204">它可用于测试目的；将此参数设置为 false，可在你没有证书的环境中进行测试。</span><span class="sxs-lookup"><span data-stu-id="81630-204">It is useful for testing purposes; you set this parameter to false so that you can test in environments where you do not have certificates.</span></span> <span data-ttu-id="81630-205">在实际部署中，JWT 持有者令牌应始终只能通过 HTTPS 传递。</span><span class="sxs-lookup"><span data-stu-id="81630-205">In real-world deployments, JWT bearer tokens should always be passed only over HTTPS.</span></span>

<span data-ttu-id="81630-206">此中间件准备就绪后，会自动从授权标头中提取 JWT 令牌。</span><span class="sxs-lookup"><span data-stu-id="81630-206">With this middleware in place, JWT tokens are automatically extracted from authorization headers.</span></span> <span data-ttu-id="81630-207">然后对其进行反序列化、验证（使用 Audience 和 Authority 参数的值），并将其存储为用户信息，稍后供 MVC 操作或授权筛选器引用。</span><span class="sxs-lookup"><span data-stu-id="81630-207">They are then deserialized, validated (using the values in the Audience and Authority parameters), and stored as user information to be referenced later by MVC actions or authorization filters.</span></span>

<span data-ttu-id="81630-208">JWT 持有者身份验证中间件还可以支持更高级的方案，例如颁发机构不可用时使用本地证书验证令牌。</span><span class="sxs-lookup"><span data-stu-id="81630-208">The JWT bearer authentication middleware can also support more advanced scenarios, such as using a local certificate to validate a token if the authority is not available.</span></span> <span data-ttu-id="81630-209">对于此方案，可以在 JwtBearerOptions 对象中指定 TokenValidationParameters 对象。</span><span class="sxs-lookup"><span data-stu-id="81630-209">For this scenario, you can specify a TokenValidationParameters object in the JwtBearerOptions object.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="81630-210">其他资源</span><span class="sxs-lookup"><span data-stu-id="81630-210">Additional resources</span></span>

-   <span data-ttu-id="81630-211">**在应用程序之间共享 cookie**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)</span><span class="sxs-lookup"><span data-stu-id="81630-211">**Sharing cookies between applications**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)</span></span>

-   <span data-ttu-id="81630-212">**标识简介**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span><span class="sxs-lookup"><span data-stu-id="81630-212">**Introduction to Identity**
[*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span></span>

-   <span data-ttu-id="81630-213">**Rick Anderson。使用 SMS 进行双因素身份验证**
    [https://docs.microsoft.com/aspnet/core/security/authentication/2fa](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)</span><span class="sxs-lookup"><span data-stu-id="81630-213">**Rick Anderson. Two-factor authentication with SMS**
[*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)</span></span>

-   <span data-ttu-id="81630-214">**启用使用 Facebook、Google 和其他外部提供程序的身份验证**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)</span><span class="sxs-lookup"><span data-stu-id="81630-214">**Enabling authentication using Facebook, Google and other external providers**
[*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)</span></span>

-   <span data-ttu-id="81630-215">**Michell Anicas。An Introduction to OAuth 2**
    [*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)（OAuth 2 简介）</span><span class="sxs-lookup"><span data-stu-id="81630-215">**Michell Anicas. An Introduction to OAuth 2**
[*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)</span></span>

-   <span data-ttu-id="81630-216">**AspNet.Security.OAuth.Providers**（ASP.NET OAuth 提供程序的 GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="81630-216">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers.</span></span>
    [*https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src*](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src)

-   <span data-ttu-id="81630-217">**Danny Strockis。Integrating Azure AD into an ASP.NET Core web app**
    [https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)（将 Azure AD 集成到 ASP.NET Core Web 应用中）</span><span class="sxs-lookup"><span data-stu-id="81630-217">**Danny Strockis. Integrating Azure AD into an ASP.NET Core web app**
[*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)</span></span>

-   <span data-ttu-id="81630-218">**IdentityServer4。官方文档**
    [https://identityserver4.readthedocs.io/en/release/](https://identityserver4.readthedocs.io/en/release/)</span><span class="sxs-lookup"><span data-stu-id="81630-218">**IdentityServer4. Official documentation**
[*https://identityserver4.readthedocs.io/en/release/*](https://identityserver4.readthedocs.io/en/release/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="81630-219">[上一页](../implement-resilient-applications/monitor-app-health.md)
[下一页](authorization-net-microservices-web-applications.md)</span><span class="sxs-lookup"><span data-stu-id="81630-219">[Previous](../implement-resilient-applications/monitor-app-health.md)
[Next](authorization-net-microservices-web-applications.md)</span></span>
