---
title: ".NET Core 运行时标识符 (RID) 目录"
description: "了解运行时标识符 (RID) 及如何在 .NET Core 中使用 RID。"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 08/22/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: b2032f5d-771f-48d9-917c-587d9509035c
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3490fb639efd223dc36190324bdf3a06bc23c10e
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="net-core-runtime-identifier-rid-catalog"></a><span data-ttu-id="f4dce-104">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="f4dce-104">.NET Core Runtime IDentifier (RID) catalog</span></span>

## <a name="what-are-rids"></a><span data-ttu-id="f4dce-105">RID 是什么？</span><span class="sxs-lookup"><span data-stu-id="f4dce-105">What are RIDs?</span></span>
<span data-ttu-id="f4dce-106">RID 是运行时标识符的缩写。</span><span class="sxs-lookup"><span data-stu-id="f4dce-106">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="f4dce-107">RID 用于标识其中将运行应用程序或资产（即程序集）的目标操作系统。</span><span class="sxs-lookup"><span data-stu-id="f4dce-107">RIDs are used to identify target operating systems where an application or asset (that is, assembly) will run.</span></span> <span data-ttu-id="f4dce-108">其外观类似如下：“ubuntu.14.04-x64”、“win7-x64”、“osx.10.11-x64”。</span><span class="sxs-lookup"><span data-stu-id="f4dce-108">They look like this: "ubuntu.14.04-x64", "win7-x64", "osx.10.11-x64".</span></span> <span data-ttu-id="f4dce-109">对于具有本机依赖项的包，它将指定在其中可以还原包的平台。</span><span class="sxs-lookup"><span data-stu-id="f4dce-109">For the packages with native dependencies, it will designate on which platforms the package can be restored.</span></span> 

<span data-ttu-id="f4dce-110">请务必注意 RID 实际上是不透明字符串。</span><span class="sxs-lookup"><span data-stu-id="f4dce-110">It is important to note that RIDs are really opaque strings.</span></span> <span data-ttu-id="f4dce-111">这意味着它们需要与使用它们的操作完全匹配。</span><span class="sxs-lookup"><span data-stu-id="f4dce-111">This means that they have to match exactly for operations using them to work.</span></span> <span data-ttu-id="f4dce-112">例如，让我们设想这样的情况，[Elementary OS](https://elementary.io/) 是 Ubuntu 14.04 的简单克隆。</span><span class="sxs-lookup"><span data-stu-id="f4dce-112">As an example, let us consider the case of [Elementary OS](https://elementary.io/), which is a straightforward clone of Ubuntu 14.04.</span></span> <span data-ttu-id="f4dce-113">虽然 .NET Core 和 CLI 基于该版本的 Ubuntu 工作，但如果尝试不进行任何修改就在 Elementary OS 上使用它们，则任何包的还原操作都将失败。</span><span class="sxs-lookup"><span data-stu-id="f4dce-113">Although .NET Core and CLI work on top of that version of Ubuntu, if you try to use them on Elementary OS without any modifications, the restore operation for any package will fail.</span></span> <span data-ttu-id="f4dce-114">这是因为当前不具有将 Elementary OS 指定为一种平台的 RID。</span><span class="sxs-lookup"><span data-stu-id="f4dce-114">This is because we currently don't have a RID that designates Elementary OS as a platform.</span></span> 

<span data-ttu-id="f4dce-115">表示具体操作系统的 RID 通常遵循以下模式：`[os].[version]-[arch]`，其中：</span><span class="sxs-lookup"><span data-stu-id="f4dce-115">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[arch]` where:</span></span>
- <span data-ttu-id="f4dce-116">`[os]` 是系统名字对象，例如 `ubuntu`。</span><span class="sxs-lookup"><span data-stu-id="f4dce-116">`[os]` is the operating system moniker, for example, `ubuntu`.</span></span>
- <span data-ttu-id="f4dce-117">`[version]` 是用圆点 (`.`) 分隔的版本号形式表示的操作系统版本（例如 `15.10`），准确性足以合理启用资产来使用该版本代表的操作系统平台 API。</span><span class="sxs-lookup"><span data-stu-id="f4dce-117">`[version]` is the operating system version in the form of a dot (`.`) separated version number, for example, `15.10`, accurate enough to reasonably enable assets to target operating system platform APIs represented by that version.</span></span>
  - <span data-ttu-id="f4dce-118">这**不应**为营销版本，因为它们通常代表该操作系统的多个离散版本，且具有不同的平台 API 外围应用。</span><span class="sxs-lookup"><span data-stu-id="f4dce-118">This **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>
- <span data-ttu-id="f4dce-119">`[arch]` 是处理器体系结构，例如 `x86`、`x64`、`arm`、`arm64` 等。</span><span class="sxs-lookup"><span data-stu-id="f4dce-119">`[arch]` is the processor architecture, for example, `x86`, `x64`, `arm`, `arm64`, etc.</span></span>

<span data-ttu-id="f4dce-120">RID 图形是在名为 `runtime.json` 的文件中名为 `Microsoft.NETCore.Platforms` 的包中定义的，请参见 [CoreFX repo](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json)。</span><span class="sxs-lookup"><span data-stu-id="f4dce-120">The RID graph is defined in a package called `Microsoft.NETCore.Platforms` in a file called `runtime.json`, which you can see on the [CoreFX repo](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json).</span></span> <span data-ttu-id="f4dce-121">如果使用此文件，你将注意到，某些 RID 中具有 `"#import"` 语句。</span><span class="sxs-lookup"><span data-stu-id="f4dce-121">If you use this file, you will notice that some of the RIDs have an `"#import"` statement in them.</span></span> <span data-ttu-id="f4dce-122">这些语句是兼容性语句。</span><span class="sxs-lookup"><span data-stu-id="f4dce-122">These statements are compatibility statements.</span></span> <span data-ttu-id="f4dce-123">这意味着其中已导入 RID 的 RID 可以作为该 RID 还原包的目标。</span><span class="sxs-lookup"><span data-stu-id="f4dce-123">That means that a RID that has an imported RID in it can be a target for restoring packages for that RID.</span></span> <span data-ttu-id="f4dce-124">看上去有点混乱，让我们看一个示例。</span><span class="sxs-lookup"><span data-stu-id="f4dce-124">Slightly confusing, but let's look at an example.</span></span> <span data-ttu-id="f4dce-125">我们来看一看 macOS：</span><span class="sxs-lookup"><span data-stu-id="f4dce-125">Let's take a look at macOS:</span></span>

```json
"osx.10.11-x64": {
    "#import": [ "osx.10.11", "osx.10.10-x64" ]
}
```
<span data-ttu-id="f4dce-126">上述 RID 指定 `osx.10.11-x64` 导入 `osx.10.10-x64`。</span><span class="sxs-lookup"><span data-stu-id="f4dce-126">The above RID specifies that `osx.10.11-x64` imports `osx.10.10-x64`.</span></span> <span data-ttu-id="f4dce-127">这意味着，当还原包时，NuGet 将能够还原指定在 `osx.10.11-x64` 上需要 `osx.10.10-x64` 的所有包。</span><span class="sxs-lookup"><span data-stu-id="f4dce-127">This means that when restoring packages, NuGet will be able to restore packages that specify that they need `osx.10.10-x64` on `osx.10.11-x64`.</span></span>

<span data-ttu-id="f4dce-128">一个稍微大点的示例 RID 关系图：</span><span class="sxs-lookup"><span data-stu-id="f4dce-128">A slightly bigger example RID graph:</span></span>  

- `win10-arm`
  - `win10`
  - `win81-arm`
    - `win81`
    - `win8-arm`
      - `win8`
        - `win7`
          - `win`
            - `any`

<span data-ttu-id="f4dce-129">所有 RID 最终都会映射回根 `any` RID。</span><span class="sxs-lookup"><span data-stu-id="f4dce-129">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="f4dce-130">虽然看起来使用相当容易，但仍有几件关于 RID 的特殊事项，在你使用它们的时候需要牢记：</span><span class="sxs-lookup"><span data-stu-id="f4dce-130">Although they look easy enough to use, there are some special things about RIDs that you have to keep in mind when working with them:</span></span>

* <span data-ttu-id="f4dce-131">它们是**不透明字符串**并且应将其视为黑框</span><span class="sxs-lookup"><span data-stu-id="f4dce-131">They are **opaque strings** and should be treated as black boxes</span></span>
    * <span data-ttu-id="f4dce-132">不应以编程方式构造 RID</span><span class="sxs-lookup"><span data-stu-id="f4dce-132">You should not construct RIDs programmatically</span></span>
* <span data-ttu-id="f4dce-133">需要使用已针对平台定义的 RID，并且此文档表明</span><span class="sxs-lookup"><span data-stu-id="f4dce-133">You need to use the RIDs that are already defined for the platform and this document shows that</span></span>
* <span data-ttu-id="f4dce-134">RID 需要具体化，因此不用假定来自实际 RID 值的任何内容；请参阅此文档以确定给定平台需要哪个 RID</span><span class="sxs-lookup"><span data-stu-id="f4dce-134">The RIDs do need to be specific so don't assume anything from the actual RID value; please consult this document to determine which RID(s) you need for a given platform</span></span>

## <a name="using-rids"></a><span data-ttu-id="f4dce-135">使用 RID</span><span class="sxs-lookup"><span data-stu-id="f4dce-135">Using RIDs</span></span>
<span data-ttu-id="f4dce-136">若要使用 RID，必须知道有哪些 RID。</span><span class="sxs-lookup"><span data-stu-id="f4dce-136">In order to use RIDs, you have to know which RIDs there are.</span></span> <span data-ttu-id="f4dce-137">新的 RID 将定期添加到该平台。</span><span class="sxs-lookup"><span data-stu-id="f4dce-137">New RIDs are added regularly to the platform.</span></span> <span data-ttu-id="f4dce-138">有关最新版本，请查看 CoreFX 存储库上的 [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 文件。</span><span class="sxs-lookup"><span data-stu-id="f4dce-138">For the latest version, please check the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

> [!NOTE]
> <span data-ttu-id="f4dce-139">我们正致力于以更具交互性的形式提供此信息。</span><span class="sxs-lookup"><span data-stu-id="f4dce-139">We are working towards getting this information into a more interactive form.</span></span> <span data-ttu-id="f4dce-140">届时，此页面将更新为指向该工具和/或其使用情况文档。</span><span class="sxs-lookup"><span data-stu-id="f4dce-140">When that happens, this page will be updated to point to that tool and/or its usage documentation.</span></span> 

## <a name="windows-rids"></a><span data-ttu-id="f4dce-141">Windows RID</span><span class="sxs-lookup"><span data-stu-id="f4dce-141">Windows RIDs</span></span>

* <span data-ttu-id="f4dce-142">Windows 7 / Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="f4dce-142">Windows 7 / Windows Server 2008 R2</span></span>
    * `win7-x64`
    * `win7-x86`
* <span data-ttu-id="f4dce-143">Windows 8 / Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="f4dce-143">Windows 8 / Windows Server 2012</span></span>
    * `win8-x64`
    * `win8-x86`
    * `win8-arm`
* <span data-ttu-id="f4dce-144">Windows 8.1 / Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f4dce-144">Windows 8.1 / Windows Server 2012 R2</span></span>
    * `win81-x64`
    * `win81-x86`
    * `win81-arm`
* <span data-ttu-id="f4dce-145">Windows 10 / Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f4dce-145">Windows 10 / Windows Server 2016</span></span>
    * `win10-x64`
    * `win10-x86`
    * `win10-arm`
    * `win10-arm64`

## <a name="linux-rids"></a><span data-ttu-id="f4dce-146">Linux RID</span><span class="sxs-lookup"><span data-stu-id="f4dce-146">Linux RIDs</span></span>

* <span data-ttu-id="f4dce-147">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="f4dce-147">Red Hat Enterprise Linux</span></span>
    * `rhel.7-x64`
* <span data-ttu-id="f4dce-148">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="f4dce-148">Ubuntu</span></span>
    * `ubuntu.14.04-x64`
    * `ubuntu.14.10-x64`
    * `ubuntu.15.04-x64`
    * `ubuntu.15.10-x64`
    * `ubuntu.16.04-x64`
    * `ubuntu.16.10-x64`
* <span data-ttu-id="f4dce-149">CentOS</span><span class="sxs-lookup"><span data-stu-id="f4dce-149">CentOS</span></span>
    * `centos.7-x64`
* <span data-ttu-id="f4dce-150">Debian</span><span class="sxs-lookup"><span data-stu-id="f4dce-150">Debian</span></span>
    * `debian.8-x64`
* <span data-ttu-id="f4dce-151">Fedora</span><span class="sxs-lookup"><span data-stu-id="f4dce-151">Fedora</span></span>
    * `fedora.23-x64`
    * `fedora.24-x64`
* <span data-ttu-id="f4dce-152">OpenSUSE</span><span class="sxs-lookup"><span data-stu-id="f4dce-152">OpenSUSE</span></span>
    * `opensuse.13.2-x64`
    * `opensuse.42.1-x64`
* <span data-ttu-id="f4dce-153">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="f4dce-153">Oracle Linux</span></span>
    * `ol.7-x64`
    * `ol.7.0-x64`
    * `ol.7.1-x64`
    * `ol.7.2-x64`
* <span data-ttu-id="f4dce-154">当前支持的 Ubuntu 派生类</span><span class="sxs-lookup"><span data-stu-id="f4dce-154">Currently supported Ubuntu derivatives</span></span> 
    * `linuxmint.17-x64`
    * `linuxmint.17.1-x64`
    * `linuxmint.17.2-x64`
    * `linuxmint.17.3-x64`
    * `linuxmint.18-x64`

## <a name="os-x-rids"></a><span data-ttu-id="f4dce-155">OS X RID</span><span class="sxs-lookup"><span data-stu-id="f4dce-155">OS X RIDs</span></span>

* `osx.10.10-x64`
* `osx.10.11-x64`
* `osx.10.12-x64`

