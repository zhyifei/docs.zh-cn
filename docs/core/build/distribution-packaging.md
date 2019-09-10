---
title: .NET Core 分发打包
description: 了解如何为 .NET Core 打包、命名并进行版本控制以进行分发。
author: tmds
ms.date: 03/02/2018
ms.custom: seodec18
ms.openlocfilehash: d72677cba1e7685f8e05cf479ec508683dd77b55
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70394162"
---
# <a name="net-core-distribution-packaging"></a><span data-ttu-id="3a633-103">.NET Core 分发打包</span><span class="sxs-lookup"><span data-stu-id="3a633-103">.NET Core distribution packaging</span></span>

<span data-ttu-id="3a633-104">由于 .NET Core 现已可用于更多平台，因此了解如何为其打包、命名并进行版本控制将很有用。</span><span class="sxs-lookup"><span data-stu-id="3a633-104">As .NET Core becomes available on more and more platforms, it's useful to learn how to package, name, and version it.</span></span> <span data-ttu-id="3a633-105">这样，无论用户选择在哪里运行 .NET，包维护人员均可以帮助确保获得一致的体验。</span><span class="sxs-lookup"><span data-stu-id="3a633-105">This way, package maintainers can help ensure a consistent experience no matter where users choose to run .NET.</span></span> <span data-ttu-id="3a633-106">本文对以下用户非常有用：</span><span class="sxs-lookup"><span data-stu-id="3a633-106">This article is useful for users that are:</span></span>

- <span data-ttu-id="3a633-107">尝试从源生成 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="3a633-107">Attempting to build .NET Core from source.</span></span>
- <span data-ttu-id="3a633-108">想要更改 .NET Core CLI，但更改可能会影响生成的布局或包。</span><span class="sxs-lookup"><span data-stu-id="3a633-108">Wanting to make changes to the .NET Core CLI that could impact the resulting layout or packages produced.</span></span>

## <a name="disk-layout"></a><span data-ttu-id="3a633-109">磁盘布局</span><span class="sxs-lookup"><span data-stu-id="3a633-109">Disk layout</span></span>

<span data-ttu-id="3a633-110">安装时，.NET Core 包含一些组件，这些组件在文件系统中排列如下：</span><span class="sxs-lookup"><span data-stu-id="3a633-110">When installed, .NET Core consists of several components that are laid out as follows in the filesystem:</span></span>

```
.
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host
│   └── fxr
│       └── <fxr version>        (2)
├── sdk
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)
├── packs
│   ├── Microsoft.AspNetCore.App.Ref
│   │   └── <aspnetcore ref version>     (11)
│   ├── Microsoft.NETCore.App.Ref
│   │   └── <netcore ref version>        (12)
│   ├── Microsoft.NETCore.App.Host.<rid>
│   │   └── <apphost version>            (13)
│   ├── Microsoft.WindowsDesktop.App.Ref
│   │   └── <desktop ref version>        (14)
│   └── NETStandard.Library.Ref
│       └── <netstandard version>        (15)
├── shared
│   ├── Microsoft.NETCore.App
│   │   └── <runtime version>     (5)
│   ├── Microsoft.AspNetCore.App
│   │   └── <aspnetcore version>  (6)
│   ├── Microsoft.AspNetCore.All
│   │   └── <aspnetcore version>  (6)
│   └── Microsoft.WindowsDesktop.App
│       └── <desktop app version> (7)
└── templates
│   └── <templates version>      (17)
/
├── etc/dotnet
│       └── install_location     (16)
├── usr/share/man/man1
│       └── dotnet.1.gz          (9)
└── usr/bin
        └── dotnet               (10)
```

- <span data-ttu-id="3a633-111">(1) **dotnet** 主机（也称为“muxer”）有两个不同角色：激活运行时以启动应用程序，及激活 SDK 以向其分派命令。</span><span class="sxs-lookup"><span data-stu-id="3a633-111">(1) **dotnet** The host (also known as the "muxer") has two distinct roles: activate a runtime to launch an application, and activate an SDK to dispatch commands to it.</span></span> <span data-ttu-id="3a633-112">主机是本机可执行文件 (`dotnet.exe`)。</span><span class="sxs-lookup"><span data-stu-id="3a633-112">The host is a native executable (`dotnet.exe`).</span></span>

<span data-ttu-id="3a633-113">主机只有一个，不过大部分的其他组件都在带有版本的目录中（2、3、5 和 6）。</span><span class="sxs-lookup"><span data-stu-id="3a633-113">While there's a single host, most of the other components are in versioned directories (2,3,5,6).</span></span> <span data-ttu-id="3a633-114">这意味着系统上可存在多个版本，因为它们是并排安装的。</span><span class="sxs-lookup"><span data-stu-id="3a633-114">This means multiple versions can be present on the system since they're installed side by side.</span></span>

- <span data-ttu-id="3a633-115">(2) **host/fxr/\<fxr version>** 包含了主机所使用的框架解析逻辑。</span><span class="sxs-lookup"><span data-stu-id="3a633-115">(2) **host/fxr/\<fxr version>** contains the framework resolution logic used by the host.</span></span> <span data-ttu-id="3a633-116">主机采用已安装的最新 hostfxr。</span><span class="sxs-lookup"><span data-stu-id="3a633-116">The host uses the latest hostfxr that is installed.</span></span> <span data-ttu-id="3a633-117">在执行 .NET Core 应用程序时，hostfxr 负责选择合适的运行时。</span><span class="sxs-lookup"><span data-stu-id="3a633-117">The hostfxr is responsible for selecting the appropriate runtime when executing a .NET Core application.</span></span> <span data-ttu-id="3a633-118">例如，为 .NET Core 2.0.0 生成的应用程序会使用 2.0.5 运行时（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="3a633-118">For example, an application built for .NET Core 2.0.0 uses the 2.0.5 runtime when it's available.</span></span> <span data-ttu-id="3a633-119">同样，hostfxr 在开发期间也会选择适当的 SDK。</span><span class="sxs-lookup"><span data-stu-id="3a633-119">Similarly, hostfxr selects the appropriate SDK during development.</span></span>

- <span data-ttu-id="3a633-120">(3) **sdk/\<sdk version>** SDK（也称为“工具”）是一组托管工具，可用于编写和生成 .NET Core 库和应用程序。</span><span class="sxs-lookup"><span data-stu-id="3a633-120">(3) **sdk/\<sdk version>** The SDK (also known as "the tooling") is a set of managed tools that are used to write and build .NET Core libraries and applications.</span></span> <span data-ttu-id="3a633-121">SDK 包括 .NET Core 命令行接口 (CLI)、托管的语言编译器、MSBuild 及相关生成任务和目标、NuGet、新项目模板等。</span><span class="sxs-lookup"><span data-stu-id="3a633-121">The SDK includes the .NET Core Command-line interface (CLI), the managed languages compilers, MSBuild, and associated build tasks and targets, NuGet, new project templates, and so on.</span></span>

- <span data-ttu-id="3a633-122">(4) **sdk/NuGetFallbackFolder** 包含 SDK 在还原操作期间使用的 NuGet 包的缓存，例如在运行 `dotnet restore` 或 `dotnet build /t:Restore` 时。</span><span class="sxs-lookup"><span data-stu-id="3a633-122">(4) **sdk/NuGetFallbackFolder** contains a cache of NuGet packages used by an SDK during the restore operation, such as when running `dotnet restore` or `dotnet build /t:Restore`.</span></span> <span data-ttu-id="3a633-123">此文件夹仅在 .NET Core 3.0 之前使用。</span><span class="sxs-lookup"><span data-stu-id="3a633-123">This folder is only used prior to .NET Core 3.0.</span></span> <span data-ttu-id="3a633-124">不能从源生成它，因为它包含来自 `nuget.org` 的预构建二进制资产。</span><span class="sxs-lookup"><span data-stu-id="3a633-124">It can't be built from source, because it contains prebuilt binary assets from `nuget.org`.</span></span>

<span data-ttu-id="3a633-125">“共享”  文件夹包含框架。</span><span class="sxs-lookup"><span data-stu-id="3a633-125">The **shared** folder contains frameworks.</span></span> <span data-ttu-id="3a633-126">共享框架提供一组位于中心位置的库，从而让不同的应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="3a633-126">A shared framework provides a set of libraries at a central location so they can be used by different applications.</span></span>

- <span data-ttu-id="3a633-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** 此框架包含.NET Core 运行时和支持托管库。</span><span class="sxs-lookup"><span data-stu-id="3a633-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** This framework contains the .NET Core runtime and supporting managed libraries.</span></span>

- <span data-ttu-id="3a633-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** 包含 ASP.NET Core 库。</span><span class="sxs-lookup"><span data-stu-id="3a633-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** contains the ASP.NET Core libraries.</span></span> <span data-ttu-id="3a633-129">已开发且支持 `Microsoft.AspNetCore.App` 下的库（作为 .NET Core 项目的一部分）。</span><span class="sxs-lookup"><span data-stu-id="3a633-129">The libraries under `Microsoft.AspNetCore.App` are developed and supported as part of the .NET Core project.</span></span> <span data-ttu-id="3a633-130">`Microsoft.AspNetCore.All` 下的库是一个超集，其中还包含第三方库。</span><span class="sxs-lookup"><span data-stu-id="3a633-130">The libraries under `Microsoft.AspNetCore.All` are a superset that also contains third-party libraries.</span></span>

- <span data-ttu-id="3a633-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** 包含 Windows 桌面库。</span><span class="sxs-lookup"><span data-stu-id="3a633-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** contains the Windows desktop libraries.</span></span> <span data-ttu-id="3a633-132">在非 Windows 平台上不包含此项。</span><span class="sxs-lookup"><span data-stu-id="3a633-132">This isn't included on non-Windows platforms.</span></span>

- <span data-ttu-id="3a633-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** 分别是 .NET Core 许可证和 .NET Core 中使用的第三方库的许可证。</span><span class="sxs-lookup"><span data-stu-id="3a633-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** are the .NET Core license and licenses of third-party libraries used in .NET Core, respectively.</span></span>

- <span data-ttu-id="3a633-134">(9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` 是 dotnet 手册页。</span><span class="sxs-lookup"><span data-stu-id="3a633-134">(9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` is the dotnet manual page.</span></span> <span data-ttu-id="3a633-135">`dotnet` 是指向 dotnet 主机 (1) 的符号链接。</span><span class="sxs-lookup"><span data-stu-id="3a633-135">`dotnet` is a symlink to the dotnet host(1).</span></span> <span data-ttu-id="3a633-136">这些文件安装在已知位置用于系统集成。</span><span class="sxs-lookup"><span data-stu-id="3a633-136">These files are installed at well known locations for system integration.</span></span>

- <span data-ttu-id="3a633-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** 分别描述了 `x.y` 版本 .NET Core 和 ASP.NET Core 的 API。</span><span class="sxs-lookup"><span data-stu-id="3a633-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** describe the API of an `x.y` version of .NET Core and ASP.NET Core respectively.</span></span> <span data-ttu-id="3a633-138">针对这些目标版本进行编译时，将使用这些包。</span><span class="sxs-lookup"><span data-stu-id="3a633-138">These packs are used when compiling for those target versions.</span></span>

- <span data-ttu-id="3a633-139">(13) **Microsoft.NETCore.App.Host.\<rid>** 包含平台 `rid` 的本机二进制文件。</span><span class="sxs-lookup"><span data-stu-id="3a633-139">(13) **Microsoft.NETCore.App.Host.\<rid>** contains a native binary for platform `rid`.</span></span> <span data-ttu-id="3a633-140">将 .NET Core 应用程序编译为适用于该平台的本机二进制文件时，将使用此二进制文件作为模板。</span><span class="sxs-lookup"><span data-stu-id="3a633-140">This binary is a template when compiling a .NET Core application into a native binary for that platform.</span></span>

- <span data-ttu-id="3a633-141">(14) **Microsoft.WindowsDesktop.App.Ref** 介绍 Windows 桌面应用程序 `x.y` 版本的 API。</span><span class="sxs-lookup"><span data-stu-id="3a633-141">(14) **Microsoft.WindowsDesktop.App.Ref** describes the API of `x.y` version of Windows Desktop applications.</span></span> <span data-ttu-id="3a633-142">在针对该目标进行编译时，将使用这些文件。</span><span class="sxs-lookup"><span data-stu-id="3a633-142">These files are used when compiling for that target.</span></span> <span data-ttu-id="3a633-143">在非 Windows 平台上不提供此项。</span><span class="sxs-lookup"><span data-stu-id="3a633-143">This isn't provided on non-Windows platforms.</span></span>

- <span data-ttu-id="3a633-144">(15) **NETStandard.Library.Ref** 描述了 netstandard `x.y` API。</span><span class="sxs-lookup"><span data-stu-id="3a633-144">(15) **NETStandard.Library.Ref** describes the netstandard `x.y` API.</span></span> <span data-ttu-id="3a633-145">在针对该目标进行编译时，将使用这些文件。</span><span class="sxs-lookup"><span data-stu-id="3a633-145">These files are used when compiling for that target.</span></span>

- <span data-ttu-id="3a633-146">(16) **/etc/dotnet/install_location** 文件包含 `dotnet` 主机二进制文件所在文件夹的完整路径。</span><span class="sxs-lookup"><span data-stu-id="3a633-146">(16) **/etc/dotnet/install_location** is a file that contains the full path to the folder that contains the `dotnet` host binary.</span></span> <span data-ttu-id="3a633-147">可以换行符终止路径。</span><span class="sxs-lookup"><span data-stu-id="3a633-147">The path may be terminated with a newline.</span></span> <span data-ttu-id="3a633-148">根路径为 `/usr/share/dotnet` 时无需添加此文件。</span><span class="sxs-lookup"><span data-stu-id="3a633-148">It's not necessary to add this file when the root is `/usr/share/dotnet`.</span></span>

- <span data-ttu-id="3a633-149">(17) templates  包含 SDK 使用的模板。</span><span class="sxs-lookup"><span data-stu-id="3a633-149">(17) **templates** contains the templates used by the SDK.</span></span> <span data-ttu-id="3a633-150">例如，`dotnet new` 在此处查找项目模板。</span><span class="sxs-lookup"><span data-stu-id="3a633-150">For example, `dotnet new` finds project templates here.</span></span>

## <a name="recommended-packages"></a><span data-ttu-id="3a633-151">推荐的包</span><span class="sxs-lookup"><span data-stu-id="3a633-151">Recommended packages</span></span>

<span data-ttu-id="3a633-152">.NET Core 版本控制基于运行时组件 `[major].[minor]` 版本号。</span><span class="sxs-lookup"><span data-stu-id="3a633-152">.NET Core versioning is based on the runtime component `[major].[minor]` version numbers.</span></span>
<span data-ttu-id="3a633-153">SDK 版本采用相同的 `[major].[minor]`，并有一个独立的 `[patch]`，它为 SDK 合并了功能和修补语义。</span><span class="sxs-lookup"><span data-stu-id="3a633-153">The SDK version uses the same `[major].[minor]` and has an independent `[patch]` that combines feature and patch semantics for the SDK.</span></span>
<span data-ttu-id="3a633-154">例如:SDK 版本 2.2.302 是支持 2.2 运行时的 SDK 的第 3 个功能版本的第 2 个补丁版本。</span><span class="sxs-lookup"><span data-stu-id="3a633-154">For example: SDK version 2.2.302 is the second patch release of the third feature release of the SDK that supports the 2.2 runtime.</span></span> <span data-ttu-id="3a633-155">有关版本控制的工作原理的详细信息，请参阅 [.NET Core 版本控制概述](../versions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="3a633-155">For more information about how versioning works, see [.NET Core versioning overview](../versions/index.md).</span></span>

<span data-ttu-id="3a633-156">一些包在自己的名称中就包含一部分版本号。</span><span class="sxs-lookup"><span data-stu-id="3a633-156">Some of the packages include part of the version number in their name.</span></span> <span data-ttu-id="3a633-157">这允许你安装特定版本。</span><span class="sxs-lookup"><span data-stu-id="3a633-157">This allows you to install a specific version.</span></span>
<span data-ttu-id="3a633-158">版本名称中不包含版本的剩余部分。</span><span class="sxs-lookup"><span data-stu-id="3a633-158">The rest of the version isn't included in the version name.</span></span> <span data-ttu-id="3a633-159">这允许 OS 包管理器更新这些包（例如，自动安装安全修补程序）。</span><span class="sxs-lookup"><span data-stu-id="3a633-159">This allows the OS package manager to update the packages (for example, automatically installing security fixes).</span></span> <span data-ttu-id="3a633-160">支持的包管理器特定于 Linux。</span><span class="sxs-lookup"><span data-stu-id="3a633-160">Supported package managers are Linux specific.</span></span>

<span data-ttu-id="3a633-161">下面列出了推荐的包：</span><span class="sxs-lookup"><span data-stu-id="3a633-161">The following lists the recommended packages:</span></span>

- <span data-ttu-id="3a633-162">`dotnet-sdk-[major].[minor]` - 安装特定运行时的最新 SDK</span><span class="sxs-lookup"><span data-stu-id="3a633-162">`dotnet-sdk-[major].[minor]` - Installs the latest sdk for specific runtime</span></span>
  - <span data-ttu-id="3a633-163">**版本：** \<运行时版本></span><span class="sxs-lookup"><span data-stu-id="3a633-163">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="3a633-164">**示例：** dotnet-sdk-2.1</span><span class="sxs-lookup"><span data-stu-id="3a633-164">**Example:** dotnet-sdk-2.1</span></span>
  - <span data-ttu-id="3a633-165">**包含：** (3),(4)</span><span class="sxs-lookup"><span data-stu-id="3a633-165">**Contains:** (3),(4)</span></span>
  - <span data-ttu-id="3a633-166">**依赖项：** `aspnetcore-runtime-[major].[minor]`、`dotnet-targeting-pack-[major].[minor]`、`aspnetcore-targeting-pack-[major].[minor]`、`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`、`dotnet-apphost-pack-[major].[minor]`、`dotnet-templates-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="3a633-166">**Dependencies:** `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span></span>

- <span data-ttu-id="3a633-167">`aspnetcore-runtime-[major].[minor]` - 安装特定 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="3a633-167">`aspnetcore-runtime-[major].[minor]` - Installs a specific ASP.NET Core runtime</span></span>
  - <span data-ttu-id="3a633-168">**版本：** \<aspnetcore 运行时版本></span><span class="sxs-lookup"><span data-stu-id="3a633-168">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="3a633-169">**示例：** aspnetcore-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="3a633-169">**Example:** aspnetcore-runtime-2.1</span></span>
  - <span data-ttu-id="3a633-170">**包含：** (6)</span><span class="sxs-lookup"><span data-stu-id="3a633-170">**Contains:** (6)</span></span>
  - <span data-ttu-id="3a633-171">**依赖项：** `dotnet-runtime-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="3a633-171">**Dependencies:** `dotnet-runtime-[major].[minor]`</span></span>

- <span data-ttu-id="3a633-172">`dotnet-runtime-deps-[major].[minor]` _（可选）_ - 安装运行自包含应用程序的依赖项</span><span class="sxs-lookup"><span data-stu-id="3a633-172">`dotnet-runtime-deps-[major].[minor]` _(Optional)_ - Installs the dependencies for running self-contained applications</span></span>
  - <span data-ttu-id="3a633-173">**版本：** \<运行时版本></span><span class="sxs-lookup"><span data-stu-id="3a633-173">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="3a633-174">**示例：** dotnet-runtime-deps-2.1</span><span class="sxs-lookup"><span data-stu-id="3a633-174">**Example:** dotnet-runtime-deps-2.1</span></span>
  - <span data-ttu-id="3a633-175">**依赖项：** _发行版特定依赖项_</span><span class="sxs-lookup"><span data-stu-id="3a633-175">**Dependencies:** _distro specific dependencies_</span></span>

- <span data-ttu-id="3a633-176">`dotnet-runtime-[major].[minor]` - 安装特定运行时</span><span class="sxs-lookup"><span data-stu-id="3a633-176">`dotnet-runtime-[major].[minor]` - Installs a specific runtime</span></span>
  - <span data-ttu-id="3a633-177">**版本：** \<运行时版本></span><span class="sxs-lookup"><span data-stu-id="3a633-177">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="3a633-178">**示例：** dotnet-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="3a633-178">**Example:** dotnet-runtime-2.1</span></span>
  - <span data-ttu-id="3a633-179">**包含：** (5)</span><span class="sxs-lookup"><span data-stu-id="3a633-179">**Contains:** (5)</span></span>
  - <span data-ttu-id="3a633-180">**依赖项：** `dotnet-hostfxr:<runtime version>+`、`dotnet-runtime-deps-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="3a633-180">**Dependencies:** `dotnet-hostfxr:<runtime version>+`, `dotnet-runtime-deps-[major].[minor]`</span></span>

- <span data-ttu-id="3a633-181">`dotnet-hostfxr` - 依赖项</span><span class="sxs-lookup"><span data-stu-id="3a633-181">`dotnet-hostfxr` - dependency</span></span>
  - <span data-ttu-id="3a633-182">**版本：** \<运行时版本></span><span class="sxs-lookup"><span data-stu-id="3a633-182">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="3a633-183">**示例：** dotnet-hostfxr</span><span class="sxs-lookup"><span data-stu-id="3a633-183">**Example:** dotnet-hostfxr</span></span>
  - <span data-ttu-id="3a633-184">**包含：** (2)</span><span class="sxs-lookup"><span data-stu-id="3a633-184">**Contains:** (2)</span></span>
  - <span data-ttu-id="3a633-185">**依赖项：** `host:<runtime version>+`</span><span class="sxs-lookup"><span data-stu-id="3a633-185">**Dependencies:** `host:<runtime version>+`</span></span>

- <span data-ttu-id="3a633-186">`dotnet-host` - 依赖项</span><span class="sxs-lookup"><span data-stu-id="3a633-186">`dotnet-host` - dependency</span></span>
  - <span data-ttu-id="3a633-187">**版本：** \<运行时版本></span><span class="sxs-lookup"><span data-stu-id="3a633-187">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="3a633-188">**示例：** dotnet-host</span><span class="sxs-lookup"><span data-stu-id="3a633-188">**Example:** dotnet-host</span></span>
  - <span data-ttu-id="3a633-189">**包含：** (1),(8),(9),(10),(16)</span><span class="sxs-lookup"><span data-stu-id="3a633-189">**Contains:** (1),(8),(9),(10),(16)</span></span>

- <span data-ttu-id="3a633-190">`dotnet-apphost-pack-[major].[minor]` - 依赖项</span><span class="sxs-lookup"><span data-stu-id="3a633-190">`dotnet-apphost-pack-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="3a633-191">**版本：** \<运行时版本></span><span class="sxs-lookup"><span data-stu-id="3a633-191">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="3a633-192">**包含：** (13)</span><span class="sxs-lookup"><span data-stu-id="3a633-192">**Contains:** (13)</span></span>

- <span data-ttu-id="3a633-193">`dotnet-targeting-pack-[major].[minor]` - 允许面向非最新的运行时</span><span class="sxs-lookup"><span data-stu-id="3a633-193">`dotnet-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="3a633-194">**版本：** \<运行时版本></span><span class="sxs-lookup"><span data-stu-id="3a633-194">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="3a633-195">**包含：** (12)</span><span class="sxs-lookup"><span data-stu-id="3a633-195">**Contains:** (12)</span></span>

- <span data-ttu-id="3a633-196">`aspnetcore-targeting-pack-[major].[minor]` - 允许面向非最新的运行时</span><span class="sxs-lookup"><span data-stu-id="3a633-196">`aspnetcore-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="3a633-197">**版本：** \<aspnetcore 运行时版本></span><span class="sxs-lookup"><span data-stu-id="3a633-197">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="3a633-198">**包含：** (11)</span><span class="sxs-lookup"><span data-stu-id="3a633-198">**Contains:** (11)</span></span>

- <span data-ttu-id="3a633-199">`netstandard-targeting-pack-[major].[minor]` - 允许面向 netstandard 版本</span><span class="sxs-lookup"><span data-stu-id="3a633-199">`netstandard-targeting-pack-[major].[minor]` - Allows targeting a netstandard version</span></span>
  - <span data-ttu-id="3a633-200">**版本：** \<sdk 版本></span><span class="sxs-lookup"><span data-stu-id="3a633-200">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="3a633-201">**包含：** (15)</span><span class="sxs-lookup"><span data-stu-id="3a633-201">**Contains:** (15)</span></span>

- `dotnet-templates-[major].[minor]`
  - <span data-ttu-id="3a633-202">**版本：** \<sdk 版本></span><span class="sxs-lookup"><span data-stu-id="3a633-202">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="3a633-203">**包含：** (15)</span><span class="sxs-lookup"><span data-stu-id="3a633-203">**Contains:** (15)</span></span>

<span data-ttu-id="3a633-204">`dotnet-runtime-deps-[major].[minor]` 要求理解_发行版特定依赖项_。</span><span class="sxs-lookup"><span data-stu-id="3a633-204">The `dotnet-runtime-deps-[major].[minor]` requires understanding the _distro specific dependencies_.</span></span> <span data-ttu-id="3a633-205">因为发行版生成系统可能能够自动派生包，所以包是可选的，如果选择，会将这些依赖项直接添加到 `dotnet-runtime-[major].[minor]` 包中。</span><span class="sxs-lookup"><span data-stu-id="3a633-205">Because the distro build system may be able to derive this automatically, the package is optional, in which case these dependencies are added directly to the `dotnet-runtime-[major].[minor]` package.</span></span>

<span data-ttu-id="3a633-206">当包内容位于受版本控制的文件夹下时，包名称 `[major].[minor]` 与受版本控制的文件夹名称匹配。</span><span class="sxs-lookup"><span data-stu-id="3a633-206">When package content is under a versioned folder, the package name `[major].[minor]` match the versioned folder name.</span></span> <span data-ttu-id="3a633-207">对于所有包（除 `netstandard-targeting-pack-[major].[minor]` 外），这也与 .NET Core 版本匹配。</span><span class="sxs-lookup"><span data-stu-id="3a633-207">For all packages, except the `netstandard-targeting-pack-[major].[minor]`, this also matches with the .NET Core version.</span></span>

<span data-ttu-id="3a633-208">包间的依赖关系应使用“等于或大于”  版本要求。</span><span class="sxs-lookup"><span data-stu-id="3a633-208">Dependencies between packages should use a _equal or greater than_ version requirement.</span></span> <span data-ttu-id="3a633-209">例如，`dotnet-sdk-2.2:2.2.401` 要求 `aspnetcore-runtime-2.2 >= 2.2.6`。</span><span class="sxs-lookup"><span data-stu-id="3a633-209">For example, `dotnet-sdk-2.2:2.2.401` requires `aspnetcore-runtime-2.2 >= 2.2.6`.</span></span> <span data-ttu-id="3a633-210">这使用户可以通过根包（例如 `dnf update dotnet-sdk-2.2`）升级其安装。</span><span class="sxs-lookup"><span data-stu-id="3a633-210">This makes it possible for the user to upgrade their installation via a root package (e.g. `dnf update dotnet-sdk-2.2`).</span></span>

<span data-ttu-id="3a633-211">大多数分发都需要从源中构建所有项目。</span><span class="sxs-lookup"><span data-stu-id="3a633-211">Most distributions require all artifacts to be built from source.</span></span> <span data-ttu-id="3a633-212">这对包有一些影响：</span><span class="sxs-lookup"><span data-stu-id="3a633-212">This has some impact on the packages:</span></span>

- <span data-ttu-id="3a633-213">不能简单地从源生成 `shared/Microsoft.AspNetCore.All` 下的第三方库。</span><span class="sxs-lookup"><span data-stu-id="3a633-213">The third-party libraries under `shared/Microsoft.AspNetCore.All` can't be easily built from source.</span></span> <span data-ttu-id="3a633-214">因此 `aspnetcore-runtime` 包中省略了该文件夹。</span><span class="sxs-lookup"><span data-stu-id="3a633-214">So that folder is omitted from the `aspnetcore-runtime` package.</span></span>

- <span data-ttu-id="3a633-215">使用 `nuget.org` 中的二进制项目填充了 `NuGetFallbackFolder`。</span><span class="sxs-lookup"><span data-stu-id="3a633-215">The `NuGetFallbackFolder` is populated using binary artifacts from `nuget.org`.</span></span> <span data-ttu-id="3a633-216">它应保留为空。</span><span class="sxs-lookup"><span data-stu-id="3a633-216">It should remain empty.</span></span>

<span data-ttu-id="3a633-217">多个 `dotnet-sdk` 包可能会为 `NuGetFallbackFolder` 提供同样的文件。</span><span class="sxs-lookup"><span data-stu-id="3a633-217">Multiple `dotnet-sdk` packages may provide the same files for the `NuGetFallbackFolder`.</span></span> <span data-ttu-id="3a633-218">若要避免包管理器出现问题，这些文件应完全相同（包括校验和、修改日期等等）。</span><span class="sxs-lookup"><span data-stu-id="3a633-218">To avoid issues with the package manager, these files should be identical (checksum, modification date, and so on).</span></span>

## <a name="building-packages"></a><span data-ttu-id="3a633-219">生成包</span><span class="sxs-lookup"><span data-stu-id="3a633-219">Building packages</span></span>

<span data-ttu-id="3a633-220">[dotnet/source-build](https://github.com/dotnet/source-build) 存储库中说明了如何生成 .NET Core SDK 的源 tarball 及其所有组件。</span><span class="sxs-lookup"><span data-stu-id="3a633-220">The [dotnet/source-build](https://github.com/dotnet/source-build) repository provides instructions on how to build a source tarball of the .NET Core SDK and all its components.</span></span> <span data-ttu-id="3a633-221">源版本存储库中的输出内容符合本文第一部分中所描述的布局。</span><span class="sxs-lookup"><span data-stu-id="3a633-221">The output of the source-build repository matches the layout described in the first section of this article.</span></span>
