---
title: 通道凭据 - 适用于 WCF 开发人员的 gRPC
description: 如何在ASP.NET酷睿3.0中实现和使用gRPC通道凭据。
ms.date: 09/02/2019
ms.openlocfilehash: 9ebe0aecb517e4cc2fe280632c4ecb593da9871c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148200"
---
# <a name="channel-credentials"></a>通道凭据

顾名思义，通道凭据附加到基础 gRPC 通道。 通道凭据的标准形式使用客户端证书身份验证。 在此过程中，客户端在进行连接时提供 TLS 证书，然后服务器在允许进行任何调用之前验证此证书。

您可以将通道凭据与呼叫凭据相结合，为 gRPC 服务提供全面的安全性。 通道凭据证明允许客户端应用程序访问服务，并且调用凭据提供有关使用客户端应用程序的人员的信息。

客户端证书身份验证适用于 gRPC，就像它适用于ASP.NET酷睿一样。 有关详细信息，请参阅在[ASP.NET 酷中配置证书身份验证](/aspnet/core/security/authentication/certauth)。

出于开发目的，可以使用自签名证书，但对于生产，应使用由受信任的机构签名的适当 HTTPS 证书。

## <a name="add-certificate-authentication-to-the-server"></a>向服务器添加证书身份验证

在主机级别（例如，在 Kestrel 服务器上）和 ASP.NET核心管道中配置证书身份验证。

### <a name="configure-certificate-validation-on-kestrel"></a>在 Kestrel 上配置证书验证

您可以配置 Kestrel（ASP.NET酷睿 HTTP 服务器）以需要客户端证书，并可以选择在接受传入连接之前对提供的证书执行某些验证。 在 类的方法中`CreateWebHostBuilder`执行此操作，`Program`而不是在 中`Startup`执行此操作。

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

此设置`ClientCertificateMode.RequireCertificate`导致 Kestrel 立即拒绝任何不提供客户端证书的连接请求，但此设置本身不会验证提供的证书。 添加`ClientCertificateValidation`回调，使 Kestrel 能够在连接时验证客户端证书，然后ASP.NET核心管道进行。 （在这种情况下，回调可确保它由与服务器证书相同的*证书颁发*。

### <a name="add-aspnet-core-certificate-authentication"></a>添加ASP.NET核心证书身份验证

[Microsoft.AspNetCore.身份验证.证书](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate)NuGet 包提供证书身份验证。

在`ConfigureServices`方法中添加证书身份验证服务，并将身份验证和授权添加到`Configure`方法中的ASP.NET核心管道。

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

## <a name="provide-channel-credentials-in-the-client-application"></a>在客户端应用程序中提供通道凭据

使用`Grpc.Net.Client`包，您可以在提供给用于连接的<xref:System.Net.Http.HttpClient>`GrpcChannel`实例上配置证书。

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

## <a name="combine-channelcredentials-and-callcredentials"></a>组合通道凭据和呼叫凭据

您可以将服务器配置为同时使用证书和令牌身份验证。 为此，将证书更改应用于 Kestrel 服务器，并使用 ASP.NET Core 中的 JWT 承载中间件。

要提供客户端`ChannelCredentials`和`CallCredentials`客户端，请使用`ChannelCredentials.Create`方法应用调用凭据。 您仍然需要使用<xref:System.Net.Http.HttpClient>实例应用证书身份验证。 如果将任何参数传递给`SslCredentials`构造函数，则内部客户端代码将引发异常。 该`SslCredentials`参数仅包含在包`Grpc.Net.Client``Create`的方法中，以保持与包的`Grpc.Core`兼容性。

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
> 您可以将 方法`ChannelCredentials.Create`用于没有证书身份验证的客户端。 这是将令牌凭据与通道上所做的每个调用传递的有用方法。

在 GitHub 上添加了[证书身份验证的 FullStockTicker 示例 gRPC 应用程序](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker)的版本。

>[!div class="step-by-step"]
>[上一个](call-credentials.md)
>[下一个](encryption.md)
