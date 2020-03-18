---
title: dotnet-install 脚本
description: 了解用于安装 .NET Core SDK 和共享运行时的 dotnet-install 脚本。
ms.date: 01/23/2020
ms.openlocfilehash: bf28f872be3ac2b4115b1d5e5c06e32afec0b49e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77092858"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="6aa73-103">dotnet-install 脚本引用</span><span class="sxs-lookup"><span data-stu-id="6aa73-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="6aa73-104">名称</span><span class="sxs-lookup"><span data-stu-id="6aa73-104">Name</span></span>

<span data-ttu-id="6aa73-105">`dotnet-install.ps1` | `dotnet-install.sh` - 用于安装 .NET Core SDK 和共享运行时的脚本。</span><span class="sxs-lookup"><span data-stu-id="6aa73-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6aa73-106">摘要</span><span class="sxs-lookup"><span data-stu-id="6aa73-106">Synopsis</span></span>

<span data-ttu-id="6aa73-107">Windows：</span><span class="sxs-lookup"><span data-stu-id="6aa73-107">Windows:</span></span>

```powershell
dotnet-install.ps1 [-Channel] [-Version] [-JSonFile] [-InstallDir] [-Architecture]
    [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential]
    [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]
```

<span data-ttu-id="6aa73-108">Linux/macOS：</span><span class="sxs-lookup"><span data-stu-id="6aa73-108">Linux/macOs:</span></span>

```bash
dotnet-install.sh [--channel] [--version] [--jsonfile] [--install-dir] [--architecture]
    [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential]
    [--runtime-id] [--skip-non-versioned-files] [--help]
```

## <a name="description"></a><span data-ttu-id="6aa73-109">说明</span><span class="sxs-lookup"><span data-stu-id="6aa73-109">Description</span></span>

<span data-ttu-id="6aa73-110">`dotnet-install` 脚本用于执行 .NET Core SDK 的非管理员安装，其中包含 .NET Core CLI 和共享运行时。</span><span class="sxs-lookup"><span data-stu-id="6aa73-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI and the shared runtime.</span></span>

<span data-ttu-id="6aa73-111">建议使用脚本的稳定版本：</span><span class="sxs-lookup"><span data-stu-id="6aa73-111">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="6aa73-112">Bash (Linux/macOS)：<https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="6aa73-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="6aa73-113">PowerShell (Windows)：<https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="6aa73-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

<span data-ttu-id="6aa73-114">这些脚本主要用于自动化方案和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="6aa73-114">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="6aa73-115">有两个脚本：一个是适用于在 Windows 上工作的 PowerShell 脚本，另一个是在 Linux/macOS 上工作的 bash 脚本。</span><span class="sxs-lookup"><span data-stu-id="6aa73-115">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="6aa73-116">这两个脚本的行为相同。</span><span class="sxs-lookup"><span data-stu-id="6aa73-116">Both scripts have the same behavior.</span></span> <span data-ttu-id="6aa73-117">bash 脚本也读取 PowerShell 开关。因此，可以在 Linux/macOS 系统上将 PowerShell 开关与脚本结合使用。</span><span class="sxs-lookup"><span data-stu-id="6aa73-117">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="6aa73-118">安装脚本从 CLI 生成放置下载 ZIP/tarball 文件，并将其安装在默认位置或 `-InstallDir|--install-dir` 所指定的位置。</span><span class="sxs-lookup"><span data-stu-id="6aa73-118">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="6aa73-119">默认情况下，安装脚本下载 SDK 并安装它。</span><span class="sxs-lookup"><span data-stu-id="6aa73-119">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="6aa73-120">如果只想获取共享的运行时，请指定 `-Runtime|--runtime` 参数。</span><span class="sxs-lookup"><span data-stu-id="6aa73-120">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="6aa73-121">默认情况下，该脚本会将安装位置添加到当前会话的 $PATH。</span><span class="sxs-lookup"><span data-stu-id="6aa73-121">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="6aa73-122">通过指定 `-NoPath|--no-path` 参数覆盖此默认行为。</span><span class="sxs-lookup"><span data-stu-id="6aa73-122">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span>

<span data-ttu-id="6aa73-123">运行脚本前，请安装所需的[依赖项](../install/dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="6aa73-123">Before running the script, install the required [dependencies](../install/dependencies.md).</span></span>

<span data-ttu-id="6aa73-124">可以使用 `-Version|--version` 参数安装特定版本。</span><span class="sxs-lookup"><span data-stu-id="6aa73-124">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="6aa73-125">必须将版本指定为由 3 部分构成的版本（例如 `2.1.0`）。</span><span class="sxs-lookup"><span data-stu-id="6aa73-125">The version must be specified as a three-part version (for example, `2.1.0`).</span></span> <span data-ttu-id="6aa73-126">如果未提供，则使用 `latest` 版本。</span><span class="sxs-lookup"><span data-stu-id="6aa73-126">If not provided, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="6aa73-127">选项</span><span class="sxs-lookup"><span data-stu-id="6aa73-127">Options</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="6aa73-128">指定安装的源通道。</span><span class="sxs-lookup"><span data-stu-id="6aa73-128">Specifies the source channel for the installation.</span></span> <span data-ttu-id="6aa73-129">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="6aa73-129">The possible values are:</span></span>

  - <span data-ttu-id="6aa73-130">`Current` - 最新版本。</span><span class="sxs-lookup"><span data-stu-id="6aa73-130">`Current` - Most current release.</span></span>
  - <span data-ttu-id="6aa73-131">`LTS` - 长期支持频道（最新受支持版本）。</span><span class="sxs-lookup"><span data-stu-id="6aa73-131">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="6aa73-132">表示特定版本的由两部分构成的 X.Y 格式的版本（例如 `2.1` 或 `3.0`）。</span><span class="sxs-lookup"><span data-stu-id="6aa73-132">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="6aa73-133">分支名称：例如 `release/3.1.1xx` 或 `master`（适用于每日测试版本）。</span><span class="sxs-lookup"><span data-stu-id="6aa73-133">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="6aa73-134">使用此选项可以从预览通道安装版本。</span><span class="sxs-lookup"><span data-stu-id="6aa73-134">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="6aa73-135">使用[安装程序和二进制文件](https://github.com/dotnet/core-sdk#installers-and-binaries)中列出的通道名称。</span><span class="sxs-lookup"><span data-stu-id="6aa73-135">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="6aa73-136">默认值为 `LTS`。</span><span class="sxs-lookup"><span data-stu-id="6aa73-136">The default value is `LTS`.</span></span> <span data-ttu-id="6aa73-137">有关 .NET 支持频道的详细信息，请参阅 [.NET 支持策略](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)页。</span><span class="sxs-lookup"><span data-stu-id="6aa73-137">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="6aa73-138">表示特定的内部版本。</span><span class="sxs-lookup"><span data-stu-id="6aa73-138">Represents a specific build version.</span></span> <span data-ttu-id="6aa73-139">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="6aa73-139">The possible values are:</span></span>

  - <span data-ttu-id="6aa73-140">`latest` - 频道上的最新内部版本（与 `-Channel` 选项结合使用）。</span><span class="sxs-lookup"><span data-stu-id="6aa73-140">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="6aa73-141">`coherent` - 频道上的最新相干内部版本；使用最新的稳定包组合（与分支名称 `-Channel` 选项结合使用）。</span><span class="sxs-lookup"><span data-stu-id="6aa73-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="6aa73-142">由三部分组成的版本，采用 X.Y.Z 格式，表示特定的内部版本；取代 `-Channel` 选项。</span><span class="sxs-lookup"><span data-stu-id="6aa73-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="6aa73-143">例如：`2.0.0-preview2-006120`。</span><span class="sxs-lookup"><span data-stu-id="6aa73-143">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="6aa73-144">如果没有指定，`-Version` 默认值为 `latest`。</span><span class="sxs-lookup"><span data-stu-id="6aa73-144">If not specified, `-Version` defaults to `latest`.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="6aa73-145">指定将用于确定 SDK 版本的 [global.json](global-json.md) 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="6aa73-145">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="6aa73-146">global.json  文件必须具有 `sdk:version` 的值。</span><span class="sxs-lookup"><span data-stu-id="6aa73-146">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="6aa73-147">指定安装路径。</span><span class="sxs-lookup"><span data-stu-id="6aa73-147">Specifies the installation path.</span></span> <span data-ttu-id="6aa73-148">如果不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="6aa73-148">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="6aa73-149">默认值为 *%LocalAppData%\Microsoft\dotnet*。</span><span class="sxs-lookup"><span data-stu-id="6aa73-149">The default value is *%LocalAppData%\Microsoft\dotnet*.</span></span> <span data-ttu-id="6aa73-150">会将二进制文件直接放入目录中。</span><span class="sxs-lookup"><span data-stu-id="6aa73-150">Binaries are placed directly in this directory.</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="6aa73-151">要安装的 .NET Core 二进制文件的体系结构。</span><span class="sxs-lookup"><span data-stu-id="6aa73-151">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="6aa73-152">可能值为 `<auto>`、`amd64`、`x64`、`x86`、`arm64` 以及 `arm`。</span><span class="sxs-lookup"><span data-stu-id="6aa73-152">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="6aa73-153">默认值为 `<auto>`，它表示当前正在运行的操作系统体系结构。</span><span class="sxs-lookup"><span data-stu-id="6aa73-153">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="6aa73-154">此参数已过时，可能会在将来版本的脚本中删除。</span><span class="sxs-lookup"><span data-stu-id="6aa73-154">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="6aa73-155">建议的替代项为 `-Runtime|--runtime` 选项。</span><span class="sxs-lookup"><span data-stu-id="6aa73-155">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="6aa73-156">仅安装共享运行时位，而非整个 SDK。</span><span class="sxs-lookup"><span data-stu-id="6aa73-156">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="6aa73-157">此选项等效于指定 `-Runtime|--runtime dotnet`。</span><span class="sxs-lookup"><span data-stu-id="6aa73-157">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="6aa73-158">仅安装共享运行时，而非整个 SDK。</span><span class="sxs-lookup"><span data-stu-id="6aa73-158">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="6aa73-159">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="6aa73-159">The possible values are:</span></span>

  - <span data-ttu-id="6aa73-160">`dotnet` - `Microsoft.NETCore.App` 共享运行时。</span><span class="sxs-lookup"><span data-stu-id="6aa73-160">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="6aa73-161">`aspnetcore` - `Microsoft.AspNetCore.App` 共享运行时。</span><span class="sxs-lookup"><span data-stu-id="6aa73-161">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="6aa73-162">`windowsdesktop` - `Microsoft.WindowsDesktop.App` 共享运行时。</span><span class="sxs-lookup"><span data-stu-id="6aa73-162">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="6aa73-163">如果设置，脚本将不会执行安装。</span><span class="sxs-lookup"><span data-stu-id="6aa73-163">If set, the script won't perform the installation.</span></span> <span data-ttu-id="6aa73-164">而会显示要使用哪个命令行来持续安装当前请求的 .NET Core CLI 版本。</span><span class="sxs-lookup"><span data-stu-id="6aa73-164">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="6aa73-165">例如，如果指定版本 `latest`，它将显示特定版本的链接，以便可在生成脚本中明确地使用此命令。</span><span class="sxs-lookup"><span data-stu-id="6aa73-165">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="6aa73-166">如果想要自行安装或下载，它还会显示二进制文件位置。</span><span class="sxs-lookup"><span data-stu-id="6aa73-166">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="6aa73-167">如果设定，不会将安装文件夹导出到当前会话的路径。</span><span class="sxs-lookup"><span data-stu-id="6aa73-167">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="6aa73-168">默认情况下，该脚本会修改 PATH，这会使 .NET Core CLI 在安装后立即可用。</span><span class="sxs-lookup"><span data-stu-id="6aa73-168">By default, the script modifies the PATH, which makes the .NET Core CLI available immediately after install.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="6aa73-169">显示诊断信息。</span><span class="sxs-lookup"><span data-stu-id="6aa73-169">Displays diagnostics information.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="6aa73-170">指定此安装程序的 Azure 源的 URL。</span><span class="sxs-lookup"><span data-stu-id="6aa73-170">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="6aa73-171">建议不要更改该值。</span><span class="sxs-lookup"><span data-stu-id="6aa73-171">We recommended that you don't change this value.</span></span> <span data-ttu-id="6aa73-172">默认值为 `https://dotnetcli.azureedge.net/dotnet`。</span><span class="sxs-lookup"><span data-stu-id="6aa73-172">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="6aa73-173">允许更改此安装程序使用的未缓存源的 URL。</span><span class="sxs-lookup"><span data-stu-id="6aa73-173">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="6aa73-174">建议不要更改该值。</span><span class="sxs-lookup"><span data-stu-id="6aa73-174">We recommended that you don't change this value.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="6aa73-175">禁止从 [Azure 内容分发网络 (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) 进行下载，并直接使用未缓存源。</span><span class="sxs-lookup"><span data-stu-id="6aa73-175">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="6aa73-176">用作追加到 Azure 源的查询字符串。</span><span class="sxs-lookup"><span data-stu-id="6aa73-176">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="6aa73-177">这允许更改 URL 以使用非公共 blob 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="6aa73-177">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`--runtime-id`**

  <span data-ttu-id="6aa73-178">指定要为其安装工具的[运行时标识符](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="6aa73-178">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="6aa73-179">使用适用于可移植 Linux 的 `linux-x64`。</span><span class="sxs-lookup"><span data-stu-id="6aa73-179">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="6aa73-180">（仅适用于 Linux/macOS）</span><span class="sxs-lookup"><span data-stu-id="6aa73-180">(Only valid for Linux/macOS)</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="6aa73-181">如果设置，安装程序发出 Web 请求时将使用该代理。</span><span class="sxs-lookup"><span data-stu-id="6aa73-181">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="6aa73-182">（仅对 Windows 有效）</span><span class="sxs-lookup"><span data-stu-id="6aa73-182">(Only valid for Windows)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="6aa73-183">如果设置，在使用代理地址时，安装程序会使用当前用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="6aa73-183">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="6aa73-184">（仅对 Windows 有效）</span><span class="sxs-lookup"><span data-stu-id="6aa73-184">(Only valid for Windows)</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="6aa73-185">跳过安装未添加版本的文件，例如 dotnet.exe  （如果它们已经存在）。</span><span class="sxs-lookup"><span data-stu-id="6aa73-185">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-Help|--help`**

  <span data-ttu-id="6aa73-186">打印脚本帮助。</span><span class="sxs-lookup"><span data-stu-id="6aa73-186">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="6aa73-187">示例</span><span class="sxs-lookup"><span data-stu-id="6aa73-187">Examples</span></span>

- <span data-ttu-id="6aa73-188">将最新的长期支持 (LTS) 版本安装到默认位置：</span><span class="sxs-lookup"><span data-stu-id="6aa73-188">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="6aa73-189">Windows：</span><span class="sxs-lookup"><span data-stu-id="6aa73-189">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="6aa73-190">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="6aa73-190">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="6aa73-191">将 3.1 通道中的最新版本安装到指定位置：</span><span class="sxs-lookup"><span data-stu-id="6aa73-191">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="6aa73-192">Windows：</span><span class="sxs-lookup"><span data-stu-id="6aa73-192">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="6aa73-193">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="6aa73-193">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="6aa73-194">安装 3.0.0 版共享运行时：</span><span class="sxs-lookup"><span data-stu-id="6aa73-194">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="6aa73-195">Windows：</span><span class="sxs-lookup"><span data-stu-id="6aa73-195">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="6aa73-196">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="6aa73-196">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="6aa73-197">获取脚本并在公司代理后面安装 2.1.2 版本（仅限 Windows）：</span><span class="sxs-lookup"><span data-stu-id="6aa73-197">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="6aa73-198">获取脚本并安装 .NET Core CLI 单行式命令示例：</span><span class="sxs-lookup"><span data-stu-id="6aa73-198">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="6aa73-199">Windows：</span><span class="sxs-lookup"><span data-stu-id="6aa73-199">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="6aa73-200">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="6aa73-200">macOS/Linux:</span></span>

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="6aa73-201">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6aa73-201">See also</span></span>

- [<span data-ttu-id="6aa73-202">.NET Core 版本</span><span class="sxs-lookup"><span data-stu-id="6aa73-202">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="6aa73-203">.NET Core 运行时和 SDK 下载存档</span><span class="sxs-lookup"><span data-stu-id="6aa73-203">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
