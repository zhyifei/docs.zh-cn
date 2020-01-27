---
title: 适用于云本机应用的 IdentityServer
description: 构建适用于 Azure 的云本机 .NET 应用 |IdentityServer
ms.date: 06/30/2019
ms.openlocfilehash: 48d0b95a40682f3127127851781b4d0e26e44630
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728582"
---
# <a name="identityserver-for-cloud-native-applications"></a><span data-ttu-id="e8775-103">适用于云原生应用程序的 IdentityServer</span><span class="sxs-lookup"><span data-stu-id="e8775-103">IdentityServer for cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="e8775-104">IdentityServer 是一种开源身份验证服务器，用于实现 ASP.NET Core 的 OpenID Connect （OIDC）和 OAuth 2.0 标准。</span><span class="sxs-lookup"><span data-stu-id="e8775-104">IdentityServer is an open-source authentication server that implements OpenID Connect (OIDC) and OAuth 2.0 standards for ASP.NET Core.</span></span> <span data-ttu-id="e8775-105">它旨在提供一种通用方法来对所有应用程序的请求进行身份验证，无论这些请求是 web、本机、移动还是 API 终结点。</span><span class="sxs-lookup"><span data-stu-id="e8775-105">It's designed to provide a common way to authenticate requests to all of your applications, whether they're web, native, mobile, or API endpoints.</span></span> <span data-ttu-id="e8775-106">IdentityServer 可用于实现多个应用程序和应用程序类型的单一登录（SSO）。</span><span class="sxs-lookup"><span data-stu-id="e8775-106">IdentityServer can be used to implement Single Sign-On (SSO) for multiple applications and application types.</span></span> <span data-ttu-id="e8775-107">它可用于通过登录窗体和类似用户界面以及基于服务的身份验证（通常涉及令牌颁发、验证和续订，无需任何用户界面）对实际用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e8775-107">It can be used to authenticate actual users via sign-in forms and similar user interfaces as well as service-based authentication that typically involves token issuance, verification, and renewal without any user interface.</span></span> <span data-ttu-id="e8775-108">IdentityServer 旨在作为可自定义的解决方案。</span><span class="sxs-lookup"><span data-stu-id="e8775-108">IdentityServer is designed to be a customizable solution.</span></span> <span data-ttu-id="e8775-109">通常，每个实例都可以进行自定义，以适应单个组织和/或一组应用程序的需求。</span><span class="sxs-lookup"><span data-stu-id="e8775-109">Each instance is typically customized to suit an individual organization and/or set of applications' needs.</span></span>

## <a name="common-web-app-scenarios"></a><span data-ttu-id="e8775-110">常见的 web 应用方案</span><span class="sxs-lookup"><span data-stu-id="e8775-110">Common web app scenarios</span></span>

<span data-ttu-id="e8775-111">通常，应用程序需要支持以下部分或所有方案：</span><span class="sxs-lookup"><span data-stu-id="e8775-111">Typically, applications need to support some or all of the following scenarios:</span></span>

- <span data-ttu-id="e8775-112">用户使用浏览器访问 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e8775-112">Human users accessing web applications with a browser.</span></span>
- <span data-ttu-id="e8775-113">用于从基于浏览器的应用程序访问后端 Web Api 的用户。</span><span class="sxs-lookup"><span data-stu-id="e8775-113">Human users accessing back-end Web APIs from browser-based apps.</span></span>
- <span data-ttu-id="e8775-114">移动/本机客户端上访问后端 Web Api 的用户。</span><span class="sxs-lookup"><span data-stu-id="e8775-114">Human users on mobile/native clients accessing back-end Web APIs.</span></span>
- <span data-ttu-id="e8775-115">访问后端 Web Api 的其他应用程序（无活动用户或用户界面）。</span><span class="sxs-lookup"><span data-stu-id="e8775-115">Other applications accessing back-end Web APIs (without an active user or user interface).</span></span>
- <span data-ttu-id="e8775-116">任何应用程序都可能需要使用其自己的标识或委托给用户的标识，与其他 Web Api 交互。</span><span class="sxs-lookup"><span data-stu-id="e8775-116">Any application may need to interact with other Web APIs, using its own identity or delegating to the user's identity.</span></span>

<span data-ttu-id="e8775-117">![**图 8-1**](./media/application-types.png)
的应用程序类型和方案。</span><span class="sxs-lookup"><span data-stu-id="e8775-117">![Application types and scenarios](./media/application-types.png)
**Figure 8-1**.</span></span> <span data-ttu-id="e8775-118">应用程序类型和方案。</span><span class="sxs-lookup"><span data-stu-id="e8775-118">Application types and scenarios.</span></span>

<span data-ttu-id="e8775-119">在上述每种情况下，都需要确保公开的功能不受未经授权的使用。</span><span class="sxs-lookup"><span data-stu-id="e8775-119">In each of these scenarios, the exposed functionality needs to be secured against unauthorized use.</span></span> <span data-ttu-id="e8775-120">通常，这通常需要对请求资源的用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e8775-120">At a minimum, this typically requires authenticating the user or principal making a request for a resource.</span></span> <span data-ttu-id="e8775-121">此身份验证可使用几种常用协议，如 SAML2p、WS 送连接或 OpenID Connect。</span><span class="sxs-lookup"><span data-stu-id="e8775-121">This authentication may use one of several common protocols such as SAML2p, WS-Fed, or OpenID Connect.</span></span> <span data-ttu-id="e8775-122">与 Api 通信通常使用 OAuth2 协议及其对安全令牌的支持。</span><span class="sxs-lookup"><span data-stu-id="e8775-122">Communicating with APIs typically uses the OAuth2 protocol and its support for security tokens.</span></span> <span data-ttu-id="e8775-123">从应用程序自身分离这些重要的交叉切削安全问题及其实现细节可确保一致性并提高安全性和可维护性。</span><span class="sxs-lookup"><span data-stu-id="e8775-123">Separating these critical cross-cutting security concerns and their implementation details from the applications themselves ensures consistency and improves security and maintainability.</span></span> <span data-ttu-id="e8775-124">将这些问题外包给专用产品（如 IdentityServer）可帮助每个应用程序自行解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="e8775-124">Outsourcing these concerns to a dedicated product like IdentityServer helps the requirement for every application to solve these problems itself.</span></span>

<span data-ttu-id="e8775-125">IdentityServer 提供在 ASP.NET Core 应用程序中运行的中间件，并添加对 OpenID Connect 和 OAuth2 的支持（请参阅[支持的规范](http://docs.identityserver.io/en/latest/intro/specs.html)）。</span><span class="sxs-lookup"><span data-stu-id="e8775-125">IdentityServer provides middleware that runs within an ASP.NET Core application and adds support for OpenID Connect and OAuth2 (see [supported specifications](http://docs.identityserver.io/en/latest/intro/specs.html)).</span></span> <span data-ttu-id="e8775-126">组织将使用 IdentityServer 中间件创建自己的 ASP.NET Core 应用程序，将其用作所有基于令牌的安全协议的 STS。</span><span class="sxs-lookup"><span data-stu-id="e8775-126">Organizations would create their own ASP.NET Core app using IdentityServer middleware to act as the STS for all of their token-based security protocols.</span></span> <span data-ttu-id="e8775-127">IdentityServer 中间件公开终结点以支持标准功能，其中包括：</span><span class="sxs-lookup"><span data-stu-id="e8775-127">The IdentityServer middleware exposes endpoints to support standard functionality, including:</span></span>

- <span data-ttu-id="e8775-128">授权（对最终用户进行身份验证）</span><span class="sxs-lookup"><span data-stu-id="e8775-128">Authorize (authenticate the end user)</span></span>
- <span data-ttu-id="e8775-129">标记（以编程方式请求标记）</span><span class="sxs-lookup"><span data-stu-id="e8775-129">Token (request a token programmatically)</span></span>
- <span data-ttu-id="e8775-130">发现（有关服务器的元数据）</span><span class="sxs-lookup"><span data-stu-id="e8775-130">Discovery (metadata about the server)</span></span>
- <span data-ttu-id="e8775-131">用户信息（使用有效的访问令牌获取用户信息）</span><span class="sxs-lookup"><span data-stu-id="e8775-131">User Info (get user information with a valid access token)</span></span>
- <span data-ttu-id="e8775-132">设备授权（用于启动设备流授权）</span><span class="sxs-lookup"><span data-stu-id="e8775-132">Device Authorization (used to start device flow authorization)</span></span>
- <span data-ttu-id="e8775-133">自检（令牌验证）</span><span class="sxs-lookup"><span data-stu-id="e8775-133">Introspection (token validation)</span></span>
- <span data-ttu-id="e8775-134">吊销（令牌吊销）</span><span class="sxs-lookup"><span data-stu-id="e8775-134">Revocation (token revocation)</span></span>
- <span data-ttu-id="e8775-135">结束会话（触发器跨所有应用的单一注销）</span><span class="sxs-lookup"><span data-stu-id="e8775-135">End Session (trigger single sign-out across all apps)</span></span>

## <a name="getting-started"></a><span data-ttu-id="e8775-136">入门</span><span class="sxs-lookup"><span data-stu-id="e8775-136">Getting started</span></span>

<span data-ttu-id="e8775-137">IdentityServer4 是开源的，可免费使用。</span><span class="sxs-lookup"><span data-stu-id="e8775-137">IdentityServer4 is open-source and free to use.</span></span> <span data-ttu-id="e8775-138">你可以使用其 NuGet 包将其添加到你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e8775-138">You can add it to your applications using its NuGet packages.</span></span> <span data-ttu-id="e8775-139">主包为[IdentityServer4](https://www.nuget.org/packages/IdentityServer4/) ，已在4000000次下载。</span><span class="sxs-lookup"><span data-stu-id="e8775-139">The main package is [IdentityServer4](https://www.nuget.org/packages/IdentityServer4/) that has been downloaded over four million times.</span></span> <span data-ttu-id="e8775-140">基包不包含任何用户界面代码，并且仅支持内存中的配置。</span><span class="sxs-lookup"><span data-stu-id="e8775-140">The base package doesn't include any user interface code and only supports in memory configuration.</span></span> <span data-ttu-id="e8775-141">若要将其与数据库一起使用，你还需要一个数据访问接口（如[IdentityServer4](https://www.nuget.org/packages/IdentityServer4.EntityFramework) ），它使用 Entity Framework Core 来存储 IdentityServer 的配置和操作数据。</span><span class="sxs-lookup"><span data-stu-id="e8775-141">To use it with a database, you'll also want a data provider like [IdentityServer4.EntityFramework](https://www.nuget.org/packages/IdentityServer4.EntityFramework) that uses Entity Framework Core to store configuration and operational data for IdentityServer.</span></span> <span data-ttu-id="e8775-142">对于用户界面，可以将文件从[快速入门 UI 存储库](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI)复制到 ASP.NET Core MVC 应用程序中，以添加对使用 IdentityServer 中间件进行登录和注销的支持。</span><span class="sxs-lookup"><span data-stu-id="e8775-142">For user interface, you can copy files from the [Quickstart UI repository](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI) into your ASP.NET Core MVC application to add support for sign in and sign out using IdentityServer middleware.</span></span>

## <a name="configuration"></a><span data-ttu-id="e8775-143">配置</span><span class="sxs-lookup"><span data-stu-id="e8775-143">Configuration</span></span>

<span data-ttu-id="e8775-144">IdentityServer 支持不同种类的协议和社交身份验证提供程序，这些提供程序可配置为每个自定义安装的一部分。</span><span class="sxs-lookup"><span data-stu-id="e8775-144">IdentityServer supports different kinds of protocols and social authentication providers that can be configured as part of each custom installation.</span></span> <span data-ttu-id="e8775-145">通常在 `ConfigureServices` 方法的 ASP.NET Core 应用程序 `Startup` 类中完成此操作。</span><span class="sxs-lookup"><span data-stu-id="e8775-145">This is typically done in the ASP.NET Core application's `Startup` class in the `ConfigureServices` method.</span></span> <span data-ttu-id="e8775-146">此配置涉及到指定支持的协议以及将使用的服务器和终结点的路径。</span><span class="sxs-lookup"><span data-stu-id="e8775-146">The configuration involves specifying the supported protocols and the paths to the servers and endpoints that will be used.</span></span> <span data-ttu-id="e8775-147">图8-2 显示了从 IdentityServer4 快速入门 UI 项目中获取的示例配置：</span><span class="sxs-lookup"><span data-stu-id="e8775-147">Figure 8-2 shows an example configuration taken from the IdentityServer4 Quickstart UI project:</span></span>

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();

        // some details omitted
        services.AddIdentityServer();

          services.AddAuthentication()
            .AddGoogle("Google", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;

                options.ClientId = "<insert here>";
                options.ClientSecret = "<insert here>";
            })
            .AddOpenIdConnect("demoidsrv", "IdentityServer", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;
                options.SignOutScheme = IdentityServerConstants.SignoutScheme;

                options.Authority = "https://demo.identityserver.io/";
                options.ClientId = "implicit";
                options.ResponseType = "id_token";
                options.SaveTokens = true;
                options.CallbackPath = new PathString("/signin-idsrv");
                options.SignedOutCallbackPath = new PathString("/signout-callback-idsrv");
                options.RemoteSignOutPath = new PathString("/signout-idsrv");

                options.TokenValidationParameters = new TokenValidationParameters
                {
                    NameClaimType = "name",
                    RoleClaimType = "role"
                };
            });
    }
}
```

<span data-ttu-id="e8775-148">**图 8-2**。</span><span class="sxs-lookup"><span data-stu-id="e8775-148">**Figure 8-2**.</span></span> <span data-ttu-id="e8775-149">配置 IdentityServer。</span><span class="sxs-lookup"><span data-stu-id="e8775-149">Configuring IdentityServer.</span></span>

<span data-ttu-id="e8775-150">IdentityServer 还托管了公共演示网站，可用于测试各种协议和配置。</span><span class="sxs-lookup"><span data-stu-id="e8775-150">IdentityServer also hosts a public demo site that can be used to test various protocols and configurations.</span></span> <span data-ttu-id="e8775-151">它位于[https://demo.identityserver.io/](https://demo.identityserver.io/) ，其中包含有关如何根据提供的 `client_id` 配置其行为的信息。</span><span class="sxs-lookup"><span data-stu-id="e8775-151">It's located at [https://demo.identityserver.io/](https://demo.identityserver.io/) and includes information on how to configure its behavior based on the `client_id` provided to it.</span></span>

## <a name="javascript-clients"></a><span data-ttu-id="e8775-152">JavaScript 客户端</span><span class="sxs-lookup"><span data-stu-id="e8775-152">JavaScript clients</span></span>

<span data-ttu-id="e8775-153">许多云本机应用程序在前端使用服务器端 Api 和丰富的客户端单页面应用程序（Spa）。</span><span class="sxs-lookup"><span data-stu-id="e8775-153">Many cloud-native applications leverage server-side APIs and rich client single page applications (SPAs) on the front end.</span></span> <span data-ttu-id="e8775-154">IdentityServer 通过 NPM 提供了一个[JavaScript 客户端](http://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html)（`oidc-client.js`），可以将其添加到 spa，使其能够使用 IdentityServer 进行登录、注销和 web api 基于令牌的身份验证。</span><span class="sxs-lookup"><span data-stu-id="e8775-154">IdentityServer ships a [JavaScript client](http://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html) (`oidc-client.js`) via NPM that can be added to SPAs to enable them to use IdentityServer for sign in, sign out, and token-based authentication of web APIs.</span></span>

## <a name="references"></a><span data-ttu-id="e8775-155">引用</span><span class="sxs-lookup"><span data-stu-id="e8775-155">References</span></span>

- [<span data-ttu-id="e8775-156">IdentityServer 文档</span><span class="sxs-lookup"><span data-stu-id="e8775-156">IdentityServer documentation</span></span>](http://docs.identityserver.io/en/latest/)
- [<span data-ttu-id="e8775-157">应用程序类型</span><span class="sxs-lookup"><span data-stu-id="e8775-157">Application types</span></span>](https://docs.microsoft.com/azure/active-directory/develop/app-types)
- [<span data-ttu-id="e8775-158">JavaScript OIDC 客户端</span><span class="sxs-lookup"><span data-stu-id="e8775-158">JavaScript OIDC client</span></span>](http://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html)

>[!div class="step-by-step"]
><span data-ttu-id="e8775-159">[上一页](azure-active-directory.md)
>[下一页](security.md)</span><span class="sxs-lookup"><span data-stu-id="e8775-159">[Previous](azure-active-directory.md)
[Next](security.md)</span></span>
