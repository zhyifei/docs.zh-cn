---
title: 自承载 gRPC 应用程序-WCF 开发人员 gRPC
description: 将 ASP.NET Core gRPC 应用程序部署为自承载服务。
ms.date: 09/02/2019
ms.openlocfilehash: 00b4ad50eae629b5b36a890d1eecf7119386c74c
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/29/2019
ms.locfileid: "75545064"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="bbd09-103">自承载的 gRPC 应用程序</span><span class="sxs-lookup"><span data-stu-id="bbd09-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="bbd09-104">尽管 ASP.NET Core 3.0 应用程序可在 Windows Server 上的 IIS 中承载，但目前无法在 IIS 中承载 gRPC 应用程序，因为尚不支持某些 HTTP/2 功能。</span><span class="sxs-lookup"><span data-stu-id="bbd09-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't yet supported.</span></span> <span data-ttu-id="bbd09-105">未来对 Windows Server 的更新中需要此功能。</span><span class="sxs-lookup"><span data-stu-id="bbd09-105">This functionality is expected in a future update to Windows Server.</span></span>

<span data-ttu-id="bbd09-106">由于 .NET Core 3.0 托管扩展中的一些新功能，你可以将应用程序作为 Windows 服务或[systemd](https://en.wikipedia.org/wiki/Systemd)控制的 Linux 服务运行。</span><span class="sxs-lookup"><span data-stu-id="bbd09-106">You can run your application as a Windows Service, or as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), thanks to some new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="bbd09-107">以 Windows 服务的形式运行你的应用</span><span class="sxs-lookup"><span data-stu-id="bbd09-107">Run your app as a Windows service</span></span>

<span data-ttu-id="bbd09-108">若要将 ASP.NET Core 应用程序配置为作为 Windows 服务运行，请从 NuGet 安装[WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices)包。</span><span class="sxs-lookup"><span data-stu-id="bbd09-108">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="bbd09-109">然后，将 `UseWindowsService` 对的调用添加到 `Program.cs`中的 `CreateHostBuilder` 方法。</span><span class="sxs-lookup"><span data-stu-id="bbd09-109">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseWindowsService() // Enable running as a Windows service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> <span data-ttu-id="bbd09-110">如果应用程序未作为 Windows 服务运行，则 `UseWindowsService` 方法不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="bbd09-110">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="bbd09-111">现在，在 Visual Studio 中发布应用程序，方法是右键单击该项目，然后从上下文菜单中选择 "*发布*"，或者从 ".NET Core CLI"。</span><span class="sxs-lookup"><span data-stu-id="bbd09-111">Now publish your application, either from Visual Studio by right-clicking the project and choosing *Publish* from the context menu, or from the .NET Core CLI.</span></span>

<span data-ttu-id="bbd09-112">发布 .NET Core 应用程序时，可以选择创建*依赖框架*的部署或*独立*部署。</span><span class="sxs-lookup"><span data-stu-id="bbd09-112">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="bbd09-113">依赖于框架的部署要求在运行的主机上安装 .NET Core 共享运行时。</span><span class="sxs-lookup"><span data-stu-id="bbd09-113">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="bbd09-114">自包含的部署是使用 .NET Core 运行时和框架的完整副本发布的，可以在任何主机上运行。</span><span class="sxs-lookup"><span data-stu-id="bbd09-114">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="bbd09-115">有关详细信息，包括每种方法的优点和缺点，请参阅[.Net Core 应用程序部署](../../core/deploying/index.md)文档。</span><span class="sxs-lookup"><span data-stu-id="bbd09-115">For more information, including the advantages and disadvantages of each approach, refer to the [.NET Core application deployment](../../core/deploying/index.md) documentation.</span></span>

<span data-ttu-id="bbd09-116">若要发布不需要在主机上安装 .NET Core 3.0 运行时的应用程序的自包含生成，请使用 `-r` （或 `--runtime`）标志来指定要包含在应用程序中的运行时。</span><span class="sxs-lookup"><span data-stu-id="bbd09-116">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application using the `-r` (or `--runtime`) flag.</span></span>

```console
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="bbd09-117">若要发布依赖于框架的生成，请省略 `-r` 标志。</span><span class="sxs-lookup"><span data-stu-id="bbd09-117">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```console
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="bbd09-118">将 `publish` 目录的完整内容复制到安装文件夹，并使用[sc 实用工具](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc)为可执行文件创建 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="bbd09-118">Copy the complete contents of the `publish` directory to an installation folder, and use the [sc utility](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-windows-event-log"></a><span data-ttu-id="bbd09-119">记录到 Windows 事件日志</span><span class="sxs-lookup"><span data-stu-id="bbd09-119">Log to Windows Event Log</span></span>

<span data-ttu-id="bbd09-120">`UseWindowsService` 方法自动添加将日志消息写入 Windows 事件日志的[日志记录](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0)提供程序。</span><span class="sxs-lookup"><span data-stu-id="bbd09-120">The `UseWindowsService` method automatically adds a [Logging](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) provider that writes log messages to the Windows Event Log.</span></span> <span data-ttu-id="bbd09-121">可以通过将 `EventLog` 条目添加到 `appsettings.json` 或其他配置源的 `Logging` 部分来配置此提供程序的日志记录。</span><span class="sxs-lookup"><span data-stu-id="bbd09-121">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or other configuration source.</span></span> <span data-ttu-id="bbd09-122">可以通过在这些设置中设置 `SourceName` 属性来重写事件日志中使用的源名称;如果未指定名称，则将使用默认应用程序名称（通常为可执行程序集名称）。</span><span class="sxs-lookup"><span data-stu-id="bbd09-122">The source name used in Event Log can be overridden by setting a `SourceName` property in these settings; if you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="bbd09-123">本章末尾介绍了日志记录的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bbd09-123">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="bbd09-124">使用 systemd 将应用作为 Linux 服务运行</span><span class="sxs-lookup"><span data-stu-id="bbd09-124">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="bbd09-125">若要将 ASP.NET Core 应用程序配置为以 Linux 服务（或 Linux 行话中的*后台*程序）运行，请从 NuGet 安装[Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd)包。</span><span class="sxs-lookup"><span data-stu-id="bbd09-125">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="bbd09-126">然后，将 `UseSystemd` 对的调用添加到 `Program.cs`中的 `CreateHostBuilder` 方法。</span><span class="sxs-lookup"><span data-stu-id="bbd09-126">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseSystemd() // Enable running as a Systemd service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> <span data-ttu-id="bbd09-127">如果应用程序未作为 Linux 服务运行，则 `UseSystemd` 方法不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="bbd09-127">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="bbd09-128">现在，通过右键单击项目，然后从上下文菜单中选择 "*发布*"，或者使用以下命令从 .NET Core CLI 中发布应用程序（依赖于框架的应用程序或独立的 Linux 运行时独立的应用程序，例如 `linux-x64`）。</span><span class="sxs-lookup"><span data-stu-id="bbd09-128">Now publish your application (either framework-dependent, or self-contained for the relevant Linux runtime, for example, `linux-x64`), either from Visual Studio by right-clicking the project and choosing *Publish* from the context menu, or from the .NET Core CLI using the following command.</span></span>

```console
dotnet publish -c Release -r linux-x64 -o ./publish
```

<span data-ttu-id="bbd09-129">将 `publish` 目录的完整内容复制到 Linux 主机上的安装文件夹中。</span><span class="sxs-lookup"><span data-stu-id="bbd09-129">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="bbd09-130">注册服务需要将一个称为 "unit file" 的特殊文件添加到 `/etc/systemd/system` 目录。</span><span class="sxs-lookup"><span data-stu-id="bbd09-130">Registering the service requires a special file, called a "unit file", to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="bbd09-131">你需要 root 权限才能在此文件夹中创建文件。</span><span class="sxs-lookup"><span data-stu-id="bbd09-131">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="bbd09-132">使用需要 `systemd` 要使用的标识符和 `.service` 扩展名来命名该文件。</span><span class="sxs-lookup"><span data-stu-id="bbd09-132">Name the file with the identifier you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="bbd09-133">例如 `/etc/systemd/system/myapp.service`。</span><span class="sxs-lookup"><span data-stu-id="bbd09-133">For example, `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="bbd09-134">服务文件使用 INI 格式，如本示例中所示。</span><span class="sxs-lookup"><span data-stu-id="bbd09-134">The service file uses INI format, as shown in this example.</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="bbd09-135">`Type=notify` 属性告知 `systemd` 应用程序在启动和关闭时将通知该应用程序。</span><span class="sxs-lookup"><span data-stu-id="bbd09-135">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="bbd09-136">`WantedBy=multi-user.target` 设置将导致在 Linux 系统达到 "运行级别 2" 时启动服务，这意味着非图形多用户 shell 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="bbd09-136">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2", meaning a non-graphical multi-user shell is active.</span></span>

<span data-ttu-id="bbd09-137">在 `systemd` 将识别该服务之前，需要重新加载其配置。</span><span class="sxs-lookup"><span data-stu-id="bbd09-137">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="bbd09-138">使用 `systemctl` 命令控制 `systemd`。</span><span class="sxs-lookup"><span data-stu-id="bbd09-138">You control `systemd` using the `systemctl` command.</span></span> <span data-ttu-id="bbd09-139">重新加载后，请使用 `status` 子命令确认已成功注册应用程序。</span><span class="sxs-lookup"><span data-stu-id="bbd09-139">After reloading, use the `status` subcommand to confirm the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="bbd09-140">如果已正确配置服务，将显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="bbd09-140">If you've configured the service correctly, the following output will be shown:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="bbd09-141">使用 `start` 命令来启动该服务。</span><span class="sxs-lookup"><span data-stu-id="bbd09-141">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="bbd09-142">使用 `systemctl start`时，`.service` 扩展名是可选的。</span><span class="sxs-lookup"><span data-stu-id="bbd09-142">The `.service` extension is optional when using `systemctl start`.</span></span>

<span data-ttu-id="bbd09-143">若要告诉 `systemd` 在系统启动时自动启动该服务，请使用 `enable` 命令。</span><span class="sxs-lookup"><span data-stu-id="bbd09-143">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="bbd09-144">登录到 journald</span><span class="sxs-lookup"><span data-stu-id="bbd09-144">Log to journald</span></span>

<span data-ttu-id="bbd09-145">Windows 事件日志的 Linux 等效项 `journald`是 `systemd`的一部分的结构化日志系统服务。</span><span class="sxs-lookup"><span data-stu-id="bbd09-145">The Linux equivalent of the Windows Event Log is `journald`, a structured logging system service that is part of `systemd`.</span></span> <span data-ttu-id="bbd09-146">由 Linux 后台程序写入标准输出的日志消息将自动写入到 `journald`，因此，若要配置日志记录级别，请使用日志记录配置的 `Console` 部分。</span><span class="sxs-lookup"><span data-stu-id="bbd09-146">Log messages written to the standard output by a Linux daemon are automatically written to `journald`, so to configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="bbd09-147">`UseSystemd` 主机生成器方法自动配置控制台输出格式以适合日志。</span><span class="sxs-lookup"><span data-stu-id="bbd09-147">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="bbd09-148">由于 `journald` 是 Linux 日志的标准，因此有多种与之集成的工具，可以轻松地将日志从 `journald` 路由到外部日志记录系统。</span><span class="sxs-lookup"><span data-stu-id="bbd09-148">Because `journald` is the standard for Linux logs, there are a variety of tools that integrate with it, and you can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="bbd09-149">在本地运行的主机上，你可以使用 `journalctl` 命令从命令行中查看日志。</span><span class="sxs-lookup"><span data-stu-id="bbd09-149">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="bbd09-150">如果主机上有可用的 GUI 环境，则可以使用一些图形日志查看器，如*QJournalctl*和*gnome 日志*。</span><span class="sxs-lookup"><span data-stu-id="bbd09-150">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="bbd09-151">若要详细了解如何在 `journalctl`的命令行中查询 systemd 日志，请参阅[手册页](https://manpages.debian.org/buster/systemd/journalctl.1)。</span><span class="sxs-lookup"><span data-stu-id="bbd09-151">To learn more about querying the systemd journal from the command line with `journalctl`, see [the man pages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="bbd09-152">用于自承载应用程序的 HTTPS 证书</span><span class="sxs-lookup"><span data-stu-id="bbd09-152">HTTPS Certificates for self-hosted applications</span></span>

<span data-ttu-id="bbd09-153">在生产环境中运行 gRPC 应用程序时，应使用来自受信任的证书颁发机构（CA）的 TLS 证书。</span><span class="sxs-lookup"><span data-stu-id="bbd09-153">When running a gRPC application in production, you should use a TLS certificate from a trusted Certificate Authority (CA).</span></span> <span data-ttu-id="bbd09-154">此 CA 可以是公共 CA，也可以是组织的内部 ca。</span><span class="sxs-lookup"><span data-stu-id="bbd09-154">This CA could be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="bbd09-155">在 Windows 主机上，可以使用 <xref:System.Security.Cryptography.X509Certificates.X509Store> 类从安全的[证书存储区](/windows/win32/seccrypto/managing-certificates-with-certificate-stores)中加载证书。</span><span class="sxs-lookup"><span data-stu-id="bbd09-155">On Windows hosts, the certificate may be loaded from a secure [Certificate Store](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) using the <xref:System.Security.Cryptography.X509Certificates.X509Store> class.</span></span> <span data-ttu-id="bbd09-156">`X509Store` 类还可与某些 Linux 主机上的 OpenSSL 密钥存储一起使用。</span><span class="sxs-lookup"><span data-stu-id="bbd09-156">The `X509Store` class can also be used with the OpenSSL key-store on some Linux hosts.</span></span>

<span data-ttu-id="bbd09-157">还可以使用[X509Certificate2 构造函数](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0)之一创建证书，无论是从文件（例如，受强密码保护的 `.pfx` 文件），还是从安全存储服务（如[Azure Key Vault](https://azure.microsoft.com/services/key-vault/)）检索到的二进制数据。</span><span class="sxs-lookup"><span data-stu-id="bbd09-157">Certificates may also be created using one of the [X509Certificate2 constructors](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0), either from a file (for example a `.pfx` file protected by a strong password), or from binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).</span></span>

<span data-ttu-id="bbd09-158">可以通过两种方式将 Kestrel 配置为使用证书：通过配置或代码。</span><span class="sxs-lookup"><span data-stu-id="bbd09-158">Kestrel can be configured to use a certificate in two ways: from configuration, or in code.</span></span>

### <a name="set-https-certificates-using-configuration"></a><span data-ttu-id="bbd09-159">使用配置设置 HTTPS 证书</span><span class="sxs-lookup"><span data-stu-id="bbd09-159">Set HTTPS certificates using configuration</span></span>

<span data-ttu-id="bbd09-160">配置方法要求在 Kestrel 配置节中设置证书的路径 `.pfx` 文件和密码。</span><span class="sxs-lookup"><span data-stu-id="bbd09-160">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="bbd09-161">在 `appsettings.json` 中，将如下所示。</span><span class="sxs-lookup"><span data-stu-id="bbd09-161">In `appsettings.json` that would look like this.</span></span>

```json
{
  "Kestrel": {
    "Certificates": {
      "Default": {
        "Path": "cert.pfx",
        "Password": "DO NOT STORE PLAINTEXT PASSWORDS IN APPSETTINGS FILES"
      }
    }
  }
}
```

<span data-ttu-id="bbd09-162">应使用安全配置源（如 Azure KeyVault 或 Hashicorp 保管库）提供密码。</span><span class="sxs-lookup"><span data-stu-id="bbd09-162">The password should be provided using a secure configuration source such as Azure KeyVault or Hashicorp Vault.</span></span>

<span data-ttu-id="bbd09-163">不应在配置文件中存储未加密的密码。</span><span class="sxs-lookup"><span data-stu-id="bbd09-163">You SHOULD NOT store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="bbd09-164">在代码中设置 HTTPS 证书</span><span class="sxs-lookup"><span data-stu-id="bbd09-164">Set HTTPS certificates in code</span></span>

<span data-ttu-id="bbd09-165">若要在代码中的 Kestrel 上配置 HTTPS，请使用 `Program` 类中 `IWebHostBuilder` 的 `ConfigureKestrel` 方法。</span><span class="sxs-lookup"><span data-stu-id="bbd09-165">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
            webBuilder.ConfigureKestrel(kestrel =>
            {
                kestrel.ConfigureHttpsDefaults(https =>
                {
                    https.ServerCertificate = new X509Certificate2("mycert.pfx", "password");
                });
            });
        });
```

<span data-ttu-id="bbd09-166">同样，`.pfx` 文件的密码应存储在安全配置源中并从该文件中检索。</span><span class="sxs-lookup"><span data-stu-id="bbd09-166">Again, the password for the `.pfx` file should be stored in and retrieved from a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bbd09-167">[上一页](grpc-in-production.md)
>[下一页](docker.md)</span><span class="sxs-lookup"><span data-stu-id="bbd09-167">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
