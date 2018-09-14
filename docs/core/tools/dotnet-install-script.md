---
title: dotnet-install 脚本
description: 了解用于安装 .NET Core CLI 工具和共享运行时的 dotnet-install 脚本。
author: blackdwarf
ms.author: mairaw
ms.date: 09/11/2017
ms.openlocfilehash: 8d1c6ebb30bd45575bb61206799c9c3e5c47ff0c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44180038"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="f5d77-103">dotnet-install 脚本引用</span><span class="sxs-lookup"><span data-stu-id="f5d77-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="f5d77-104">name</span><span class="sxs-lookup"><span data-stu-id="f5d77-104">Name</span></span>

<span data-ttu-id="f5d77-105">`dotnet-install.ps1` | `dotnet-install.sh` - 用于安装 .NET Core CLI 工具和共享运行时的脚本。</span><span class="sxs-lookup"><span data-stu-id="f5d77-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f5d77-106">摘要</span><span class="sxs-lookup"><span data-stu-id="f5d77-106">Synopsis</span></span>

<span data-ttu-id="f5d77-107">Windows：</span><span class="sxs-lookup"><span data-stu-id="f5d77-107">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress] [--Verbose] [--Help]`

<span data-ttu-id="f5d77-108">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="f5d77-108">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--dry-run] [--no-path] [--azure-feed] [--verbose] [--help]`

## <a name="description"></a><span data-ttu-id="f5d77-109">描述</span><span class="sxs-lookup"><span data-stu-id="f5d77-109">Description</span></span>

<span data-ttu-id="f5d77-110">`dotnet-install` 脚本用于执行 .NET Core SDK 的非管理员安装，其中包含 .NET Core CLI 工具和共享运行时。</span><span class="sxs-lookup"><span data-stu-id="f5d77-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="f5d77-111">建议使用在 [.NET Core 主网站](https://dot.net)上托管的稳定版本。</span><span class="sxs-lookup"><span data-stu-id="f5d77-111">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="f5d77-112">脚本的直接路径为：</span><span class="sxs-lookup"><span data-stu-id="f5d77-112">The direct paths to the scripts are:</span></span>

* <span data-ttu-id="f5d77-113">https://dot.net/v1/dotnet-install.sh（bash、UNIX）</span><span class="sxs-lookup"><span data-stu-id="f5d77-113">https://dot.net/v1/dotnet-install.sh (bash, UNIX)</span></span>
* <span data-ttu-id="f5d77-114">https://dot.net/v1/dotnet-install.ps1（Powershell、Windows）</span><span class="sxs-lookup"><span data-stu-id="f5d77-114">https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)</span></span>

<span data-ttu-id="f5d77-115">这些脚本主要用于自动化方案和非管理员安装。</span><span class="sxs-lookup"><span data-stu-id="f5d77-115">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="f5d77-116">共有两个脚本，一个是在 Windows 上运行的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="f5d77-116">There are two scripts: One is a PowerShell script that works on Windows.</span></span> <span data-ttu-id="f5d77-117">另一脚本是适用于 Linux/macOS 的 bash 脚本。</span><span class="sxs-lookup"><span data-stu-id="f5d77-117">The other script is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="f5d77-118">这两个脚本的行为相同。</span><span class="sxs-lookup"><span data-stu-id="f5d77-118">Both scripts have the same behavior.</span></span> <span data-ttu-id="f5d77-119">bash 脚本也读取 PowerShell 开关。因此，可以在 Linux/macOS 系统上将 PowerShell 开关与脚本结合使用。</span><span class="sxs-lookup"><span data-stu-id="f5d77-119">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="f5d77-120">安装脚本从 CLI 生成放置下载 ZIP/tarball 文件，并将其安装在默认位置或 `-InstallDir|--install-dir` 所指定的位置。</span><span class="sxs-lookup"><span data-stu-id="f5d77-120">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="f5d77-121">默认情况下，安装脚本下载 SDK 并安装它。</span><span class="sxs-lookup"><span data-stu-id="f5d77-121">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="f5d77-122">如果只想获取共享的运行时，请指定 `--shared-runtime` 参数。</span><span class="sxs-lookup"><span data-stu-id="f5d77-122">If you wish to only obtain the shared runtime, specify the `--shared-runtime` argument.</span></span>

<span data-ttu-id="f5d77-123">默认情况下，该脚本会将安装位置添加到当前会话的 $PATH。</span><span class="sxs-lookup"><span data-stu-id="f5d77-123">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="f5d77-124">通过指定 `--no-path` 参数覆盖此默认行为。</span><span class="sxs-lookup"><span data-stu-id="f5d77-124">Override this default behavior by specifying the `--no-path` argument.</span></span>

<span data-ttu-id="f5d77-125">运行脚本前，请安装所需的[依赖项](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)。</span><span class="sxs-lookup"><span data-stu-id="f5d77-125">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="f5d77-126">可以使用 `--version` 参数安装特定版本。</span><span class="sxs-lookup"><span data-stu-id="f5d77-126">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="f5d77-127">必须将该版本指定为一个 3 部分构成的版本（例如，1.0.0-13232）。</span><span class="sxs-lookup"><span data-stu-id="f5d77-127">The version must be specified as a 3-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="f5d77-128">如果省略，则使用 `latest` 版本。</span><span class="sxs-lookup"><span data-stu-id="f5d77-128">If omitted, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="f5d77-129">选项</span><span class="sxs-lookup"><span data-stu-id="f5d77-129">Options</span></span>

`-Channel <CHANNEL>`

<span data-ttu-id="f5d77-130">指定安装的源通道。</span><span class="sxs-lookup"><span data-stu-id="f5d77-130">Specifies the source channel for the installation.</span></span> <span data-ttu-id="f5d77-131">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="f5d77-131">The possible values are:</span></span>

- <span data-ttu-id="f5d77-132">`Current` - 当前版本</span><span class="sxs-lookup"><span data-stu-id="f5d77-132">`Current` - Current release</span></span>
- <span data-ttu-id="f5d77-133">`LTS` - 长期支持频道（当前支持版本）</span><span class="sxs-lookup"><span data-stu-id="f5d77-133">`LTS` - Long-Term Support channel (current supported release)</span></span>
- <span data-ttu-id="f5d77-134">表示特定版本的由两部分构成的 X.Y 格式的版本（例如 `2.0` 或 `1.0`）</span><span class="sxs-lookup"><span data-stu-id="f5d77-134">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`)</span></span>
- <span data-ttu-id="f5d77-135">分支名称 [例如 `release/2.0.0`、`release/2.0.0-preview2` 或 `master` 分支中的最新版 `master`（“最前沿”的每日构建）]</span><span class="sxs-lookup"><span data-stu-id="f5d77-135">Branch name [for example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` for the latest from the `master` branch ("bleeding edge" nightly releases)]</span></span>

<span data-ttu-id="f5d77-136">默认值为 `LTS`。</span><span class="sxs-lookup"><span data-stu-id="f5d77-136">The default value is `LTS`.</span></span> <span data-ttu-id="f5d77-137">有关 .NET 支持频道的详细信息，请参阅 [.NET Core 支持生命周期](https://www.microsoft.com/net/core/support)主题。</span><span class="sxs-lookup"><span data-stu-id="f5d77-137">For more information on .NET support channels, see the [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) topic.</span></span>

`-Version <VERSION>`

<span data-ttu-id="f5d77-138">表示特定的内部版本。</span><span class="sxs-lookup"><span data-stu-id="f5d77-138">Represents a specific build version.</span></span> <span data-ttu-id="f5d77-139">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="f5d77-139">The possible values are:</span></span>

- <span data-ttu-id="f5d77-140">`latest` - 频道上的最新内部版本（与 `-Channel` 选项结合使用）</span><span class="sxs-lookup"><span data-stu-id="f5d77-140">`latest` - Latest build on the channel (used with the `-Channel` option)</span></span>
- <span data-ttu-id="f5d77-141">`coherent` - 频道上的最新相干内部版本；使用最新的稳定包组合（与分支名称 `-Channel` 选项结合使用）</span><span class="sxs-lookup"><span data-stu-id="f5d77-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options)</span></span>
- <span data-ttu-id="f5d77-142">由三部分组成的版本，采用 X.Y.Z 格式，表示特定的内部版本；取代 `-Channel` 选项。</span><span class="sxs-lookup"><span data-stu-id="f5d77-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="f5d77-143">例如：`2.0.0-preview2-006120`</span><span class="sxs-lookup"><span data-stu-id="f5d77-143">For example: `2.0.0-preview2-006120`</span></span>

<span data-ttu-id="f5d77-144">如果省略，`-Version` 默认为 `latest`。</span><span class="sxs-lookup"><span data-stu-id="f5d77-144">If omitted, `-Version` defaults to `latest`.</span></span>

`-InstallDir <DIRECTORY>`

<span data-ttu-id="f5d77-145">指定安装路径。</span><span class="sxs-lookup"><span data-stu-id="f5d77-145">Specifies the installation path.</span></span> <span data-ttu-id="f5d77-146">如果不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="f5d77-146">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="f5d77-147">默认值为 *%LocalAppData%\.dotnet*。</span><span class="sxs-lookup"><span data-stu-id="f5d77-147">The default value is *%LocalAppData%\.dotnet*.</span></span> <span data-ttu-id="f5d77-148">请注意，会将二进制文件直接放入目录中。</span><span class="sxs-lookup"><span data-stu-id="f5d77-148">Note that binaries are placed directly in the directory.</span></span>

`-Architecture <ARCHITECTURE>`

<span data-ttu-id="f5d77-149">要安装的 .NET Core 二进制文件的体系结构。</span><span class="sxs-lookup"><span data-stu-id="f5d77-149">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="f5d77-150">可能的值包括 `auto`、`x64` 和 `x86`。</span><span class="sxs-lookup"><span data-stu-id="f5d77-150">Possible values are `auto`, `x64`, and `x86`.</span></span> <span data-ttu-id="f5d77-151">默认值为 `auto`，它表示当前正在运行的操作系统体系结构。</span><span class="sxs-lookup"><span data-stu-id="f5d77-151">The default value is `auto`, which represents the currently running OS architecture.</span></span>

`-SharedRuntime`

<span data-ttu-id="f5d77-152">如果设置，则此开关限制到共享运行时的安装。</span><span class="sxs-lookup"><span data-stu-id="f5d77-152">If set, this switch limits installation to the shared runtime.</span></span> <span data-ttu-id="f5d77-153">不会安装整个 SDK。</span><span class="sxs-lookup"><span data-stu-id="f5d77-153">The entire SDK isn't installed.</span></span>

`-DryRun`

<span data-ttu-id="f5d77-154">如果设置，该脚本不会执行安装，而会显示要使用哪个命令行来持续安装当前请求的 .NET Core CLI 版本。</span><span class="sxs-lookup"><span data-stu-id="f5d77-154">If set, the script won't perform the installation; but instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="f5d77-155">例如，如果指定版本 `latest`，它将显示特定版本的链接，以便可在生成脚本中明确地使用此命令。</span><span class="sxs-lookup"><span data-stu-id="f5d77-155">For example if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="f5d77-156">如果想要自行安装或下载，它还会显示二进制文件位置。</span><span class="sxs-lookup"><span data-stu-id="f5d77-156">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

`-NoPath`

<span data-ttu-id="f5d77-157">如果设定，不会将 prefix/installdir 导出到当前会话的路径。</span><span class="sxs-lookup"><span data-stu-id="f5d77-157">If set, the prefix/installdir are not exported to the path for the current session.</span></span> <span data-ttu-id="f5d77-158">默认情况下，该脚本将修改 PATH，这会使 CLI 工具在安装后立即可用。</span><span class="sxs-lookup"><span data-stu-id="f5d77-158">By default, the script will modify the PATH, which makes the CLI tools available immediately after install.</span></span>

`-AzureFeed`

<span data-ttu-id="f5d77-159">指定此安装程序的 Azure 源的 URL。</span><span class="sxs-lookup"><span data-stu-id="f5d77-159">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="f5d77-160">不建议更改该值。</span><span class="sxs-lookup"><span data-stu-id="f5d77-160">It isn't recommended that you change this value.</span></span> <span data-ttu-id="f5d77-161">默认值为 `https://dotnetcli.azureedge.net/dotnet`。</span><span class="sxs-lookup"><span data-stu-id="f5d77-161">The default is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

`-ProxyAddress`

<span data-ttu-id="f5d77-162">如果设置，安装程序发出 Web 请求时将使用该代理。</span><span class="sxs-lookup"><span data-stu-id="f5d77-162">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="f5d77-163">（仅对 Windows 有效）</span><span class="sxs-lookup"><span data-stu-id="f5d77-163">(Only valid for Windows)</span></span>

`--verbose`

<span data-ttu-id="f5d77-164">显示诊断信息。</span><span class="sxs-lookup"><span data-stu-id="f5d77-164">Display diagnostics information.</span></span>

`--help`

<span data-ttu-id="f5d77-165">打印脚本帮助。</span><span class="sxs-lookup"><span data-stu-id="f5d77-165">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="f5d77-166">示例</span><span class="sxs-lookup"><span data-stu-id="f5d77-166">Examples</span></span>

<span data-ttu-id="f5d77-167">将最新的长期支持 (LTS) 版本安装到默认位置：</span><span class="sxs-lookup"><span data-stu-id="f5d77-167">Install the latest long-term supported (LTS) version to the default location:</span></span>

<span data-ttu-id="f5d77-168">Windows：</span><span class="sxs-lookup"><span data-stu-id="f5d77-168">Windows:</span></span>

`./dotnet-install.ps1 -Channel LTS`

<span data-ttu-id="f5d77-169">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="f5d77-169">macOS/Linux:</span></span>

`./dotnet-install.sh --channel LTS`

<span data-ttu-id="f5d77-170">将 2.0 频道中的最新版本安装到指定位置：</span><span class="sxs-lookup"><span data-stu-id="f5d77-170">Install the latest version from 2.0 channel to the specified location:</span></span>

<span data-ttu-id="f5d77-171">Windows：</span><span class="sxs-lookup"><span data-stu-id="f5d77-171">Windows:</span></span>

`./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli`

<span data-ttu-id="f5d77-172">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="f5d77-172">macOS/Linux:</span></span>

`./dotnet-install.sh --channel 2.0 --install-dir ~/cli`

<span data-ttu-id="f5d77-173">安装 1.1.0 版共享运行时：</span><span class="sxs-lookup"><span data-stu-id="f5d77-173">Install the 1.1.0 version of the shared runtime:</span></span>

<span data-ttu-id="f5d77-174">Windows：</span><span class="sxs-lookup"><span data-stu-id="f5d77-174">Windows:</span></span>

`./dotnet-install.ps1 -SharedRuntime -Version 1.1.0`

<span data-ttu-id="f5d77-175">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="f5d77-175">macOS/Linux:</span></span>

`./dotnet-install.sh --shared-runtime --version 1.1.0`

<span data-ttu-id="f5d77-176">获取脚本并安装 .NET Core CLI 单行式命令示例：</span><span class="sxs-lookup"><span data-stu-id="f5d77-176">Obtain script and install .NET Core CLI one-liner examples:</span></span>

<span data-ttu-id="f5d77-177">Windows：</span><span class="sxs-lookup"><span data-stu-id="f5d77-177">Windows:</span></span>

`@powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -useb 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"`

<span data-ttu-id="f5d77-178">macOS/Linux：</span><span class="sxs-lookup"><span data-stu-id="f5d77-178">macOS/Linux:</span></span>

`curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>`

## <a name="see-also"></a><span data-ttu-id="f5d77-179">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5d77-179">See also</span></span>

* [<span data-ttu-id="f5d77-180">.NET Core 版本</span><span class="sxs-lookup"><span data-stu-id="f5d77-180">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
* [<span data-ttu-id="f5d77-181">.NET Core 运行时和 SDK 下载存档</span><span class="sxs-lookup"><span data-stu-id="f5d77-181">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
