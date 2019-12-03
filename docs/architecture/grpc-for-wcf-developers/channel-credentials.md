---
title: 通道凭据-适用于 WCF 开发人员的 gRPC
description: 如何在 ASP.NET Core 3.0 中实现和使用 gRPC 通道凭据。
ms.date: 09/02/2019
ms.openlocfilehash: 133de2c732e72844f249f11bfe22b5980b828b89
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711491"
---
# <a name="channel-credentials"></a>通道凭据

顾名思义，通道凭据会附加到基础 gRPC 通道。 通道凭据的标准形式使用客户端证书身份验证。 在此过程中，客户端会在建立连接时提供 TLS 证书，然后服务器会在允许进行任何调用之前验证此证书。

可以将通道凭据与呼叫凭据相结合，为 gRPC 服务提供全面的安全性。 通道凭据证明允许客户端应用程序访问该服务，而调用凭据则提供了有关使用该客户端应用程序的用户的信息。

对于 gRPC，客户端证书身份验证的工作方式与 ASP.NET Core 的工作方式相同。 有关详细信息，请参阅[在 ASP.NET Core 中配置证书身份验证](/aspnet/core/security/authentication/certauth)。

出于开发目的，你可以使用自签名证书，但对于生产，你应该使用由受信任的颁发机构签名的正确 HTTPS 证书。

## <a name="add-certificate-authentication-to-the-server"></a>将证书身份验证添加到服务器

在主机级别（例如，在 Kestrel 服务器上）以及在 ASP.NET Core 管道中配置证书身份验证。

### <a name="configure-certificate-validation-on-kestrel"></a>在 Kestrel 上配置证书验证

可以将 Kestrel （ASP.NET Core HTTP 服务器）配置为需要客户端证书，并在接受传入连接之前，执行提供的证书的部分验证。 可以在 `Program` 类的 `CreateWebHostBuilder` 方法中执行此操作，而不是在 `Startup`中执行此操作。

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

`ClientCertificateMode.RequireCertificate` 设置会导致 Kestrel 立即拒绝不提供客户端证书的任何连接请求，但此设置本身不会验证提供的证书。 添加 `ClientCertificateValidation` 回调，以使 Kestrel 能够在连接到 ASP.NET Core 管道之前验证客户端证书。 （在这种情况下，回叫将确保它由与服务器证书相同的*证书颁发机构*颁发。） 

### <a name="add-aspnet-core-certificate-authentication"></a>添加 ASP.NET Core 证书身份验证

[AspNetCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet 包提供证书身份验证。

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

## <a name="provide-channel-credentials-in-the-client-application"></a>提供客户端应用程序中的通道凭据

使用 `Grpc.Net.Client` 包，你可以在提供给用于连接的 `GrpcChannel` 的 <xref:System.Net.Http.HttpClient> 实例上配置证书。

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

## <a name="combine-channelcredentials-and-callcredentials"></a>合并 ChannelCredentials 和 CallCredentials

你可以将服务器配置为使用证书和令牌身份验证。 为此，可将证书更改应用到 Kestrel 服务器，并使用 ASP.NET Core 中的 JWT 持有者中间件。

若要在客户端上提供 `ChannelCredentials` 和 `CallCredentials`，请使用 `ChannelCredentials.Create` 方法应用调用凭据。 仍需使用 <xref:System.Net.Http.HttpClient> 实例应用证书身份验证。 如果将任何参数传递到 `SslCredentials` 构造函数，则内部客户端代码将引发异常。 `SslCredentials` 参数仅包含在 `Grpc.Net.Client` 包的 `Create` 方法中，以便保持与 `Grpc.Core` 包的兼容性。

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
> 无需证书身份验证即可将 `ChannelCredentials.Create` 方法用于客户端。 这是一种将令牌凭据与通道上发出的每个调用一起传递的有用方法。

GitHub 上已[添加证书身份验证的 FullStockTicker 示例 gRPC 应用程序](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker)的版本。

>[!div class="step-by-step"]
>[上一页](call-credentials.md)
>[下一页](encryption.md)
