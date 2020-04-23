---
title: dotnet-install 脚本
description: 了解用于安装 .NET Core SDK 和共享运行时的 dotnet-install 脚本。
ms.date: 01/23/2020
ms.openlocfilehash: 591413a17db577560bd0324995066c8ea7a35895
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463680"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="138c6-103">dotnet-install 脚本引用</span><span class="sxs-lookup"><span data-stu-id="138c6-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="138c6-104">“属性”</span><span class="sxs-lookup"><span data-stu-id="138c6-104">Name</span></span>

<span data-ttu-id="138c6-105">`dotnet-install.ps1` | `dotnet-install.sh` - 用于安装 .NET Core SDK 和共享运行时的脚本。</span><span class="sxs-lookup"><span data-stu-id="138c6-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="138c6-106">摘要</span><span class="sxs-lookup"><span data-stu-id="138c6-106">Synopsis</span></span>

<span data-ttu-id="138c6-107">Windows：</span><span class="sxs-lookup"><span data-stu-id="138c6-107">Windows:</span></span>

```powershell
dotnet-install.ps1 [-Architecture <ARCHITECTURE>] [-AzureFeed]
    [-Channel <CHANNEL>] [-DryRun] [-FeedCredential]
    [-InstallDir <DIRECTORY>] [-JSonFile <JSONFILE>]
    [-NoCdn] [-NoPath] [-ProxyAddress]
    [-ProxyUseDefaultCredentials] [-Runtime <RUNTIME>]
    [-SkipNonVersionedFiles] [-UncachedFeed] [-Verbose]
    [-Version <VERSION>]

dotnet-install.ps1 -Help
```

<span data-ttu-id="138c6-108">Linux/macOS：</span><span class="sxs-lookup"><span data-stu-id="138c6-108">Linux/macOs:</span></span>

```bash
dotnet-install.sh  [--architecture <ARCHITECTURE>] [--azure-feed]
    [--channel <CHANNEL>] [--dry-run] [--feed-credential]
    [--install-dir <DIRECTORY>] [--jsonfile <JSONFILE>]
    [--no-cdn] [--no-path] [--runtime <RUNTIME>] [--runtime-id <RID>]
    [--skip-non-versioned-files] [--uncached-feed] [--verbose]
    [--version <VERSION>]

dotnet-install.sh --help
```

## <a name="description"></a><span data-ttu-id="138c6-109">描述</span><span class="sxs-lookup"><span data-stu-id="138c6-109">Description</span></span>

<span data-ttu-id="138c6-110">`dotnet-install` 脚本用于执行 .NET Core SDK 的非管理员安装，其中包含 .NET Core CLI 和共享运行时。</span><span class="sxs-lookup"><span data-stu-id="138c6-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI and the shared runtime.</span></span>

<span data-ttu-id="138c6-111">建议使用脚本的稳定版本：</span><span class="sxs-lookup"><span data-stu-id="138c6-111">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="138c6-112">Bash (Linux/macOS)：<https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="138c6-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="138c6-113">PowerShell (Windows)：<https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="138c6-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

<span data-ttu-id="138c6-114">这些脚本主要用于自动化方案和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="138c6-114">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="138c6-115">有两个脚本：一个是适用于在 Windows 上工作的 PowerShell 脚本，另一个是在 Linux/macOS 上工作的 bash 脚本。</span><span class="sxs-lookup"><span data-stu-id="138c6-115">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="138c6-116">这两个脚本的行为相同。</span><span class="sxs-lookup"><span data-stu-id="138c6-116">Both scripts have the same behavior.</span></span> <span data-ttu-id="138c6-117">bash 脚本也读取 PowerShell 开关。因此，可以在 Linux/macOS 系统上将 PowerShell 开关与脚本结合使用。</span><span class="sxs-lookup"><span data-stu-id="138c6-117">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="138c6-118">安装脚本从 CLI 生成放置下载 ZIP/tarball 文件，并将其安装在默认位置或 `-InstallDir|--install-dir` 所指定的位置。</span><span class="sxs-lookup"><span data-stu-id="138c6-118">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="138c6-119">默认情况下，安装脚本下载 SDK 并安装它。</span><span class="sxs-lookup"><span data-stu-id="138c6-119">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="138c6-120">如果只想获取共享的运行时，请指定 `-Runtime|--runtime` 参数。</span><span class="sxs-lookup"><span data-stu-id="138c6-120">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="138c6-121">默认情况下，该脚本会将安装位置添加到当前会话的 $PATH。</span><span class="sxs-lookup"><span data-stu-id="138c6-121">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="138c6-122">通过指定 `-NoPath|--no-path` 参数覆盖此默认行为。</span><span class="sxs-lookup"><span data-stu-id="138c6-122">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span>

<span data-ttu-id="138c6-123">运行脚本前，请安装所需的[依赖项](../install/dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="138c6-123">Before running the script, install the required [dependencies](../install/dependencies.md).</span></span>

<span data-ttu-id="138c6-124">可以使用 `-Version|--version` 参数安装特定版本。</span><span class="sxs-lookup"><span data-stu-id="138c6-124">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="138c6-125">必须将版本指定为由 3 部分构成的版本（例如 `2.1.0`）。</span><span class="sxs-lookup"><span data-stu-id="138c6-125">The version must be specified as a three-part version (for example, `2.1.0`).</span></span> <span data-ttu-id="138c6-126">如果未提供，则使用 `latest` 版本。</span><span class="sxs-lookup"><span data-stu-id="138c6-126">If not provided, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="138c6-127">选项</span><span class="sxs-lookup"><span data-stu-id="138c6-127">Options</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="138c6-128">要安装的 .NET Core 二进制文件的体系结构。</span><span class="sxs-lookup"><span data-stu-id="138c6-128">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="138c6-129">可能值为 `<auto>`、`amd64`、`x64`、`x86`、`arm64` 以及 `arm`。</span><span class="sxs-lookup"><span data-stu-id="138c6-129">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="138c6-130">默认值为 `<auto>`，它表示当前正在运行的操作系统体系结构。</span><span class="sxs-lookup"><span data-stu-id="138c6-130">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="138c6-131">指定此安装程序的 Azure 源的 URL。</span><span class="sxs-lookup"><span data-stu-id="138c6-131">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="138c6-132">建议不要更改该值。</span><span class="sxs-lookup"><span data-stu-id="138c6-132">We recommended that you don't change this value.</span></span> <span data-ttu-id="138c6-133">默认值为 `https://dotnetcli.azureedge.net/dotnet`。</span><span class="sxs-lookup"><span data-stu-id="138c6-133">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="138c6-134">指定安装的源通道。</span><span class="sxs-lookup"><span data-stu-id="138c6-134">Specifies the source channel for the installation.</span></span> <span data-ttu-id="138c6-135">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="138c6-135">The possible values are:</span></span>

  - <span data-ttu-id="138c6-136">`Current` - 最新版本。</span><span class="sxs-lookup"><span data-stu-id="138c6-136">`Current` - Most current release.</span></span>
  - <span data-ttu-id="138c6-137">`LTS` - 长期支持频道（最新受支持版本）。</span><span class="sxs-lookup"><span data-stu-id="138c6-137">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="138c6-138">表示特定版本的由两部分构成的 X.Y 格式的版本（例如 `2.1` 或 `3.0`）。</span><span class="sxs-lookup"><span data-stu-id="138c6-138">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="138c6-139">分支名称：例如 `release/3.1.1xx` 或 `master`（适用于每日测试版本）。</span><span class="sxs-lookup"><span data-stu-id="138c6-139">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="138c6-140">使用此选项可以从预览通道安装版本。</span><span class="sxs-lookup"><span data-stu-id="138c6-140">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="138c6-141">使用[安装程序和二进制文件](https://github.com/dotnet/core-sdk#installers-and-binaries)中列出的通道名称。</span><span class="sxs-lookup"><span data-stu-id="138c6-141">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="138c6-142">默认值为 `LTS`。</span><span class="sxs-lookup"><span data-stu-id="138c6-142">The default value is `LTS`.</span></span> <span data-ttu-id="138c6-143">有关 .NET 支持频道的详细信息，请参阅 [.NET 支持策略](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)页。</span><span class="sxs-lookup"><span data-stu-id="138c6-143">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="138c6-144">如果设置，脚本将不会执行安装。</span><span class="sxs-lookup"><span data-stu-id="138c6-144">If set, the script won't perform the installation.</span></span> <span data-ttu-id="138c6-145">而会显示要使用哪个命令行来持续安装当前请求的 .NET Core CLI 版本。</span><span class="sxs-lookup"><span data-stu-id="138c6-145">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="138c6-146">例如，如果指定版本 `latest`，它将显示特定版本的链接，以便可在生成脚本中明确地使用此命令。</span><span class="sxs-lookup"><span data-stu-id="138c6-146">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="138c6-147">如果想要自行安装或下载，它还会显示二进制文件位置。</span><span class="sxs-lookup"><span data-stu-id="138c6-147">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="138c6-148">用作追加到 Azure 源的查询字符串。</span><span class="sxs-lookup"><span data-stu-id="138c6-148">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="138c6-149">这允许更改 URL 以使用非公共 blob 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="138c6-149">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`-Help|--help`**

  <span data-ttu-id="138c6-150">打印脚本帮助。</span><span class="sxs-lookup"><span data-stu-id="138c6-150">Prints out help for the script.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="138c6-151">指定安装路径。</span><span class="sxs-lookup"><span data-stu-id="138c6-151">Specifies the installation path.</span></span> <span data-ttu-id="138c6-152">如果不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="138c6-152">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="138c6-153">默认值为 *%LocalAppData%\Microsoft\dotnet*。</span><span class="sxs-lookup"><span data-stu-id="138c6-153">The default value is *%LocalAppData%\Microsoft\dotnet*.</span></span> <span data-ttu-id="138c6-154">会将二进制文件直接放入目录中。</span><span class="sxs-lookup"><span data-stu-id="138c6-154">Binaries are placed directly in this directory.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="138c6-155">指定将用于确定 SDK 版本的 [global.json](global-json.md) 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="138c6-155">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="138c6-156">global.json  文件必须具有 `sdk:version` 的值。</span><span class="sxs-lookup"><span data-stu-id="138c6-156">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="138c6-157">禁止从 [Azure 内容分发网络 (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) 进行下载，并直接使用未缓存源。</span><span class="sxs-lookup"><span data-stu-id="138c6-157">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="138c6-158">如果设定，不会将安装文件夹导出到当前会话的路径。</span><span class="sxs-lookup"><span data-stu-id="138c6-158">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="138c6-159">默认情况下，该脚本会修改 PATH，这会使 .NET Core CLI 在安装后立即可用。</span><span class="sxs-lookup"><span data-stu-id="138c6-159">By default, the script modifies the PATH, which makes the .NET Core CLI available immediately after install.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="138c6-160">如果设置，安装程序发出 Web 请求时将使用该代理。</span><span class="sxs-lookup"><span data-stu-id="138c6-160">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="138c6-161">（仅适用于 Windows。）</span><span class="sxs-lookup"><span data-stu-id="138c6-161">(Only valid for Windows.)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="138c6-162">如果设置，在使用代理地址时，安装程序会使用当前用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="138c6-162">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="138c6-163">（仅适用于 Windows。）</span><span class="sxs-lookup"><span data-stu-id="138c6-163">(Only valid for Windows.)</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="138c6-164">仅安装共享运行时，而非整个 SDK。</span><span class="sxs-lookup"><span data-stu-id="138c6-164">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="138c6-165">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="138c6-165">The possible values are:</span></span>

  - <span data-ttu-id="138c6-166">`dotnet` - `Microsoft.NETCore.App` 共享运行时。</span><span class="sxs-lookup"><span data-stu-id="138c6-166">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="138c6-167">`aspnetcore` - `Microsoft.AspNetCore.App` 共享运行时。</span><span class="sxs-lookup"><span data-stu-id="138c6-167">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="138c6-168">`windowsdesktop` - `Microsoft.WindowsDesktop.App` 共享运行时。</span><span class="sxs-lookup"><span data-stu-id="138c6-168">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- **`--runtime-id <RID>`**

  <span data-ttu-id="138c6-169">指定要为其安装工具的[运行时标识符](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="138c6-169">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="138c6-170">使用适用于可移植 Linux 的 `linux-x64`。</span><span class="sxs-lookup"><span data-stu-id="138c6-170">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="138c6-171">（仅适用于 Linux/macOS。）</span><span class="sxs-lookup"><span data-stu-id="138c6-171">(Only valid for Linux/macOS.)</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="138c6-172">此参数已过时，可能会在将来版本的脚本中删除。</span><span class="sxs-lookup"><span data-stu-id="138c6-172">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="138c6-173">建议的替代项为 `-Runtime|--runtime` 选项。</span><span class="sxs-lookup"><span data-stu-id="138c6-173">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="138c6-174">仅安装共享运行时位，而非整个 SDK。</span><span class="sxs-lookup"><span data-stu-id="138c6-174">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="138c6-175">此选项等效于指定 `-Runtime|--runtime dotnet`。</span><span class="sxs-lookup"><span data-stu-id="138c6-175">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="138c6-176">跳过安装未添加版本的文件，例如 dotnet.exe  （如果它们已经存在）。</span><span class="sxs-lookup"><span data-stu-id="138c6-176">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="138c6-177">允许更改此安装程序使用的未缓存源的 URL。</span><span class="sxs-lookup"><span data-stu-id="138c6-177">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="138c6-178">建议不要更改该值。</span><span class="sxs-lookup"><span data-stu-id="138c6-178">We recommended that you don't change this value.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="138c6-179">显示诊断信息。</span><span class="sxs-lookup"><span data-stu-id="138c6-179">Displays diagnostics information.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="138c6-180">表示特定的内部版本。</span><span class="sxs-lookup"><span data-stu-id="138c6-180">Represents a specific build version.</span></span> <span data-ttu-id="138c6-181">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="138c6-181">The possible values are:</span></span>

  - <span data-ttu-id="138c6-182">`latest` - 频道上的最新内部版本（与 `-Channel` 选项结合使用）。</span><span class="sxs-lookup"><span data-stu-id="138c6-182">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="138c6-183">`coherent` - 频道上的最新相干内部版本；使用最新的稳定包组合（与分支名称 `-Channel` 选项结合使用）。</span><span class="sxs-lookup"><span data-stu-id="138c6-183">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="138c6-184">由三部分组成的版本，采用 X.Y.Z 格式，表示特定的内部版本；取代 `-Channel` 选项。</span><span class="sxs-lookup"><span data-stu-id="138c6-184">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="138c6-185">例如：`2.0.0-preview2-006120`。</span><span class="sxs-lookup"><span data-stu-id="138c6-185">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="138c6-186">如果没有指定，`-Version` 默认值为 `latest`。</span><span class="sxs-lookup"><span data-stu-id="138c6-186">If not specified, `-Version` defaults to `latest`.</span></span>

## <a name="examples"></a><span data-ttu-id="138c6-187">示例</span><span class="sxs-lookup"><span data-stu-id="138c6-187">Examples</span></span>

- <span data-ttu-id="138c6-188">将最新的长期支持 (LTS) 版本安装到默认位置：</span><span class="sxs-lookup"><span data-stu-id="138c6-188">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="138c6-189">Windows：</span><span class="sxs-lookup"><span data-stu-id="138c6-189">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="138c6-190">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="138c6-190">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="138c6-191">将 3.1 通道中的最新版本安装到指定位置：</span><span class="sxs-lookup"><span data-stu-id="138c6-191">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="138c6-192">Windows：</span><span class="sxs-lookup"><span data-stu-id="138c6-192">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="138c6-193">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="138c6-193">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="138c6-194">安装 3.0.0 版共享运行时：</span><span class="sxs-lookup"><span data-stu-id="138c6-194">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="138c6-195">Windows：</span><span class="sxs-lookup"><span data-stu-id="138c6-195">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="138c6-196">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="138c6-196">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="138c6-197">获取脚本并在公司代理后面安装 2.1.2 版本（仅限 Windows）：</span><span class="sxs-lookup"><span data-stu-id="138c6-197">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="138c6-198">获取脚本并安装 .NET Core CLI 单行式命令示例：</span><span class="sxs-lookup"><span data-stu-id="138c6-198">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="138c6-199">Windows：</span><span class="sxs-lookup"><span data-stu-id="138c6-199">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="138c6-200">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="138c6-200">macOS/Linux:</span></span>

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="138c6-201">请参阅</span><span class="sxs-lookup"><span data-stu-id="138c6-201">See also</span></span>

- [<span data-ttu-id="138c6-202">.NET Core 版本</span><span class="sxs-lookup"><span data-stu-id="138c6-202">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="138c6-203">.NET Core 运行时和 SDK 下载存档</span><span class="sxs-lookup"><span data-stu-id="138c6-203">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
