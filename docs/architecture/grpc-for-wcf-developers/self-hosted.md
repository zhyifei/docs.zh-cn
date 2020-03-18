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
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="57c90-103">自托管 gRPC 应用程序</span><span class="sxs-lookup"><span data-stu-id="57c90-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="57c90-104">尽管 ASP.NET Core 3.0 应用程序可以在 Windows 服务器上的 IIS 中托管，但当前无法在 IIS 中托管 gRPC 应用程序，因为某些 HTTP/2 功能不受支持。</span><span class="sxs-lookup"><span data-stu-id="57c90-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't supported.</span></span> <span data-ttu-id="57c90-105">此功能是将来更新到 Windows 服务器的目标。</span><span class="sxs-lookup"><span data-stu-id="57c90-105">This functionality is a goal for a future update to Windows Server.</span></span>

<span data-ttu-id="57c90-106">您可以将应用程序作为 Windows 服务运行。</span><span class="sxs-lookup"><span data-stu-id="57c90-106">You can run your application as a Windows service.</span></span> <span data-ttu-id="57c90-107">或者，由于 .NET Core 3.0 托管扩展中的新功能，您可以将它作为由[系统控制的](https://en.wikipedia.org/wiki/Systemd)Linux 服务运行。</span><span class="sxs-lookup"><span data-stu-id="57c90-107">Or you can run it as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), because of new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="57c90-108">将应用作为 Windows 服务运行</span><span class="sxs-lookup"><span data-stu-id="57c90-108">Run your app as a Windows service</span></span>

<span data-ttu-id="57c90-109">要将ASP.NET核心应用程序配置为 Windows 服务运行，请安装来自 NuGet 的[Microsoft.扩展.托管.Windows服务](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices)包。</span><span class="sxs-lookup"><span data-stu-id="57c90-109">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="57c90-110">然后向`UseWindowsService`中`CreateHostBuilder``Program.cs`的方法添加调用。</span><span class="sxs-lookup"><span data-stu-id="57c90-110">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="57c90-111">如果应用程序未作为 Windows 服务运行，则`UseWindowsService`该方法不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="57c90-111">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="57c90-112">现在使用以下方法之一发布应用程序：</span><span class="sxs-lookup"><span data-stu-id="57c90-112">Now publish your application by using one of these methods:</span></span>

* <span data-ttu-id="57c90-113">通过右键单击项目并在快捷菜单上选择 **"发布"，** 从可视化工作室开始。</span><span class="sxs-lookup"><span data-stu-id="57c90-113">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="57c90-114">从 .NET 核心 CLI。</span><span class="sxs-lookup"><span data-stu-id="57c90-114">From the .NET Core CLI.</span></span>

<span data-ttu-id="57c90-115">发布 .NET Core 应用程序时，可以选择创建*与框架相关的*部署或*自包含*部署。</span><span class="sxs-lookup"><span data-stu-id="57c90-115">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="57c90-116">与框架相关的部署要求在运行它们的主机上安装 .NET Core 共享运行时。</span><span class="sxs-lookup"><span data-stu-id="57c90-116">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="57c90-117">自包含部署使用 .NET Core 运行时和框架的完整副本发布，可在任何主机上运行。</span><span class="sxs-lookup"><span data-stu-id="57c90-117">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="57c90-118">有关详细信息（包括每种方法的优缺点），请参阅[.NET Core 应用程序部署](../../core/deploying/index.md)文档。</span><span class="sxs-lookup"><span data-stu-id="57c90-118">For more information, including the advantages and disadvantages of each approach, see the [.NET Core application deployment](../../core/deploying/index.md) documentation.</span></span>

<span data-ttu-id="57c90-119">要发布不需要在主机上安装 .NET Core 3.0 运行时的应用程序的自包含生成，请指定要包含在应用程序中的运行时。</span><span class="sxs-lookup"><span data-stu-id="57c90-119">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application.</span></span> <span data-ttu-id="57c90-120">使用`-r`（或`--runtime`） 标志。</span><span class="sxs-lookup"><span data-stu-id="57c90-120">Use the `-r` (or `--runtime`) flag.</span></span>

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="57c90-121">要发布与框架相关的生成，省略该`-r`标志。</span><span class="sxs-lookup"><span data-stu-id="57c90-121">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```dotnetcli
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="57c90-122">将`publish`目录的完整内容复制到安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="57c90-122">Copy the complete contents of the `publish` directory to an installation folder.</span></span> <span data-ttu-id="57c90-123">然后，使用[sc 工具](/windows/desktop/services/controlling-a-service-using-sc)为可执行文件创建 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="57c90-123">Then, use the [sc tool](/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable file.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a><span data-ttu-id="57c90-124">登录到 Windows 事件日志</span><span class="sxs-lookup"><span data-stu-id="57c90-124">Log to the Windows event log</span></span>

<span data-ttu-id="57c90-125">该方法`UseWindowsService`会自动添加将日志消息写入 Windows 事件日志的[日志记录](/aspnet/core/fundamentals/logging/)提供程序。</span><span class="sxs-lookup"><span data-stu-id="57c90-125">The `UseWindowsService` method automatically adds a [logging](/aspnet/core/fundamentals/logging/) provider that writes log messages to the Windows event log.</span></span> <span data-ttu-id="57c90-126">您可以通过向 的 分区或其他配置源添加`EventLog`条目来配置`Logging`此提供程序`appsettings.json`的日志记录。</span><span class="sxs-lookup"><span data-stu-id="57c90-126">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or another configuration source.</span></span>

<span data-ttu-id="57c90-127">可以通过在这些设置中设置`SourceName`属性来覆盖事件日志中使用的源名称。</span><span class="sxs-lookup"><span data-stu-id="57c90-127">You can override the source name used in the event log by setting a `SourceName` property in these settings.</span></span> <span data-ttu-id="57c90-128">如果不指定名称，将使用默认应用程序名称（通常是可执行程序集名称）。</span><span class="sxs-lookup"><span data-stu-id="57c90-128">If you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="57c90-129">有关日志记录的详细信息，在本章的末尾。</span><span class="sxs-lookup"><span data-stu-id="57c90-129">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="57c90-130">使用系统运行应用作为 Linux 服务</span><span class="sxs-lookup"><span data-stu-id="57c90-130">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="57c90-131">要将ASP.NET核心应用程序配置为以 Linux 服务（或 Linux 术语中的*守护进程*）运行，请安装[Microsoft.扩展.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd)程序包（ NuGet）。</span><span class="sxs-lookup"><span data-stu-id="57c90-131">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="57c90-132">然后向`UseSystemd`中`CreateHostBuilder``Program.cs`的方法添加调用。</span><span class="sxs-lookup"><span data-stu-id="57c90-132">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="57c90-133">如果应用程序未作为 Linux 服务运行，则`UseSystemd`该方法不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="57c90-133">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="57c90-134">现在发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="57c90-134">Now publish your application.</span></span> <span data-ttu-id="57c90-135">对于相关的 Linux 运行时（例如，）。`linux-x64`应用程序可以是依赖于框架的，也可以是自包含的。</span><span class="sxs-lookup"><span data-stu-id="57c90-135">The application can be either framework dependent or self-contained for the relevant Linux runtime (for example, `linux-x64`).</span></span> <span data-ttu-id="57c90-136">可以使用以下方法之一进行发布：</span><span class="sxs-lookup"><span data-stu-id="57c90-136">You can publish by using one of these methods:</span></span>

* <span data-ttu-id="57c90-137">通过右键单击项目并在快捷菜单上选择 **"发布"，** 从可视化工作室开始。</span><span class="sxs-lookup"><span data-stu-id="57c90-137">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="57c90-138">从 .NET 核心 CLI，通过使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="57c90-138">From the .NET Core CLI, by using the following command:</span></span>

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
<span data-ttu-id="57c90-139">将`publish`目录的完整内容复制到 Linux 主机上的安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="57c90-139">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="57c90-140">注册服务需要将一个特殊的文件（称为*单元文件*）添加到`/etc/systemd/system`目录中。</span><span class="sxs-lookup"><span data-stu-id="57c90-140">Registering the service requires a special file, called a *unit file*, to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="57c90-141">您需要根权限才能在此文件夹中创建文件。</span><span class="sxs-lookup"><span data-stu-id="57c90-141">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="57c90-142">使用要使用的`systemd`标识符和扩展名`.service`命名文件。</span><span class="sxs-lookup"><span data-stu-id="57c90-142">Name the file with the identifier that you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="57c90-143">例如，使用 `/etc/systemd/system/myapp.service`。</span><span class="sxs-lookup"><span data-stu-id="57c90-143">For example, use `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="57c90-144">服务文件使用 INI 格式，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="57c90-144">The service file uses INI format, as shown in this example:</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="57c90-145">该`Type=notify`属性告诉`systemd`应用程序将在启动和关闭时通知它。</span><span class="sxs-lookup"><span data-stu-id="57c90-145">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="57c90-146">当`WantedBy=multi-user.target`Linux 系统达到"运行级别 2"时，该设置将导致服务启动，这意味着非图形多用户外壳处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="57c90-146">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2," which means a non-graphical multi-user shell is active.</span></span>

<span data-ttu-id="57c90-147">在`systemd`识别服务之前，它需要重新加载其配置。</span><span class="sxs-lookup"><span data-stu-id="57c90-147">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="57c90-148">您可以使用`systemd`命令`systemctl`进行控制。</span><span class="sxs-lookup"><span data-stu-id="57c90-148">You control `systemd` by using the `systemctl` command.</span></span> <span data-ttu-id="57c90-149">重新加载后，`status`使用子命令确认应用程序已成功注册。</span><span class="sxs-lookup"><span data-stu-id="57c90-149">After reloading, use the `status` subcommand to confirm that the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="57c90-150">如果配置的服务正确，您将获得以下输出：</span><span class="sxs-lookup"><span data-stu-id="57c90-150">If you've configured the service correctly, you'll get the following output:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="57c90-151">使用`start`命令启动服务。</span><span class="sxs-lookup"><span data-stu-id="57c90-151">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="57c90-152">使用`.service``systemctl start`时，扩展是可选的。</span><span class="sxs-lookup"><span data-stu-id="57c90-152">The `.service` extension is optional when you're using `systemctl start`.</span></span>

<span data-ttu-id="57c90-153">要告诉`systemd`在系统启动时自动启动服务，请使用 命令`enable`。</span><span class="sxs-lookup"><span data-stu-id="57c90-153">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="57c90-154">日志</span><span class="sxs-lookup"><span data-stu-id="57c90-154">Log to journald</span></span>

<span data-ttu-id="57c90-155">与 Windows 事件日志等效的`journald`Linux 是 ，是 中的`systemd`结构化日志记录系统服务。</span><span class="sxs-lookup"><span data-stu-id="57c90-155">The Linux equivalent of the Windows event log is `journald`, a structured logging system service that's part of `systemd`.</span></span> <span data-ttu-id="57c90-156">Linux 守护进程写入标准输出的日志消息将自动写入`journald`。</span><span class="sxs-lookup"><span data-stu-id="57c90-156">Log messages written to the standard output by a Linux daemon are automatically written to `journald`.</span></span> <span data-ttu-id="57c90-157">要配置日志记录级别，`Console`请使用日志记录配置的部分。</span><span class="sxs-lookup"><span data-stu-id="57c90-157">To configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="57c90-158">主机`UseSystemd`生成器方法自动配置控制台输出格式以适应日志。</span><span class="sxs-lookup"><span data-stu-id="57c90-158">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="57c90-159">因为它是`journald`Linux 日志的标准，因此各种工具都集成在一起。</span><span class="sxs-lookup"><span data-stu-id="57c90-159">Because `journald` is the standard for Linux logs, a variety of tools integrate with it.</span></span> <span data-ttu-id="57c90-160">您可以轻松地将日志从`journald`外部日志记录系统路由到外部日志记录系统。</span><span class="sxs-lookup"><span data-stu-id="57c90-160">You can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="57c90-161">在主机的本地工作，可以使用 命令`journalctl`查看命令行中的日志。</span><span class="sxs-lookup"><span data-stu-id="57c90-161">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="57c90-162">如果您的主机上有可用的 GUI 环境，则一些图形日志查看器可用于 Linux，例如*QJournalctl*和*gnome 日志*。</span><span class="sxs-lookup"><span data-stu-id="57c90-162">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="57c90-163">要了解有关使用`journalctl`从 命令`systemd`行查询日志的更多内容，请参阅[man 页](https://manpages.debian.org/buster/systemd/journalctl.1)。</span><span class="sxs-lookup"><span data-stu-id="57c90-163">To learn more about querying the `systemd` journal from the command line by using `journalctl`, see [the man pages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="57c90-164">用于自托管应用程序的 HTTPS 证书</span><span class="sxs-lookup"><span data-stu-id="57c90-164">HTTPS certificates for self-hosted applications</span></span>

<span data-ttu-id="57c90-165">在生产中运行 gRPC 应用程序时，应使用来自受信任的证书颁发机构 （CA） 的 TLS 证书。</span><span class="sxs-lookup"><span data-stu-id="57c90-165">When you're running a gRPC application in production, you should use a TLS certificate from a trusted certificate authority (CA).</span></span> <span data-ttu-id="57c90-166">此 CA 可能是公共 CA，也可以是组织的内部 CA。</span><span class="sxs-lookup"><span data-stu-id="57c90-166">This CA might be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="57c90-167">在 Windows 主机上，可以使用<xref:System.Security.Cryptography.X509Certificates.X509Store>类从安全[证书存储加载](/windows/win32/seccrypto/managing-certificates-with-certificate-stores)证书。</span><span class="sxs-lookup"><span data-stu-id="57c90-167">On Windows hosts, you can load the certificate from a secure [certificate store](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) by using the <xref:System.Security.Cryptography.X509Certificates.X509Store> class.</span></span> <span data-ttu-id="57c90-168">您还可以在某些 Linux`X509Store`主机上将该类与 OpenSSL 密钥存储一起使用。</span><span class="sxs-lookup"><span data-stu-id="57c90-168">You can also use the `X509Store` class with the OpenSSL key store on some Linux hosts.</span></span>

<span data-ttu-id="57c90-169">还可以通过使用[X509 证书2构造函数](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)之一从以下任一创建证书：</span><span class="sxs-lookup"><span data-stu-id="57c90-169">You can also create certificates by using one of the [X509Certificate2 constructors](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), from either:</span></span>

* <span data-ttu-id="57c90-170">文件，`.pfx`如受强密码保护的文件</span><span class="sxs-lookup"><span data-stu-id="57c90-170">A file, such as a `.pfx` file protected by a strong password</span></span>
* <span data-ttu-id="57c90-171">从安全存储服务（如[Azure 密钥保管库](https://azure.microsoft.com/services/key-vault/)）检索的二进制数据</span><span class="sxs-lookup"><span data-stu-id="57c90-171">Binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span></span>

<span data-ttu-id="57c90-172">您可以将 Kestrel 配置为以两种方式使用证书：从配置或代码中。</span><span class="sxs-lookup"><span data-stu-id="57c90-172">You can configure Kestrel to use a certificate in two ways: from configuration or in code.</span></span>

### <a name="set-https-certificates-by-using-configuration"></a><span data-ttu-id="57c90-173">使用配置设置 HTTPS 证书</span><span class="sxs-lookup"><span data-stu-id="57c90-173">Set HTTPS certificates by using configuration</span></span>

<span data-ttu-id="57c90-174">配置方法要求在 Kestrel 配置部分`.pfx`中设置证书文件和密码的路径。</span><span class="sxs-lookup"><span data-stu-id="57c90-174">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="57c90-175">在`appsettings.json`中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="57c90-175">In `appsettings.json`, that would look like this:</span></span>

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

<span data-ttu-id="57c90-176">通过使用安全配置源（如 Azure 密钥保管库或 Hashicorp 保管库）提供密码。</span><span class="sxs-lookup"><span data-stu-id="57c90-176">Provide the password by using a secure configuration source such as Azure Key Vault or Hashicorp Vault.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="57c90-177">不要在配置文件中存储未加密的密码。</span><span class="sxs-lookup"><span data-stu-id="57c90-177">Don't store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="57c90-178">在代码中设置 HTTPS 证书</span><span class="sxs-lookup"><span data-stu-id="57c90-178">Set HTTPS certificates in code</span></span>

<span data-ttu-id="57c90-179">要在代码中配置 Kestrel 上的`ConfigureKestrel`HTTPS，`IWebHostBuilder`请使用`Program`类 中 的方法。</span><span class="sxs-lookup"><span data-stu-id="57c90-179">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

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

<span data-ttu-id="57c90-180">同样，请确保将`.pfx`文件的密码存储在安全配置源中并从中检索。</span><span class="sxs-lookup"><span data-stu-id="57c90-180">Again, be sure to store the password for the `.pfx` file in, and retrieve it from, a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="57c90-181">[上一个](grpc-in-production.md)
>[下一个](docker.md)</span><span class="sxs-lookup"><span data-stu-id="57c90-181">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
