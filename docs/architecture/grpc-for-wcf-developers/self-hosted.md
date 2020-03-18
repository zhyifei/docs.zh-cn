---
title: 自托管 gRPC 应用程序 - 适用于 WCF 开发人员的 gRPC
description: 将 ASP.NET核心 gRPC 应用程序部署为自托管服务。
ms.date: 09/02/2019
ms.openlocfilehash: 00fb1453e19a02469f80af79672e0c1f72c7280f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147797"
---
# <a name="self-hosted-grpc-applications"></a>自托管 gRPC 应用程序

尽管 ASP.NET Core 3.0 应用程序可以在 Windows 服务器上的 IIS 中托管，但当前无法在 IIS 中托管 gRPC 应用程序，因为某些 HTTP/2 功能不受支持。 此功能是将来更新到 Windows 服务器的目标。

您可以将应用程序作为 Windows 服务运行。 或者，由于 .NET Core 3.0 托管扩展中的新功能，您可以将它作为由[系统控制的](https://en.wikipedia.org/wiki/Systemd)Linux 服务运行。

## <a name="run-your-app-as-a-windows-service"></a>将应用作为 Windows 服务运行

要将ASP.NET核心应用程序配置为 Windows 服务运行，请安装来自 NuGet 的[Microsoft.扩展.托管.Windows服务](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices)包。 然后向`UseWindowsService`中`CreateHostBuilder``Program.cs`的方法添加调用。

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
> 如果应用程序未作为 Windows 服务运行，则`UseWindowsService`该方法不执行任何操作。

现在使用以下方法之一发布应用程序：

* 通过右键单击项目并在快捷菜单上选择 **"发布"，** 从可视化工作室开始。
* 从 .NET 核心 CLI。

发布 .NET Core 应用程序时，可以选择创建*与框架相关的*部署或*自包含*部署。 与框架相关的部署要求在运行它们的主机上安装 .NET Core 共享运行时。 自包含部署使用 .NET Core 运行时和框架的完整副本发布，可在任何主机上运行。 有关详细信息（包括每种方法的优缺点），请参阅[.NET Core 应用程序部署](../../core/deploying/index.md)文档。

要发布不需要在主机上安装 .NET Core 3.0 运行时的应用程序的自包含生成，请指定要包含在应用程序中的运行时。 使用`-r`（或`--runtime`） 标志。

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

要发布与框架相关的生成，省略该`-r`标志。

```dotnetcli
dotnet publish -c Release -o ./publish
```

将`publish`目录的完整内容复制到安装文件夹。 然后，使用[sc 工具](/windows/desktop/services/controlling-a-service-using-sc)为可执行文件创建 Windows 服务。

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a>登录到 Windows 事件日志

该方法`UseWindowsService`会自动添加将日志消息写入 Windows 事件日志的[日志记录](/aspnet/core/fundamentals/logging/)提供程序。 您可以通过向 的 分区或其他配置源添加`EventLog`条目来配置`Logging`此提供程序`appsettings.json`的日志记录。

可以通过在这些设置中设置`SourceName`属性来覆盖事件日志中使用的源名称。 如果不指定名称，将使用默认应用程序名称（通常是可执行程序集名称）。

有关日志记录的详细信息，在本章的末尾。

## <a name="run-your-app-as-a-linux-service-with-systemd"></a>使用系统运行应用作为 Linux 服务

要将ASP.NET核心应用程序配置为以 Linux 服务（或 Linux 术语中的*守护进程*）运行，请安装[Microsoft.扩展.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd)程序包（ NuGet）。 然后向`UseSystemd`中`CreateHostBuilder``Program.cs`的方法添加调用。

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
> 如果应用程序未作为 Linux 服务运行，则`UseSystemd`该方法不执行任何操作。

现在发布应用程序。 对于相关的 Linux 运行时（例如，）。`linux-x64`应用程序可以是依赖于框架的，也可以是自包含的。 可以使用以下方法之一进行发布：

* 通过右键单击项目并在快捷菜单上选择 **"发布"，** 从可视化工作室开始。
* 从 .NET 核心 CLI，通过使用以下命令：

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
将`publish`目录的完整内容复制到 Linux 主机上的安装文件夹。 注册服务需要将一个特殊的文件（称为*单元文件*）添加到`/etc/systemd/system`目录中。 您需要根权限才能在此文件夹中创建文件。 使用要使用的`systemd`标识符和扩展名`.service`命名文件。 例如，使用 `/etc/systemd/system/myapp.service`。

服务文件使用 INI 格式，如以下示例所示：

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

该`Type=notify`属性告诉`systemd`应用程序将在启动和关闭时通知它。 当`WantedBy=multi-user.target`Linux 系统达到"运行级别 2"时，该设置将导致服务启动，这意味着非图形多用户外壳处于活动状态。

在`systemd`识别服务之前，它需要重新加载其配置。 您可以使用`systemd`命令`systemctl`进行控制。 重新加载后，`status`使用子命令确认应用程序已成功注册。

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

如果配置的服务正确，您将获得以下输出：

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

使用`start`命令启动服务。

```console
sudo systemctl start myapp.service
```

> [!TIP]
> 使用`.service``systemctl start`时，扩展是可选的。

要告诉`systemd`在系统启动时自动启动服务，请使用 命令`enable`。

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a>日志

与 Windows 事件日志等效的`journald`Linux 是 ，是 中的`systemd`结构化日志记录系统服务。 Linux 守护进程写入标准输出的日志消息将自动写入`journald`。 要配置日志记录级别，`Console`请使用日志记录配置的部分。 主机`UseSystemd`生成器方法自动配置控制台输出格式以适应日志。

因为它是`journald`Linux 日志的标准，因此各种工具都集成在一起。 您可以轻松地将日志从`journald`外部日志记录系统路由到外部日志记录系统。 在主机的本地工作，可以使用 命令`journalctl`查看命令行中的日志。

```console
sudo journalctl -u myapp
```

> [!TIP]
> 如果您的主机上有可用的 GUI 环境，则一些图形日志查看器可用于 Linux，例如*QJournalctl*和*gnome 日志*。

要了解有关使用`journalctl`从 命令`systemd`行查询日志的更多内容，请参阅[man 页](https://manpages.debian.org/buster/systemd/journalctl.1)。

## <a name="https-certificates-for-self-hosted-applications"></a>用于自托管应用程序的 HTTPS 证书

在生产中运行 gRPC 应用程序时，应使用来自受信任的证书颁发机构 （CA） 的 TLS 证书。 此 CA 可能是公共 CA，也可以是组织的内部 CA。

在 Windows 主机上，可以使用<xref:System.Security.Cryptography.X509Certificates.X509Store>类从安全[证书存储加载](/windows/win32/seccrypto/managing-certificates-with-certificate-stores)证书。 您还可以在某些 Linux`X509Store`主机上将该类与 OpenSSL 密钥存储一起使用。

还可以通过使用[X509 证书2构造函数](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)之一从以下任一创建证书：

* 文件，`.pfx`如受强密码保护的文件
* 从安全存储服务（如[Azure 密钥保管库](https://azure.microsoft.com/services/key-vault/)）检索的二进制数据

您可以将 Kestrel 配置为以两种方式使用证书：从配置或代码中。

### <a name="set-https-certificates-by-using-configuration"></a>使用配置设置 HTTPS 证书

配置方法要求在 Kestrel 配置部分`.pfx`中设置证书文件和密码的路径。 在`appsettings.json`中，如下所示：

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

通过使用安全配置源（如 Azure 密钥保管库或 Hashicorp 保管库）提供密码。

> [!IMPORTANT]
> 不要在配置文件中存储未加密的密码。

### <a name="set-https-certificates-in-code"></a>在代码中设置 HTTPS 证书

要在代码中配置 Kestrel 上的`ConfigureKestrel`HTTPS，`IWebHostBuilder`请使用`Program`类 中 的方法。

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

同样，请确保将`.pfx`文件的密码存储在安全配置源中并从中检索。

>[!div class="step-by-step"]
>[上一个](grpc-in-production.md)
>[下一个](docker.md)
