---
title: ".NET Core 运行时标识符 (RID) 目录"
description: "了解运行时标识符 (RID) 及如何在 .NET Core 中使用 RID。"
author: mairaw
ms.author: mairaw
ms.date: 09/07/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 067f9cfc283a14b7ea59a7454b7f593ce6eb5806
ms.sourcegitcommit: 62d3e3e74c1b7ffa927590012c0b9f87de1b0848
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="ee125-103">.NET Core RID 目录</span><span class="sxs-lookup"><span data-stu-id="ee125-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="ee125-104">RID 是运行时标识符的缩写。</span><span class="sxs-lookup"><span data-stu-id="ee125-104">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="ee125-105">RID 值用于标识应用程序运行所在的目标平台。</span><span class="sxs-lookup"><span data-stu-id="ee125-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="ee125-106">.NET 包使用它们来表示 NuGet 包中特定于平台的资产。</span><span class="sxs-lookup"><span data-stu-id="ee125-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="ee125-107">以下值是 RID 的示例：`linux-x64`、`ubuntu.14.04-x64`、`win7-x64` 或 `osx.10.12-x64`。</span><span class="sxs-lookup"><span data-stu-id="ee125-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="ee125-108">对于具有本机依赖项的包，RID 将指定在其中可以还原包的平台。</span><span class="sxs-lookup"><span data-stu-id="ee125-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="ee125-109">可在项目文件的 `<RuntimeIdentifier>` 元素中设置 RID。</span><span class="sxs-lookup"><span data-stu-id="ee125-109">RIDs can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="ee125-110">也可使用以下 [.NET Core CLI 命令](./tools/index.md) 通过 `--runtime` 选项使用它们：</span><span class="sxs-lookup"><span data-stu-id="ee125-110">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="ee125-111">dotnet build</span><span class="sxs-lookup"><span data-stu-id="ee125-111">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="ee125-112">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="ee125-112">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="ee125-113">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="ee125-113">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="ee125-114">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="ee125-114">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="ee125-115">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="ee125-115">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="ee125-116">dotnet run</span><span class="sxs-lookup"><span data-stu-id="ee125-116">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="ee125-117">dotnet store</span><span class="sxs-lookup"><span data-stu-id="ee125-117">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="ee125-118">表示具体操作系统的 RID 通常遵循以下模式：`[os].[version]-[architecture]-[additional qualifiers]`，其中：</span><span class="sxs-lookup"><span data-stu-id="ee125-118">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="ee125-119">`[os]` 是操作系统/平台系统名字对象。</span><span class="sxs-lookup"><span data-stu-id="ee125-119">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="ee125-120">例如 `ubuntu`。</span><span class="sxs-lookup"><span data-stu-id="ee125-120">For example, `ubuntu`.</span></span>

- <span data-ttu-id="ee125-121">`[version]` 是操作系统版本，使用的格式是以点 (`.`) 分隔的版本号。</span><span class="sxs-lookup"><span data-stu-id="ee125-121">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="ee125-122">例如 `15.10`。</span><span class="sxs-lookup"><span data-stu-id="ee125-122">For example, `15.10`.</span></span>

  - <span data-ttu-id="ee125-123">版本不应为营销版本，因为它们通常代表该操作系统的多个离散版本，且具有不同的平台 API 外围应用。</span><span class="sxs-lookup"><span data-stu-id="ee125-123">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="ee125-124">`[architecture]` 是处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="ee125-124">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="ee125-125">例如：`x86`、`x64`、`arm` 或 `arm64`。</span><span class="sxs-lookup"><span data-stu-id="ee125-125">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="ee125-126">`[additional qualifiers]` 进一步区分了不同的平台。</span><span class="sxs-lookup"><span data-stu-id="ee125-126">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="ee125-127">例如 `aot` 或 `corert`。</span><span class="sxs-lookup"><span data-stu-id="ee125-127">For example: `aot` or `corert`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="ee125-128">RID 图表</span><span class="sxs-lookup"><span data-stu-id="ee125-128">RID graph</span></span>

<span data-ttu-id="ee125-129">RID 图表或运行时回退图表是互相兼容的 RID 列表。</span><span class="sxs-lookup"><span data-stu-id="ee125-129">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="ee125-130">[Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) 包中定义了 RID。</span><span class="sxs-lookup"><span data-stu-id="ee125-130">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="ee125-131">可以在 CoreFX 存储库的 [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 文件中查看支持的 RID 列表和 RID 图表。</span><span class="sxs-lookup"><span data-stu-id="ee125-131">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the CoreFX repo.</span></span> <span data-ttu-id="ee125-132">在此文件中，可以看到除基 RID 以外的所有 RID 均包含 `"#import"` 语句。</span><span class="sxs-lookup"><span data-stu-id="ee125-132">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="ee125-133">这些语句指示的是兼容的 RID。</span><span class="sxs-lookup"><span data-stu-id="ee125-133">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="ee125-134">NuGet 还原包时，它将尝试找到指定运行时的完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="ee125-134">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="ee125-135">如果未找到完全匹配项，NuGet 将返回此图表，直至它根据 RID 图表找到最相近的兼容系统。</span><span class="sxs-lookup"><span data-stu-id="ee125-135">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="ee125-136">以下示例是 `osx.10.12-x64` RID 的实际条目：</span><span class="sxs-lookup"><span data-stu-id="ee125-136">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="ee125-137">上述 RID 指定 `osx.10.12-x64` 导入 `osx.10.11-x64`。</span><span class="sxs-lookup"><span data-stu-id="ee125-137">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="ee125-138">因此，当 NuGet 还原包时，它将尝试找到包中的 `osx.10.12-x64` 的完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="ee125-138">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="ee125-139">例如，如果 NuGet 无法找到特定的运行时，可以还原指定 `osx.10.11-x64` 运行时的包。</span><span class="sxs-lookup"><span data-stu-id="ee125-139">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="ee125-140">以下示例演示了 runtime.json 文件中定义的另一个略大的 RID 图表：</span><span class="sxs-lookup"><span data-stu-id="ee125-140">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

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

<span data-ttu-id="ee125-141">所有 RID 最终都会映射回根 `any` RID。</span><span class="sxs-lookup"><span data-stu-id="ee125-141">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="ee125-142">使用 RID 时，必须牢记以下几个注意事项：</span><span class="sxs-lookup"><span data-stu-id="ee125-142">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="ee125-143">RID 是不透明字符串，应将其视为黑盒。</span><span class="sxs-lookup"><span data-stu-id="ee125-143">RIDs are **opaque strings** and should be treated as black boxes.</span></span>
- <span data-ttu-id="ee125-144">请勿以编程方式生成 RID。</span><span class="sxs-lookup"><span data-stu-id="ee125-144">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="ee125-145">使用已为平台定义的 RID。</span><span class="sxs-lookup"><span data-stu-id="ee125-145">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="ee125-146">RID 必须具有特定性，因此请勿通过实际的 RID 值假定任何情况。</span><span class="sxs-lookup"><span data-stu-id="ee125-146">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="ee125-147">使用 RID</span><span class="sxs-lookup"><span data-stu-id="ee125-147">Using RIDs</span></span>

<span data-ttu-id="ee125-148">若要使用 RID，必须知道有哪些 RID。</span><span class="sxs-lookup"><span data-stu-id="ee125-148">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="ee125-149">新值将定期添加到该平台。</span><span class="sxs-lookup"><span data-stu-id="ee125-149">New values are added regularly to the platform.</span></span>
<span data-ttu-id="ee125-150">若要获取最新的完整版，请参阅 CoreFX 存储库上的 [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 文件。</span><span class="sxs-lookup"><span data-stu-id="ee125-150">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

<span data-ttu-id="ee125-151">.NET Core 2.0 SDK 引入了可移植 RID 的概念。</span><span class="sxs-lookup"><span data-stu-id="ee125-151">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="ee125-152">它们是添加到 RID 图表的新值，并且未与特定版本或 OS 发行版本关联。</span><span class="sxs-lookup"><span data-stu-id="ee125-152">They are new values added to the RID graph that aren't tied to a specific version or OS distribution.</span></span> <span data-ttu-id="ee125-153">处理多个 Linux 发行版时，它们是特别有用。</span><span class="sxs-lookup"><span data-stu-id="ee125-153">They're particularly useful when dealing with multiple Linux distros.</span></span>

<span data-ttu-id="ee125-154">以下列表显示了用于每个 OS 的最常见 RID。</span><span class="sxs-lookup"><span data-stu-id="ee125-154">The following list shows the most common RIDs used for each OS.</span></span> <span data-ttu-id="ee125-155">其中不包含 `arm` 或 `corert` 值。</span><span class="sxs-lookup"><span data-stu-id="ee125-155">It doesn't cover `arm` or `corert` values.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="ee125-156">Windows RID</span><span class="sxs-lookup"><span data-stu-id="ee125-156">Windows RIDs</span></span>

- <span data-ttu-id="ee125-157">可移植</span><span class="sxs-lookup"><span data-stu-id="ee125-157">Portable</span></span>
  - `win-x86`
  - `win-x64`
- <span data-ttu-id="ee125-158">Windows 7 / Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ee125-158">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="ee125-159">Windows 8 / Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ee125-159">Windows 8 / Windows Server 2012</span></span>
  - `win8-x64`
  - `win8-x86`
  - `win8-arm`
- <span data-ttu-id="ee125-160">Windows 8.1 / Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ee125-160">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="ee125-161">Windows 10 / Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ee125-161">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="ee125-162">请参阅[.NET 核心 Windows 上的先决条件](windows-prerequisites.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="ee125-162">See [Prerequisites for .NET Core on Windows](windows-prerequisites.md) for more information.</span></span>

## <a name="linux-rids"></a><span data-ttu-id="ee125-163">Linux RID</span><span class="sxs-lookup"><span data-stu-id="ee125-163">Linux RIDs</span></span>

- <span data-ttu-id="ee125-164">可移植</span><span class="sxs-lookup"><span data-stu-id="ee125-164">Portable</span></span>
  - `linux-x64`
- <span data-ttu-id="ee125-165">CentOS</span><span class="sxs-lookup"><span data-stu-id="ee125-165">CentOS</span></span>
  - `centos-x64`
  - `centos.7-x64`
- <span data-ttu-id="ee125-166">Debian</span><span class="sxs-lookup"><span data-stu-id="ee125-166">Debian</span></span>
  - `debian-x64`
  - `debian.8-x64`
- <span data-ttu-id="ee125-167">Fedora</span><span class="sxs-lookup"><span data-stu-id="ee125-167">Fedora</span></span>
  - `fedora-x64`
  - `fedora.24-x64`
  - <span data-ttu-id="ee125-168">`fedora.25-x64`（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="ee125-168">`fedora.25-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="ee125-169">`fedora.26-x64`（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="ee125-169">`fedora.26-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="ee125-170">Gentoo（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="ee125-170">Gentoo (.NET Core 2.0 or later versions)</span></span>
  - `gentoo-x64`
- <span data-ttu-id="ee125-171">openSUSE</span><span class="sxs-lookup"><span data-stu-id="ee125-171">openSUSE</span></span>
  - `opensuse-x64`
  - `opensuse.42.1-x64`
- <span data-ttu-id="ee125-172">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="ee125-172">Oracle Linux</span></span>
  - `ol-x64`
  - `ol.7-x64`
  - `ol.7.0-x64`
  - `ol.7.1-x64`
  - `ol.7.2-x64`
- <span data-ttu-id="ee125-173">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="ee125-173">Red Hat Enterprise Linux</span></span>
  - `rhel-x64`
  - <span data-ttu-id="ee125-174">`rhel.6-x64`（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="ee125-174">`rhel.6-x64` (.NET Core 2.0 or later versions)</span></span>
  - `rhel.7-x64`
  - `rhel.7.1-x64`
  - `rhel.7.2-x64`
  - <span data-ttu-id="ee125-175">`rhel.7.3-x64`（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="ee125-175">`rhel.7.3-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="ee125-176">`rhel.7.4-x64`（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="ee125-176">`rhel.7.4-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="ee125-177">Tizen（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="ee125-177">Tizen (.NET Core 2.0 or later versions)</span></span>
  - `tizen`
- <span data-ttu-id="ee125-178">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="ee125-178">Ubuntu</span></span>
  - `ubuntu-x64`
  - `ubuntu.14.04-x64`
  - `ubuntu.14.10-x64`
  - `ubuntu.15.04-x64`
  - `ubuntu.15.10-x64`
  - `ubuntu.16.04-x64`
  - `ubuntu.16.10-x64`
- <span data-ttu-id="ee125-179">Ubuntu 衍生内容</span><span class="sxs-lookup"><span data-stu-id="ee125-179">Ubuntu derivatives</span></span>
  - `linuxmint.17-x64`
  - `linuxmint.17.1-x64`
  - `linuxmint.17.2-x64`
  - `linuxmint.17.3-x64`
  - `linuxmint.18-x64`
  - <span data-ttu-id="ee125-180">`linuxmint.18.1-x64`（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="ee125-180">`linuxmint.18.1-x64` (.NET Core 2.0 or later versions)</span></span>

<span data-ttu-id="ee125-181">请参阅[在 Linux 上的.NET 核心的先决条件](linux-prerequisites.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="ee125-181">See [Prerequisites for .NET Core on Linux](linux-prerequisites.md) for more information.</span></span>

## <a name="macos-rids"></a><span data-ttu-id="ee125-182">macOS Rid</span><span class="sxs-lookup"><span data-stu-id="ee125-182">macOS RIDs</span></span>

<span data-ttu-id="ee125-183">macOS Rid 使用较旧的"OSX"品牌。</span><span class="sxs-lookup"><span data-stu-id="ee125-183">macOS RIDs use the older "OSX" branding.</span></span>

- <span data-ttu-id="ee125-184">`osx-x64`(.NET 核心 2.0 或更高版本，最低版本是`osx.10.12-x64`)</span><span class="sxs-lookup"><span data-stu-id="ee125-184">`osx-x64` (.NET Core 2.0 or later versions, minimum version is `osx.10.12-x64`)</span></span>
- `osx.10.10-x64`
- `osx.10.11-x64`
- <span data-ttu-id="ee125-185">`osx.10.12-x64`（.NET Core 1.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="ee125-185">`osx.10.12-x64` (.NET Core 1.1 or later versions)</span></span>
- `osx.10.13-x64`

<span data-ttu-id="ee125-186">请参阅[在 macOS 上的.NET 核心的先决条件](macos-prerequisites.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="ee125-186">See [Prerequisites for .NET Core on macOS](macos-prerequisites.md) for more information.</span></span>

## <a name="android-rids-net-core-20-or-later-versions"></a><span data-ttu-id="ee125-187">Android RID（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="ee125-187">Android RIDs (.NET Core 2.0 or later versions)</span></span>

- `android`
- `android.21`

## <a name="see-also"></a><span data-ttu-id="ee125-188">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee125-188">See also</span></span>

[<span data-ttu-id="ee125-189">运行时 ID</span><span class="sxs-lookup"><span data-stu-id="ee125-189">Runtime IDs</span></span>](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/readme.md)
