---
title: 调用 gRPC for WCF 开发人员
description: 如何在 ASP.NET Core 3.0 中实现和使用 gRPC 调用凭据。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 5f29d69ec37fe60bcd7ca01391001ea9eb71e7e4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841671"
---
# <a name="call-credentials"></a><span data-ttu-id="7c72d-103">调用凭据</span><span class="sxs-lookup"><span data-stu-id="7c72d-103">Call credentials</span></span>

<span data-ttu-id="7c72d-104">调用凭据都基于在元数据中与每个请求一起传递的某种类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="7c72d-104">Call credentials are all based on some kind of token passed in metadata with each request.</span></span>

## <a name="ws-federation"></a><span data-ttu-id="7c72d-105">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="7c72d-105">WS-Federation</span></span>

<span data-ttu-id="7c72d-106">ASP.NET Core 使用[WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) NuGet 包支持 WS 联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="7c72d-106">ASP.NET Core supports WS-Federation using the [WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) NuGet package.</span></span> <span data-ttu-id="7c72d-107">WS 联合身份验证是 Windows 身份验证的最接近可用替代方法，不受 HTTP/2 支持。</span><span class="sxs-lookup"><span data-stu-id="7c72d-107">WS-Federation is the closest available alternative to Windows Authentication, which is not supported over HTTP/2.</span></span> <span data-ttu-id="7c72d-108">使用 Active Directory 联合身份验证服务（ADFS）对用户进行身份验证，该令牌提供可用于向 ASP.NET Core 进行身份验证的令牌。</span><span class="sxs-lookup"><span data-stu-id="7c72d-108">Users are authenticated using Active Directory Federation Services (ADFS), which provides a token that can be used to authenticate with ASP.NET Core.</span></span>

<span data-ttu-id="7c72d-109">有关如何开始处理此身份验证方法的详细信息，请参阅在[ASP.NET Core 文章中对用户进行身份验证](https://docs.microsoft.com/aspnet/core/security/authentication/ws-federation?view=aspnetcore-3.0)。</span><span class="sxs-lookup"><span data-stu-id="7c72d-109">For more information on how to get started with this authentication method, see the [Authenticate users with WS-Federation in ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/ws-federation?view=aspnetcore-3.0) article.</span></span>

## <a name="jwt-bearer-tokens"></a><span data-ttu-id="7c72d-110">JWT 持有者令牌</span><span class="sxs-lookup"><span data-stu-id="7c72d-110">JWT Bearer tokens</span></span>

<span data-ttu-id="7c72d-111">[JSON Web 令牌](https://jwt.io)标准提供了一种方法，用于在编码的字符串中对用户及其声明的信息进行编码，并以这种方式对令牌进行签名，以便使用者可以使用公钥加密来验证令牌的完整性。</span><span class="sxs-lookup"><span data-stu-id="7c72d-111">The [JSON Web Token](https://jwt.io) standard provides a way to encode information about a user and their claims in an encoded string, and to sign that token in such a way that the consumer can verify the integrity of the token using public key cryptography.</span></span> <span data-ttu-id="7c72d-112">你可以使用各种服务（例如 IdentityServer4）对用户进行身份验证，并生成 OpenID Connect （OIDC）令牌以用于 gRPC 和 HTTP Api。</span><span class="sxs-lookup"><span data-stu-id="7c72d-112">You can use various services, such as IdentityServer4, to authenticate users and generate OpenID Connect (OIDC) tokens to use with gRPC and HTTP APIs.</span></span>

<span data-ttu-id="7c72d-113">ASP.NET Core 3.0 可以使用 JWT 持有者包处理 JSON Web 令牌。</span><span class="sxs-lookup"><span data-stu-id="7c72d-113">ASP.NET Core 3.0 can handle JSON Web Tokens using the JWT Bearer package.</span></span> <span data-ttu-id="7c72d-114">对于 gRPC 应用程序，配置与 ASP.NET Core MVC 应用程序完全相同。</span><span class="sxs-lookup"><span data-stu-id="7c72d-114">The configuration is exactly the same for a gRPC application as an ASP.NET Core MVC application.</span></span>

<span data-ttu-id="7c72d-115">本章重点介绍 JWT 持有者令牌，因为它们比 WS-FEDERATION 更易于开发。</span><span class="sxs-lookup"><span data-stu-id="7c72d-115">This chapter will focus on JWT Bearer tokens as they're easier to develop with than WS-Federation.</span></span>

## <a name="adding-authentication-and-authorization-to-the-server"></a><span data-ttu-id="7c72d-116">向服务器添加身份验证和授权</span><span class="sxs-lookup"><span data-stu-id="7c72d-116">Adding authentication and authorization to the server</span></span>

<span data-ttu-id="7c72d-117">默认情况下，ASP.NET Core 3.0 中不包括 JWT 持有者包。</span><span class="sxs-lookup"><span data-stu-id="7c72d-117">The JWT Bearer package isn't included in ASP.NET Core 3.0 by default.</span></span> <span data-ttu-id="7c72d-118">在应用程序中安装[AspNetCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="7c72d-118">Install the [Microsoft.AspNetCore.Authentication.JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) NuGet package in your app.</span></span>

<span data-ttu-id="7c72d-119">在 Startup 类中添加身份验证服务，并配置 JWT 持有者处理程序。</span><span class="sxs-lookup"><span data-stu-id="7c72d-119">Add the Authentication service in the Startup class and configure the JWT Bearer handler.</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();

    var signingKey = ObtainSigningKeySomehow();

    services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
        .AddJwtBearer(options =>
        {
            options.TokenValidationParameters =
                new TokenValidationParameters
                {
                    ValidateAudience = false,
                    ValidateIssuer = false,
                    ValidateActor = false,
                    ValidateLifetime = true,
                    IssuerSigningKey = signingKey
                };
        });

}
```

<span data-ttu-id="7c72d-120">`IssuerSigningKey` 属性需要具有用于验证签名令牌的加密数据 `Microsoft.IdentityModels.Tokens.SecurityKey` 的实现。</span><span class="sxs-lookup"><span data-stu-id="7c72d-120">The `IssuerSigningKey` property requires an implementation of `Microsoft.IdentityModels.Tokens.SecurityKey` with the cryptographic data necessary to validate the signed tokens.</span></span> <span data-ttu-id="7c72d-121">此令牌应安全地存储在*机密服务器*中，如 Azure KeyVault。</span><span class="sxs-lookup"><span data-stu-id="7c72d-121">This token should be stored securely in a *secrets server* like Azure KeyVault.</span></span>

<span data-ttu-id="7c72d-122">接下来添加授权服务，该服务控制对系统的访问。</span><span class="sxs-lookup"><span data-stu-id="7c72d-122">Next add the Authorization service, which controls access to the system.</span></span>

```csharp
    services.AddAuthorization(options =>
    {
        options.AddPolicy(JwtBearerDefaults.AuthenticationScheme, policy =>
        {
            policy.AddAuthenticationSchemes(JwtBearerDefaults.AuthenticationScheme);
            policy.RequireClaim(ClaimTypes.Name);
        });
    });

```

> [!TIP]
> <span data-ttu-id="7c72d-123">身份验证和授权是两个单独的步骤。</span><span class="sxs-lookup"><span data-stu-id="7c72d-123">Authentication and Authorization are two separate steps.</span></span> <span data-ttu-id="7c72d-124">身份验证用于确定用户的标识。</span><span class="sxs-lookup"><span data-stu-id="7c72d-124">Authentication is used to determine the user's identity.</span></span> <span data-ttu-id="7c72d-125">授权决定是否允许该用户访问系统的各个部分。</span><span class="sxs-lookup"><span data-stu-id="7c72d-125">Authorization decides whether that user is allowed to access various parts of the system.</span></span>

<span data-ttu-id="7c72d-126">现在，将身份验证和授权中间件添加到 `Configure` 方法中的 ASP.NET Core 管道。</span><span class="sxs-lookup"><span data-stu-id="7c72d-126">Now add the Authentication and Authorization middleware to the ASP.NET Core pipeline in the `Configure` method.</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    // Authenticate, then Authorize
    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

<span data-ttu-id="7c72d-127">最后，将 `[Authorize]` 特性应用到要保护的任何服务或方法，并使用底层 `HttpContext` 的 `User` 属性验证权限。</span><span class="sxs-lookup"><span data-stu-id="7c72d-127">Finally, apply the `[Authorize]` attribute to any services or methods to be secured, and use the `User` property from the underlying `HttpContext` to verify permissions.</span></span>

```csharp
[Authorize]
public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!TryValidateUser(request.TraderId, context.GetHttpContext().User))
    {
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Denied."));
    }

    var portfolio = await _repository.GetAsync(traderId, request.PortfolioId);

    return new GetResponse
    {
        Portfolio = Portfolio.FromRepositoryModel(portfolio)
    };
}
```

## <a name="providing-call-credentials-in-the-client-application"></a><span data-ttu-id="7c72d-128">在客户端应用程序中提供调用凭据</span><span class="sxs-lookup"><span data-stu-id="7c72d-128">Providing call credentials in the client application</span></span>

<span data-ttu-id="7c72d-129">从标识服务器获取 JWT 令牌后，可以使用它通过将其作为元数据标头添加到调用，来对客户端中的 gRPC 调用进行身份验证，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7c72d-129">Once you've obtained a JWT token from an identity server, you can use it to authenticate gRPC calls from the client by adding it as a metadata header on the call, as follows:</span></span>

```csharp
public async Task ShowPortfolioAsync(int portfolioId)
{
    var headers = new Grpc.Core.Metadata
    {
        { "Authorization", $"Bearer {_userToken}" }
    };
    var request = new GetRequest
    {
        TraderId = _userId,
        PortfolioId = portfolioId
    };
    var response = await _portfoliosClient.GetAsync(request, headers);

    // Display portfolio
}
```

<span data-ttu-id="7c72d-130">现在，已使用 JWT 持有者令牌作为调用凭据来保护 gRPC 服务。</span><span class="sxs-lookup"><span data-stu-id="7c72d-130">Now, you've secured your gRPC service using JWT bearer tokens as call credentials.</span></span> <span data-ttu-id="7c72d-131">GitHub 上已[添加身份验证和授权的包示例 gRPC 应用程序](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth)的版本。</span><span class="sxs-lookup"><span data-stu-id="7c72d-131">A version of the [Portfolios sample gRPC application with authentication and authorization added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7c72d-132">[上一页](security.md)
>[下一页](channel-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="7c72d-132">[Previous](security.md)
[Next](channel-credentials.md)</span></span>
