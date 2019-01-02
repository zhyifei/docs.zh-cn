---
title: global.json 概述
description: 了解如何在运行 .NET Core CLI 命令时使用 global.json 文件设置 .NET Core SDK 版本。
ms.date: 12/03/2018
ms.custom: updateeachrelease, seodec18
ms.openlocfilehash: e0f929a049812cac6f62e5218629c9b0add83de8
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170764"
---
# <a name="globaljson-overview"></a><span data-ttu-id="a00f0-103">global.json 概述</span><span class="sxs-lookup"><span data-stu-id="a00f0-103">global.json overview</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

<span data-ttu-id="a00f0-104">通过 global.json 文件，可定义在运行 .NET Core CLI 命令时使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="a00f0-104">The *global.json* file allows you to define which .NET Core SDK version is used when you run .NET Core CLI commands.</span></span> <span data-ttu-id="a00f0-105">选择 .NET Core SDK 与指定项目所面向的运行时无关。</span><span class="sxs-lookup"><span data-stu-id="a00f0-105">Selecting the .NET Core SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="a00f0-106">.NET Core SDK 版本指示使用哪个版本的 .NET Core CLI 工具。</span><span class="sxs-lookup"><span data-stu-id="a00f0-106">The .NET Core SDK version indicates which versions of the .NET Core CLI tools are used.</span></span> <span data-ttu-id="a00f0-107">通常会使用最新版本的工具，因此不需要 global.json 文件。</span><span class="sxs-lookup"><span data-stu-id="a00f0-107">In general, you want to use the latest version of the tools, so no *global.json* file is needed.</span></span>

<span data-ttu-id="a00f0-108">有关指定运行时的详细信息，请参阅[目标框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="a00f0-108">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="a00f0-109">.NET Core SDK 在当前工作目录（不必与项目目录相同）或其某个父目录中查找 global.json 文件。</span><span class="sxs-lookup"><span data-stu-id="a00f0-109">.NET Core SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="a00f0-110">global.json 架构</span><span class="sxs-lookup"><span data-stu-id="a00f0-110">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="a00f0-111">SDK</span><span class="sxs-lookup"><span data-stu-id="a00f0-111">sdk</span></span>

<span data-ttu-id="a00f0-112">类型：对象</span><span class="sxs-lookup"><span data-stu-id="a00f0-112">Type: Object</span></span>

<span data-ttu-id="a00f0-113">指定要选择的 .NET Core SDK 的相关信息。</span><span class="sxs-lookup"><span data-stu-id="a00f0-113">Specifies information about the .NET Core SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="a00f0-114">version</span><span class="sxs-lookup"><span data-stu-id="a00f0-114">version</span></span>

<span data-ttu-id="a00f0-115">类型：String</span><span class="sxs-lookup"><span data-stu-id="a00f0-115">Type: String</span></span>

<span data-ttu-id="a00f0-116">要使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="a00f0-116">The version of the .NET Core SDK to use.</span></span>

<span data-ttu-id="a00f0-117">请注意，此字段：</span><span class="sxs-lookup"><span data-stu-id="a00f0-117">Note that this field:</span></span>

- <span data-ttu-id="a00f0-118">不具备通配支持，也就是说，必须指定完整版本号。</span><span class="sxs-lookup"><span data-stu-id="a00f0-118">Doesn't have globbing support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="a00f0-119">不支持版本范围。</span><span class="sxs-lookup"><span data-stu-id="a00f0-119">Doesn't support version ranges.</span></span>

<span data-ttu-id="a00f0-120">下面的示例展示 global.json 文件的内容：</span><span class="sxs-lookup"><span data-stu-id="a00f0-120">The following example shows the contents of a *global.json* file:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a><span data-ttu-id="a00f0-121">global.json 和 .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="a00f0-121">global.json and the .NET Core CLI</span></span>

<span data-ttu-id="a00f0-122">最好能知道哪些版本可用，以便在 global.json 文件中设置相应版本。</span><span class="sxs-lookup"><span data-stu-id="a00f0-122">It's helpful to know which versions are available in order to set one in the *global.json* file.</span></span> <span data-ttu-id="a00f0-123">可在 [.NET 下载](https://www.microsoft.com/net/download/all)站点中找到支持的可用 SDK 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="a00f0-123">You can find the full list of supported available SDKs at the [.NET Downloads](https://www.microsoft.com/net/download/all) site.</span></span> <span data-ttu-id="a00f0-124">从 .NET Core 2.1 SDK 开始，可运行以下命令来验证计算机上已安装的 SDK 版本：</span><span class="sxs-lookup"><span data-stu-id="a00f0-124">Starting with .NET Core 2.1 SDK, you can run the following command to verify which SDK versions are already installed on your machine:</span></span>

```console
dotnet --list-sdks
```

<span data-ttu-id="a00f0-125">若要在计算机上安装其他 .NET Core SDK 版本，请访问 [.NET 下载](https://www.microsoft.com/net/download/all)站点。</span><span class="sxs-lookup"><span data-stu-id="a00f0-125">To install additional .NET Core SDK versions on your machine, visit the [.NET Downloads](https://www.microsoft.com/net/download/all) site.</span></span>

<span data-ttu-id="a00f0-126">可执行 [dotnet new](dotnet-new.md) 命令在当前目录中创建一个新的 global.json 文件，类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="a00f0-126">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```console
dotnet new globaljson --sdk-version 2.2.100
```

## <a name="matching-rules"></a><span data-ttu-id="a00f0-127">匹配规则</span><span class="sxs-lookup"><span data-stu-id="a00f0-127">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="a00f0-128">匹配规则由 apphost 掌管，apphost 是.NET Core 运行时的一部分。</span><span class="sxs-lookup"><span data-stu-id="a00f0-128">The matching rules are governed by the apphost, which is part of the .NET Core runtime.</span></span>
> <span data-ttu-id="a00f0-129">如果并行安装了多个运行时，则使用最新版本的主机。</span><span class="sxs-lookup"><span data-stu-id="a00f0-129">The latest version of the host is used when you have multiple runtimes installed side-by-side.</span></span>

<span data-ttu-id="a00f0-130">从 .NET Core 2.0 开始，在确定要使用的 SDK 版本时，适用以下规则：</span><span class="sxs-lookup"><span data-stu-id="a00f0-130">Starting with .NET Core 2.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="a00f0-131">如果未找到 global.json 文件或 global.json 未指定 SDK 版本，则使用最新安装的 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="a00f0-131">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="a00f0-132">最新 SDK 版本可能是发布版本或预发布版本 - 以版本号更高的为准。</span><span class="sxs-lookup"><span data-stu-id="a00f0-132">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>
- <span data-ttu-id="a00f0-133">如果 global.json 指定了 SDK 版本：</span><span class="sxs-lookup"><span data-stu-id="a00f0-133">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="a00f0-134">如果计算机上安装了该指定的 SDK 版本，则使用该版本。</span><span class="sxs-lookup"><span data-stu-id="a00f0-134">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="a00f0-135">如果计算机上未安装指定的 SDK 版本，则使用最新安装的该版本的 SDK 修补程序版本。</span><span class="sxs-lookup"><span data-stu-id="a00f0-135">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="a00f0-136">最新安装的 SDK 修补程序版本可能是发布版本或预发布版本 - 以版本号更高的为准。</span><span class="sxs-lookup"><span data-stu-id="a00f0-136">Latest installed SDK **patch version** can be either release or pre-release - the highest version number wins.</span></span> <span data-ttu-id="a00f0-137">在 .NET Core 2.1 及更高版本中，在选择 SDK 版本时将忽略低于指定修补程序版本的修补程序版本。</span><span class="sxs-lookup"><span data-stu-id="a00f0-137">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="a00f0-138">如果找不到指定的 SDK 版本和相应的 SDK 修补程序版本，会引发错误。</span><span class="sxs-lookup"><span data-stu-id="a00f0-138">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="a00f0-139">SDK 版本目前由以下部分组成：</span><span class="sxs-lookup"><span data-stu-id="a00f0-139">The SDK version is currently composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="a00f0-140">.NET Core SDK 的功能版本由 SDK 版本 2.1.100 及更高版本所采用的版本号的最后一部分 (`xyz`) 的第一个数字 (`x`) 表示。</span><span class="sxs-lookup"><span data-stu-id="a00f0-140">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="a00f0-141">通常，.NET Core SDK 的发布周期比 .NET Core 快。</span><span class="sxs-lookup"><span data-stu-id="a00f0-141">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="a00f0-142">修补程序版本由 SDK 版本 2.1.100 及更高版本所采用的版本号的最后一部分 (`xyz`) 的后两位数字 (`yz`) 表示。</span><span class="sxs-lookup"><span data-stu-id="a00f0-142">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="a00f0-143">例如，如果将 `2.1.300` 指定为 SDK 版本，则可选的 SDK 版本号最多到 `2.1.399`，但 `2.1.400` 不视为 `2.1.300` 的一个修补程序版本。</span><span class="sxs-lookup"><span data-stu-id="a00f0-143">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="a00f0-144">版本号架构过渡期间发布了 .NET Core SDK 版本 `2.1.100` 到 `2.1.201`，但未正确使用 `xyz` 表示法。</span><span class="sxs-lookup"><span data-stu-id="a00f0-144">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="a00f0-145">强烈建议如果在 global.json 文件中指定了这些版本，请确保目标计算机上安装了指定版本。</span><span class="sxs-lookup"><span data-stu-id="a00f0-145">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

<span data-ttu-id="a00f0-146">如果使用 .NET Core SDK 1.x，在指定了版本但未找到完全匹配项的情况下，则使用最新安装的 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="a00f0-146">With .NET Core SDK 1.x, if you specified a version and no exact match was found, the latest installed SDK version was used.</span></span> <span data-ttu-id="a00f0-147">最新 SDK 版本可能是发布版本或预发布版本 - 以版本号更高的为准。</span><span class="sxs-lookup"><span data-stu-id="a00f0-147">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>

## <a name="troubleshooting-build-warnings"></a><span data-ttu-id="a00f0-148">针对生成警告的疑难解答</span><span class="sxs-lookup"><span data-stu-id="a00f0-148">Troubleshooting build warnings</span></span>

> [!WARNING]
> <span data-ttu-id="a00f0-149">使用的是 .NET Core SDK 的预览版本，</span><span class="sxs-lookup"><span data-stu-id="a00f0-149">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="a00f0-150">可通过当前项目中的 global.json 文件定义 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="a00f0-150">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="a00f0-151">有关详细信息，请访问 <https://go.microsoft.com/fwlink/?linkid=869452></span><span class="sxs-lookup"><span data-stu-id="a00f0-151">More at <https://go.microsoft.com/fwlink/?linkid=869452></span></span>

<span data-ttu-id="a00f0-152">此警告指示正在使用 .NET Core SDK 预览版本编译项目，如[匹配规则](#matching-rules)部分所述。</span><span class="sxs-lookup"><span data-stu-id="a00f0-152">This warning indicates that your project is being compiled using a preview version of the .NET Core SDK, as explained in the [Matching rules](#matching-rules) section.</span></span> <span data-ttu-id="a00f0-153">.NET Core SDK 的各种版本均品质优良稳定，在业内口碑良好。</span><span class="sxs-lookup"><span data-stu-id="a00f0-153">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="a00f0-154">但如果不想使用预览版本，可将 global.json 文件添加到项目层次结构中以指定要使用的 SDK 版本，并使用 `dotnet --list-sdks` 来确认计算机上已安装该版本。</span><span class="sxs-lookup"><span data-stu-id="a00f0-154">However, if you don't want to use a preview version, add a *global.json* file to your project hierarchy structure to specify which SDK version to use, and use `dotnet --list-sdks` to confirm that the version is installed on your machine.</span></span> <span data-ttu-id="a00f0-155">发布新版本时，若要使用新版本，可删除 global.json 文件或将其更新以使用较新版本。</span><span class="sxs-lookup"><span data-stu-id="a00f0-155">When a new version is released, to use the new version, either remove the *global.json* file or update it to use the newer version.</span></span>

> [!WARNING]
> <span data-ttu-id="a00f0-156">启动项目 '{startupProject}' 面向框架 '.NETCoreApp' 的版本 '{targetFrameworkVersion}'。</span><span class="sxs-lookup"><span data-stu-id="a00f0-156">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="a00f0-157">此版本的 Entity Framework Core .NET 命令行工具仅支持 2.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a00f0-157">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="a00f0-158">有关使用旧版工具的信息，请参阅 <https://go.microsoft.com/fwlink/?linkid=871254></span><span class="sxs-lookup"><span data-stu-id="a00f0-158">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254></span></span>

<span data-ttu-id="a00f0-159">从 .NET Core 2.1 SDK（版本 2.1.300）开始，SDK 中包含 `dotnet ef` 命令。</span><span class="sxs-lookup"><span data-stu-id="a00f0-159">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="a00f0-160">此警告指示项目面向 EF Core 1.0 或 1.1，后者与 .NET Core 2.1 SDK 及更高版本不兼容。</span><span class="sxs-lookup"><span data-stu-id="a00f0-160">This warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions.</span></span> <span data-ttu-id="a00f0-161">若要编译项目，请在计算机上安装 .NET Core 2.0 SDK（版本 2.1.201）及更早版本，并使用 global.json 文件定义所需 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="a00f0-161">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) and earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="a00f0-162">有关 `dotnet ef` 命令的详细信息，请参阅 [EF Core .NET 命令行工具](/ef/core/miscellaneous/cli/dotnet)。</span><span class="sxs-lookup"><span data-stu-id="a00f0-162">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="a00f0-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="a00f0-163">See also</span></span>

- [<span data-ttu-id="a00f0-164">如何解析 SDK 项目</span><span class="sxs-lookup"><span data-stu-id="a00f0-164">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)