---
title: dotnet-install 脚本
description: 了解用于安装 .NET Core CLI 工具和共享运行时的 dotnet-install 脚本。
ms.date: 11/15/2018
ms.openlocfilehash: 0f565fee3e4ff4bec65bd196f635e9e9601485c2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148311"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="606c2-103">dotnet-install 脚本引用</span><span class="sxs-lookup"><span data-stu-id="606c2-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="606c2-104">name</span><span class="sxs-lookup"><span data-stu-id="606c2-104">Name</span></span>

<span data-ttu-id="606c2-105">`dotnet-install.ps1` | `dotnet-install.sh` - 用于安装 .NET Core CLI 工具和共享运行时的脚本。</span><span class="sxs-lookup"><span data-stu-id="606c2-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="606c2-106">摘要</span><span class="sxs-lookup"><span data-stu-id="606c2-106">Synopsis</span></span>

<span data-ttu-id="606c2-107">Windows：</span><span class="sxs-lookup"><span data-stu-id="606c2-107">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential] [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]`

<span data-ttu-id="606c2-108">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="606c2-108">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential] [--runtime-id] [--skip-non-versioned-files] [--help]`

## <a name="description"></a><span data-ttu-id="606c2-109">说明</span><span class="sxs-lookup"><span data-stu-id="606c2-109">Description</span></span>

<span data-ttu-id="606c2-110">`dotnet-install` 脚本用于执行 .NET Core SDK 的非管理员安装，其中包含 .NET Core CLI 工具和共享运行时。</span><span class="sxs-lookup"><span data-stu-id="606c2-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="606c2-111">建议使用在 [.NET Core 主网站](https://dot.net)上托管的稳定版本。</span><span class="sxs-lookup"><span data-stu-id="606c2-111">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="606c2-112">脚本的直接路径为：</span><span class="sxs-lookup"><span data-stu-id="606c2-112">The direct paths to the scripts are:</span></span>

* <span data-ttu-id="606c2-113"><https://dot.net/v1/dotnet-install.sh>（bash、UNIX）</span><span class="sxs-lookup"><span data-stu-id="606c2-113"><https://dot.net/v1/dotnet-install.sh> (bash, UNIX)</span></span>
* <span data-ttu-id="606c2-114"><https://dot.net/v1/dotnet-install.ps1>（Powershell、Windows）</span><span class="sxs-lookup"><span data-stu-id="606c2-114"><https://dot.net/v1/dotnet-install.ps1> (Powershell, Windows)</span></span>

<span data-ttu-id="606c2-115">这些脚本主要用于自动化方案和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="606c2-115">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="606c2-116">有两个脚本：一个是适用于在 Windows 上工作的 PowerShell 脚本，另一个是在 Linux/macOS 上工作的 bash 脚本。</span><span class="sxs-lookup"><span data-stu-id="606c2-116">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="606c2-117">这两个脚本的行为相同。</span><span class="sxs-lookup"><span data-stu-id="606c2-117">Both scripts have the same behavior.</span></span> <span data-ttu-id="606c2-118">bash 脚本也读取 PowerShell 开关。因此，可以在 Linux/macOS 系统上将 PowerShell 开关与脚本结合使用。</span><span class="sxs-lookup"><span data-stu-id="606c2-118">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="606c2-119">安装脚本从 CLI 生成放置下载 ZIP/tarball 文件，并将其安装在默认位置或 `-InstallDir|--install-dir` 所指定的位置。</span><span class="sxs-lookup"><span data-stu-id="606c2-119">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="606c2-120">默认情况下，安装脚本下载 SDK 并安装它。</span><span class="sxs-lookup"><span data-stu-id="606c2-120">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="606c2-121">如果只想获取共享的运行时，请指定 `--shared-runtime` 参数。</span><span class="sxs-lookup"><span data-stu-id="606c2-121">If you wish to only obtain the shared runtime, specify the `--shared-runtime` argument.</span></span>

<span data-ttu-id="606c2-122">默认情况下，该脚本会将安装位置添加到当前会话的 $PATH。</span><span class="sxs-lookup"><span data-stu-id="606c2-122">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="606c2-123">通过指定 `--no-path` 参数覆盖此默认行为。</span><span class="sxs-lookup"><span data-stu-id="606c2-123">Override this default behavior by specifying the `--no-path` argument.</span></span>

<span data-ttu-id="606c2-124">运行脚本前，请安装所需的[依赖项](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)。</span><span class="sxs-lookup"><span data-stu-id="606c2-124">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="606c2-125">可以使用 `--version` 参数安装特定版本。</span><span class="sxs-lookup"><span data-stu-id="606c2-125">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="606c2-126">必须将该版本指定为一个 3 部分构成的版本（例如，1.0.0-13232）。</span><span class="sxs-lookup"><span data-stu-id="606c2-126">The version must be specified as a three-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="606c2-127">如果未提供，则使用 `latest` 版本。</span><span class="sxs-lookup"><span data-stu-id="606c2-127">If not provided, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="606c2-128">选项</span><span class="sxs-lookup"><span data-stu-id="606c2-128">Options</span></span>

* **`-Channel <CHANNEL>`**

  <span data-ttu-id="606c2-129">指定安装的源通道。</span><span class="sxs-lookup"><span data-stu-id="606c2-129">Specifies the source channel for the installation.</span></span> <span data-ttu-id="606c2-130">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="606c2-130">The possible values are:</span></span>

  * <span data-ttu-id="606c2-131">`Current` - 最新版本。</span><span class="sxs-lookup"><span data-stu-id="606c2-131">`Current` - Most current release.</span></span>
  * <span data-ttu-id="606c2-132">`LTS` - 长期支持频道（最新受支持版本）。</span><span class="sxs-lookup"><span data-stu-id="606c2-132">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  * <span data-ttu-id="606c2-133">表示特定版本的由两部分构成的 X.Y 格式的版本（例如 `2.0` 或 `1.0`）。</span><span class="sxs-lookup"><span data-stu-id="606c2-133">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`).</span></span>
  * <span data-ttu-id="606c2-134">分支名称。</span><span class="sxs-lookup"><span data-stu-id="606c2-134">Branch name.</span></span> <span data-ttu-id="606c2-135">例如，`release/2.0.0`、`release/2.0.0-preview2` 或 `master`（适用于每日测试版本）。</span><span class="sxs-lookup"><span data-stu-id="606c2-135">For example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` (for nightly releases).</span></span>

  <span data-ttu-id="606c2-136">默认值为 `LTS`。</span><span class="sxs-lookup"><span data-stu-id="606c2-136">The default value is `LTS`.</span></span> <span data-ttu-id="606c2-137">有关 .NET 支持频道的详细信息，请参阅 [.NET 支持策略](https://www.microsoft.com/net/platform/support-policy#dotnet-core)页。</span><span class="sxs-lookup"><span data-stu-id="606c2-137">For more information on .NET support channels, see the [.NET Support Policy](https://www.microsoft.com/net/platform/support-policy#dotnet-core) page.</span></span>

* **`-Version <VERSION>`**

  <span data-ttu-id="606c2-138">表示特定的内部版本。</span><span class="sxs-lookup"><span data-stu-id="606c2-138">Represents a specific build version.</span></span> <span data-ttu-id="606c2-139">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="606c2-139">The possible values are:</span></span>

  * <span data-ttu-id="606c2-140">`latest` - 频道上的最新内部版本（与 `-Channel` 选项结合使用）。</span><span class="sxs-lookup"><span data-stu-id="606c2-140">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  * <span data-ttu-id="606c2-141">`coherent` - 频道上的最新相干内部版本；使用最新的稳定包组合（与分支名称 `-Channel` 选项结合使用）。</span><span class="sxs-lookup"><span data-stu-id="606c2-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  * <span data-ttu-id="606c2-142">由三部分组成的版本，采用 X.Y.Z 格式，表示特定的内部版本；取代 `-Channel` 选项。</span><span class="sxs-lookup"><span data-stu-id="606c2-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="606c2-143">例如：`2.0.0-preview2-006120`。</span><span class="sxs-lookup"><span data-stu-id="606c2-143">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="606c2-144">如果没有指定，`-Version` 默认值为 `latest`。</span><span class="sxs-lookup"><span data-stu-id="606c2-144">If not specified, `-Version` defaults to `latest`.</span></span>

* **`-InstallDir <DIRECTORY>`**

  <span data-ttu-id="606c2-145">指定安装路径。</span><span class="sxs-lookup"><span data-stu-id="606c2-145">Specifies the installation path.</span></span> <span data-ttu-id="606c2-146">如果不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="606c2-146">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="606c2-147">默认值为 *%LocalAppData%\Microsoft\dotnet*。</span><span class="sxs-lookup"><span data-stu-id="606c2-147">The default value is *%LocalAppData%\Microsoft\dotnet*.</span></span> <span data-ttu-id="606c2-148">会将二进制文件直接放入目录中。</span><span class="sxs-lookup"><span data-stu-id="606c2-148">Binaries are placed directly in this directory.</span></span>

* **`-Architecture <ARCHITECTURE>`**

  <span data-ttu-id="606c2-149">要安装的 .NET Core 二进制文件的体系结构。</span><span class="sxs-lookup"><span data-stu-id="606c2-149">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="606c2-150">可能的值包括 `auto`、`x64` 和 `x86`。</span><span class="sxs-lookup"><span data-stu-id="606c2-150">Possible values are `auto`, `x64`, and `x86`.</span></span> <span data-ttu-id="606c2-151">默认值为 `auto`，它表示当前正在运行的操作系统体系结构。</span><span class="sxs-lookup"><span data-stu-id="606c2-151">The default value is `auto`, which represents the currently running OS architecture.</span></span>

* **`-SharedRuntime`**

  > [!NOTE]
  > <span data-ttu-id="606c2-152">此参数已过时，可能会在将来版本的脚本中删除。</span><span class="sxs-lookup"><span data-stu-id="606c2-152">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="606c2-153">建议的替代项为 `Runtime` 选项。</span><span class="sxs-lookup"><span data-stu-id="606c2-153">The recommended alternative is the `Runtime` option.</span></span>

  <span data-ttu-id="606c2-154">仅安装共享运行时位，而非整个 SDK。</span><span class="sxs-lookup"><span data-stu-id="606c2-154">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="606c2-155">这等效于指定 `-Runtime dotnet`。</span><span class="sxs-lookup"><span data-stu-id="606c2-155">This is equivalent to specifying `-Runtime dotnet`.</span></span>

* **`-Runtime <RUNTIME>`**

  <span data-ttu-id="606c2-156">仅安装共享运行时，而非整个 SDK。</span><span class="sxs-lookup"><span data-stu-id="606c2-156">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="606c2-157">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="606c2-157">The possible values are:</span></span>

  * <span data-ttu-id="606c2-158">`dotnet` - `Microsoft.NETCore.App` 共享运行时。</span><span class="sxs-lookup"><span data-stu-id="606c2-158">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  * <span data-ttu-id="606c2-159">`aspnetcore` - `Microsoft.AspNetCore.App` 共享运行时。</span><span class="sxs-lookup"><span data-stu-id="606c2-159">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>

* **`-DryRun`**

  <span data-ttu-id="606c2-160">如果设置，脚本将不会执行安装。</span><span class="sxs-lookup"><span data-stu-id="606c2-160">If set, the script won't perform the installation.</span></span> <span data-ttu-id="606c2-161">而会显示要使用哪个命令行来持续安装当前请求的 .NET Core CLI 版本。</span><span class="sxs-lookup"><span data-stu-id="606c2-161">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="606c2-162">例如，如果指定版本 `latest`，它将显示特定版本的链接，以便可在生成脚本中明确地使用此命令。</span><span class="sxs-lookup"><span data-stu-id="606c2-162">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="606c2-163">如果想要自行安装或下载，它还会显示二进制文件位置。</span><span class="sxs-lookup"><span data-stu-id="606c2-163">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

* **`-NoPath`**

  <span data-ttu-id="606c2-164">如果设定，不会将安装文件夹导出到当前会话的路径。</span><span class="sxs-lookup"><span data-stu-id="606c2-164">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="606c2-165">默认情况下，该脚本会修改 PATH，这会使 CLI 工具在安装后立即可用。</span><span class="sxs-lookup"><span data-stu-id="606c2-165">By default, the script modifies the PATH, which makes the CLI tools available immediately after install.</span></span>

* **`-Verbose`**

  <span data-ttu-id="606c2-166">显示诊断信息。</span><span class="sxs-lookup"><span data-stu-id="606c2-166">Displays diagnostics information.</span></span>

* **`-AzureFeed`**

  <span data-ttu-id="606c2-167">指定此安装程序的 Azure 源的 URL。</span><span class="sxs-lookup"><span data-stu-id="606c2-167">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="606c2-168">建议不要更改该值。</span><span class="sxs-lookup"><span data-stu-id="606c2-168">We recommended that you don't change this value.</span></span> <span data-ttu-id="606c2-169">默认值为 `https://dotnetcli.azureedge.net/dotnet`。</span><span class="sxs-lookup"><span data-stu-id="606c2-169">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

* **`-UncachedFeed`**

  <span data-ttu-id="606c2-170">允许更改此安装程序使用的未缓存源的 URL。</span><span class="sxs-lookup"><span data-stu-id="606c2-170">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="606c2-171">建议不要更改该值。</span><span class="sxs-lookup"><span data-stu-id="606c2-171">We recommended that you don't change this value.</span></span>

* **`-NoCdn`**

  <span data-ttu-id="606c2-172">禁止从 [Azure 内容分发网络 (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) 进行下载，并直接使用未缓存源。</span><span class="sxs-lookup"><span data-stu-id="606c2-172">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

* **`-FeedCredential`**

  <span data-ttu-id="606c2-173">用作追加到 Azure 源的查询字符串。</span><span class="sxs-lookup"><span data-stu-id="606c2-173">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="606c2-174">这允许更改 URL 以使用非公共 blob 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="606c2-174">It allows changing the URL to use non-public blob storage accounts.</span></span>

* **`-ProxyAddress`**

  <span data-ttu-id="606c2-175">如果设置，安装程序发出 Web 请求时将使用该代理。</span><span class="sxs-lookup"><span data-stu-id="606c2-175">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="606c2-176">（仅对 Windows 有效）</span><span class="sxs-lookup"><span data-stu-id="606c2-176">(Only valid for Windows)</span></span>

* **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="606c2-177">如果设置，在使用代理地址时，安装程序会使用当前用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="606c2-177">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="606c2-178">（仅对 Windows 有效）</span><span class="sxs-lookup"><span data-stu-id="606c2-178">(Only valid for Windows)</span></span>

* **`-SkipNonVersionedFiles`**

  <span data-ttu-id="606c2-179">跳过安装未添加版本的文件，例如 dotnet.exe（如果它们已经存在）。</span><span class="sxs-lookup"><span data-stu-id="606c2-179">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

* **`-Help`**

  <span data-ttu-id="606c2-180">打印脚本帮助。</span><span class="sxs-lookup"><span data-stu-id="606c2-180">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="606c2-181">示例</span><span class="sxs-lookup"><span data-stu-id="606c2-181">Examples</span></span>

* <span data-ttu-id="606c2-182">将最新的长期支持 (LTS) 版本安装到默认位置：</span><span class="sxs-lookup"><span data-stu-id="606c2-182">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="606c2-183">Windows：</span><span class="sxs-lookup"><span data-stu-id="606c2-183">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="606c2-184">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="606c2-184">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

* <span data-ttu-id="606c2-185">将 2.0 频道中的最新版本安装到指定位置：</span><span class="sxs-lookup"><span data-stu-id="606c2-185">Install the latest version from 2.0 channel to the specified location:</span></span>

  <span data-ttu-id="606c2-186">Windows：</span><span class="sxs-lookup"><span data-stu-id="606c2-186">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli
  ```

  <span data-ttu-id="606c2-187">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="606c2-187">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 2.0 --install-dir ~/cli
  ```

* <span data-ttu-id="606c2-188">安装 1.1.0 版共享运行时：</span><span class="sxs-lookup"><span data-stu-id="606c2-188">Install the 1.1.0 version of the shared runtime:</span></span>

  <span data-ttu-id="606c2-189">Windows：</span><span class="sxs-lookup"><span data-stu-id="606c2-189">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -SharedRuntime -Version 1.1.0
  ```

  <span data-ttu-id="606c2-190">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="606c2-190">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --shared-runtime --version 1.1.0
  ```

* <span data-ttu-id="606c2-191">获取脚本并在公司代理后面安装 2.1.2 版本（仅限 Windows）：</span><span class="sxs-lookup"><span data-stu-id="606c2-191">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

* <span data-ttu-id="606c2-192">获取脚本并安装 .NET Core CLI 单行式命令示例：</span><span class="sxs-lookup"><span data-stu-id="606c2-192">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="606c2-193">Windows：</span><span class="sxs-lookup"><span data-stu-id="606c2-193">Windows:</span></span>

  ```powershell
  @powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -useb 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="606c2-194">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="606c2-194">macOS/Linux:</span></span>

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="606c2-195">请参阅</span><span class="sxs-lookup"><span data-stu-id="606c2-195">See also</span></span>

* [<span data-ttu-id="606c2-196">.NET Core 版本</span><span class="sxs-lookup"><span data-stu-id="606c2-196">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
* [<span data-ttu-id="606c2-197">.NET Core 运行时和 SDK 下载存档</span><span class="sxs-lookup"><span data-stu-id="606c2-197">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
