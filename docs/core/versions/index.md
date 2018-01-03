---
title: ".NET Core 版本控制"
description: "了解 .NET Core 版本控制的工作原理。"
author: bleroy
ms.author: mairaw
ms.date: 08/25/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: f6f684b1-1d2c-4105-8376-7c1959e23803
ms.workload: dotnetcore
ms.openlocfilehash: 369d280268123a69ae9458a2c47e45396728deb5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="net-core-versioning"></a><span data-ttu-id="b9a9e-103">.NET Core 版本控制</span><span class="sxs-lookup"><span data-stu-id="b9a9e-103">.NET Core versioning</span></span>

<span data-ttu-id="b9a9e-104">.NET Core 由作为单元分布的 [NuGet 包](../packages.md)、工具和框架组成。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-104">.NET Core is made of [NuGet packages](../packages.md), tools, and frameworks that are distributed as a unit.</span></span> <span data-ttu-id="b9a9e-105">每个平台层都可单独进行版本控制，以实现更好的敏捷性。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-105">Each of these platform layers can be versioned separately, enabling better agility.</span></span> <span data-ttu-id="b9a9e-106">虽然在此方面有巨大的版本控制灵活性，但仍需要将平台作为单元进行版本控制以使产品更易于理解。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-106">While there is significant versioning flexibility in that regard, there's also a desire to version the platform as a unit to make the product easier to understand.</span></span>

<span data-ttu-id="b9a9e-107">本文旨在说明 .NET Core SDK 和运行时版本控制的工作原理。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-107">This article aims at clarifying how the .NET Core SDK and runtime are versioned.</span></span>

<span data-ttu-id="b9a9e-108">.NET Core 中有很多版本各异的移动部件。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-108">There are lots of moving parts that version independently in .NET Core.</span></span> <span data-ttu-id="b9a9e-109">但从 .NET Core 2.0 开始，采用了所有人都易于理解的顶级版本号，即作为整体的“.NET Core”的唯一版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-109">However, starting with .NET Core 2.0, there is an easy to understand top-level version number that everybody understands to be *the* version of ".NET Core" as a whole.</span></span> <span data-ttu-id="b9a9e-110">本文的其余部分将详细介绍所有这些部分的版本控制。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-110">The rest of this document goes into the details of the versioning of all those parts.</span></span> <span data-ttu-id="b9a9e-111">这些详细信息对包管理员很重要。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-111">These details can be important if you're a package manager, for example.</span></span>

## <a name="versioning-details"></a><span data-ttu-id="b9a9e-112">版本控制详细信息</span><span class="sxs-lookup"><span data-stu-id="b9a9e-112">Versioning details</span></span>

<span data-ttu-id="b9a9e-113">从 .NET Core 2.0 开始，下载会在其文件名中显示单一版本号。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-113">Starting with .NET Core 2.0, downloads show a single version number in their file name.</span></span> <span data-ttu-id="b9a9e-114">以下版本号已统一：</span><span class="sxs-lookup"><span data-stu-id="b9a9e-114">The following version numbers were unified:</span></span>

* <span data-ttu-id="b9a9e-115">共享框架和关联的运行时。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-115">The shared framework and associated runtime.</span></span>
* <span data-ttu-id="b9a9e-116">.NET Core SDK 和关联的 .NET Core CLI。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-116">The .NET Core SDK and associated .NET Core CLI.</span></span>
* <span data-ttu-id="b9a9e-117">`Microsoft.NETCore.App` 元包。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-117">The `Microsoft.NETCore.App` metapackage.</span></span>

<span data-ttu-id="b9a9e-118">使用单一版本号可让用户更容易知道要在其开发计算机上安装什么版本的 SDK，以及在预配生产环境时应使用共享框架的哪种相应版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-118">The use of a single version number makes it easier for users to know what version of the SDK to install on their dev machines, and what the corresponding version of the shared framework should be when time comes to provision a production environment.</span></span> <span data-ttu-id="b9a9e-119">下载 SDK 或运行时时，你看到的版本号应相同。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-119">When downloading an SDK or runtime, the version number you see is going to be the same.</span></span>

### <a name="installers"></a><span data-ttu-id="b9a9e-120">安装程序</span><span class="sxs-lookup"><span data-stu-id="b9a9e-120">Installers</span></span>

<span data-ttu-id="b9a9e-121">从 .NET Core 2.0 开始，[Daily Builds](https://github.com/dotnet/core-setup#daily-builds)（每日生成）和[发布](https://www.microsoft.com/net/download/core)上提供的下载采用了一种更容易理解的新命名方案。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-121">Starting with .NET Core 2.0, downloads for our [daily builds](https://github.com/dotnet/core-setup#daily-builds) and [our releases](https://www.microsoft.com/net/download/core) adhere to a new naming scheme that is easier to understand.</span></span>
<span data-ttu-id="b9a9e-122">还修改了这些下载中的安装程序 UI，以便清楚地显示所安装组件的名称和版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-122">The installer UI in those downloads were also modified to clearly present the names and versions of the components being installed.</span></span> <span data-ttu-id="b9a9e-123">具体而言，标题现在显示与下载的文件名相同的版本号。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-123">In particular, titles now show the same version number that is in the download's file name.</span></span>

#### <a name="file-name-format"></a><span data-ttu-id="b9a9e-124">文件名格式</span><span class="sxs-lookup"><span data-stu-id="b9a9e-124">File name format</span></span>

`[product]-[component]-[major].[minor].[patch]-[previewN]-[optional build #]-[rid].[file ext]`

<span data-ttu-id="b9a9e-125">下面是该格式的一些示例：</span><span class="sxs-lookup"><span data-stu-id="b9a9e-125">Here are some examples of this format:</span></span>

```
dotnet-runtime-2.0.4-macos.10.12-x64.pkg            # Mac runtime installer
dotnet-sdk-2.0.4-win10-x64.exe                      # Windows SDK installer
dotnet-sdk-2.0.4-fedora.24-x64.tar.gz               # Fedora 24 binary archive

#Ubuntu file set needed for the SDK
dotnet-host-2.0.4-ubuntu.16.04-x64.deb              # Host / muxer and host policy
dotnet-runtime-2.0.4-ubuntu.16.04-x64.deb           # runtime
dotnet-sdk-2.0.4-ubuntu.16.04-x64.deb               # SDK tools
```

<span data-ttu-id="b9a9e-126">这是一种可读格式，能够清晰地显示下载内容、版本，以及适用平台。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-126">The format is readable and clearly shows what you're downloading, what version it is, and where you can use it.</span></span> <span data-ttu-id="b9a9e-127">运行时包名称包括 `runtime`，SDK 包括`SDK`。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-127">The runtime package name includes `runtime`, and the SDK includes `SDK`.</span></span>

#### <a name="ui-string-format"></a><span data-ttu-id="b9a9e-128">UI 字符串格式</span><span class="sxs-lookup"><span data-stu-id="b9a9e-128">UI string format</span></span>

<span data-ttu-id="b9a9e-129">安装程序中的所有网站说明和 UI 字符串都保持一致、准确、简单。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-129">All web site descriptions and UI strings in the installers are kept consistent, accurate, and simple.</span></span> <span data-ttu-id="b9a9e-130">下表展示了一些示例：</span><span class="sxs-lookup"><span data-stu-id="b9a9e-130">The following table shows some examples:</span></span>

| <span data-ttu-id="b9a9e-131">Installer</span><span class="sxs-lookup"><span data-stu-id="b9a9e-131">Installer</span></span> | <span data-ttu-id="b9a9e-132">窗口标题</span><span class="sxs-lookup"><span data-stu-id="b9a9e-132">Window Title</span></span>                          | <span data-ttu-id="b9a9e-133">安装程序中的其他内容</span><span class="sxs-lookup"><span data-stu-id="b9a9e-133">Other content in installer</span></span> | <span data-ttu-id="b9a9e-134">安装内容</span><span class="sxs-lookup"><span data-stu-id="b9a9e-134">What is installed</span></span>                               |
| :--       | :--                                   | :--                        | :--                                             |
| <span data-ttu-id="b9a9e-135">SDK</span><span class="sxs-lookup"><span data-stu-id="b9a9e-135">SDK</span></span>       | <span data-ttu-id="b9a9e-136">.NET Core 2.0 SDK (x64) Installer</span><span class="sxs-lookup"><span data-stu-id="b9a9e-136">.NET Core 2.0 SDK (x64) Installer</span></span>     | <span data-ttu-id="b9a9e-137">.NET Core 2.0.4 SDK</span><span class="sxs-lookup"><span data-stu-id="b9a9e-137">.NET Core 2.0.4 SDK</span></span>        | <span data-ttu-id="b9a9e-138">.NET Core 2.0.4 Tools + .NET Core 2.0.4 Runtime</span><span class="sxs-lookup"><span data-stu-id="b9a9e-138">.NET Core 2.0.4 Tools + .NET Core 2.0.4 Runtime</span></span> |
| <span data-ttu-id="b9a9e-139">运行时</span><span class="sxs-lookup"><span data-stu-id="b9a9e-139">Runtime</span></span>   | <span data-ttu-id="b9a9e-140">.NET Core 2.0 Runtime (x64) Installer</span><span class="sxs-lookup"><span data-stu-id="b9a9e-140">.NET Core 2.0 Runtime (x64) Installer</span></span> | <span data-ttu-id="b9a9e-141">.NET Core 2.0.4 Runtime</span><span class="sxs-lookup"><span data-stu-id="b9a9e-141">.NET Core 2.0.4 Runtime</span></span>    | <span data-ttu-id="b9a9e-142">.NET Core 2.0.4 Runtime</span><span class="sxs-lookup"><span data-stu-id="b9a9e-142">.NET Core 2.0.4 Runtime</span></span>                         |

<span data-ttu-id="b9a9e-143">预览版略有不同：</span><span class="sxs-lookup"><span data-stu-id="b9a9e-143">Preview releases differ only slightly:</span></span>

| <span data-ttu-id="b9a9e-144">Installer</span><span class="sxs-lookup"><span data-stu-id="b9a9e-144">Installer</span></span> | <span data-ttu-id="b9a9e-145">窗口标题</span><span class="sxs-lookup"><span data-stu-id="b9a9e-145">Window Title</span></span>                                    | <span data-ttu-id="b9a9e-146">安装程序中的其他内容</span><span class="sxs-lookup"><span data-stu-id="b9a9e-146">Other content in installer</span></span>        | <span data-ttu-id="b9a9e-147">安装内容</span><span class="sxs-lookup"><span data-stu-id="b9a9e-147">What is installed</span></span>                                                   |
| :--       | :--                                             | :--                               | :--                                                                 |
| <span data-ttu-id="b9a9e-148">SDK</span><span class="sxs-lookup"><span data-stu-id="b9a9e-148">SDK</span></span>       | <span data-ttu-id="b9a9e-149">.NET Core 2.0 Preview 1 SDK (x64) Installer</span><span class="sxs-lookup"><span data-stu-id="b9a9e-149">.NET Core 2.0 Preview 1 SDK (x64) Installer</span></span>     | <span data-ttu-id="b9a9e-150">.NET Core 2.0.0 Preview 1 SDK</span><span class="sxs-lookup"><span data-stu-id="b9a9e-150">.NET Core 2.0.0 Preview 1 SDK</span></span>     | <span data-ttu-id="b9a9e-151">.NET Core 2.0.0 Preview 1 Tools + .NET Core 2.0.0 Preview 1 Runtime</span><span class="sxs-lookup"><span data-stu-id="b9a9e-151">.NET Core 2.0.0 Preview 1 Tools + .NET Core 2.0.0 Preview 1 Runtime</span></span> |
| <span data-ttu-id="b9a9e-152">运行时</span><span class="sxs-lookup"><span data-stu-id="b9a9e-152">Runtime</span></span>   | <span data-ttu-id="b9a9e-153">.NET Core 2.0 Preview 1 Runtime (x64) Installer</span><span class="sxs-lookup"><span data-stu-id="b9a9e-153">.NET Core 2.0 Preview 1 Runtime (x64) Installer</span></span> | <span data-ttu-id="b9a9e-154">.NET Core 2.0.0 Preview 1 Runtime</span><span class="sxs-lookup"><span data-stu-id="b9a9e-154">.NET Core 2.0.0 Preview 1 Runtime</span></span> | <span data-ttu-id="b9a9e-155">.NET Core 2.0.0 Preview 1 Runtime</span><span class="sxs-lookup"><span data-stu-id="b9a9e-155">.NET Core 2.0.0 Preview 1 Runtime</span></span>                                   |

<span data-ttu-id="b9a9e-156">有时一个 SDK 版本可能会包含多个版本的运行时。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-156">It may happen that an SDK release contains more than one version of the runtime.</span></span> <span data-ttu-id="b9a9e-157">出现这种情况时，安装程序 UX 如下所示（只显示 SDK 版本，而已安装的运行时版本显示在 Windows 和 Mac 上安装过程结束时出现的摘要页上）：</span><span class="sxs-lookup"><span data-stu-id="b9a9e-157">When that happens, the installer UX looks like the following (only the SDK version is shown and the installed Runtime versions are shown on a summary page at the end of the installation process on Windows and Mac):</span></span>

| <span data-ttu-id="b9a9e-158">Installer</span><span class="sxs-lookup"><span data-stu-id="b9a9e-158">Installer</span></span> | <span data-ttu-id="b9a9e-159">窗口标题</span><span class="sxs-lookup"><span data-stu-id="b9a9e-159">Window Title</span></span>                      | <span data-ttu-id="b9a9e-160">安装程序中的其他内容</span><span class="sxs-lookup"><span data-stu-id="b9a9e-160">Other content in installer</span></span>                                   | <span data-ttu-id="b9a9e-161">安装内容</span><span class="sxs-lookup"><span data-stu-id="b9a9e-161">What is installed</span></span>                                                         |
| :--       | :--                               | :--                                                          | :--                                                                       |
| <span data-ttu-id="b9a9e-162">SDK</span><span class="sxs-lookup"><span data-stu-id="b9a9e-162">SDK</span></span>       | <span data-ttu-id="b9a9e-163">.NET Core 2.1 SDK (x64) Installer</span><span class="sxs-lookup"><span data-stu-id="b9a9e-163">.NET Core 2.1 SDK (x64) Installer</span></span> | <span data-ttu-id="b9a9e-164">.NET Core 2.1.1 SDK</span><span class="sxs-lookup"><span data-stu-id="b9a9e-164">.NET Core 2.1.1 SDK</span></span> <br> <span data-ttu-id="b9a9e-165">.NET Core 2.1.1 Runtime</span><span class="sxs-lookup"><span data-stu-id="b9a9e-165">.NET Core 2.1.1 Runtime</span></span> <br> <span data-ttu-id="b9a9e-166">.NET Core 2.0.6 Runtime</span><span class="sxs-lookup"><span data-stu-id="b9a9e-166">.NET Core 2.0.6 Runtime</span></span> | <span data-ttu-id="b9a9e-167">.NET Core 2.1.1 Tools + .NET Core 2.1.1 Runtime + .NET Core 2.0.6 Runtime</span><span class="sxs-lookup"><span data-stu-id="b9a9e-167">.NET Core 2.1.1 Tools + .NET Core 2.1.1 Runtime + .NET Core 2.0.6 Runtime</span></span> |

<span data-ttu-id="b9a9e-168">.NET Core Tools 也可能需要更新，但运行时保持不变。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-168">It's also possible that .NET Core Tools need to be updated, without runtime changes.</span></span> <span data-ttu-id="b9a9e-169">在这种情况下，SDK 版本会升级（例如，升级至 2.1.2），然后运行时在下次传送时升级（例如，运行时和 SDK 在下次传送时升级为 2.1.3）。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-169">In that case, the SDK version is increased (for example, to 2.1.2) and then the Runtime catches up the next time it ships (for example, both the Runtime and SDK ship the next time as 2.1.3).</span></span>

### <a name="package-managers"></a><span data-ttu-id="b9a9e-170">包管理器</span><span class="sxs-lookup"><span data-stu-id="b9a9e-170">Package managers</span></span>

<span data-ttu-id="b9a9e-171">.NET Core 可由 Microsoft 以外的其他实体分发。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-171">.NET Core can be distributed by other entities than Microsoft.</span></span> <span data-ttu-id="b9a9e-172">具体而言，Linux 分发所有者和包维护人员可将 .NET Core 包添加到其包管理器。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-172">In particular, Linux distribution owners and package maintainers may add .NET Core packages to their package managers.</span></span> <span data-ttu-id="b9a9e-173">有关如何对这些包进行命名和版本控制的建议，请参阅 [ .NET Core 分发打包](../build/distribution-packaging.md)。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-173">For recommendations on how those packages should be named and versioned, see [.NET Core distribution packaging](../build/distribution-packaging.md).</span></span>

#### <a name="minimum-package-set"></a><span data-ttu-id="b9a9e-174">最小包集</span><span class="sxs-lookup"><span data-stu-id="b9a9e-174">Minimum package set</span></span>

* <span data-ttu-id="b9a9e-175">`dotnet-runtime-[major].[minor]`：包含指定版本的运行时（包管理器中应仅提供针对给定的主要/次要组合的最新修补程序版本）。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-175">`dotnet-runtime-[major].[minor]`: a runtime with the specified version (only the latest patch version for a given major+minor combination should be available in the package manager).</span></span> <span data-ttu-id="b9a9e-176">新的修补程序版本更新此包，但是新的次要和主要版本是独立的包。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-176">New patch versions update the package, but new minor or major versions are separate packages.</span></span>
 
  <span data-ttu-id="b9a9e-177">**依赖项**：`dotnet-host`</span><span class="sxs-lookup"><span data-stu-id="b9a9e-177">**Dependencies**: `dotnet-host`</span></span>

* <span data-ttu-id="b9a9e-178">`dotnet-sdk`：最新的 SDK。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-178">`dotnet-sdk`: the latest SDK.</span></span> <span data-ttu-id="b9a9e-179">`update`：前滚主要、次要和修补程序版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-179">`update` rolls forward major, minor, and patch versions.</span></span>

  <span data-ttu-id="b9a9e-180">**依赖项**：最新的 `dotnet-sdk-[major].[minor]`。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-180">**Dependencies**: the latest `dotnet-sdk-[major].[minor]`.</span></span>

* <span data-ttu-id="b9a9e-181">`dotnet-sdk-[major].[minor]`：包含指定版本的 SDK。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-181">`dotnet-sdk-[major].[minor]`: the SDK with the specified version.</span></span> <span data-ttu-id="b9a9e-182">指定的版本是包含的共享框架中最高的包含版本，以便用户可以将 SDK 轻松关联到共享框架。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-182">The version specified is the highest included version of included shared frameworks, so that users can easily relate an SDK to a shared framework.</span></span> <span data-ttu-id="b9a9e-183">新的修补程序版本更新此包，但是新的次要和主要版本是独立的包。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-183">New patch versions update the package, but new minor or major versions are separate packages.</span></span>

  <span data-ttu-id="b9a9e-184">**依赖项**： `dotnet-host`，一个或多个 `dotnet-runtime-[major].[minor]`（其中之一将供 SDK 代码本身使用，在此处用户针对其他运行时进行生成和运行）。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-184">**Dependencies**: `dotnet-host`, one or more `dotnet-runtime-[major].[minor]` (one of those is used by the SDK code itself, the others are here for users to build and run against).</span></span>

* <span data-ttu-id="b9a9e-185">`dotnet-host`：最新的主机。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-185">`dotnet-host`: the latest host.</span></span>

##### <a name="preview-versions"></a><span data-ttu-id="b9a9e-186">预览版</span><span class="sxs-lookup"><span data-stu-id="b9a9e-186">Preview versions</span></span>

<span data-ttu-id="b9a9e-187">包维护人员可以决定包含运行时和 SDK 的预览版。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-187">Package maintainers may decide to include preview versions of the runtime and SDK.</span></span> <span data-ttu-id="b9a9e-188">请勿将这些预览版包含在未进行版本控制的 `dotnet-sdk` 包中，但是可将其发布为已进行版本控制的包，并将额外的预览标记追加到该名称的主要和次要版本中。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-188">Don't include those preview versions in the unversioned `dotnet-sdk` package, but you can release them as versioned packages with an additional preview marker appended to the major and minor version sections of the name.</span></span> <span data-ttu-id="b9a9e-189">例如，可以有 `dotnet-sdk-2.0-preview1-final` 包。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-189">For example, there may be a `dotnet-sdk-2.0-preview1-final` package.</span></span>

### <a name="docker"></a><span data-ttu-id="b9a9e-190">Docker</span><span class="sxs-lookup"><span data-stu-id="b9a9e-190">Docker</span></span>

<span data-ttu-id="b9a9e-191">Docker 标记的一般命名约定为，将版本号放在组件名称之前。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-191">A general Docker tag naming convention is to place the version number before the component name.</span></span> <span data-ttu-id="b9a9e-192">可以继续使用此约定。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-192">This convention may continue to be utilized.</span></span> <span data-ttu-id="b9a9e-193">当前标记仅包含运行时版本，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-193">The current tags include only the Runtime version as follows.</span></span>

* <span data-ttu-id="b9a9e-194">1.0.8-runtime</span><span class="sxs-lookup"><span data-stu-id="b9a9e-194">1.0.8-runtime</span></span>
* <span data-ttu-id="b9a9e-195">1.0.8-sdk</span><span class="sxs-lookup"><span data-stu-id="b9a9e-195">1.0.8-sdk</span></span>
* <span data-ttu-id="b9a9e-196">2.0.4-runtime</span><span class="sxs-lookup"><span data-stu-id="b9a9e-196">2.0.4-runtime</span></span>
* <span data-ttu-id="b9a9e-197">2.0.4-sdk</span><span class="sxs-lookup"><span data-stu-id="b9a9e-197">2.0.4-sdk</span></span>
* <span data-ttu-id="b9a9e-198">2.1.1-runtime</span><span class="sxs-lookup"><span data-stu-id="b9a9e-198">2.1.1-runtime</span></span>
* <span data-ttu-id="b9a9e-199">2.1.1-sdk</span><span class="sxs-lookup"><span data-stu-id="b9a9e-199">2.1.1-sdk</span></span>

<span data-ttu-id="b9a9e-200">应更新 SDK 标记以表示 SDK 版本，而不是运行时版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-200">The SDK tags should be updated to represent the SDK version rather than Runtime.</span></span>

<span data-ttu-id="b9a9e-201">还有可能我们需要修复 .NET Core 工具，但重新传送一个现有的运行时。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-201">It's also possible that we need to fix the .NET Core Tools but reship an existing runtime.</span></span> <span data-ttu-id="b9a9e-202">在这种情况下，SDK 版本会升级（例如，升级至 2.1.2），然后运行时在下次传送时升级（例如，运行时和 SDK 在其后传送时升级为 2.1.3）。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-202">In that case, the SDK version is increased (for example, to 2.1.2) and then the Runtime catches up the next time it ships (for example, both the Runtime and SDK ship the following time as 2.1.3).</span></span>

## <a name="semantic-versioning"></a><span data-ttu-id="b9a9e-203">语义版本控制</span><span class="sxs-lookup"><span data-stu-id="b9a9e-203">Semantic Versioning</span></span>

<span data-ttu-id="b9a9e-204">.NET Core 使用[语义版本控制 (SemVer)](http://semver.org/)，采用 `MAJOR.MINOR.PATCH` 版本控制，通过版本号的各部分来描述更改程度和类型。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-204">.NET Core uses [Semantic Versioning (SemVer)](http://semver.org/), adopting the use of `MAJOR.MINOR.PATCH` versioning, using the various parts of the version number to describe the degree and type of change.</span></span>

```
MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]
```

<span data-ttu-id="b9a9e-205">可选的 `PRERELEASE` 和 `BUILDNUMBER` 部分将永远不会成为受支持版本的一部分，并且将仅存在于夜间版本、来自源目标的本地版本，以及不受支持的预览版本中。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-205">The optional `PRERELEASE` and `BUILDNUMBER` parts will never be part of supported releases, and only exist on nightly builds, locally built from source targets, and unsupported preview releases.</span></span>

### <a name="how-version-numbers-are-incremented"></a><span data-ttu-id="b9a9e-206">版本号如何递增？</span><span class="sxs-lookup"><span data-stu-id="b9a9e-206">How version numbers are incremented?</span></span>

<span data-ttu-id="b9a9e-207">`MAJOR` 在下列情况时递增：</span><span class="sxs-lookup"><span data-stu-id="b9a9e-207">`MAJOR` is incremented when:</span></span>
  - <span data-ttu-id="b9a9e-208">旧版本不再受支持。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-208">An old version is no longer supported.</span></span>
  - <span data-ttu-id="b9a9e-209">采用了现有依赖项的较新 `MAJOR` 版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-209">A newer `MAJOR` version of an existing dependency is adopted.</span></span>
  - <span data-ttu-id="b9a9e-210">兼容性的默认设置更改为“关”。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-210">The default setting of a compatibility quirk is changed to "off."</span></span>

<span data-ttu-id="b9a9e-211">`MINOR` 在下列情况时递增：</span><span class="sxs-lookup"><span data-stu-id="b9a9e-211">`MINOR` is incremented when:</span></span>
  - <span data-ttu-id="b9a9e-212">添加了公共 API 外围应用。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-212">Public API surface area is added.</span></span>
  - <span data-ttu-id="b9a9e-213">添加了新行为。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-213">A new behavior is added.</span></span>
  - <span data-ttu-id="b9a9e-214">采用了现有依赖项的较新 `MINOR` 版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-214">A newer `MINOR` version of an existing dependency is adopted.</span></span>
  - <span data-ttu-id="b9a9e-215">引入了新依赖项。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-215">A new dependency is introduced.</span></span>
  
<span data-ttu-id="b9a9e-216">`PATCH` 在下列情况时递增：</span><span class="sxs-lookup"><span data-stu-id="b9a9e-216">`PATCH` is incremented when:</span></span>
  - <span data-ttu-id="b9a9e-217">进行了 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-217">Bug fixes are made.</span></span>
  - <span data-ttu-id="b9a9e-218">添加了对较新平台的支持。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-218">Support for a newer platform is added.</span></span>
  - <span data-ttu-id="b9a9e-219">采用了现有依赖项的较新 `PATCH` 版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-219">A newer `PATCH` version of an existing dependency is adopted.</span></span>
  - <span data-ttu-id="b9a9e-220">任何其他不符合上述情况的更改。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-220">Any other change that doesn't fit one of the previous cases.</span></span>

<span data-ttu-id="b9a9e-221">存在多处更改时，单个更改影响的最高级别元素会递增，并将随后的元素重置为零。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-221">When there are multiple changes, the highest element affected by individual changes is incremented, and the following ones are reset to zero.</span></span> <span data-ttu-id="b9a9e-222">例如，当 `MAJOR` 递增时，`MINOR` 和 `PATCH` 将重置为零。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-222">For example, when `MAJOR` is incremented, `MINOR` and `PATCH` are reset to zero.</span></span> <span data-ttu-id="b9a9e-223">当 `MINOR` 递增时，`PATCH` 将重置为零，而 `MAJOR` 保持不变。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-223">When `MINOR` is incremented, `PATCH` is reset to zero while `MAJOR` is left untouched.</span></span>

### <a name="preview-versions"></a><span data-ttu-id="b9a9e-224">预览版</span><span class="sxs-lookup"><span data-stu-id="b9a9e-224">Preview versions</span></span>

<span data-ttu-id="b9a9e-225">预览版向版本中追加了 `-preview[number]-([build]|"final")`。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-225">Preview versions have a `-preview[number]-([build]|"final")` appended to the version.</span></span> <span data-ttu-id="b9a9e-226">例如 `2.0.0-preview1-final`。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-226">For example, `2.0.0-preview1-final`.</span></span>

### <a name="servicing-versions"></a><span data-ttu-id="b9a9e-227">服务版本</span><span class="sxs-lookup"><span data-stu-id="b9a9e-227">Servicing versions</span></span>

<span data-ttu-id="b9a9e-228">在版本发布后，版本分支通常停止生成日常版本，而开始生成服务版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-228">After a release goes out, the release branches generally stop producing daily builds and instead start producing servicing builds.</span></span> <span data-ttu-id="b9a9e-229">服务版本向版本追加了 `-servicing-[number]`。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-229">Servicing versions have a `-servicing-[number]` appended to the version.</span></span> <span data-ttu-id="b9a9e-230">例如 `2.0.1-servicing-006924`。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-230">For example, `2.0.1-servicing-006924`.</span></span>

### <a name="lts-vs-current"></a><span data-ttu-id="b9a9e-231">对比 LTS 与 Current</span><span class="sxs-lookup"><span data-stu-id="b9a9e-231">LTS vs. current</span></span>

<span data-ttu-id="b9a9e-232">.NET Core 包含两个发行版本系列：Long Term Support (LTS) 和 Current。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-232">There are two trains of releases for .NET Core: Long Term Support (LTS) and Current.</span></span> <span data-ttu-id="b9a9e-233">这使得用户能够选择所需的稳定性级别和新功能，同时仍然受到支持。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-233">That enables users to pick the level of stability and new features they want, while still being supported.</span></span>

- <span data-ttu-id="b9a9e-234">LTS 意味着用户不会频繁地获得新功能，但是会得到一个更成熟的平台。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-234">LTS means you get new features less frequently, but you have a more mature platform.</span></span> <span data-ttu-id="b9a9e-235">LTS 还具有更长的支持期。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-235">LTS also has a longer period of support.</span></span>
- <span data-ttu-id="b9a9e-236">Current 意味着用户可以更频繁地获得新功能和 API，但缺点是用来安装更新的时间更短，并且这些更新会更频繁地出现。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-236">Current means you get new features and APIs more frequently, but the disadvantage is that you have a shorter window of time to install updates, and those updates happen more frequently.</span></span> <span data-ttu-id="b9a9e-237">Current 也具有完全支持，但支持期短于 LTS。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-237">Current is also fully supported but the support period is shorter than LTS.</span></span>

<span data-ttu-id="b9a9e-238">Current 版本可以升级为 LTS。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-238">A "Current" version may get promoted to LTS.</span></span>

<span data-ttu-id="b9a9e-239">应将“LTS”和“Current”版本视为我们对特定版本添加的标签，便于对关联的支持级别做出声明。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-239">"LTS" and "Current" should be considered as labels that we put on specific releases to make a statement about the associated level of support.</span></span>

<span data-ttu-id="b9a9e-240">有关详细信息，请参阅 [.NET Core 支持生命周期简报](https://www.microsoft.com/net/core/support)。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-240">For more information, see [.NET Core Support Lifecycle Fact Sheet](https://www.microsoft.com/net/core/support).</span></span>

## <a name="versioning-scheme-details"></a><span data-ttu-id="b9a9e-241">版本控制方案详细信息</span><span class="sxs-lookup"><span data-stu-id="b9a9e-241">Versioning scheme details</span></span>

<span data-ttu-id="b9a9e-242">.NET Core 包括以下部件：</span><span class="sxs-lookup"><span data-stu-id="b9a9e-242">.NET Core is made of the following parts:</span></span>

- <span data-ttu-id="b9a9e-243">主机（也称为 muxer）：`dotnet.exe` 与 `hostfxr` 策略库。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-243">A host (also known as muxer): `dotnet.exe` with `hostfxr` policy libraries.</span></span>
- <span data-ttu-id="b9a9e-244">SDK（开发人员计算机上必需的一套工具，但不用于生产）。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-244">An SDK (the set of tools necessary on a developer's machine, but not in production).</span></span>
- <span data-ttu-id="b9a9e-245">运行时。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-245">A runtime.</span></span>
- <span data-ttu-id="b9a9e-246">以包的形式分发的共享框架实现。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-246">A shared framework implementation, distributed as packages.</span></span> <span data-ttu-id="b9a9e-247">对每个包进行独立的版本控制，特别是对于修补程序版本控制。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-247">Each package is versioned independently, particularly for patch versioning.</span></span>
- <span data-ttu-id="b9a9e-248">（可选）将细粒度包作为版本控制单元引用的一组[元包](../packages.md)。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-248">Optionally, a set of [metapackages](../packages.md) that reference fine-grained packages as a versioned unit.</span></span> <span data-ttu-id="b9a9e-249">可从包单独对元包进行版本控制。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-249">Metapackages can be versioned separately from packages.</span></span>

<span data-ttu-id="b9a9e-250">.NET Core 还包括表示一组随版本号增加而逐渐变大的 API 集的目标框架（如 `netstandard` 或 `netcoreapp`）。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-250">.NET Core also includes a set of target frameworks (for example, `netstandard` or `netcoreapp`) that represent a progressively larger API set, as version numbers are incremented.</span></span>

### <a name="net-standard"></a><span data-ttu-id="b9a9e-251">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="b9a9e-251">.NET Standard</span></span>

<span data-ttu-id="b9a9e-252">.NET Standard 一直在使用 `MAJOR.MINOR` 版本控制方案。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-252">.NET Standard has been using a `MAJOR.MINOR` versioning scheme.</span></span> <span data-ttu-id="b9a9e-253">`PATCH` 级别对于 .NET Standard 无效，因为它表示一组不太经常迭代的协定，并且它对版本控制的要求也与实际实现不相同。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-253">`PATCH` level isn't useful for .NET Standard because it expresses a set of contracts that are iterated on less often and doesn't present the same requirements for versioning as an actual implementation.</span></span>

<span data-ttu-id="b9a9e-254">.NET Standard 版本和 .NET Core 版本之间没有真正的耦合：.NET Core 2.0 恰好实现 .NET Standard 2.0，但不能保证 .NET Core 的未来版本将映射到相同的 .NET Standard 版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-254">There is no real coupling between .NET Standard versions and .NET Core versions: .NET Core 2.0 happens to implement .NET Standard 2.0, but there is no guarantee that future versions of .NET Core will map to the same .NET Standard version.</span></span> <span data-ttu-id="b9a9e-255">.NET Core 可传送未由 .NET Standard 定义的 API，因此，无需新的 .NET Standard 也可以传送新版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-255">.NET Core can ship APIs that aren't defined by .NET Standard, and, as such, may ship new versions without requiring a new .NET Standard.</span></span> <span data-ttu-id="b9a9e-256">.NET Standard 也是一个适用于其他目标版本（如 .NET Framework 或 Mono）的概念，即使它的开始恰好与 .NET Core 的开始相一致。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-256">.NET Standard is also a concept that applies to other targets, such as .NET Framework or Mono, even if its inception happened to coincide with that of .NET Core.</span></span>

### <a name="packages"></a><span data-ttu-id="b9a9e-257">包</span><span class="sxs-lookup"><span data-stu-id="b9a9e-257">Packages</span></span>

<span data-ttu-id="b9a9e-258">库包单独发展，并单独进行版本控制。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-258">Library packages evolve and version independently.</span></span> <span data-ttu-id="b9a9e-259">与 .NET Framework System.\* 程序集重叠的程序包通常使用 4.x 版本，这符合 .NET Framework 4.x 版本控制（历史选择）。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-259">Packages that overlap with .NET Framework System.\* assemblies typically use 4.x versions, aligning with the .NET Framework 4.x versioning (a historical choice).</span></span> <span data-ttu-id="b9a9e-260">不与 .NET Framework 库重叠的包（如 [`System.Reflection.Metadata`](https://www.nuget.org/packages/System.Reflection.Metadata)）通常从 1.0 开始并由此递增。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-260">Packages that do not overlap with the .NET Framework libraries (for example, [`System.Reflection.Metadata`](https://www.nuget.org/packages/System.Reflection.Metadata)) typically start at 1.0 and increment from there.</span></span>

<span data-ttu-id="b9a9e-261">由于处于平台的基底，由 [`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library) 描述的包将被特殊处理。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-261">The packages described by [`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library) are treated specially due to being at the base of the platform.</span></span>

<span data-ttu-id="b9a9e-262">`NETStandard.Library` 包通常作为集合进行版本控制，因为这些包之间具有实现级依赖项。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-262">`NETStandard.Library` packages will typically version as a set, since they have implementation-level dependencies between them.</span></span>

### <a name="metapackages"></a><span data-ttu-id="b9a9e-263">元包</span><span class="sxs-lookup"><span data-stu-id="b9a9e-263">Metapackages</span></span>

<span data-ttu-id="b9a9e-264">.NET Core 元包的版本控制基于其所属的 .NET Core 版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-264">Versioning for .NET Core metapackages is based on the .NET Core version they are a part of.</span></span>

<span data-ttu-id="b9a9e-265">例如，.NET Core 2.1.3 中的元包都应具有 2.1 作为其 `MAJOR` 和 `MINOR` 版本号。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-265">For instance, the metapackages in .NET Core 2.1.3 should all have 2.1 as their `MAJOR` and `MINOR` version numbers.</span></span>

<span data-ttu-id="b9a9e-266">每次更新任何引用的包时，元包的修补程序版本都会递增。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-266">The patch version for the metapackage is incremented every time any referenced package is updated.</span></span> <span data-ttu-id="b9a9e-267">修补程序版本不会包含更新的框架版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-267">Patch versions don't include an updated framework version.</span></span> <span data-ttu-id="b9a9e-268">因此，从严格意义上讲，元包并不符合 SemVer，因为其版本控制方案不表示基础包中的更改程度，而是主要表示 API 级别。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-268">As a result, the metapackages aren't strictly SemVer-compliant because their versioning scheme doesn't represent the degree of change in the underlying packages, but primarily the API level.</span></span> 

<span data-ttu-id="b9a9e-269">.NET Core 当前有两种主要的元包：</span><span class="sxs-lookup"><span data-stu-id="b9a9e-269">There are currently two primary metapackages for .NET Core:</span></span>

<span data-ttu-id="b9a9e-270">**Microsoft.NETCore.App**</span><span class="sxs-lookup"><span data-stu-id="b9a9e-270">**Microsoft.NETCore.App**</span></span>

- <span data-ttu-id="b9a9e-271">自 .NET Core 1.0 的 v1.0 开始（这些版本匹配）。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-271">v1.0 as of .NET Core 1.0 (these versions match).</span></span>
- <span data-ttu-id="b9a9e-272">映射到 `netcoreapp` 框架。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-272">Maps to the `netcoreapp` framework.</span></span>
- <span data-ttu-id="b9a9e-273">描述 .NET Core 分发中的包。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-273">Describes the packages in the .NET Core distribution.</span></span>

<span data-ttu-id="b9a9e-274">注意：[`Microsoft.NETCore.Portable.Compatibility`](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility) 是另一个 .NET Core 元包，它的存在是为了与 .NET 的预 .NET Standard 实现兼容。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-274">Note: [`Microsoft.NETCore.Portable.Compatibility`](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility) is another .NET Core metapackage that exists to enable compatibility with pre-.NET Standard implementation of .NET.</span></span> <span data-ttu-id="b9a9e-275">该元包不会映射到特殊框架，因此其版本控制与包相同。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-275">It doesn't map to a particular framework, so it versions like a package.</span></span>

<span data-ttu-id="b9a9e-276">**NETStandard.Library**</span><span class="sxs-lookup"><span data-stu-id="b9a9e-276">**NETStandard.Library**</span></span>

<span data-ttu-id="b9a9e-277">[`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library) - 描述了属于 [.NET Standard](../../standard/library.md) 一部分的各种库。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-277">[`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library) describes the libraries that are part of the [.NET Standard](../../standard/library.md).</span></span> <span data-ttu-id="b9a9e-278">适用于所有支持 .NET Standard 的 .NET 实现（例如，.NET Framework、.NET Core 和 Mono）。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-278">Applies to all .NET implementations that support .NET Standard, such as .NET Framework, .NET Core, and Mono.</span></span>

### <a name="target-frameworks"></a><span data-ttu-id="b9a9e-279">目标框架</span><span class="sxs-lookup"><span data-stu-id="b9a9e-279">Target frameworks</span></span>

<span data-ttu-id="b9a9e-280">添加新 API 时，目标框架版本也会更新。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-280">Target framework versions are updated when new APIs are added.</span></span> <span data-ttu-id="b9a9e-281">它们没有修补程序版本的概念，因为其表示 API 形状，不表示实现问题。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-281">They have no concept of patch version, since they represent API shape and not implementation concerns.</span></span> <span data-ttu-id="b9a9e-282">主要和次要版本控制遵循先前指定的 SemVer 规则，并且与实现它们的 .NET Core 分发的 `MAJOR` 和 `MINOR` 数量一致。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-282">Major and minor versioning follows the SemVer rules specified earlier, and coincides with the `MAJOR` and `MINOR` numbers of the .NET Core distributions that implement them.</span></span>

## <a name="versioning-in-practice"></a><span data-ttu-id="b9a9e-283">版本控制实践</span><span class="sxs-lookup"><span data-stu-id="b9a9e-283">Versioning in practice</span></span>

<span data-ttu-id="b9a9e-284">下载 .NET Core 时，下载的文件名中将包含版本，例如 `dotnet-sdk-2.0.4-win10-x64.exe`。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-284">When you download .NET Core, the name of the file you download carries the version, for example, `dotnet-sdk-2.0.4-win10-x64.exe`.</span></span>

<span data-ttu-id="b9a9e-285">每天，在 GitHub 上的 .NET Core 存储库中都有提交和拉取请求，因此会新生成许多库。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-285">There are commits and pull requests on .NET Core repos on GitHub on a daily basis, resulting in new builds of many libraries.</span></span> <span data-ttu-id="b9a9e-286">为每个更改创建 .NET Core 的新公共版本是不切实际的。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-286">It isn't practical to create new public versions of .NET Core for every change.</span></span> <span data-ttu-id="b9a9e-287">但可在发布新的 .NET Core 公共稳定版前，不定期（例如，几周或几个月一次）聚合更改。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-287">Instead, changes are aggregated over an undetermined period of time (for example, weeks or months) before making a new public stable .NET Core version.</span></span>

<span data-ttu-id="b9a9e-288">新版本的 .NET Core 可能意味着以下内容：</span><span class="sxs-lookup"><span data-stu-id="b9a9e-288">A new version of .NET Core could mean several things:</span></span>

- <span data-ttu-id="b9a9e-289">包和元包的新版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-289">New versions of packages and metapackages.</span></span>
- <span data-ttu-id="b9a9e-290">各种框架的新版本，假定添加新 API。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-290">New versions of various frameworks, assuming the addition of new APIs.</span></span>
- <span data-ttu-id="b9a9e-291">.NET Core 分发的新版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-291">New version of the .NET Core distribution.</span></span>

### <a name="shipping-a-patch-release"></a><span data-ttu-id="b9a9e-292">传送修补程序版本</span><span class="sxs-lookup"><span data-stu-id="b9a9e-292">Shipping a patch release</span></span>

<span data-ttu-id="b9a9e-293">传送 .NET Core 的主要版本（如 2.0.0 版本）后，对 .NET Core 库进行修补程序级别更改以修复 bug 并改进性能和可靠性。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-293">After shipping a major release of .NET Core, such as version 2.0.0, patch-level changes are made to .NET Core libraries to fix bugs and improve performance and reliability.</span></span> <span data-ttu-id="b9a9e-294">这意味着没有引入新的 API。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-294">That means that no new APIs are introduced.</span></span> <span data-ttu-id="b9a9e-295">更新各种元包以引用更新的 .NET Core 库包。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-295">The various metapackages are updated to reference the updated .NET Core library packages.</span></span> <span data-ttu-id="b9a9e-296">将元包作为修补程序更新 (`MAJOR.MINOR.PATCH`) 进行版本控制。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-296">The metapackages are versioned as patch updates (`MAJOR.MINOR.PATCH`).</span></span> <span data-ttu-id="b9a9e-297">目标框架永远不会作为修补程序版本的一部分更新。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-297">Target frameworks are never updated as part of patch releases.</span></span> <span data-ttu-id="b9a9e-298">发布新的 .NET Core 分发，其中版本号与 `Microsoft.NETCore.App` 元包匹配。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-298">A new .NET Core distribution is released with a version number that matches that of the `Microsoft.NETCore.App` metapackage.</span></span>

### <a name="shipping-a-minor-release"></a><span data-ttu-id="b9a9e-299">传送次要发布</span><span class="sxs-lookup"><span data-stu-id="b9a9e-299">Shipping a minor release</span></span>

<span data-ttu-id="b9a9e-300">传送具有递增 `MAJOR` 版本号的 .NET Core 版本后，将新的 API 添加到 .NET Core 库以启用新方案。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-300">After shipping a .NET Core version with an incremented `MAJOR` version number, new APIs are added to .NET Core libraries to enable new scenarios.</span></span> <span data-ttu-id="b9a9e-301">更新各种元包以引用更新的 .NET Core 库包。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-301">The various metapackages are updated to reference the updated .NET Core library packages.</span></span> <span data-ttu-id="b9a9e-302">将元包作为具有 `MAJOR` 和 `MINOR` 版本号的修补程序更新进行版本控制，以匹配新的框架版本。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-302">The metapackages are versioned as patch updates with `MAJOR` and `MINOR` version numbers matching the new framework version.</span></span> <span data-ttu-id="b9a9e-303">添加了具有新 `MAJOR.MINOR` 版本的新目标框架名称，用以描述新的 API（例如 `netcoreapp2.1`）。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-303">New target framework names with the new `MAJOR.MINOR` version are added to describe the new APIs (for example, `netcoreapp2.1`).</span></span> <span data-ttu-id="b9a9e-304">发布新的 .NET Core 分发，其具有与 `Microsoft.NETCore.App` 元包匹配的版本号。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-304">A new .NET Core distribution is released with a matching version number to the `Microsoft.NETCore.App` metapackage.</span></span>

### <a name="shipping-a-major-release"></a><span data-ttu-id="b9a9e-305">传送主要发布</span><span class="sxs-lookup"><span data-stu-id="b9a9e-305">Shipping a major release</span></span>

<span data-ttu-id="b9a9e-306">每次传送新的 .NET Core 的主要版本时，`MAJOR` 版本号将递增，`MINOR` 版本号将重置为零。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-306">Every time a new major version of .NET Core ships, the `MAJOR` version number gets incremented, and the `MINOR` version number gets reset to zero.</span></span> <span data-ttu-id="b9a9e-307">新的主要版本至少包含由前一个主要版本后面的次要版本添加的所有 API。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-307">The new major version contains at least all the APIs that were added by minor releases after the previous major version.</span></span> <span data-ttu-id="b9a9e-308">新的主要版本应能够实现重要的新方案，它也可能会失去对旧平台的支持。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-308">A new major version should enable important new scenarios, and it may also drop support for an older platform.</span></span>

<span data-ttu-id="b9a9e-309">更新各种元包以引用更新的 .NET Core 库包。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-309">The various metapackages are updated to reference the updated .NET Core library packages.</span></span> <span data-ttu-id="b9a9e-310">[`Microsoft.NETCore.App`](https://www.nuget.org/packages/Microsoft.NETCore.App) 元包和 `netcore` 目标框架作为匹配新版本的 `MAJOR` 版本号的主要更新进行版本控制。</span><span class="sxs-lookup"><span data-stu-id="b9a9e-310">The [`Microsoft.NETCore.App`](https://www.nuget.org/packages/Microsoft.NETCore.App) metapackage and the `netcore` target framework are versioned as a major update matching the `MAJOR` version number of the new release.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9a9e-311">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9a9e-311">See also</span></span>
<span data-ttu-id="b9a9e-312">[目标框架](../../standard/frameworks.md) </span><span class="sxs-lookup"><span data-stu-id="b9a9e-312">[Target frameworks](../../standard/frameworks.md) </span></span>  
<span data-ttu-id="b9a9e-313">[.NET Core 分发打包](../build/distribution-packaging.md) </span><span class="sxs-lookup"><span data-stu-id="b9a9e-313">[.NET Core distribution packaging](../build/distribution-packaging.md) </span></span>  
<span data-ttu-id="b9a9e-314">[.NET Core 支持生命周期简报](https://www.microsoft.com/net/core/support) </span><span class="sxs-lookup"><span data-stu-id="b9a9e-314">[.NET Core Support Lifecycle Fact Sheet](https://www.microsoft.com/net/core/support) </span></span>  
[<span data-ttu-id="b9a9e-315">.NET Core 2 和版本绑定</span><span class="sxs-lookup"><span data-stu-id="b9a9e-315">.NET Core 2+ Version Binding</span></span>](https://github.com/dotnet/designs/issues/3)   
