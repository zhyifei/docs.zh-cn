---
title: 调用 gRPC for WCF 开发人员
description: 如何在 ASP.NET Core 3.0 中实现和使用 gRPC 调用凭据。
ms.date: 09/02/2019
ms.openlocfilehash: 01f21f58ed4235f45509c948c84653cd99d35618
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711540"
---
# <a name="call-credentials"></a>调用凭据

调用凭据都基于在元数据中随每个请求传入的令牌。

## <a name="ws-federation"></a>WS-Federation

ASP.NET Core 使用[WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) NuGet 包支持 WS 联合身份验证。 WS 联合身份验证是 Windows 身份验证的最接近可用替代方法，不受 HTTP/2 支持。 使用 Active Directory 联合身份验证服务（AD FS）对用户进行身份验证，该令牌提供可用于向 ASP.NET Core 进行身份验证的令牌。

有关如何开始处理此身份验证方法的详细信息，请参阅[在 ASP.NET Core 中对具有 ws-federation 的用户进行身份验证](/aspnet/core/security/authentication/ws-federation)。

## <a name="jwt-bearer-tokens"></a>JWT 持有者令牌

[JSON Web 令牌](https://jwt.io)（JWT）标准提供了一种方法，用于在编码字符串中对用户及其声明的信息进行编码。 它还提供了一种方法来对令牌进行签名，以便使用者可以通过使用公钥加密来验证令牌的完整性。 你可以使用各种服务（例如 IdentityServer4）对用户进行身份验证，并生成 OpenID Connect （OIDC）令牌以用于 gRPC 和 HTTP Api。

ASP.NET Core 3.0 可以使用 JWT 持有者包处理 Jwt。 GRPC 应用程序的配置与 ASP.NET Core MVC 应用程序的配置完全相同。 在这里，我们将重点介绍 JWT 持有者令牌，因为它们比 WS 联合身份验证更易于开发。

## <a name="add-authentication-and-authorization-to-the-server"></a>向服务器添加身份验证和授权

默认情况下，ASP.NET Core 3.0 中不包括 JWT 持有者包。 在应用程序中安装[AspNetCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) NuGet 包。

在 Startup 类中添加身份验证服务，并配置 JWT 持有者处理程序：

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

`IssuerSigningKey` 属性需要具有用于验证签名令牌的加密数据 `Microsoft.IdentityModels.Tokens.SecurityKey` 的实现。 将该令牌安全地存储在*机密服务器*中，如 Azure Key Vault。

接下来，添加授权服务，该服务控制对系统的访问权限：

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
> 身份验证和授权是两个单独的步骤。 使用身份验证可以确定用户的身份。 使用授权确定是否允许该用户访问系统的各个部分。

现在，将身份验证和授权中间件添加到 `Configure` 方法中的 ASP.NET Core 管道：

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

最后，将 `[Authorize]` 特性应用到要保护的任何服务或方法，并使用底层 `HttpContext` 的 `User` 属性验证权限。

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

## <a name="provide-call-credentials-in-the-client-application"></a>提供客户端应用程序中的调用凭据

从标识服务器获取 JWT 令牌后，可以使用它通过将 gRPC 调用作为元数据标头添加到调用中来对其进行身份验证，如下所示：

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

现在，使用 JWT 持有者令牌作为调用凭据来保护 gRPC 服务。 GitHub 上已[添加身份验证和授权的包示例 gRPC 应用程序](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth)的版本。

>[!div class="step-by-step"]
>[上一页](security.md)
>[下一页](channel-credentials.md)
