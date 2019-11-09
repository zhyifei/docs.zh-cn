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
# <a name="channel-credentials"></a><span data-ttu-id="9ebb1-103">通道凭据</span><span class="sxs-lookup"><span data-stu-id="9ebb1-103">Channel credentials</span></span>

<span data-ttu-id="9ebb1-104">顾名思义，通道凭据会附加到基础 gRPC 通道。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="9ebb1-105">通道凭据的标准形式使用客户端证书身份验证，其中客户端在建立连接时提供 TLS 证书，该证书是在允许进行任何调用之前由服务器验证的。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-105">The standard form of channel credentials uses Client Certificate authentication, where the client provides a TLS certificate when it's making the connection, which is verified by the server before allowing any calls to be made.</span></span>

<span data-ttu-id="9ebb1-106">通道凭据可以与调用凭据结合使用，为 gRPC 服务提供全面的安全性。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-106">Channel credentials can be combined with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="9ebb1-107">通道凭据证明允许客户端应用程序访问该服务，而调用凭据则提供有关使用该客户端应用程序的人员的信息。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-107">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person using the client application.</span></span>

<span data-ttu-id="9ebb1-108">对于 gRPC，客户端证书身份验证的工作方式与 ASP.NET Core 的工作方式相同。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-108">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="9ebb1-109">此配置过程将在此处汇总，但在 ASP.NET Core 一文[中配置证书身份验证](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0)中提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-109">The configuration process will be summarized here, but more information is available in the [Configure certificate authentication in ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0) article.</span></span>

<span data-ttu-id="9ebb1-110">出于开发目的，你可以使用自签名证书，但对于生产，你应该使用由受信任的颁发机构签名的正确 HTTPS 证书。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-110">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="adding-certificate-authentication-to-the-server"></a><span data-ttu-id="9ebb1-111">将证书身份验证添加到服务器</span><span class="sxs-lookup"><span data-stu-id="9ebb1-111">Adding certificate authentication to the server</span></span>

<span data-ttu-id="9ebb1-112">需要在主机级别配置证书身份验证（例如，在 Kestrel 服务器上），并在 ASP.NET Core 管道中配置证书身份验证。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-112">You need to configure certificate authentication both at the host level, for example on the Kestrel server, and in the ASP.NET Core pipeline.</span></span>

### <a name="configuring-certificate-validation-on-kestrel"></a><span data-ttu-id="9ebb1-113">在 Kestrel 上配置证书验证</span><span class="sxs-lookup"><span data-stu-id="9ebb1-113">Configuring certificate validation on Kestrel</span></span>

<span data-ttu-id="9ebb1-114">你可以将 Kestrel （ASP.NET Core HTTP 服务器）配置为需要客户端证书，并在接受传入连接之前，选择执行提供的证书的某些验证。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-114">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate before accepting incoming connections.</span></span> <span data-ttu-id="9ebb1-115">此配置在 `Program` 类的 `CreateWebHostBuilder` 方法中完成，而不是在 `Startup`中完成。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-115">This configuration is done in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

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

<span data-ttu-id="9ebb1-116">`ClientCertificateMode.RequireCertificate` 设置将导致 Kestrel 立即拒绝不提供客户端证书的任何连接请求，但不会验证证书。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-116">The `ClientCertificateMode.RequireCertificate` setting will cause Kestrel to immediately reject any connection request that doesn't provide a client certificate, but it won't validate the certificate.</span></span> <span data-ttu-id="9ebb1-117">添加 `ClientCertificateValidation` 回调后，Kestrel 就可以在建立 ASP.NET Core 管道之前，验证客户端证书（在这种情况下，确保它由与服务器证书相同的*证书颁发机构*颁发）。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-117">Adding the `ClientCertificateValidation` callback enables Kestrel to validate the client certificate (in this case, ensuring that it was issued by the same *Certificate Authority* as the server certificate) at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span>

### <a name="adding-aspnet-core-certificate-authentication"></a><span data-ttu-id="9ebb1-118">添加 ASP.NET Core 证书身份验证</span><span class="sxs-lookup"><span data-stu-id="9ebb1-118">Adding ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="9ebb1-119">证书身份验证由[AspNetCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet 包提供。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-119">Certificate authentication is provided by the [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package.</span></span>

<span data-ttu-id="9ebb1-120">在 `ConfigureServices` 方法中添加证书身份验证服务，并在 `Configure` 方法中将身份验证和授权添加到 ASP.NET Core 管道。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-120">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

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

## <a name="providing-channel-credentials-in-the-client-application"></a><span data-ttu-id="9ebb1-121">提供客户端应用程序中的通道凭据</span><span class="sxs-lookup"><span data-stu-id="9ebb1-121">Providing channel credentials in the client application</span></span>

<span data-ttu-id="9ebb1-122">使用 `Grpc.Net.Client` 包，证书在提供给用于连接的 `GrpcChannel` 的 <xref:System.Net.Http.HttpClient> 实例上进行配置。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-122">With the `Grpc.Net.Client` package, certificates are configured on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

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

## <a name="combining-channelcredentials-and-callcredentials"></a><span data-ttu-id="9ebb1-123">结合 ChannelCredentials 和 CallCredentials</span><span class="sxs-lookup"><span data-stu-id="9ebb1-123">Combining ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="9ebb1-124">可以通过将证书更改应用于 Kestrel 服务器并使用 ASP.NET Core 中的 JWT 持有者中间件，将服务器配置为使用证书和令牌身份验证。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-124">You can configure your server to use both certificate and token authentication by applying the certificate changes to the Kestrel server and using the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="9ebb1-125">若要在客户端上同时提供 ChannelCredentials 和 CallCredentials，请使用 `ChannelCredentials.Create` 方法应用调用凭据。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-125">To provide both ChannelCredentials and CallCredentials on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="9ebb1-126">仍需使用 <xref:System.Net.Http.HttpClient> 实例应用证书身份验证：如果将任何参数传递给 `SslCredentials` 构造函数，则内部客户端代码将引发异常。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-126">Certificate authentication still needs to be applied using the <xref:System.Net.Http.HttpClient> instance: if you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="9ebb1-127">`SslCredentials` 参数仅包含在 `Grpc.Net.Client` 包的 `Create` 方法中，以便保持与 `Grpc.Core` 包的兼容性。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-127">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

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
> <span data-ttu-id="9ebb1-128">你可以将 `ChannelCredentials.Create` 方法用于不使用证书身份验证的客户端，作为一种将令牌凭据与通道上发出的每个调用一起传递的有用方法。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-128">You can use the `ChannelCredentials.Create` method for a client without certificate authentication, as a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="9ebb1-129">GitHub 上已[添加证书身份验证的 FullStockTicker 示例 gRPC 应用程序](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker)的版本。</span><span class="sxs-lookup"><span data-stu-id="9ebb1-129">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9ebb1-130">[上一页](call-credentials.md)
>[下一页](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="9ebb1-130">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
