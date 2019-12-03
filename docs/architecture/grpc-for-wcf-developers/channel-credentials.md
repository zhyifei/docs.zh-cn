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
# <a name="channel-credentials"></a><span data-ttu-id="3d269-103">通道凭据</span><span class="sxs-lookup"><span data-stu-id="3d269-103">Channel credentials</span></span>

<span data-ttu-id="3d269-104">顾名思义，通道凭据会附加到基础 gRPC 通道。</span><span class="sxs-lookup"><span data-stu-id="3d269-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="3d269-105">通道凭据的标准形式使用客户端证书身份验证。</span><span class="sxs-lookup"><span data-stu-id="3d269-105">The standard form of channel credentials uses client certificate authentication.</span></span> <span data-ttu-id="3d269-106">在此过程中，客户端会在建立连接时提供 TLS 证书，然后服务器会在允许进行任何调用之前验证此证书。</span><span class="sxs-lookup"><span data-stu-id="3d269-106">In this process, the client provides a TLS certificate when it's making the connection, and then the server verifies this before allowing any calls to be made.</span></span>

<span data-ttu-id="3d269-107">可以将通道凭据与呼叫凭据相结合，为 gRPC 服务提供全面的安全性。</span><span class="sxs-lookup"><span data-stu-id="3d269-107">You can combine channel credentials with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="3d269-108">通道凭据证明允许客户端应用程序访问该服务，而调用凭据则提供了有关使用该客户端应用程序的用户的信息。</span><span class="sxs-lookup"><span data-stu-id="3d269-108">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person who is using the client application.</span></span>

<span data-ttu-id="3d269-109">对于 gRPC，客户端证书身份验证的工作方式与 ASP.NET Core 的工作方式相同。</span><span class="sxs-lookup"><span data-stu-id="3d269-109">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="3d269-110">有关详细信息，请参阅[在 ASP.NET Core 中配置证书身份验证](/aspnet/core/security/authentication/certauth)。</span><span class="sxs-lookup"><span data-stu-id="3d269-110">For more information, see [Configure certificate authentication in ASP.NET Core](/aspnet/core/security/authentication/certauth).</span></span>

<span data-ttu-id="3d269-111">出于开发目的，你可以使用自签名证书，但对于生产，你应该使用由受信任的颁发机构签名的正确 HTTPS 证书。</span><span class="sxs-lookup"><span data-stu-id="3d269-111">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="add-certificate-authentication-to-the-server"></a><span data-ttu-id="3d269-112">将证书身份验证添加到服务器</span><span class="sxs-lookup"><span data-stu-id="3d269-112">Add certificate authentication to the server</span></span>

<span data-ttu-id="3d269-113">在主机级别（例如，在 Kestrel 服务器上）以及在 ASP.NET Core 管道中配置证书身份验证。</span><span class="sxs-lookup"><span data-stu-id="3d269-113">Configure certificate authentication both at the host level (for example, on the Kestrel server), and in the ASP.NET Core pipeline.</span></span>

### <a name="configure-certificate-validation-on-kestrel"></a><span data-ttu-id="3d269-114">在 Kestrel 上配置证书验证</span><span class="sxs-lookup"><span data-stu-id="3d269-114">Configure certificate validation on Kestrel</span></span>

<span data-ttu-id="3d269-115">可以将 Kestrel （ASP.NET Core HTTP 服务器）配置为需要客户端证书，并在接受传入连接之前，执行提供的证书的部分验证。</span><span class="sxs-lookup"><span data-stu-id="3d269-115">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate, before accepting incoming connections.</span></span> <span data-ttu-id="3d269-116">可以在 `Program` 类的 `CreateWebHostBuilder` 方法中执行此操作，而不是在 `Startup`中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="3d269-116">You do this in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

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

<span data-ttu-id="3d269-117">`ClientCertificateMode.RequireCertificate` 设置会导致 Kestrel 立即拒绝不提供客户端证书的任何连接请求，但此设置本身不会验证提供的证书。</span><span class="sxs-lookup"><span data-stu-id="3d269-117">The `ClientCertificateMode.RequireCertificate` setting causes Kestrel to immediately reject any connection request that doesn't provide a client certificate, but this setting by itself won't validate a certificate that is provided.</span></span> <span data-ttu-id="3d269-118">添加 `ClientCertificateValidation` 回调，以使 Kestrel 能够在连接到 ASP.NET Core 管道之前验证客户端证书。</span><span class="sxs-lookup"><span data-stu-id="3d269-118">Add the `ClientCertificateValidation` callback to enable Kestrel to validate the client certificate at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span> <span data-ttu-id="3d269-119">（在这种情况下，回叫将确保它由与服务器证书相同的*证书颁发机构*颁发。）</span><span class="sxs-lookup"><span data-stu-id="3d269-119">(In this case, the callback ensures that it was issued by the same *Certificate Authority* as the server certificate.)</span></span> 

### <a name="add-aspnet-core-certificate-authentication"></a><span data-ttu-id="3d269-120">添加 ASP.NET Core 证书身份验证</span><span class="sxs-lookup"><span data-stu-id="3d269-120">Add ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="3d269-121">[AspNetCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet 包提供证书身份验证。</span><span class="sxs-lookup"><span data-stu-id="3d269-121">The [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package provides certificate authentication.</span></span>

<span data-ttu-id="3d269-122">在 `ConfigureServices` 方法中添加证书身份验证服务，并在 `Configure` 方法中将身份验证和授权添加到 ASP.NET Core 管道。</span><span class="sxs-lookup"><span data-stu-id="3d269-122">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

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

## <a name="provide-channel-credentials-in-the-client-application"></a><span data-ttu-id="3d269-123">提供客户端应用程序中的通道凭据</span><span class="sxs-lookup"><span data-stu-id="3d269-123">Provide channel credentials in the client application</span></span>

<span data-ttu-id="3d269-124">使用 `Grpc.Net.Client` 包，你可以在提供给用于连接的 `GrpcChannel` 的 <xref:System.Net.Http.HttpClient> 实例上配置证书。</span><span class="sxs-lookup"><span data-stu-id="3d269-124">With the `Grpc.Net.Client` package, you configure certificates on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

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

## <a name="combine-channelcredentials-and-callcredentials"></a><span data-ttu-id="3d269-125">合并 ChannelCredentials 和 CallCredentials</span><span class="sxs-lookup"><span data-stu-id="3d269-125">Combine ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="3d269-126">你可以将服务器配置为使用证书和令牌身份验证。</span><span class="sxs-lookup"><span data-stu-id="3d269-126">You can configure your server to use both certificate and token authentication.</span></span> <span data-ttu-id="3d269-127">为此，可将证书更改应用到 Kestrel 服务器，并使用 ASP.NET Core 中的 JWT 持有者中间件。</span><span class="sxs-lookup"><span data-stu-id="3d269-127">Do this by applying the certificate changes to the Kestrel server, and using the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="3d269-128">若要在客户端上提供 `ChannelCredentials` 和 `CallCredentials`，请使用 `ChannelCredentials.Create` 方法应用调用凭据。</span><span class="sxs-lookup"><span data-stu-id="3d269-128">To provide both `ChannelCredentials` and `CallCredentials` on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="3d269-129">仍需使用 <xref:System.Net.Http.HttpClient> 实例应用证书身份验证。</span><span class="sxs-lookup"><span data-stu-id="3d269-129">You still need to apply certificate authentication by using the <xref:System.Net.Http.HttpClient> instance.</span></span> <span data-ttu-id="3d269-130">如果将任何参数传递到 `SslCredentials` 构造函数，则内部客户端代码将引发异常。</span><span class="sxs-lookup"><span data-stu-id="3d269-130">If you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="3d269-131">`SslCredentials` 参数仅包含在 `Grpc.Net.Client` 包的 `Create` 方法中，以便保持与 `Grpc.Core` 包的兼容性。</span><span class="sxs-lookup"><span data-stu-id="3d269-131">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

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
> <span data-ttu-id="3d269-132">无需证书身份验证即可将 `ChannelCredentials.Create` 方法用于客户端。</span><span class="sxs-lookup"><span data-stu-id="3d269-132">You can use the `ChannelCredentials.Create` method for a client without certificate authentication.</span></span> <span data-ttu-id="3d269-133">这是一种将令牌凭据与通道上发出的每个调用一起传递的有用方法。</span><span class="sxs-lookup"><span data-stu-id="3d269-133">This is a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="3d269-134">GitHub 上已[添加证书身份验证的 FullStockTicker 示例 gRPC 应用程序](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker)的版本。</span><span class="sxs-lookup"><span data-stu-id="3d269-134">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3d269-135">[上一页](call-credentials.md)
>[下一页](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="3d269-135">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
