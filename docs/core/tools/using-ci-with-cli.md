---
title: "在持续集成 (CI) 中使用 .NET Core SDK 和工具"
description: "了解如何在生成服务器上使用 .NET Core SDK 及其工具。"
keywords: ".NET, .NET Core, 持续集成, ci, 生成, 自动化, Travis CI, AppVeyor, Visual Studio Team Services, vsts"
author: guardrex
ms.author: mairaw
ms.date: 05/18/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0d6e1e34-277c-4aaf-9880-3ebf81023857
ms.workload:
- dotnetcore
ms.openlocfilehash: 552865f225ceac9e7a365452ee06d7fefeeb7213
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="using-net-core-sdk-and-tools-in-continuous-integration-ci"></a><span data-ttu-id="5f592-104">在持续集成 (CI) 中使用 .NET Core SDK 和工具</span><span class="sxs-lookup"><span data-stu-id="5f592-104">Using .NET Core SDK and tools in Continuous Integration (CI)</span></span>

## <a name="overview"></a><span data-ttu-id="5f592-105">概述</span><span class="sxs-lookup"><span data-stu-id="5f592-105">Overview</span></span>

<span data-ttu-id="5f592-106">本文档概述了如何在生成服务器上使用 .NET Core SDK 及其工具。</span><span class="sxs-lookup"><span data-stu-id="5f592-106">This document outlines using the .NET Core SDK and its tools on a build server.</span></span> <span data-ttu-id="5f592-107">.NET Core 工具集既可以交互方式运行（当开发者在命令提示符处键入命令时），也可以自动运行（当持续集成 (CI) 服务器运行生成脚本时）。</span><span class="sxs-lookup"><span data-stu-id="5f592-107">The .NET Core toolset works both interactively, where a developer types commands at a command prompt, and automatically, where a Continuous Integration (CI) server runs a build script.</span></span> <span data-ttu-id="5f592-108">命令、选项、输入和输出都相同，可通过提供的唯一内容来获取用于生成应用的工具和系统。</span><span class="sxs-lookup"><span data-stu-id="5f592-108">The commands, options, inputs, and outputs are the same, and the only things you supply are a way to acquire the tooling and a system to build your app.</span></span> <span data-ttu-id="5f592-109">本文档重点介绍了 CI 工具获取方案，并提供了有关如何设计和构建生成脚本的建议。</span><span class="sxs-lookup"><span data-stu-id="5f592-109">This document focuses on scenarios of tool acquisition for CI with recommendations on how to design and structure your build scripts.</span></span>

## <a name="installation-options-for-ci-build-servers"></a><span data-ttu-id="5f592-110">CI 生成服务器的安装选项</span><span class="sxs-lookup"><span data-stu-id="5f592-110">Installation options for CI build servers</span></span>

### <a name="using-the-native-installers"></a><span data-ttu-id="5f592-111">使用本机安装程序</span><span class="sxs-lookup"><span data-stu-id="5f592-111">Using the native installers</span></span>

<span data-ttu-id="5f592-112">本机安装程序适用于 macOS、Linux 和 Windows。</span><span class="sxs-lookup"><span data-stu-id="5f592-112">Native installers are available for macOS, Linux, and Windows.</span></span> <span data-ttu-id="5f592-113">安装程序需要拥有对生成服务器的管理员 (sudo) 访问权限。</span><span class="sxs-lookup"><span data-stu-id="5f592-113">The installers require admin (sudo) access to the build server.</span></span> <span data-ttu-id="5f592-114">使用本机安装程序的优势在于，可以安装运行工具所需的全部本机依赖项。</span><span class="sxs-lookup"><span data-stu-id="5f592-114">The advantage of using a native installer is that it installs all of the native dependencies required for the tooling to run.</span></span> <span data-ttu-id="5f592-115">本机安装程序还可以在整个系统内安装 SDK。</span><span class="sxs-lookup"><span data-stu-id="5f592-115">Native installers also provide a system-wide installation of the SDK.</span></span>

<span data-ttu-id="5f592-116">macOS 用户应使用 PKG 安装程序。</span><span class="sxs-lookup"><span data-stu-id="5f592-116">macOS users should use the PKG installers.</span></span> <span data-ttu-id="5f592-117">在 Linux 上，可选择使用基于源的包管理器（如用于 Ubuntu 的 apt-get 或用于 CentOS 的 yum），也可以选择使用包本身（即 DEB 或 RPM）。</span><span class="sxs-lookup"><span data-stu-id="5f592-117">On Linux, there's a choice of using a feed-based package manager, such as apt-get for Ubuntu or yum for CentOS, or using the packages themselves, DEB or RPM.</span></span> <span data-ttu-id="5f592-118">在 Windows 上，使用 MSI 安装程序。</span><span class="sxs-lookup"><span data-stu-id="5f592-118">On Windows, use the MSI installer.</span></span>

<span data-ttu-id="5f592-119">有关最新的稳定二进制文件，请参阅 [.NET Core 入门](https://aka.ms/dotnetcoregs)。</span><span class="sxs-lookup"><span data-stu-id="5f592-119">The latest stable binaries are found at [Get Started with .NET Core](https://aka.ms/dotnetcoregs).</span></span> <span data-ttu-id="5f592-120">若要使用最新（但可能不稳定）的预览版工具，请使用 [dotnet/cli GitHub 存储库](https://github.com/dotnet/cli#installers-and-binaries)中提供的链接。</span><span class="sxs-lookup"><span data-stu-id="5f592-120">If you wish to use the latest (and potentially unstable) pre-release tooling, use the links provided at the [dotnet/cli GitHub repository](https://github.com/dotnet/cli#installers-and-binaries).</span></span> <span data-ttu-id="5f592-121">对于 Linux 发行版本，可以使用 `tar.gz` 存档（亦称为 `tarballs`）；使用存档中的安装脚本来安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="5f592-121">For Linux distributions, `tar.gz` archives (also known as `tarballs`) are available; use the installation scripts within the archives to install .NET Core.</span></span>

### <a name="using-the-installer-script"></a><span data-ttu-id="5f592-122">使用安装程序脚本</span><span class="sxs-lookup"><span data-stu-id="5f592-122">Using the installer script</span></span>

<span data-ttu-id="5f592-123">使用安装程序脚本，可以在生成服务器上执行非管理员安装，并能轻松实现自动化，以便获取工具。</span><span class="sxs-lookup"><span data-stu-id="5f592-123">Using the installer script allows for non-administrative installation on your build server and easy automation for obtaining the tooling.</span></span> <span data-ttu-id="5f592-124">安装程序脚本负责下载并将工具提取到默认或指定位置，以供使用。</span><span class="sxs-lookup"><span data-stu-id="5f592-124">The script takes care of downloading the tooling and extracting it into a default or specified location for use.</span></span> <span data-ttu-id="5f592-125">还可以指定要安装的工具版本，以及是要安装整个 SDK，还是仅安装共享运行时。</span><span class="sxs-lookup"><span data-stu-id="5f592-125">You can also specify a version of the tooling that you wish to install and whether you want to install the entire SDK or only the shared runtime.</span></span>

<span data-ttu-id="5f592-126">安装程序脚本在开始生成时自动运行，以提取和安装相应版本的 SDK。</span><span class="sxs-lookup"><span data-stu-id="5f592-126">The installer script is automated to run at the start of the build to fetch and install the desired version of the SDK.</span></span> <span data-ttu-id="5f592-127">相应版本是指生成项目所需的任意 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="5f592-127">The *desired version* is whatever version of the SDK your projects require to build.</span></span> <span data-ttu-id="5f592-128">使用安装程序脚本，可以在服务器的本地目录中安装 SDK，并能从安装位置运行工具，还可以在生成后进行清理（或让 CI 服务进行清理）。</span><span class="sxs-lookup"><span data-stu-id="5f592-128">The script allows you to install the SDK in a local directory on the server, run the tools from the installed location, and then clean up (or let the CI service clean up) after the build.</span></span> <span data-ttu-id="5f592-129">这样，可以封装和隔离整个生成进程。</span><span class="sxs-lookup"><span data-stu-id="5f592-129">This provides encapsulation and isolation to your entire build process.</span></span> <span data-ttu-id="5f592-130">有关安装脚本参考，请参阅 [dotnet-install](dotnet-install-script.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="5f592-130">The installation script reference is found in the [dotnet-install](dotnet-install-script.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="5f592-131">使用安装程序脚本时，不会自动安装本机依赖项。</span><span class="sxs-lookup"><span data-stu-id="5f592-131">When using the installer script, native dependencies aren't installed automatically.</span></span> <span data-ttu-id="5f592-132">如果操作系统没有本机依赖项，必须手动安装。</span><span class="sxs-lookup"><span data-stu-id="5f592-132">You must install the native dependencies if the operating system doesn't have them.</span></span> <span data-ttu-id="5f592-133">请参阅 [.NET Core 本机先决条件](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)主题中的先决条件列表。</span><span class="sxs-lookup"><span data-stu-id="5f592-133">See the list of prerequisites in the [.NET Core native prerequisites](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) topic.</span></span>

## <a name="ci-setup-examples"></a><span data-ttu-id="5f592-134">CI 安装示例</span><span class="sxs-lookup"><span data-stu-id="5f592-134">CI setup examples</span></span>

<span data-ttu-id="5f592-135">此部分介绍了如何使用 PowerShell 或 bash 脚本进行手动安装，同时还介绍了多个服务型软件 (SaaS) CI 解决方案。</span><span class="sxs-lookup"><span data-stu-id="5f592-135">This section describes a manual setup using a PowerShell or bash script, along with a description of several software as a service (SaaS) CI solutions.</span></span> <span data-ttu-id="5f592-136">涵盖的 SaaS CI 解决方案包括 [Travis CI](https://travis-ci.org/)、[AppVeyor](https://www.appveyor.com/) 和 [Visual Studio Team Services 生成](https://docs.microsoft.com/vsts/build-release/index)。</span><span class="sxs-lookup"><span data-stu-id="5f592-136">The SaaS CI solutions covered are [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), and [Visual Studio Team Services Build](https://docs.microsoft.com/vsts/build-release/index).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="5f592-137">手动安装</span><span class="sxs-lookup"><span data-stu-id="5f592-137">Manual setup</span></span>

<span data-ttu-id="5f592-138">每个 SaaS 服务都有自己的生成进程创建和配置方法。</span><span class="sxs-lookup"><span data-stu-id="5f592-138">Each SaaS service has its own methods for creating and configuring a build process.</span></span> <span data-ttu-id="5f592-139">如果使用与所列不同的 SaaS 解决方案，或需要超越预封装支持范围的自定义设置，至少必须执行一些手动配置。</span><span class="sxs-lookup"><span data-stu-id="5f592-139">If you use different SaaS solution than those listed or require customization beyond the pre-packaged support, you must perform at least some manual configuration.</span></span>

<span data-ttu-id="5f592-140">一般来说，手动安装需要获取一个版本的工具（或最新每日版工具），再运行生成脚本。</span><span class="sxs-lookup"><span data-stu-id="5f592-140">In general, a manual setup requires you to acquire a version of the tools (or the latest nightly builds of the tools) and run your build script.</span></span> <span data-ttu-id="5f592-141">可以使用 PowerShell 或 bash 脚本安排 .NET Core 命令，也可以使用概述生成进程的项目文件。</span><span class="sxs-lookup"><span data-stu-id="5f592-141">You can use a PowerShell or bash script to orchestrate the .NET Core commands or use a project file that outlines the build process.</span></span> <span data-ttu-id="5f592-142">[业务流程部分](#orchestrating-the-build)详细介绍了这些选项。</span><span class="sxs-lookup"><span data-stu-id="5f592-142">The [orchestration section](#orchestrating-the-build) provides more detail on these options.</span></span>

<span data-ttu-id="5f592-143">创建执行手动 CI 生成服务器安装的脚本后，在开发计算机上使用它来生成本地代码以供测试。</span><span class="sxs-lookup"><span data-stu-id="5f592-143">After you create a script that performs a manual CI build server setup, use it on your dev machine to build your code locally for testing purposes.</span></span> <span data-ttu-id="5f592-144">确认此脚本可以在本地正常运行后，将它部署到 CI 生成服务器。</span><span class="sxs-lookup"><span data-stu-id="5f592-144">Once you confirm that the script is running well locally, deploy it to your CI build server.</span></span> <span data-ttu-id="5f592-145">下面展示了相对简单的 PowerShell 脚本，以说明如何获取 .NET Core SDK，并将它安装到 Windows 生成服务器上：</span><span class="sxs-lookup"><span data-stu-id="5f592-145">A relatively simple PowerShell script demonstrates how to obtain the .NET Core SDK and install it on a Windows build server:</span></span>

```powershell
$ErrorActionPreference="Stop"
$ProgressPreference="SilentlyContinue"

# $LocalDotnet is the path to the locally-installed SDK to ensure the 
#   correct version of the tools are executed.
$LocalDotnet=""
# $InstallDir and $CliVersion variables can come from options to the 
#   script.
$InstallDir = "./cli-tools"
$CliVersion = "1.0.1"

# Test the path provided by $InstallDir to confirm it exists. If it 
#   does, it's removed. This is not strictly required, but it's a 
#   good way to reset the environment.
if (Test-Path $InstallDir)
{
    rm -Recurse $InstallDir
}
New-Item -Type "directory" -Path $InstallDir

Write-Host "Downloading the CLI installer..."

# Use the Invoke-WebRequest PowerShell cmdlet to obtain the 
#   installation script and save it into the installation directory.
Invoke-WebRequest `
    -Uri "https://dot.net/v1/dotnet-install.ps1" `
    -OutFile "$InstallDir/dotnet-install.ps1"

Write-Host "Installing the CLI requested version ($CliVersion) ..."

# Install the SDK of the version specified in $CliVersion into the 
#   specified location ($InstallDir).
& $InstallDir/dotnet-install.ps1 -Version $CliVersion `
    -InstallDir $InstallDir

Write-Host "Downloading and installation of the SDK is complete."

# $LocalDotnet holds the path to dotnet.exe for future use by the 
#   script.
$LocalDotnet = "$InstallDir/dotnet"

# Run the build process now. Implement your build script here.
```

<span data-ttu-id="5f592-146">在此脚本末尾提供生成进程的实现代码。</span><span class="sxs-lookup"><span data-stu-id="5f592-146">You provide the implementation for your build process at the end of the script.</span></span> <span data-ttu-id="5f592-147">此脚本先获取工具，再执行生成进程。</span><span class="sxs-lookup"><span data-stu-id="5f592-147">The script acquires the tools and then executes your build process.</span></span> <span data-ttu-id="5f592-148">对于 UNIX 计算机，下面的 bash 脚本以类似方式执行 PowerShell 脚本中所述的操作：</span><span class="sxs-lookup"><span data-stu-id="5f592-148">For UNIX machines, the following bash script performs the actions described in the PowerShell script in a similar manner:</span></span>

```bash
#!/bin/bash
INSTALLDIR="cli-tools"
CLI_VERSION=1.0.1
DOWNLOADER=$(which curl)
if [ -d "$INSTALLDIR" ]
then
    rm -rf "$INSTALLDIR"
fi
mkdir -p "$INSTALLDIR"
echo Downloading the CLI installer.
$DOWNLOADER https://dot.net/v1/dotnet-install.sh > "$INSTALLDIR/dotnet-install.sh"
chmod +x "$INSTALLDIR/dotnet-install.sh"
echo Installing the CLI requested version $CLI_VERSION. Please wait, installation may take a few minutes.
"$INSTALLDIR/dotnet-install.sh" --install-dir "$INSTALLDIR" --version $CLI_VERSION
if [ $? -ne 0 ]
then
    echo Download of $CLI_VERSION version of the CLI failed. Exiting now.
    exit 0
fi
echo The CLI has been installed.
LOCALDOTNET="$INSTALLDIR/dotnet"
# Run the build process now. Implement your build script here.
```

### <a name="travis-ci"></a><span data-ttu-id="5f592-149">Travis CI</span><span class="sxs-lookup"><span data-stu-id="5f592-149">Travis CI</span></span>

<span data-ttu-id="5f592-150">可以将 [Travis CI](https://travis-ci.org/) 配置为使用 `csharp` 语言和 `dotnet` 键安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="5f592-150">You can configure [Travis CI](https://travis-ci.org/) to install the .NET Core SDK using the `csharp` language and the `dotnet` key.</span></span> <span data-ttu-id="5f592-151">有关详细信息，请参阅 Travis CI 官方文档[生成 C#、F# 或 Visual Basic 项目](https://docs.travis-ci.com/user/languages/csharp/)。</span><span class="sxs-lookup"><span data-stu-id="5f592-151">See the official Travis CI docs on [Building a C#, F#, or Visual Basic Project](https://docs.travis-ci.com/user/languages/csharp/) for more information.</span></span> <span data-ttu-id="5f592-152">请注意，访问 Travis CI 信息时，社区维护的 `language: csharp` 语言标识符适用于所有 .NET 语言，包括 F# 和 Mono。</span><span class="sxs-lookup"><span data-stu-id="5f592-152">Note as you access the Travis CI information that the community-maintained `language: csharp` language identifier works for all .NET languages, including F#, and Mono.</span></span>

<span data-ttu-id="5f592-153">Travis CI 可同时在生成矩阵中运行 macOS（OS X 10.11、OS X 10.12）和 Linux (Ubuntu 14.04) 作业。在生成矩阵中，可以指定运行时、环境和排除项/包含项的组合，从而涵盖应用的生成组合。</span><span class="sxs-lookup"><span data-stu-id="5f592-153">Travis CI runs both macOS (OS X 10.11, OS X 10.12) and Linux (Ubuntu 14.04) jobs in a *build matrix*, where you specify a combination of runtime, environment, and exclusions/inclusions to cover your build combinations for your app.</span></span> <span data-ttu-id="5f592-154">有关详细信息，请参阅 Travis CI 文档 [.travis.yml 示例](https://github.com/dotnet/docs/blob/master/.travis.yml)文件和[自定义生成](https://docs.travis-ci.com/user/customizing-the-build)。</span><span class="sxs-lookup"><span data-stu-id="5f592-154">See the [.travis.yml example](https://github.com/dotnet/docs/blob/master/.travis.yml) file and [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build) in the Travis CI docs for more information.</span></span> <span data-ttu-id="5f592-155">基于 MSBuild 的工具在包中添加 LTS (1.0.x) 和最新 (1.1.x) 运行时；因此，通过安装 SDK，可以收到执行生成所需的一切。</span><span class="sxs-lookup"><span data-stu-id="5f592-155">The MSBuild-based tools include the LTS (1.0.x) and Current (1.1.x) runtimes in the package; so by installing the SDK, you receive everything you need to build.</span></span>

### <a name="appveyor"></a><span data-ttu-id="5f592-156">AppVeyor</span><span class="sxs-lookup"><span data-stu-id="5f592-156">AppVeyor</span></span>

<span data-ttu-id="5f592-157">[AppVeyor](https://www.appveyor.com/) 使用 `Visual Studio 2017` 生成辅助角色映像安装 .NET Core 1.0.1 SDK。</span><span class="sxs-lookup"><span data-stu-id="5f592-157">[AppVeyor](https://www.appveyor.com/) installs the .NET Core 1.0.1 SDK with the `Visual Studio 2017` build worker image.</span></span> <span data-ttu-id="5f592-158">可以使用其他包含不同版本 .NET Core SDK 的生成映像；有关详细信息，请参阅 AppVeyor 文档中的 [appveyor.yml 示例](https://github.com/dotnet/docs/blob/master/appveyor.yml)和[生成辅助角色映像](https://www.appveyor.com/docs/build-environment/#build-worker-images)主题。</span><span class="sxs-lookup"><span data-stu-id="5f592-158">Other build images with different versions of the .NET Core SDK are available; see the [appveyor.yml example](https://github.com/dotnet/docs/blob/master/appveyor.yml) and the [Build worker images](https://www.appveyor.com/docs/build-environment/#build-worker-images) topic in the AppVeyor docs for more information.</span></span>

<span data-ttu-id="5f592-159">.NET Core SDK 二进制文件通过安装脚本下载并解压缩到子目录，再添加到 `PATH` 环境变量。</span><span class="sxs-lookup"><span data-stu-id="5f592-159">The .NET Core SDK binaries are downloaded and unzipped in a subdirectory using the install script, and then they're added to the `PATH` environment variable.</span></span> <span data-ttu-id="5f592-160">添加生成矩阵可以运行包含多个版本 .NET Core SDK 的集成测试：</span><span class="sxs-lookup"><span data-stu-id="5f592-160">Add a build matrix to run integration tests with multiple versions of the .NET Core SDK:</span></span>

```yaml
environment:
  matrix:
    - CLI_VERSION: 1.0.1
    - CLI_VERSION: Latest

install:
  # See appveyor.yml example for install script
```

### <a name="visual-studio-team-services-vsts"></a><span data-ttu-id="5f592-161">Visual Studio Team Services (VSTS)</span><span class="sxs-lookup"><span data-stu-id="5f592-161">Visual Studio Team Services (VSTS)</span></span>

<span data-ttu-id="5f592-162">将 Visual Studio Team Services (VSTS) 配置为使用以下方法之一生成 .NET Core 项目：</span><span class="sxs-lookup"><span data-stu-id="5f592-162">Configure Visual Studio Team Services (VSTS) to build .NET Core projects using one of these approaches:</span></span>

1. <span data-ttu-id="5f592-163">使用命令运行[手动安装步骤](#manual-setup)中的脚本。</span><span class="sxs-lookup"><span data-stu-id="5f592-163">Run the script from the [manual setup step](#manual-setup) using your commands.</span></span>
1. <span data-ttu-id="5f592-164">创建包含多个 VSTS 内置生成任务的生成，这些任务被配置为使用 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="5f592-164">Create a build composed of several VSTS built-in build tasks that are configured to use .NET Core tools.</span></span>

<span data-ttu-id="5f592-165">这两种均为有效解决方案。</span><span class="sxs-lookup"><span data-stu-id="5f592-165">Both solutions are valid.</span></span> <span data-ttu-id="5f592-166">使用手动安装脚本，可以控制收到的工具版本，因为工具是作为生成的一部分进行下载。</span><span class="sxs-lookup"><span data-stu-id="5f592-166">Using a manual setup script, you control the version of the tools that you receive, since you download them as part of the build.</span></span> <span data-ttu-id="5f592-167">此生成是通过必须创建的脚本进行运行。</span><span class="sxs-lookup"><span data-stu-id="5f592-167">The build is run from a script that you must create.</span></span> <span data-ttu-id="5f592-168">本主题仅涉及手动选项。</span><span class="sxs-lookup"><span data-stu-id="5f592-168">This topic only covers the manual option.</span></span> <span data-ttu-id="5f592-169">若要详细了解如何撰写包含 VSTS 生成任务的生成，请参阅 VSTS [持续集成和部署](https://docs.microsoft.com/vsts/build-release/index)主题。</span><span class="sxs-lookup"><span data-stu-id="5f592-169">For more information on composing a build with VSTS build tasks, visit the VSTS [Continuous integration and deployment](https://docs.microsoft.com/vsts/build-release/index) topic.</span></span>

<span data-ttu-id="5f592-170">若要在 VSTS 中使用手动安装脚本，请新建生成定义，并指定要对生成步骤运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="5f592-170">To use a manual setup script in VSTS, create a new build definition and specify the script to run for the build step.</span></span> <span data-ttu-id="5f592-171">为此，请使用 VSTS 用户界面：</span><span class="sxs-lookup"><span data-stu-id="5f592-171">This is accomplished using the VSTS user interface:</span></span>

1. <span data-ttu-id="5f592-172">首先，新建生成定义。</span><span class="sxs-lookup"><span data-stu-id="5f592-172">Start by creating a new build definition.</span></span> <span data-ttu-id="5f592-173">到达可以定义要创建的生成类型的屏幕后，选择“空”选项。</span><span class="sxs-lookup"><span data-stu-id="5f592-173">Once you reach the screen that provides you an option to define what kind of a build you wish to create, select the **Empty** option.</span></span>

   ![选择空的生成定义](./media/using-ci-with-cli/screen1.png)

1. <span data-ttu-id="5f592-175">配置要生成的存储库后，将转到生成定义。</span><span class="sxs-lookup"><span data-stu-id="5f592-175">After configuring the repository to build, you're directed to the build definitions.</span></span> <span data-ttu-id="5f592-176">选择“添加生成步骤”：</span><span class="sxs-lookup"><span data-stu-id="5f592-176">Select **Add build step**:</span></span>

   ![添加生成步骤](./media/using-ci-with-cli/screen2.png)

1. <span data-ttu-id="5f592-178">此时，系统会显示“任务目录”。</span><span class="sxs-lookup"><span data-stu-id="5f592-178">You're presented with the **Task catalog**.</span></span> <span data-ttu-id="5f592-179">此目录包含在生成中使用的任务。</span><span class="sxs-lookup"><span data-stu-id="5f592-179">The catalog contains tasks that you use in the build.</span></span> <span data-ttu-id="5f592-180">由于已有脚本，因此选择“PowerShell:运行 PowerShell 脚本”旁边的“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="5f592-180">Since you have a script, select the **Add** button for **PowerShell: Run a PowerShell script**.</span></span>

   ![添加 PowerShell 脚本步骤](./media/using-ci-with-cli/screen3.png)

1. <span data-ttu-id="5f592-182">配置生成步骤。</span><span class="sxs-lookup"><span data-stu-id="5f592-182">Configure the build step.</span></span> <span data-ttu-id="5f592-183">从要生成的存储库中添加脚本：</span><span class="sxs-lookup"><span data-stu-id="5f592-183">Add the script from the repository that you're building:</span></span>

   ![指定要运行的 PowerShell 脚本](./media/using-ci-with-cli/screen4.png)

## <a name="orchestrating-the-build"></a><span data-ttu-id="5f592-185">安排生成</span><span class="sxs-lookup"><span data-stu-id="5f592-185">Orchestrating the build</span></span>

<span data-ttu-id="5f592-186">本文档的大部分内容介绍了如何获取 .NET Core 工具和配置各种 CI 服务，并未介绍如何安排或实际生成 .NET Core 代码。</span><span class="sxs-lookup"><span data-stu-id="5f592-186">Most of this document describes how to acquire the .NET Core tools and configure various CI services without providing information on how to orchestrate, or *actually build*, your code with .NET Core.</span></span> <span data-ttu-id="5f592-187">具体如何构建生成进程取决于许多因素，我们无法在本文中笼统概述。</span><span class="sxs-lookup"><span data-stu-id="5f592-187">The choices on how to structure the build process depend on many factors that cannot be covered in a general way here.</span></span> <span data-ttu-id="5f592-188">请浏览 [Travis CI](https://travis-ci.org/)、[AppVeyor](https://www.appveyor.com/) 和 [VSTS](https://docs.microsoft.com/vsts/build-release/index) 文档集中提供的资源和示例，详细了解如何使用每种技术安排生成。</span><span class="sxs-lookup"><span data-stu-id="5f592-188">Explore the resources and samples provided in the documentation sets of [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), and [VSTS](https://docs.microsoft.com/vsts/build-release/index) for more information on orchestrating your builds with each technology.</span></span>

<span data-ttu-id="5f592-189">使用 .NET Core 工具构建 .NET Core 代码生成进程的两种常规方法是，直接使用 MSBuild 或使用 .NET Core 命令行命令。</span><span class="sxs-lookup"><span data-stu-id="5f592-189">Two general approaches that you take in structuring the build process for .NET Core code using the .NET Core tools are using MSBuild directly or using the .NET Core command-line commands.</span></span> <span data-ttu-id="5f592-190">应采用哪种方法取决于对方法的熟悉程度和复杂性取舍。</span><span class="sxs-lookup"><span data-stu-id="5f592-190">Which approach you should take is determined by your comfort level with the approaches and trade-offs in complexity.</span></span> <span data-ttu-id="5f592-191">使用 MSBuild，可以将生成进程表达为任务和目标，但需要学习 MSBuild 项目文件语法，这增加了复杂性。</span><span class="sxs-lookup"><span data-stu-id="5f592-191">MSBuild provides you the ability to express your build process as tasks and targets, but it comes with the added complexity of learning MSBuild project file syntax.</span></span> <span data-ttu-id="5f592-192">使用 .NET Core 命令行工具可能更为简单，但需要在 `bash` 或 PowerShell 等脚本语言中编写业务流程逻辑。</span><span class="sxs-lookup"><span data-stu-id="5f592-192">Using the .NET Core command-line tools is perhaps simpler, but it requires you to write orchestration logic in a scripting language like `bash` or PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f592-193">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f592-193">See also</span></span>

[<span data-ttu-id="5f592-194">Ubuntu 获取步骤</span><span class="sxs-lookup"><span data-stu-id="5f592-194">Ubuntu acquisition steps</span></span>](https://www.microsoft.com/net/core#linuxubuntu)   
