---
title: .NET Core 运行时标识符 (RID) 目录
description: 了解运行时标识符 (RID) 及如何在 .NET Core 中使用 RID。
ms.date: 02/22/2019
ms.openlocfilehash: 0d03e39c755b43e145edf5efe48422cbae7abcab
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745737"
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="0b97f-103">.NET Core RID 目录</span><span class="sxs-lookup"><span data-stu-id="0b97f-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="0b97f-104">RID 是运行时标识符的缩写。</span><span class="sxs-lookup"><span data-stu-id="0b97f-104">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="0b97f-105">RID 值用于标识应用程序运行所在的目标平台。</span><span class="sxs-lookup"><span data-stu-id="0b97f-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="0b97f-106">.NET 包使用它们来表示 NuGet 包中特定于平台的资产。</span><span class="sxs-lookup"><span data-stu-id="0b97f-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="0b97f-107">以下值是 RID 的示例：`linux-x64`、`ubuntu.14.04-x64`、`win7-x64` 或 `osx.10.12-x64`。</span><span class="sxs-lookup"><span data-stu-id="0b97f-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="0b97f-108">对于具有本机依赖项的包，RID 将指定在其中可以还原包的平台。</span><span class="sxs-lookup"><span data-stu-id="0b97f-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="0b97f-109">可以在项目文件的 `<RuntimeIdentifier>` 元素中设置一个 RID。</span><span class="sxs-lookup"><span data-stu-id="0b97f-109">A single RID can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="0b97f-110">可以将多个 RID 定义为项目文件的 `<RuntimeIdentifiers>` 元素中的列表（以分号分隔）。</span><span class="sxs-lookup"><span data-stu-id="0b97f-110">Multiple RIDs can be defined as a semicolon-delimited list in the project file's `<RuntimeIdentifiers>` element.</span></span> <span data-ttu-id="0b97f-111">也可使用以下 [.NET Core CLI 命令](./tools/index.md) 通过 `--runtime` 选项使用它们：</span><span class="sxs-lookup"><span data-stu-id="0b97f-111">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="0b97f-112">dotnet build</span><span class="sxs-lookup"><span data-stu-id="0b97f-112">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="0b97f-113">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="0b97f-113">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="0b97f-114">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="0b97f-114">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="0b97f-115">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="0b97f-115">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="0b97f-116">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="0b97f-116">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="0b97f-117">dotnet run</span><span class="sxs-lookup"><span data-stu-id="0b97f-117">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="0b97f-118">dotnet store</span><span class="sxs-lookup"><span data-stu-id="0b97f-118">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="0b97f-119">表示具体操作系统的 RID 通常遵循以下模式：`[os].[version]-[architecture]-[additional qualifiers]`，其中：</span><span class="sxs-lookup"><span data-stu-id="0b97f-119">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="0b97f-120">`[os]` 是操作系统/平台系统名字对象。</span><span class="sxs-lookup"><span data-stu-id="0b97f-120">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="0b97f-121">例如 `ubuntu`。</span><span class="sxs-lookup"><span data-stu-id="0b97f-121">For example, `ubuntu`.</span></span>

- <span data-ttu-id="0b97f-122">`[version]` 是操作系统版本，使用的格式是以点 (`.`) 分隔的版本号。</span><span class="sxs-lookup"><span data-stu-id="0b97f-122">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="0b97f-123">例如 `15.10`。</span><span class="sxs-lookup"><span data-stu-id="0b97f-123">For example, `15.10`.</span></span>

  - <span data-ttu-id="0b97f-124">版本不应为营销版本，因为它们通常代表该操作系统的多个离散版本，且具有不同的平台 API 外围应用。</span><span class="sxs-lookup"><span data-stu-id="0b97f-124">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="0b97f-125">`[architecture]` 是处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="0b97f-125">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="0b97f-126">例如：`x86`、`x64`、`arm` 或 `arm64`。</span><span class="sxs-lookup"><span data-stu-id="0b97f-126">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="0b97f-127">`[additional qualifiers]` 进一步区分了不同的平台。</span><span class="sxs-lookup"><span data-stu-id="0b97f-127">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="0b97f-128">例如：`aot`。</span><span class="sxs-lookup"><span data-stu-id="0b97f-128">For example: `aot`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="0b97f-129">RID 图表</span><span class="sxs-lookup"><span data-stu-id="0b97f-129">RID graph</span></span>

<span data-ttu-id="0b97f-130">RID 图表或运行时回退图表是互相兼容的 RID 列表。</span><span class="sxs-lookup"><span data-stu-id="0b97f-130">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="0b97f-131">[Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) 包中定义了 RID。</span><span class="sxs-lookup"><span data-stu-id="0b97f-131">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="0b97f-132">可以在 CoreFX 存储库的 [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 文件中查看支持的 RID 列表和 RID 图表。</span><span class="sxs-lookup"><span data-stu-id="0b97f-132">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the CoreFX repo.</span></span> <span data-ttu-id="0b97f-133">在此文件中，可以看到除基 RID 以外的所有 RID 均包含 `"#import"` 语句。</span><span class="sxs-lookup"><span data-stu-id="0b97f-133">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="0b97f-134">这些语句指示的是兼容的 RID。</span><span class="sxs-lookup"><span data-stu-id="0b97f-134">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="0b97f-135">NuGet 还原包时，它将尝试找到指定运行时的完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="0b97f-135">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="0b97f-136">如果未找到完全匹配项，NuGet 将返回此图表，直至它根据 RID 图表找到最相近的兼容系统。</span><span class="sxs-lookup"><span data-stu-id="0b97f-136">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="0b97f-137">以下示例是 `osx.10.12-x64` RID 的实际条目：</span><span class="sxs-lookup"><span data-stu-id="0b97f-137">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="0b97f-138">上述 RID 指定 `osx.10.12-x64` 导入 `osx.10.11-x64`。</span><span class="sxs-lookup"><span data-stu-id="0b97f-138">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="0b97f-139">因此，当 NuGet 还原包时，它将尝试找到包中的 `osx.10.12-x64` 的完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="0b97f-139">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="0b97f-140">例如，如果 NuGet 无法找到特定的运行时，可以还原指定 `osx.10.11-x64` 运行时的包。</span><span class="sxs-lookup"><span data-stu-id="0b97f-140">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="0b97f-141">以下示例演示了 runtime.json 文件中定义的另一个略大的 RID 图表：</span><span class="sxs-lookup"><span data-stu-id="0b97f-141">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

<span data-ttu-id="0b97f-142">所有 RID 最终都会映射回根 `any` RID。</span><span class="sxs-lookup"><span data-stu-id="0b97f-142">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="0b97f-143">使用 RID 时，必须牢记以下几个注意事项：</span><span class="sxs-lookup"><span data-stu-id="0b97f-143">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="0b97f-144">RID 是不透明字符串，应将其视为黑盒。</span><span class="sxs-lookup"><span data-stu-id="0b97f-144">RIDs are **opaque strings** and should be treated as black boxes.</span></span>
- <span data-ttu-id="0b97f-145">请勿以编程方式生成 RID。</span><span class="sxs-lookup"><span data-stu-id="0b97f-145">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="0b97f-146">使用已为平台定义的 RID。</span><span class="sxs-lookup"><span data-stu-id="0b97f-146">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="0b97f-147">RID 必须具有特定性，因此请勿通过实际的 RID 值假定任何情况。</span><span class="sxs-lookup"><span data-stu-id="0b97f-147">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="0b97f-148">使用 RID</span><span class="sxs-lookup"><span data-stu-id="0b97f-148">Using RIDs</span></span>

<span data-ttu-id="0b97f-149">若要使用 RID，必须知道有哪些 RID。</span><span class="sxs-lookup"><span data-stu-id="0b97f-149">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="0b97f-150">新值将定期添加到该平台。</span><span class="sxs-lookup"><span data-stu-id="0b97f-150">New values are added regularly to the platform.</span></span>
<span data-ttu-id="0b97f-151">若要获取最新的完整版，请参阅 CoreFX 存储库上的 [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 文件。</span><span class="sxs-lookup"><span data-stu-id="0b97f-151">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

<span data-ttu-id="0b97f-152">.NET Core 2.0 SDK 引入了可移植 RID 的概念。</span><span class="sxs-lookup"><span data-stu-id="0b97f-152">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="0b97f-153">它们是添加到 RID 图表的新值，并且未与特定版本或 OS 发行版本关联，是使用 .NET Core 2.0 及更高版本的首选值。</span><span class="sxs-lookup"><span data-stu-id="0b97f-153">They are new values added to the RID graph that aren't tied to a specific version or OS distribution and are the preferred choice when using .NET Core 2.0 and higher.</span></span> <span data-ttu-id="0b97f-154">它们在处理多个 Linux 发行版时特别有用，因为大多数发行版 RID 都映射到可移植的 RID。</span><span class="sxs-lookup"><span data-stu-id="0b97f-154">They're particularly useful when dealing with multiple Linux distros since most distribution RIDs are mapped to the portable RIDs.</span></span>

<span data-ttu-id="0b97f-155">以下列表显示了一小部分用于每个 OS 的最常见 RID。</span><span class="sxs-lookup"><span data-stu-id="0b97f-155">The following list shows a small subset of the most common RIDs used for each OS.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="0b97f-156">Windows RID</span><span class="sxs-lookup"><span data-stu-id="0b97f-156">Windows RIDs</span></span>

<span data-ttu-id="0b97f-157">仅列出了公共值。</span><span class="sxs-lookup"><span data-stu-id="0b97f-157">Only common values are listed.</span></span> <span data-ttu-id="0b97f-158">若要获取最新的完整版，请参阅 CoreFX 存储库上的 [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 文件。</span><span class="sxs-lookup"><span data-stu-id="0b97f-158">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

- <span data-ttu-id="0b97f-159">可移植（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="0b97f-159">Portable (.NET Core 2.0 or later versions)</span></span>
  - `win-x64`
  - `win-x86`
  - `win-arm`
  - `win-arm64`
- <span data-ttu-id="0b97f-160">Windows 7 / Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="0b97f-160">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="0b97f-161">Windows 8.1 / Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="0b97f-161">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="0b97f-162">Windows 10 / Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="0b97f-162">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="0b97f-163">有关详细信息，请参阅 [Windows 上 .NET Core 的先决条件](windows-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="0b97f-163">See [Prerequisites for .NET Core on Windows](windows-prerequisites.md) for more information.</span></span>

## <a name="linux-rids"></a><span data-ttu-id="0b97f-164">Linux RID</span><span class="sxs-lookup"><span data-stu-id="0b97f-164">Linux RIDs</span></span>

<span data-ttu-id="0b97f-165">仅列出了公共值。</span><span class="sxs-lookup"><span data-stu-id="0b97f-165">Only common values are listed.</span></span> <span data-ttu-id="0b97f-166">若要获取最新的完整版，请参阅 CoreFX 存储库上的 [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 文件。</span><span class="sxs-lookup"><span data-stu-id="0b97f-166">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span> <span data-ttu-id="0b97f-167">运行以下未列出的发行版的设备可能适用于其中一个可移植 RID。</span><span class="sxs-lookup"><span data-stu-id="0b97f-167">Devices running a distribution not listed below may work with one of the Portable RIDs.</span></span> <span data-ttu-id="0b97f-168">例如，可以将运行未列出的 Linux 发行版的 Raspberry Pi 设备定向为使用 `linux-arm`。</span><span class="sxs-lookup"><span data-stu-id="0b97f-168">For example, Raspberry Pi devices running a Linux distribution not listed can be targeted with `linux-arm`.</span></span>

- <span data-ttu-id="0b97f-169">可移植（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="0b97f-169">Portable (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="0b97f-170">`linux-x64`（大多数桌面发行版，如 CentOS、Debian、Fedora、Ubuntu 及派生版本）</span><span class="sxs-lookup"><span data-stu-id="0b97f-170">`linux-x64` (Most desktop distributions like CentOS, Debian, Fedora, Ubuntu and derivatives)</span></span>
  - <span data-ttu-id="0b97f-171">`linux-musl-x64`（使用 [musl](https://wiki.musl-libc.org/projects-using-musl.html) 的轻量级发行版，如 Alpine Linux）</span><span class="sxs-lookup"><span data-stu-id="0b97f-171">`linux-musl-x64` (Lightweight distributions using [musl](https://wiki.musl-libc.org/projects-using-musl.html) like Alpine Linux)</span></span>
  - <span data-ttu-id="0b97f-172">`linux-arm`（在 ARM 上运行的 Linux 分发版，如 Raspberry Pi）</span><span class="sxs-lookup"><span data-stu-id="0b97f-172">`linux-arm` (Linux distributions running on ARM like Raspberry Pi)</span></span>
- <span data-ttu-id="0b97f-173">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="0b97f-173">Red Hat Enterprise Linux</span></span>
  - <span data-ttu-id="0b97f-174">`rhel-x64`（被 `linux-x64` 取代，适用于 RHEL 6 以上版本）</span><span class="sxs-lookup"><span data-stu-id="0b97f-174">`rhel-x64` (Superseded by `linux-x64` for RHEL above version 6)</span></span>
  - <span data-ttu-id="0b97f-175">`rhel.6-x64`（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="0b97f-175">`rhel.6-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="0b97f-176">Tizen（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="0b97f-176">Tizen (.NET Core 2.0 or later versions)</span></span>
  - `tizen`
  - `tizen.4.0.0`
  - `tizen.5.0.0`

<span data-ttu-id="0b97f-177">有关详细信息，请参阅 [Linux 上 .NET Core 的先决条件](linux-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="0b97f-177">See [Prerequisites for .NET Core on Linux](linux-prerequisites.md) for more information.</span></span>

## <a name="macos-rids"></a><span data-ttu-id="0b97f-178">macOS RID</span><span class="sxs-lookup"><span data-stu-id="0b97f-178">macOS RIDs</span></span>

<span data-ttu-id="0b97f-179">macOS RID 使用较早的“OSX”品牌。</span><span class="sxs-lookup"><span data-stu-id="0b97f-179">macOS RIDs use the older "OSX" branding.</span></span> <span data-ttu-id="0b97f-180">仅列出了公共值。</span><span class="sxs-lookup"><span data-stu-id="0b97f-180">Only common values are listed.</span></span> <span data-ttu-id="0b97f-181">若要获取最新的完整版，请参阅 CoreFX 存储库上的 [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 文件。</span><span class="sxs-lookup"><span data-stu-id="0b97f-181">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

- <span data-ttu-id="0b97f-182">可移植（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="0b97f-182">Portable (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="0b97f-183">`osx-x64`（最低 OS 版本为 macOS 10.12 Sierra）</span><span class="sxs-lookup"><span data-stu-id="0b97f-183">`osx-x64` (Minimum OS version is macOS 10.12 Sierra)</span></span>
- <span data-ttu-id="0b97f-184">macOS 10.10  Yosemite</span><span class="sxs-lookup"><span data-stu-id="0b97f-184">macOS 10.10  Yosemite</span></span>
  - `osx.10.10-x64`
- <span data-ttu-id="0b97f-185">macOS 10.11 El Capitan</span><span class="sxs-lookup"><span data-stu-id="0b97f-185">macOS 10.11 El Capitan</span></span>
  - `osx.10.11-x64`
- <span data-ttu-id="0b97f-186">macOS 10.12 Sierra（.NET Core 1.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="0b97f-186">macOS 10.12 Sierra (.NET Core 1.1 or later versions)</span></span>
  - `osx.10.12-x64`
- <span data-ttu-id="0b97f-187">macOS 10.13 High Sierra（.NET Core 1.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="0b97f-187">macOS 10.13 High Sierra (.NET Core 1.1 or later versions)</span></span>
  - `osx.10.13-x64`
- <span data-ttu-id="0b97f-188">macOS 10.14 Mojave（.NET Core 1.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="0b97f-188">macOS 10.14 Mojave (.NET Core 1.1 or later versions)</span></span>
  - `osx.10.14-x64`

<span data-ttu-id="0b97f-189">有关详细信息，请参阅 [macOS 上 .NET Core 的先决条件](macos-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="0b97f-189">See [Prerequisites for .NET Core on macOS](macos-prerequisites.md) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b97f-190">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b97f-190">See also</span></span>

- [<span data-ttu-id="0b97f-191">运行时 ID</span><span class="sxs-lookup"><span data-stu-id="0b97f-191">Runtime IDs</span></span>](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/readme.md)
