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
# <a name="self-hosted-grpc-applications"></a>自承载的 gRPC 应用程序

尽管 ASP.NET Core 3.0 应用程序可在 Windows Server 上的 IIS 中承载，但目前无法在 IIS 中承载 gRPC 应用程序，因为尚不支持某些 HTTP/2 功能。 未来对 Windows Server 的更新中需要此功能。

由于 .NET Core 3.0 托管扩展中的一些新功能，你可以将应用程序作为 Windows 服务或[systemd](https://en.wikipedia.org/wiki/Systemd)控制的 Linux 服务运行。

## <a name="run-your-app-as-a-windows-service"></a>以 Windows 服务的形式运行你的应用

若要将 ASP.NET Core 应用程序配置为作为 Windows 服务运行，请从 NuGet 安装[WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices)包。 然后，将 `UseWindowsService` 对的调用添加到 `Program.cs`中的 `CreateHostBuilder` 方法。

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
> 如果应用程序未作为 Windows 服务运行，则 `UseWindowsService` 方法不执行任何操作。

现在，在 Visual Studio 中发布应用程序，方法是右键单击该项目，然后从上下文菜单中选择 "*发布*"，或者从 ".NET Core CLI"。

发布 .NET Core 应用程序时，可以选择创建*依赖框架*的部署或*独立*部署。 依赖于框架的部署要求在运行的主机上安装 .NET Core 共享运行时。 自包含的部署是使用 .NET Core 运行时和框架的完整副本发布的，可以在任何主机上运行。 有关详细信息，包括每种方法的优点和缺点，请参阅[.Net Core 应用程序部署](../../core/deploying/index.md)文档。

若要发布不需要在主机上安装 .NET Core 3.0 运行时的应用程序的自包含生成，请使用 `-r` （或 `--runtime`）标志来指定要包含在应用程序中的运行时。

```console
dotnet publish -c Release -r win-x64 -o ./publish
```

若要发布依赖于框架的生成，请省略 `-r` 标志。

```console
dotnet publish -c Release -o ./publish
```

将 `publish` 目录的完整内容复制到安装文件夹，并使用[sc 实用工具](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc)为可执行文件创建 Windows 服务。

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-windows-event-log"></a>记录到 Windows 事件日志

`UseWindowsService` 方法自动添加将日志消息写入 Windows 事件日志的[日志记录](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0)提供程序。 可以通过将 `EventLog` 条目添加到 `appsettings.json` 或其他配置源的 `Logging` 部分来配置此提供程序的日志记录。 可以通过在这些设置中设置 `SourceName` 属性来重写事件日志中使用的源名称;如果未指定名称，则将使用默认应用程序名称（通常为可执行程序集名称）。

本章末尾介绍了日志记录的详细信息。

## <a name="run-your-app-as-a-linux-service-with-systemd"></a>使用 systemd 将应用作为 Linux 服务运行

若要将 ASP.NET Core 应用程序配置为以 Linux 服务（或 Linux 行话中的*后台*程序）运行，请从 NuGet 安装[Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd)包。 然后，将 `UseSystemd` 对的调用添加到 `Program.cs`中的 `CreateHostBuilder` 方法。

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
> 如果应用程序未作为 Linux 服务运行，则 `UseSystemd` 方法不执行任何操作。

现在，通过右键单击项目，然后从上下文菜单中选择 "*发布*"，或者使用以下命令从 .NET Core CLI 中发布应用程序（依赖于框架的应用程序或独立的 Linux 运行时独立的应用程序，例如 `linux-x64`）。

```console
dotnet publish -c Release -r linux-x64 -o ./publish
```

将 `publish` 目录的完整内容复制到 Linux 主机上的安装文件夹中。 注册服务需要将一个称为 "unit file" 的特殊文件添加到 `/etc/systemd/system` 目录。 你需要 root 权限才能在此文件夹中创建文件。 使用需要 `systemd` 要使用的标识符和 `.service` 扩展名来命名该文件。 例如 `/etc/systemd/system/myapp.service`。

服务文件使用 INI 格式，如本示例中所示。

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

`Type=notify` 属性告知 `systemd` 应用程序在启动和关闭时将通知该应用程序。 `WantedBy=multi-user.target` 设置将导致在 Linux 系统达到 "运行级别 2" 时启动服务，这意味着非图形多用户 shell 处于活动状态。

在 `systemd` 将识别该服务之前，需要重新加载其配置。 使用 `systemctl` 命令控制 `systemd`。 重新加载后，请使用 `status` 子命令确认已成功注册应用程序。

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

如果已正确配置服务，将显示以下输出：

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

使用 `start` 命令来启动该服务。

```console
sudo systemctl start myapp.service
```

> [!TIP]
> 使用 `systemctl start`时，`.service` 扩展名是可选的。

若要告诉 `systemd` 在系统启动时自动启动该服务，请使用 `enable` 命令。

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a>登录到 journald

Windows 事件日志的 Linux 等效项 `journald`是 `systemd`的一部分的结构化日志系统服务。 由 Linux 后台程序写入标准输出的日志消息将自动写入到 `journald`，因此，若要配置日志记录级别，请使用日志记录配置的 `Console` 部分。 `UseSystemd` 主机生成器方法自动配置控制台输出格式以适合日志。

由于 `journald` 是 Linux 日志的标准，因此有多种与之集成的工具，可以轻松地将日志从 `journald` 路由到外部日志记录系统。 在本地运行的主机上，你可以使用 `journalctl` 命令从命令行中查看日志。

```console
sudo journalctl -u myapp
```

> [!TIP]
> 如果主机上有可用的 GUI 环境，则可以使用一些图形日志查看器，如*QJournalctl*和*gnome 日志*。

若要详细了解如何在 `journalctl`的命令行中查询 systemd 日志，请参阅[手册页](https://manpages.debian.org/buster/systemd/journalctl.1)。

## <a name="https-certificates-for-self-hosted-applications"></a>用于自承载应用程序的 HTTPS 证书

在生产环境中运行 gRPC 应用程序时，应使用来自受信任的证书颁发机构（CA）的 TLS 证书。 此 CA 可以是公共 CA，也可以是组织的内部 ca。

在 Windows 主机上，可以使用 <xref:System.Security.Cryptography.X509Certificates.X509Store> 类从安全的[证书存储区](/windows/win32/seccrypto/managing-certificates-with-certificate-stores)中加载证书。 `X509Store` 类还可与某些 Linux 主机上的 OpenSSL 密钥存储一起使用。

还可以使用[X509Certificate2 构造函数](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0)之一创建证书，无论是从文件（例如，受强密码保护的 `.pfx` 文件），还是从安全存储服务（如[Azure Key Vault](https://azure.microsoft.com/services/key-vault/)）检索到的二进制数据。

可以通过两种方式将 Kestrel 配置为使用证书：通过配置或代码。

### <a name="set-https-certificates-using-configuration"></a>使用配置设置 HTTPS 证书

配置方法要求在 Kestrel 配置节中设置证书的路径 `.pfx` 文件和密码。 在 `appsettings.json` 中，将如下所示。

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

应使用安全配置源（如 Azure KeyVault 或 Hashicorp 保管库）提供密码。

不应在配置文件中存储未加密的密码。

### <a name="set-https-certificates-in-code"></a>在代码中设置 HTTPS 证书

若要在代码中的 Kestrel 上配置 HTTPS，请使用 `Program` 类中 `IWebHostBuilder` 的 `ConfigureKestrel` 方法。

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

同样，`.pfx` 文件的密码应存储在安全配置源中并从该文件中检索。

>[!div class="step-by-step"]
>[上一页](grpc-in-production.md)
>[下一页](docker.md)
