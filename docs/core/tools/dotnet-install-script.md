---
title: "dotnet-install 脚本"
description: "了解用于安装 .NET Core CLI 工具和共享运行时的 dotnet-install 脚本。"
keywords: "dotnet-install, dotnet-install 脚本, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 09/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: b64e7e6f-ffb4-4fc8-b43b-5731c89479c2
ms.openlocfilehash: 2f15f37016fe824d76b501e4793e0b28bbdbe167
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="dc060-104">dotnet-install 脚本引用</span><span class="sxs-lookup"><span data-stu-id="dc060-104">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="dc060-105">名称</span><span class="sxs-lookup"><span data-stu-id="dc060-105">Name</span></span>

<span data-ttu-id="dc060-106">`dotnet-install.ps1` | `dotnet-install.sh` - 用于安装 .NET Core CLI 工具和共享运行时的脚本。</span><span class="sxs-lookup"><span data-stu-id="dc060-106">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="dc060-107">摘要</span><span class="sxs-lookup"><span data-stu-id="dc060-107">Synopsis</span></span>

<span data-ttu-id="dc060-108">Windows：</span><span class="sxs-lookup"><span data-stu-id="dc060-108">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress] [--Verbose] [--Help]`

<span data-ttu-id="dc060-109">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="dc060-109">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--dry-run] [--no-path] [--azure-feed] [--verbose] [--help]`

## <a name="description"></a><span data-ttu-id="dc060-110">描述</span><span class="sxs-lookup"><span data-stu-id="dc060-110">Description</span></span>

<span data-ttu-id="dc060-111">`dotnet-install` 脚本用于执行 .NET Core SDK 的非管理员安装，其中包含 .NET Core CLI 工具和共享运行时。</span><span class="sxs-lookup"><span data-stu-id="dc060-111">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="dc060-112">建议使用在 [.NET Core 主网站](https://dot.net)上托管的稳定版本。</span><span class="sxs-lookup"><span data-stu-id="dc060-112">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="dc060-113">脚本的直接路径为：</span><span class="sxs-lookup"><span data-stu-id="dc060-113">The direct paths to the scripts are:</span></span>

* <span data-ttu-id="dc060-114">https://dot.net/v1/dotnet-install.sh (UNIX bash)</span><span class="sxs-lookup"><span data-stu-id="dc060-114">https://dot.net/v1/dotnet-install.sh (bash, UNIX)</span></span>
* <span data-ttu-id="dc060-115">https://dot.net/v1/dotnet-install.ps1 (Windows Powershell)</span><span class="sxs-lookup"><span data-stu-id="dc060-115">https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)</span></span>

<span data-ttu-id="dc060-116">这些脚本主要用于自动化方案和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="dc060-116">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="dc060-117">共有两个脚本，一个是在 Windows 上运行的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="dc060-117">There are two scripts: One is a PowerShell script that works on Windows.</span></span> <span data-ttu-id="dc060-118">另一脚本是适用于 Linux/macOS 的 bash 脚本。</span><span class="sxs-lookup"><span data-stu-id="dc060-118">The other script is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="dc060-119">这两个脚本的行为相同。</span><span class="sxs-lookup"><span data-stu-id="dc060-119">Both scripts have the same behavior.</span></span> <span data-ttu-id="dc060-120">bash 脚本也读取 PowerShell 开关。因此，可以在 Linux/macOS 系统上将 PowerShell 开关与脚本结合使用。</span><span class="sxs-lookup"><span data-stu-id="dc060-120">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span> 

<span data-ttu-id="dc060-121">安装脚本从 CLI 生成放置下载 ZIP/tarball 文件，并将其安装在默认位置或 `-InstallDir|--install-dir` 所指定的位置。</span><span class="sxs-lookup"><span data-stu-id="dc060-121">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="dc060-122">默认情况下，安装脚本下载 SDK 并安装它。</span><span class="sxs-lookup"><span data-stu-id="dc060-122">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="dc060-123">如果只想获取共享的运行时，请指定 `--shared-runtime` 参数。</span><span class="sxs-lookup"><span data-stu-id="dc060-123">If you wish to only obtain the shared runtime, specify the `--shared-runtime` argument.</span></span> 

<span data-ttu-id="dc060-124">默认情况下，该脚本会将安装位置添加到当前会话的 $PATH。</span><span class="sxs-lookup"><span data-stu-id="dc060-124">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="dc060-125">通过指定 `--no-path` 参数覆盖此默认行为。</span><span class="sxs-lookup"><span data-stu-id="dc060-125">Override this default behavior by specifying the `--no-path` argument.</span></span> 

<span data-ttu-id="dc060-126">运行脚本前，请安装所需的[依赖项](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)。</span><span class="sxs-lookup"><span data-stu-id="dc060-126">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="dc060-127">可以使用 `--version` 参数安装特定版本。</span><span class="sxs-lookup"><span data-stu-id="dc060-127">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="dc060-128">必须将该版本指定为一个 3 部分构成的版本（例如，1.0.0-13232）。</span><span class="sxs-lookup"><span data-stu-id="dc060-128">The version must be specified as a 3-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="dc060-129">如果省略，则使用 `latest` 版本。</span><span class="sxs-lookup"><span data-stu-id="dc060-129">If omitted, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="dc060-130">选项</span><span class="sxs-lookup"><span data-stu-id="dc060-130">Options</span></span>

`-Channel <CHANNEL>`

<span data-ttu-id="dc060-131">指定安装的源通道。</span><span class="sxs-lookup"><span data-stu-id="dc060-131">Specifies the source channel for the installation.</span></span> <span data-ttu-id="dc060-132">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="dc060-132">The possible values are:</span></span>

- <span data-ttu-id="dc060-133">`Current` - 当前版本</span><span class="sxs-lookup"><span data-stu-id="dc060-133">`Current` - Current release</span></span>
- <span data-ttu-id="dc060-134">`LTS` - 长期支持频道（当前支持版本）</span><span class="sxs-lookup"><span data-stu-id="dc060-134">`LTS` - Long-Term Support channel (current supported release)</span></span>
- <span data-ttu-id="dc060-135">表示特定版本的由两部分构成的 X.Y 格式的版本（例如 `2.0` 或 `1.0`）</span><span class="sxs-lookup"><span data-stu-id="dc060-135">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`)</span></span>
- <span data-ttu-id="dc060-136">分支名称 [例如 `release/2.0.0`、`release/2.0.0-preview2` 或 `master` 分支中的最新版 `master`（“最前沿”的每日构建）]</span><span class="sxs-lookup"><span data-stu-id="dc060-136">Branch name [for example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` for the latest from the `master` branch ("bleeding edge" nightly releases)]</span></span>

<span data-ttu-id="dc060-137">默认值为 `LTS`。</span><span class="sxs-lookup"><span data-stu-id="dc060-137">The default value is `LTS`.</span></span> <span data-ttu-id="dc060-138">有关 .NET 支持频道的详细信息，请参阅 [.NET Core 支持生命周期](https://www.microsoft.com/net/core/support)主题。</span><span class="sxs-lookup"><span data-stu-id="dc060-138">For more information on .NET support channels, see the [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) topic.</span></span>

`-Version <VERSION>`

<span data-ttu-id="dc060-139">表示特定的内部版本。</span><span class="sxs-lookup"><span data-stu-id="dc060-139">Represents a specific build version.</span></span> <span data-ttu-id="dc060-140">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="dc060-140">The possible values are:</span></span>

- <span data-ttu-id="dc060-141">`latest` - 频道上的最新内部版本（与 `-Channel` 选项结合使用）</span><span class="sxs-lookup"><span data-stu-id="dc060-141">`latest` - Latest build on the channel (used with the `-Channel` option)</span></span>
- <span data-ttu-id="dc060-142">`coherent` - 频道上的最新相干内部版本；使用最新的稳定包组合（与分支名称 `-Channel` 选项结合使用）</span><span class="sxs-lookup"><span data-stu-id="dc060-142">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options)</span></span>
- <span data-ttu-id="dc060-143">由三部分组成的版本，采用 X.Y.Z 格式，表示特定的内部版本；取代 `-Channel` 选项。</span><span class="sxs-lookup"><span data-stu-id="dc060-143">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="dc060-144">例如：`2.0.0-preview2-006120`</span><span class="sxs-lookup"><span data-stu-id="dc060-144">For example: `2.0.0-preview2-006120`</span></span>

<span data-ttu-id="dc060-145">如果省略，`-Version` 默认为 `latest`。</span><span class="sxs-lookup"><span data-stu-id="dc060-145">If omitted, `-Version` defaults to `latest`.</span></span>

`-InstallDir <DIRECTORY>`

<span data-ttu-id="dc060-146">指定安装路径。</span><span class="sxs-lookup"><span data-stu-id="dc060-146">Specifies the installation path.</span></span> <span data-ttu-id="dc060-147">如果不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="dc060-147">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="dc060-148">默认值为 *%LocalAppData%\.dotnet*。</span><span class="sxs-lookup"><span data-stu-id="dc060-148">The default value is *%LocalAppData%\.dotnet*.</span></span> <span data-ttu-id="dc060-149">请注意，会将二进制文件直接放入目录中。</span><span class="sxs-lookup"><span data-stu-id="dc060-149">Note that binaries are placed directly in the directory.</span></span>

`-Architecture <ARCHITECTURE>`

<span data-ttu-id="dc060-150">要安装的 .NET Core 二进制文件的体系结构。</span><span class="sxs-lookup"><span data-stu-id="dc060-150">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="dc060-151">可能的值包括 `auto`、`x64` 和 `x86`。</span><span class="sxs-lookup"><span data-stu-id="dc060-151">Possible values are `auto`, `x64`, and `x86`.</span></span> <span data-ttu-id="dc060-152">默认值为 `auto`，它表示当前正在运行的操作系统体系结构。</span><span class="sxs-lookup"><span data-stu-id="dc060-152">The default value is `auto`, which represents the currently running OS architecture.</span></span>

`-SharedRuntime`

<span data-ttu-id="dc060-153">如果设置，则此开关限制到共享运行时的安装。</span><span class="sxs-lookup"><span data-stu-id="dc060-153">If set, this switch limits installation to the shared runtime.</span></span> <span data-ttu-id="dc060-154">不会安装整个 SDK。</span><span class="sxs-lookup"><span data-stu-id="dc060-154">The entire SDK isn't installed.</span></span>

`-DryRun`

<span data-ttu-id="dc060-155">如果设置，该脚本不会执行安装，而会显示要使用哪个命令行来持续安装当前请求的 .NET Core CLI 版本。</span><span class="sxs-lookup"><span data-stu-id="dc060-155">If set, the script won't perform the installation; but instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="dc060-156">例如，如果指定版本 `latest`，它将显示特定版本的链接，以便可在生成脚本中明确地使用此命令。</span><span class="sxs-lookup"><span data-stu-id="dc060-156">For example if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="dc060-157">如果想要自行安装或下载，它还会显示二进制文件位置。</span><span class="sxs-lookup"><span data-stu-id="dc060-157">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

`-NoPath`

<span data-ttu-id="dc060-158">如果设定，不会将 prefix/installdir 导出到当前会话的路径。</span><span class="sxs-lookup"><span data-stu-id="dc060-158">If set, the prefix/installdir are not exported to the path for the current session.</span></span> <span data-ttu-id="dc060-159">默认情况下，该脚本将修改 PATH，这会使 CLI 工具在安装后立即可用。</span><span class="sxs-lookup"><span data-stu-id="dc060-159">By default, the script will modify the PATH, which makes the CLI tools available immediately after install.</span></span>

`-AzureFeed`

<span data-ttu-id="dc060-160">指定此安装程序的 Azure 源的 URL。</span><span class="sxs-lookup"><span data-stu-id="dc060-160">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="dc060-161">不建议更改该值。</span><span class="sxs-lookup"><span data-stu-id="dc060-161">It isn't recommended that you change this value.</span></span> <span data-ttu-id="dc060-162">默认值为 `https://dotnetcli.azureedge.net/dotnet`。</span><span class="sxs-lookup"><span data-stu-id="dc060-162">The default is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

`-ProxyAddress`

<span data-ttu-id="dc060-163">如果设置，安装程序发出 Web 请求时将使用该代理。</span><span class="sxs-lookup"><span data-stu-id="dc060-163">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="dc060-164">（仅对 Windows 有效）</span><span class="sxs-lookup"><span data-stu-id="dc060-164">(Only valid for Windows)</span></span>

`--verbose`

<span data-ttu-id="dc060-165">显示诊断信息。</span><span class="sxs-lookup"><span data-stu-id="dc060-165">Display diagnostics information.</span></span>

`--help`

<span data-ttu-id="dc060-166">打印脚本帮助。</span><span class="sxs-lookup"><span data-stu-id="dc060-166">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="dc060-167">示例</span><span class="sxs-lookup"><span data-stu-id="dc060-167">Examples</span></span>

<span data-ttu-id="dc060-168">将最新的长期支持 (LTS) 版本安装到默认位置：</span><span class="sxs-lookup"><span data-stu-id="dc060-168">Install the latest long-term supported (LTS) version to the default location:</span></span>

<span data-ttu-id="dc060-169">Windows：</span><span class="sxs-lookup"><span data-stu-id="dc060-169">Windows:</span></span>

`./dotnet-install.ps1 -Channel LTS`

<span data-ttu-id="dc060-170">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="dc060-170">macOS/Linux:</span></span>

`./dotnet-install.sh --channel LTS`

<span data-ttu-id="dc060-171">将 2.0 频道中的最新版本安装到指定位置：</span><span class="sxs-lookup"><span data-stu-id="dc060-171">Install the latest version from 2.0 channel to the specified location:</span></span>

<span data-ttu-id="dc060-172">Windows：</span><span class="sxs-lookup"><span data-stu-id="dc060-172">Windows:</span></span>

`./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli`

<span data-ttu-id="dc060-173">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="dc060-173">macOS/Linux:</span></span>

`./dotnet-install.sh --channel 2.0 --install-dir ~/cli`

<span data-ttu-id="dc060-174">安装 1.1.0 版共享运行时：</span><span class="sxs-lookup"><span data-stu-id="dc060-174">Install the 1.1.0 version of the shared runtime:</span></span>

<span data-ttu-id="dc060-175">Windows：</span><span class="sxs-lookup"><span data-stu-id="dc060-175">Windows:</span></span>

`./dotnet-install.ps1 -SharedRuntime -Version 1.1.0`

<span data-ttu-id="dc060-176">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="dc060-176">macOS/Linux:</span></span>

`./dotnet-install.sh --shared-runtime --version 1.1.0`

<span data-ttu-id="dc060-177">获取脚本并安装 .NET Core CLI 单行式命令示例：</span><span class="sxs-lookup"><span data-stu-id="dc060-177">Obtain script and install .NET Core CLI one-liner examples:</span></span>

<span data-ttu-id="dc060-178">Windows：</span><span class="sxs-lookup"><span data-stu-id="dc060-178">Windows:</span></span>

`@powershell -NoProfile -ExecutionPolicy unrestricted -Command "&([scriptblock]::Create((Invoke-WebRequest -useb 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"`

<span data-ttu-id="dc060-179">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="dc060-179">macOS/Linux:</span></span>

`curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>`

## <a name="see-also"></a><span data-ttu-id="dc060-180">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc060-180">See also</span></span>

<span data-ttu-id="dc060-181">[.NET Core 版本](https://github.com/dotnet/core/releases) </span><span class="sxs-lookup"><span data-stu-id="dc060-181">[.NET Core releases](https://github.com/dotnet/core/releases) </span></span>  
[<span data-ttu-id="dc060-182">.NET Core 运行时和 SDK 下载存档</span><span class="sxs-lookup"><span data-stu-id="dc060-182">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
