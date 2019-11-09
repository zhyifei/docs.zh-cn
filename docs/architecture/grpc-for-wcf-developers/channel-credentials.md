---
title: 通道凭据-适用于 WCF 开发人员的 gRPC
description: 如何在 ASP.NET Core 3.0 中实现和使用 gRPC 通道凭据。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 61141dc4143f36f9ac511c3369c3fde668c9d703
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841665"
---
# <a name="channel-credentials"></a>通道凭据

顾名思义，通道凭据会附加到基础 gRPC 通道。 通道凭据的标准形式使用客户端证书身份验证，其中客户端在建立连接时提供 TLS 证书，该证书是在允许进行任何调用之前由服务器验证的。

通道凭据可以与调用凭据结合使用，为 gRPC 服务提供全面的安全性。 通道凭据证明允许客户端应用程序访问该服务，而调用凭据则提供有关使用该客户端应用程序的人员的信息。

对于 gRPC，客户端证书身份验证的工作方式与 ASP.NET Core 的工作方式相同。 此配置过程将在此处汇总，但在 ASP.NET Core 一文[中配置证书身份验证](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0)中提供了详细信息。

出于开发目的，你可以使用自签名证书，但对于生产，你应该使用由受信任的颁发机构签名的正确 HTTPS 证书。

## <a name="adding-certificate-authentication-to-the-server"></a>将证书身份验证添加到服务器

需要在主机级别配置证书身份验证（例如，在 Kestrel 服务器上），并在 ASP.NET Core 管道中配置证书身份验证。

### <a name="configuring-certificate-validation-on-kestrel"></a>在 Kestrel 上配置证书验证

你可以将 Kestrel （ASP.NET Core HTTP 服务器）配置为需要客户端证书，并在接受传入连接之前，选择执行提供的证书的某些验证。 此配置在 `Program` 类的 `CreateWebHostBuilder` 方法中完成，而不是在 `Startup`中完成。

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            var serverCert = ObtainServerCertificate();
            webBuilder.UseStartup<Startup>()
                .ConfigureKestrel(kestrelServerOptions => {
                    kestrelServerOptions.ConfigureHttpsDefaults(opt =>
                    {
                        opt.ClientCertificateMode = ClientCertificateMode.RequireCertificate;

                        // Verify that client certificate was issued by same CA as server certificate
                        opt.ClientCertificateValidation = (certificate, chain, errors) =>
                            certificate.Issuer == serverCert.Issuer;
                    });
                });
        });

```

`ClientCertificateMode.RequireCertificate` 设置将导致 Kestrel 立即拒绝不提供客户端证书的任何连接请求，但不会验证证书。 添加 `ClientCertificateValidation` 回调后，Kestrel 就可以在建立 ASP.NET Core 管道之前，验证客户端证书（在这种情况下，确保它由与服务器证书相同的*证书颁发机构*颁发）。

### <a name="adding-aspnet-core-certificate-authentication"></a>添加 ASP.NET Core 证书身份验证

证书身份验证由[AspNetCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet 包提供。

在 `ConfigureServices` 方法中添加证书身份验证服务，并在 `Configure` 方法中将身份验证和授权添加到 ASP.NET Core 管道。

```csharp
public class Startup
{
    private readonly bool _isDevelopment;

    public Startup(IWebHostEnvironment env)
    {
        _isDevelopment = env.IsDevelopment();
    }

    public void ConfigureServices(IServiceCollection services)
    {
        services.AddAuthentication(CertificateAuthenticationDefaults.AuthenticationScheme)
            .AddCertificate(options =>
            {
                if (_isDevelopment)
                {
                    // DO NOT DO THIS IN PRODUCTION!
                    options.RevocationMode = X509RevocationMode.NoCheck;
                }
            });
        services.AddAuthorization();
        services.AddGrpc();
    }

    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        app.UseRouting();

        app.UseAuthentication();
        app.UseAuthorization();

        app.UseEndpoints(endpoints => { endpoints.MapGrpcService<GreeterService>(); });
    }
}
```

## <a name="providing-channel-credentials-in-the-client-application"></a>提供客户端应用程序中的通道凭据

使用 `Grpc.Net.Client` 包，证书在提供给用于连接的 `GrpcChannel` 的 <xref:System.Net.Http.HttpClient> 实例上进行配置。

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        // Assume path to a client .pfx file and password are passed from command line
        // On Windows this would probably be a reference to the Certificate Store
        var cert = new X509Certificate2(args[0], args[1]);

        var handler = new HttpClientHandler();
        handler.ClientCertificates.Add(cert);
        var httpClient = new HttpClient(handler);

        var channel = GrpcChannel.ForAddress("https://localhost:5001/", new GrpcChannelOptions
        {
            HttpClient = httpClient
        });

        var grpc = new Greeter.GreeterClient(channel);
        var response = await grpc.SayHelloAsync(new HelloRequest { Name = "Bob" });
        System.Console.WriteLine(response.Message);
    }
}
```

## <a name="combining-channelcredentials-and-callcredentials"></a>结合 ChannelCredentials 和 CallCredentials

可以通过将证书更改应用于 Kestrel 服务器并使用 ASP.NET Core 中的 JWT 持有者中间件，将服务器配置为使用证书和令牌身份验证。

若要在客户端上同时提供 ChannelCredentials 和 CallCredentials，请使用 `ChannelCredentials.Create` 方法应用调用凭据。 仍需使用 <xref:System.Net.Http.HttpClient> 实例应用证书身份验证：如果将任何参数传递给 `SslCredentials` 构造函数，则内部客户端代码将引发异常。 `SslCredentials` 参数仅包含在 `Grpc.Net.Client` 包的 `Create` 方法中，以便保持与 `Grpc.Core` 包的兼容性。

```csharp
var handler = new HttpClientHandler();
handler.ClientCertificates.Add(cert);

var httpClient = new HttpClient(handler);

var callCredentials = CallCredentials.FromInterceptor(((context, metadata) =>
    {
        metadata.Add("Authorization", $"Bearer {_token}");
    }));

var channelCredentials = ChannelCredentials.Create(new SslCredentials(), callCredentials);

var channel = GrpcChannel.ForAddress("https://localhost:5001/", new GrpcChannelOptions
{
    HttpClient = httpClient,
    Credentials = channelCredentials
});

var grpc = new Portfolios.PortfoliosClient(channel);
```

> [!TIP]
> 你可以将 `ChannelCredentials.Create` 方法用于不使用证书身份验证的客户端，作为一种将令牌凭据与通道上发出的每个调用一起传递的有用方法。

GitHub 上已[添加证书身份验证的 FullStockTicker 示例 gRPC 应用程序](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker)的版本。

>[!div class="step-by-step"]
>[上一页](call-credentials.md)
>[下一页](encryption.md)
