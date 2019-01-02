---
title: .NET Core 运行时标识符 (RID) 目录
description: 了解运行时标识符 (RID) 及如何在 .NET Core 中使用 RID。
ms.date: 07/19/2018
ms.openlocfilehash: b801b7866b563ae06499d8ccd2d07cf5fd52b928
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170190"
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="bc0ab-103">.NET Core RID 目录</span><span class="sxs-lookup"><span data-stu-id="bc0ab-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="bc0ab-104">RID 是运行时标识符的缩写。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-104">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="bc0ab-105">RID 值用于标识应用程序运行所在的目标平台。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="bc0ab-106">.NET 包使用它们来表示 NuGet 包中特定于平台的资产。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="bc0ab-107">以下值是 RID 的示例：`linux-x64`、`ubuntu.14.04-x64`、`win7-x64` 或 `osx.10.12-x64`。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="bc0ab-108">对于具有本机依赖项的包，RID 将指定在其中可以还原包的平台。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="bc0ab-109">可以在项目文件的 `<RuntimeIdentifier>` 元素中设置一个 RID。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-109">A single RID can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="bc0ab-110">可以将多个 RID 定义为项目文件的 `<RuntimeIdentifiers>` 元素中的列表（以分号分隔）。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-110">Multiple RIDs can be defined as a semicolon-delimited list in the project file's `<RuntimeIdentifiers>` element.</span></span> <span data-ttu-id="bc0ab-111">也可使用以下 [.NET Core CLI 命令](./tools/index.md) 通过 `--runtime` 选项使用它们：</span><span class="sxs-lookup"><span data-stu-id="bc0ab-111">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="bc0ab-112">dotnet build</span><span class="sxs-lookup"><span data-stu-id="bc0ab-112">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="bc0ab-113">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="bc0ab-113">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="bc0ab-114">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="bc0ab-114">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="bc0ab-115">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="bc0ab-115">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="bc0ab-116">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="bc0ab-116">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="bc0ab-117">dotnet run</span><span class="sxs-lookup"><span data-stu-id="bc0ab-117">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="bc0ab-118">dotnet store</span><span class="sxs-lookup"><span data-stu-id="bc0ab-118">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="bc0ab-119">表示具体操作系统的 RID 通常遵循以下模式：`[os].[version]-[architecture]-[additional qualifiers]`，其中：</span><span class="sxs-lookup"><span data-stu-id="bc0ab-119">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="bc0ab-120">`[os]` 是操作系统/平台系统名字对象。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-120">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="bc0ab-121">例如 `ubuntu`。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-121">For example, `ubuntu`.</span></span>

- <span data-ttu-id="bc0ab-122">`[version]` 是操作系统版本，使用的格式是以点 (`.`) 分隔的版本号。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-122">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="bc0ab-123">例如 `15.10`。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-123">For example, `15.10`.</span></span>

  - <span data-ttu-id="bc0ab-124">版本不应为营销版本，因为它们通常代表该操作系统的多个离散版本，且具有不同的平台 API 外围应用。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-124">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="bc0ab-125">`[architecture]` 是处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-125">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="bc0ab-126">例如：`x86`、`x64`、`arm` 或 `arm64`。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-126">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="bc0ab-127">`[additional qualifiers]` 进一步区分了不同的平台。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-127">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="bc0ab-128">例如 `aot` 或 `corert`。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-128">For example: `aot` or `corert`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="bc0ab-129">RID 图表</span><span class="sxs-lookup"><span data-stu-id="bc0ab-129">RID graph</span></span>

<span data-ttu-id="bc0ab-130">RID 图表或运行时回退图表是互相兼容的 RID 列表。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-130">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="bc0ab-131">[Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) 包中定义了 RID。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-131">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="bc0ab-132">可以在 CoreFX 存储库的 [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 文件中查看支持的 RID 列表和 RID 图表。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-132">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the CoreFX repo.</span></span> <span data-ttu-id="bc0ab-133">在此文件中，可以看到除基 RID 以外的所有 RID 均包含 `"#import"` 语句。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-133">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="bc0ab-134">这些语句指示的是兼容的 RID。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-134">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="bc0ab-135">NuGet 还原包时，它将尝试找到指定运行时的完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-135">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="bc0ab-136">如果未找到完全匹配项，NuGet 将返回此图表，直至它根据 RID 图表找到最相近的兼容系统。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-136">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="bc0ab-137">以下示例是 `osx.10.12-x64` RID 的实际条目：</span><span class="sxs-lookup"><span data-stu-id="bc0ab-137">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="bc0ab-138">上述 RID 指定 `osx.10.12-x64` 导入 `osx.10.11-x64`。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-138">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="bc0ab-139">因此，当 NuGet 还原包时，它将尝试找到包中的 `osx.10.12-x64` 的完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-139">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="bc0ab-140">例如，如果 NuGet 无法找到特定的运行时，可以还原指定 `osx.10.11-x64` 运行时的包。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-140">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="bc0ab-141">以下示例演示了 runtime.json 文件中定义的另一个略大的 RID 图表：</span><span class="sxs-lookup"><span data-stu-id="bc0ab-141">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

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

<span data-ttu-id="bc0ab-142">所有 RID 最终都会映射回根 `any` RID。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-142">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="bc0ab-143">使用 RID 时，必须牢记以下几个注意事项：</span><span class="sxs-lookup"><span data-stu-id="bc0ab-143">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="bc0ab-144">RID 是不透明字符串，应将其视为黑盒。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-144">RIDs are **opaque strings** and should be treated as black boxes.</span></span>
- <span data-ttu-id="bc0ab-145">请勿以编程方式生成 RID。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-145">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="bc0ab-146">使用已为平台定义的 RID。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-146">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="bc0ab-147">RID 必须具有特定性，因此请勿通过实际的 RID 值假定任何情况。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-147">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="bc0ab-148">使用 RID</span><span class="sxs-lookup"><span data-stu-id="bc0ab-148">Using RIDs</span></span>

<span data-ttu-id="bc0ab-149">若要使用 RID，必须知道有哪些 RID。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-149">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="bc0ab-150">新值将定期添加到该平台。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-150">New values are added regularly to the platform.</span></span>
<span data-ttu-id="bc0ab-151">若要获取最新的完整版，请参阅 CoreFX 存储库上的 [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 文件。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-151">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

<span data-ttu-id="bc0ab-152">.NET Core 2.0 SDK 引入了可移植 RID 的概念。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-152">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="bc0ab-153">它们是添加到 RID 图表的新值，并且未与特定版本或 OS 发行版本关联。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-153">They are new values added to the RID graph that aren't tied to a specific version or OS distribution.</span></span> <span data-ttu-id="bc0ab-154">处理多个 Linux 发行版本时，它们非常有用。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-154">They're particularly useful when dealing with multiple Linux distros.</span></span>

<span data-ttu-id="bc0ab-155">以下列表显示了用于每个 OS 的最常见 RID。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-155">The following list shows the most common RIDs used for each OS.</span></span> <span data-ttu-id="bc0ab-156">其中不包含 `arm` 或 `corert` 值。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-156">It doesn't cover `arm` or `corert` values.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="bc0ab-157">Windows RID</span><span class="sxs-lookup"><span data-stu-id="bc0ab-157">Windows RIDs</span></span>

- <span data-ttu-id="bc0ab-158">可移植</span><span class="sxs-lookup"><span data-stu-id="bc0ab-158">Portable</span></span>
  - `win-x86`
  - `win-x64`
- <span data-ttu-id="bc0ab-159">Windows 7 / Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="bc0ab-159">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="bc0ab-160">Windows 8 / Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="bc0ab-160">Windows 8 / Windows Server 2012</span></span>
  - `win8-x64`
  - `win8-x86`
  - `win8-arm`
- <span data-ttu-id="bc0ab-161">Windows 8.1 / Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="bc0ab-161">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="bc0ab-162">Windows 10 / Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="bc0ab-162">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="bc0ab-163">有关详细信息，请参阅 [Windows 上 .NET Core 的先决条件](windows-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-163">See [Prerequisites for .NET Core on Windows](windows-prerequisites.md) for more information.</span></span>

## <a name="linux-rids"></a><span data-ttu-id="bc0ab-164">Linux RID</span><span class="sxs-lookup"><span data-stu-id="bc0ab-164">Linux RIDs</span></span>

- <span data-ttu-id="bc0ab-165">可移植</span><span class="sxs-lookup"><span data-stu-id="bc0ab-165">Portable</span></span>
  - `linux-x64`
- <span data-ttu-id="bc0ab-166">CentOS</span><span class="sxs-lookup"><span data-stu-id="bc0ab-166">CentOS</span></span>
  - `centos-x64`
  - `centos.7-x64`
- <span data-ttu-id="bc0ab-167">Debian</span><span class="sxs-lookup"><span data-stu-id="bc0ab-167">Debian</span></span>
  - `debian-x64`
  - `debian.8-x64`
  - <span data-ttu-id="bc0ab-168">`debian.9-x64`（.NET Core 1.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-168">`debian.9-x64` (.NET Core 1.1 or later versions)</span></span>
- <span data-ttu-id="bc0ab-169">Fedora</span><span class="sxs-lookup"><span data-stu-id="bc0ab-169">Fedora</span></span>
  - `fedora-x64`
  - `fedora.27-x64`
  - <span data-ttu-id="bc0ab-170">`fedora.28-x64`（.NET Core 1.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-170">`fedora.28-x64` (.NET Core 1.1 or later versions)</span></span>
- <span data-ttu-id="bc0ab-171">Gentoo（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-171">Gentoo (.NET Core 2.0 or later versions)</span></span>
  - `gentoo-x64`
- <span data-ttu-id="bc0ab-172">openSUSE</span><span class="sxs-lookup"><span data-stu-id="bc0ab-172">openSUSE</span></span>
  - `opensuse-x64`
  - `opensuse.42.3-x64`
- <span data-ttu-id="bc0ab-173">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="bc0ab-173">Oracle Linux</span></span>
  - `ol-x64`
  - `ol.7-x64`
  - `ol.7.0-x64`
  - `ol.7.1-x64`
  - `ol.7.2-x64`
  - `ol.7.3-x64`
  - `ol.7.4-x64`
- <span data-ttu-id="bc0ab-174">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="bc0ab-174">Red Hat Enterprise Linux</span></span>
  - `rhel-x64`
  - <span data-ttu-id="bc0ab-175">`rhel.6-x64`（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-175">`rhel.6-x64` (.NET Core 2.0 or later versions)</span></span>
  - `rhel.7-x64`
  - `rhel.7.1-x64`
  - `rhel.7.2-x64`
  - <span data-ttu-id="bc0ab-176">`rhel.7.3-x64`（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-176">`rhel.7.3-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="bc0ab-177">`rhel.7.4-x64`（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-177">`rhel.7.4-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="bc0ab-178">Tizen（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-178">Tizen (.NET Core 2.0 or later versions)</span></span>
  - `tizen`
  - `tizen.4.0.0`
  - `tizen.5.0.0`
- <span data-ttu-id="bc0ab-179">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="bc0ab-179">Ubuntu</span></span>
  - `ubuntu-x64`
  - `ubuntu.14.04-x64`
  - `ubuntu.16.04-x64`
  - `ubuntu.17.10-x64`
  - `ubuntu.18.04-x64`
- <span data-ttu-id="bc0ab-180">Ubuntu 衍生内容</span><span class="sxs-lookup"><span data-stu-id="bc0ab-180">Ubuntu derivatives</span></span>
  - `linuxmint.17-x64`
  - `linuxmint.17.1-x64`
  - `linuxmint.17.2-x64`
  - `linuxmint.17.3-x64`
  - <span data-ttu-id="bc0ab-181">`linuxmint.18-x64`（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-181">`linuxmint.18-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="bc0ab-182">`linuxmint.18.1-x64`（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-182">`linuxmint.18.1-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="bc0ab-183">`linuxmint.18.2-x64`（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-183">`linuxmint.18.2-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="bc0ab-184">`linuxmint.18.3-x64`（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-184">`linuxmint.18.3-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="bc0ab-185">SUSE Enterprise Linux (SLES)（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-185">SUSE Enterprise Linux (SLES) (.NET Core 2.0 or later versions)</span></span>
  - `sles-x64`
  - `sles.12-x64`
  - `sles.12.1-x64`
  - `sles.12.2-x64`
  - `sles.12.3-x64`
- <span data-ttu-id="bc0ab-186">Alpine Linux（.NET Core 2.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-186">Alpine Linux (.NET Core 2.1 or later versions)</span></span>
  - `alpine-x64`
  - `alpine.3.7-x64`

<span data-ttu-id="bc0ab-187">有关详细信息，请参阅 [Linux 上 .NET Core 的先决条件](linux-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-187">See [Prerequisites for .NET Core on Linux](linux-prerequisites.md) for more information.</span></span>

## <a name="macos-rids"></a><span data-ttu-id="bc0ab-188">macOS RID</span><span class="sxs-lookup"><span data-stu-id="bc0ab-188">macOS RIDs</span></span>

<span data-ttu-id="bc0ab-189">macOS RID 使用较早的“OSX”品牌。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-189">macOS RIDs use the older "OSX" branding.</span></span>

- <span data-ttu-id="bc0ab-190">`osx-x64`（NET Core 2.0 或更高版本，最低版本为 `osx.10.12-x64`）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-190">`osx-x64` (.NET Core 2.0 or later versions, minimum version is `osx.10.12-x64`)</span></span>
- `osx.10.10-x64`
- `osx.10.11-x64`
- <span data-ttu-id="bc0ab-191">`osx.10.12-x64`（.NET Core 1.1 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-191">`osx.10.12-x64` (.NET Core 1.1 or later versions)</span></span>
- `osx.10.13-x64`

<span data-ttu-id="bc0ab-192">有关详细信息，请参阅 [macOS 上 .NET Core 的先决条件](macos-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="bc0ab-192">See [Prerequisites for .NET Core on macOS](macos-prerequisites.md) for more information.</span></span>

## <a name="android-rids-net-core-20-or-later-versions"></a><span data-ttu-id="bc0ab-193">Android RID（.NET Core 2.0 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="bc0ab-193">Android RIDs (.NET Core 2.0 or later versions)</span></span>

- `android`
- `android.21`

## <a name="see-also"></a><span data-ttu-id="bc0ab-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc0ab-194">See also</span></span>

* [<span data-ttu-id="bc0ab-195">运行时 ID</span><span class="sxs-lookup"><span data-stu-id="bc0ab-195">Runtime IDs</span></span>](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/readme.md)
