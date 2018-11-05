---
title: 版本控制和 .NET 库
description: 版本控制 .NET 库的最佳实践建议。
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: f95c8ade1f91af5c13184b839b327c9397c6fe5a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187853"
---
# <a name="versioning"></a><span data-ttu-id="6656f-103">版本管理</span><span class="sxs-lookup"><span data-stu-id="6656f-103">Versioning</span></span>

<span data-ttu-id="6656f-104">软件库在版本 1.0 中很少是完整的。</span><span class="sxs-lookup"><span data-stu-id="6656f-104">A software library is rarely complete in version 1.0.</span></span> <span data-ttu-id="6656f-105">良好的库随时间而演变，例如，添加功能、修复缺陷和提高性能。</span><span class="sxs-lookup"><span data-stu-id="6656f-105">Good libraries evolve over time, adding features, fixing bugs and improving performance.</span></span> <span data-ttu-id="6656f-106">重要的是你可以发布新版本的 .NET 库，为每个版本提供附加值，而不会中断现有用户。</span><span class="sxs-lookup"><span data-stu-id="6656f-106">It is important that you can release new versions of a .NET library, providing additional value with each version, without breaking existing users.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="6656f-107">重大更改</span><span class="sxs-lookup"><span data-stu-id="6656f-107">Breaking changes</span></span>

<span data-ttu-id="6656f-108">有关处理版本之间的重大更改的信息，请参阅[重大更改](./breaking-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="6656f-108">For information about handling breaking changes between versions, see [Breaking changes](./breaking-changes.md).</span></span>

## <a name="version-numbers"></a><span data-ttu-id="6656f-109">版本号</span><span class="sxs-lookup"><span data-stu-id="6656f-109">Version numbers</span></span>

<span data-ttu-id="6656f-110">.NET 库有多种方法用来指定版本。</span><span class="sxs-lookup"><span data-stu-id="6656f-110">A .NET library has many ways to specify a version.</span></span> <span data-ttu-id="6656f-111">以下版本是最重要的：</span><span class="sxs-lookup"><span data-stu-id="6656f-111">These versions are the most important:</span></span>

### <a name="nuget-package-version"></a><span data-ttu-id="6656f-112">NuGet 包版本</span><span class="sxs-lookup"><span data-stu-id="6656f-112">NuGet package version</span></span>

<span data-ttu-id="6656f-113">使用 NuGet 包时，[NuGet 包版本](/nuget/reference/package-versioning)会显示在 NuGet.org（即 Visual Studio NuGet 包管理器）上，并添加到源代码。</span><span class="sxs-lookup"><span data-stu-id="6656f-113">The [NuGet package version](/nuget/reference/package-versioning) is displayed on NuGet.org, the Visual Studio NuGet package manager, and is added to source code when the package is used.</span></span> <span data-ttu-id="6656f-114">NuGet 包版本是用户通常看到的版本号，并且会在用户谈论所用的库的版本时引用该包版本。</span><span class="sxs-lookup"><span data-stu-id="6656f-114">The NuGet package version is the version number users will commonly see, and they'll refer to it when they talk about the version of a library they're using.</span></span> <span data-ttu-id="6656f-115">NuGet 包版本由 NuGet 使用，并且对运行时行为没有影响。</span><span class="sxs-lookup"><span data-stu-id="6656f-115">The NuGet package version is used by NuGet and has no effect on runtime behavior.</span></span>

```xml
<PackageVersion>1.0.0-alpha1</PackageVersion>
```

<span data-ttu-id="6656f-116">与 NuGet 包版本结合使用的 NuGet 包标识符用于标识 NuGet 中的包。</span><span class="sxs-lookup"><span data-stu-id="6656f-116">The NuGet package identifier combined with the NuGet package version is used to identify a package in NuGet.</span></span> <span data-ttu-id="6656f-117">例如，`Newtonsoft.Json` + `11.0.2`。</span><span class="sxs-lookup"><span data-stu-id="6656f-117">For example, `Newtonsoft.Json` + `11.0.2`.</span></span> <span data-ttu-id="6656f-118">带有后缀的包是一个预发行包，其中的特殊行为非常适用于测试。</span><span class="sxs-lookup"><span data-stu-id="6656f-118">A package with a suffix is a pre-release package and has special behavior that makes it ideal for testing.</span></span> <span data-ttu-id="6656f-119">有关详细信息，请参阅[预发行包](./nuget.md#pre-release-packages)。</span><span class="sxs-lookup"><span data-stu-id="6656f-119">For more information, see [Pre-release packages](./nuget.md#pre-release-packages).</span></span>

<span data-ttu-id="6656f-120">由于 NuGet 包版本是开发人员最易于可见的版本，因此最好使用[语义化版本控制 (SemVer)](https://semver.org/) 进行更新。</span><span class="sxs-lookup"><span data-stu-id="6656f-120">Because the NuGet package version is the most visible version to developers, it's a good idea to update it using [Semantic Versioning (SemVer)](https://semver.org/).</span></span> <span data-ttu-id="6656f-121">SemVer 指出版本之间的重大更改，并且可以帮助开发人员在选择要使用哪个版本时做出明智的决策。</span><span class="sxs-lookup"><span data-stu-id="6656f-121">SemVer indicates the significance of changes between release and helps developers make an informed decision when choosing what version to use.</span></span> <span data-ttu-id="6656f-122">例如，从 `1.0` 到 `2.0` 指示可能有重大更改。</span><span class="sxs-lookup"><span data-stu-id="6656f-122">For example, going from `1.0` to `2.0` indicates that there are potentially breaking changes.</span></span>

<span data-ttu-id="6656f-123">✔️请考虑使用 [SemVer 2.0.0](https://semver.org/) 控制 NuGet 包的版本。</span><span class="sxs-lookup"><span data-stu-id="6656f-123">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="6656f-124">✔️请在公共文档中使用 NuGet 包版本，因为它是用户通常看到的版本号。</span><span class="sxs-lookup"><span data-stu-id="6656f-124">**✔️ DO** use the NuGet package version in public documentation as it's the version number that users will commonly see.</span></span>

<span data-ttu-id="6656f-125">✔️请在发布非稳定版包时包含预发行后缀。</span><span class="sxs-lookup"><span data-stu-id="6656f-125">**✔️ DO** include a pre-release suffix when releasing a non-stable package.</span></span>

> <span data-ttu-id="6656f-126">用户必须选择获取预发行包，以便了解包不是完整的。</span><span class="sxs-lookup"><span data-stu-id="6656f-126">Users must opt in to getting pre-release packages, so they will understand that the package is not complete.</span></span>

### <a name="assembly-version"></a><span data-ttu-id="6656f-127">程序集版本</span><span class="sxs-lookup"><span data-stu-id="6656f-127">Assembly version</span></span>

<span data-ttu-id="6656f-128">程序集版本是 CLR 在运行时用来选择要加载哪个程序集版本的依据。</span><span class="sxs-lookup"><span data-stu-id="6656f-128">The assembly version is what the CLR uses at runtime to select which version of an assembly to load.</span></span> <span data-ttu-id="6656f-129">使用版本控制选择程序集仅适用于具有强名称的程序集。</span><span class="sxs-lookup"><span data-stu-id="6656f-129">Selecting an assembly using versioning only applies to assemblies with a strong name.</span></span>

```xml
<AssemblyVersion>1.0.0.0</AssemblyVersion>
```

<span data-ttu-id="6656f-130">Windows .NET Framework CLR 要求完全匹配以便加载具有强名称的程序集。</span><span class="sxs-lookup"><span data-stu-id="6656f-130">The Windows .NET Framework CLR demands an exact match to load a strong named assembly.</span></span> <span data-ttu-id="6656f-131">例如，`Libary1, Version=1.0.0.0` 已使用对 `Newtonsoft.Json, Version=11.0.0.0` 的引用进行编译。</span><span class="sxs-lookup"><span data-stu-id="6656f-131">For example, `Libary1, Version=1.0.0.0` was compiled with a reference to `Newtonsoft.Json, Version=11.0.0.0`.</span></span> <span data-ttu-id="6656f-132">.NET Framework 将仅加载该确切版本 `11.0.0.0`。</span><span class="sxs-lookup"><span data-stu-id="6656f-132">The .NET Framework will only load that exact version `11.0.0.0`.</span></span> <span data-ttu-id="6656f-133">若要在运行时加载其他版本，必须向 .NET 应用程序的配置文件添加绑定重定向。</span><span class="sxs-lookup"><span data-stu-id="6656f-133">To load a different version at runtime, a binding redirect must be added to the .NET application's config file.</span></span>

<span data-ttu-id="6656f-134">与程序集版本组合使用的强命名启用[严格的程序集版本加载](../../framework/app-domains/assembly-versioning.md)。</span><span class="sxs-lookup"><span data-stu-id="6656f-134">Strong naming combined with assembly version enables [strict assembly version loading](../../framework/app-domains/assembly-versioning.md).</span></span> <span data-ttu-id="6656f-135">虽然强命名库具有很多好处，但通常会导致出现找不到程序集的运行时异常，并且在要修复的 `app.config`/`web.config` 中[需要绑定重定向](../../framework/configure-apps/redirect-assembly-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="6656f-135">While strong naming a library has a number of benefits, it often results in runtime exceptions that an assembly can't be found and [requires binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) in `app.config`/`web.config` to be fixed.</span></span> <span data-ttu-id="6656f-136">已放宽 .NET Core 程序集加载，并且 .NET Core CLR 将在运行时自动加载更高版本的程序集。</span><span class="sxs-lookup"><span data-stu-id="6656f-136">.NET Core assembly loading has been relaxed, and the .NET Core CLR will automatically load assemblies at runtime with a higher version.</span></span>

<span data-ttu-id="6656f-137">✔️请考虑在 AssemblyVersion 中仅包括主版本。</span><span class="sxs-lookup"><span data-stu-id="6656f-137">**✔️ CONSIDER** only including a major version in the AssemblyVersion.</span></span>

> <span data-ttu-id="6656f-138">例如，库 1.0 和库 1.0.1 都具有 AssemblyVersion `1.0.0.0`，而库 2.0 具有 AssemblyVersion `2.0.0.0`。</span><span class="sxs-lookup"><span data-stu-id="6656f-138">e.g. Library 1.0 and Library 1.0.1 both have an AssemblyVersion of `1.0.0.0`, while Library 2.0 has AssemblyVersion of `2.0.0.0`.</span></span> <span data-ttu-id="6656f-139">当程序集版本不常更改时，会减少绑定重定向。</span><span class="sxs-lookup"><span data-stu-id="6656f-139">When the assembly version changes less often, it reduces binding redirects.</span></span>

<span data-ttu-id="6656f-140">✔️请考虑使 AssemblyVersion 的主版本号与 NuGet 包版本保持同步。</span><span class="sxs-lookup"><span data-stu-id="6656f-140">**✔️ CONSIDER** keeping the major version number of the AssemblyVersion and the NuGet package version in sync.</span></span>

> <span data-ttu-id="6656f-141">AssemblyVersion 包含在向用户显示的一些信息性消息中，例如异常消息中的程序集名称和程序集限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="6656f-141">The AssemblyVersion is included in some informational messages displayed to the user, e.g. the assembly name and assembly qualified type names in exception messages.</span></span> <span data-ttu-id="6656f-142">维持版本之间的关系可向开发人员提供有关所用版本的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6656f-142">Maintaining a relationship between the versions provides more information to developers about which version they are using.</span></span>

<span data-ttu-id="6656f-143">❌不要有固定的 AssemblyVersion。</span><span class="sxs-lookup"><span data-stu-id="6656f-143">**❌ DO NOT** have a fixed AssemblyVersion.</span></span>

> <span data-ttu-id="6656f-144">虽然不变的 AssemblyVersion 不需要绑定重定向，但意味着在全局程序集缓存 (GAC) 中只能安装单个程序集版本。</span><span class="sxs-lookup"><span data-stu-id="6656f-144">While an unchanging AssemblyVersion avoids the need for binding redirects, it means that only a single version of the assembly can be installed in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="6656f-145">此外，引用 GAC 中的程序集的应用程序将中断，前提是另一个应用程序使用重大更改更新 GAC 程序集。</span><span class="sxs-lookup"><span data-stu-id="6656f-145">Also, the applications that reference the assembly in the GAC will break if another application updates the GAC assembly with breaking changes.</span></span>

### <a name="assembly-file-version"></a><span data-ttu-id="6656f-146">程序集文件版本</span><span class="sxs-lookup"><span data-stu-id="6656f-146">Assembly file version</span></span>

<span data-ttu-id="6656f-147">程序集文件版本用于在 Windows 中显示文件版本，并且对运行时行为没有影响。</span><span class="sxs-lookup"><span data-stu-id="6656f-147">The assembly file version is used to display a file version in Windows and has no effect on runtime behavior.</span></span> <span data-ttu-id="6656f-148">设置此版本是可选的。</span><span class="sxs-lookup"><span data-stu-id="6656f-148">Setting this version is optional.</span></span> <span data-ttu-id="6656f-149">它在 Windows 资源管理器的“文件属性”对话框中可见：</span><span class="sxs-lookup"><span data-stu-id="6656f-149">It's visible in the File Properties dialog in Windows Explorer:</span></span>

```xml
<FileVersion>11.0.2.21924</FileVersion>
```

<span data-ttu-id="6656f-150">![Windows 资源管理器](./media/versioning/win-properties.png "Windows 资源管理器")</span><span class="sxs-lookup"><span data-stu-id="6656f-150">![Windows Explorer](./media/versioning/win-properties.png "Windows Explorer")</span></span>

> [!NOTE]
> <span data-ttu-id="6656f-151">如果此版本未采用 `Major.Minor.Build.Revision` 格式，则会引发没有威胁的生成警告。</span><span class="sxs-lookup"><span data-stu-id="6656f-151">An innocuous build warning is raised if this version does not follow the format `Major.Minor.Build.Revision`.</span></span> <span data-ttu-id="6656f-152">可放心忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="6656f-152">The warning can be safely ignored.</span></span>

<span data-ttu-id="6656f-153">✔️请考虑包括持续集成内部版本号作为 AssemblyFileVersion 修订号。</span><span class="sxs-lookup"><span data-stu-id="6656f-153">**✔️ CONSIDER** including a continuous integration build number as the AssemblyFileVersion revision.</span></span>

> <span data-ttu-id="6656f-154">例如，生成的项目版本为 1.0.0 且持续集成内部版本号为 99，则 AssemblyFileVersion 为 1.0.0.99。</span><span class="sxs-lookup"><span data-stu-id="6656f-154">For example, you are building version 1.0.0 of your project, and the continuous integration build number is 99 so your AssemblyFileVersion is 1.0.0.99.</span></span>

### <a name="assembly-informational-version"></a><span data-ttu-id="6656f-155">程序集信息性版本</span><span class="sxs-lookup"><span data-stu-id="6656f-155">Assembly informational version</span></span>

<span data-ttu-id="6656f-156">程序集信息性版本用于记录附加版本信息，并且对运行时行为没有影响。</span><span class="sxs-lookup"><span data-stu-id="6656f-156">The assembly informational version is used to record additional version information and has no effect on runtime behavior.</span></span> <span data-ttu-id="6656f-157">设置此版本是可选的。</span><span class="sxs-lookup"><span data-stu-id="6656f-157">Setting this version is optional.</span></span> <span data-ttu-id="6656f-158">如果使用的是 SourceLink，则将在具有 NuGet 包版本以及源代码管理版本的内部版本上设置此版本。</span><span class="sxs-lookup"><span data-stu-id="6656f-158">If you're using SourceLink, this version will be set on build with the NuGet package version plus a source control version.</span></span> <span data-ttu-id="6656f-159">例如，`1.0.0-beta1+204ff0a` 包括从中生成程序集的源代码的提交哈希。</span><span class="sxs-lookup"><span data-stu-id="6656f-159">For example, `1.0.0-beta1+204ff0a` includes the commit hash of the source code the assembly was built from.</span></span> <span data-ttu-id="6656f-160">有关详细信息，请参阅 [SourceLink](./sourcelink.md)。</span><span class="sxs-lookup"><span data-stu-id="6656f-160">For more information, see [SourceLink](./sourcelink.md).</span></span>

```xml
<AssemblyInformationalVersion>The quick brown fox jumped over the lazy dog.</AssemblyInformationalVersion>
```

<span data-ttu-id="6656f-161">❌请避免自行设置程序集信息性版本。</span><span class="sxs-lookup"><span data-stu-id="6656f-161">**❌ AVOID** setting the assembly informational version yourself.</span></span>

> <span data-ttu-id="6656f-162">允许 SourceLink 自动生成包含 NuGet 和源代码管理元数据的版本。</span><span class="sxs-lookup"><span data-stu-id="6656f-162">Allow SourceLink to automatically generate the version containing NuGet and source control metadata.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="6656f-163">[上一页](./publish-nuget-package.md)
[下一页](./breaking-changes.md)</span><span class="sxs-lookup"><span data-stu-id="6656f-163">[Previous](./publish-nuget-package.md)
[Next](./breaking-changes.md)</span></span>
