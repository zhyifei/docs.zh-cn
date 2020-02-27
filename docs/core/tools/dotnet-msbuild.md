---
title: dotnet msbuild 命令
description: dotnet msbuild 命令可提供对 MSBuild 命令行的访问权限。
ms.date: 02/14/2020
ms.openlocfilehash: 28a32a460d644d3e22f16b5dd9416222ae466e2e
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503676"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="861c0-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="861c0-103">dotnet msbuild</span></span>

<span data-ttu-id="861c0-104">**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="861c0-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="861c0-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="861c0-105">Name</span></span>

<span data-ttu-id="861c0-106">`dotnet msbuild` - 生成项目及其所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="861c0-106">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="861c0-107">摘要</span><span class="sxs-lookup"><span data-stu-id="861c0-107">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="861c0-108">描述</span><span class="sxs-lookup"><span data-stu-id="861c0-108">Description</span></span>

<span data-ttu-id="861c0-109">`dotnet msbuild` 命令允许访问功能完备的 MSBuild。</span><span class="sxs-lookup"><span data-stu-id="861c0-109">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="861c0-110">该命令与仅适用于 SDK 样式项目的现有 MSBuild 命令行客户端具有完全相同的功能。</span><span class="sxs-lookup"><span data-stu-id="861c0-110">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="861c0-111">选项一致。</span><span class="sxs-lookup"><span data-stu-id="861c0-111">The options are all the same.</span></span> <span data-ttu-id="861c0-112">有关可用选项的详细信息，请参阅 [MSBuild 命令行参考](/visualstudio/msbuild/msbuild-command-line-reference)。</span><span class="sxs-lookup"><span data-stu-id="861c0-112">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="861c0-113">[dotnet build](dotnet-build.md) 命令相当于 `dotnet msbuild -restore -target:Build`。</span><span class="sxs-lookup"><span data-stu-id="861c0-113">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="861c0-114">[dotnet build](dotnet-build.md) 更常用于生成项目，但由于它始终运行生成目标，因此不想生成项目时可以使用 `dotnet msbuild`。</span><span class="sxs-lookup"><span data-stu-id="861c0-114">[dotnet build](dotnet-build.md) is more commonly used for building projects, but because it always runs the build target, you can use `dotnet msbuild` when you don't want to build the project.</span></span> <span data-ttu-id="861c0-115">例如，如果想要运行特定目标而不生成项目，请使用 `dotnet msbuild` 指定目标。</span><span class="sxs-lookup"><span data-stu-id="861c0-115">For example, if you have a specific target you want to run without building the project, use `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="861c0-116">示例</span><span class="sxs-lookup"><span data-stu-id="861c0-116">Examples</span></span>

- <span data-ttu-id="861c0-117">生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="861c0-117">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

- <span data-ttu-id="861c0-118">使用“发布”配置生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="861c0-118">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- <span data-ttu-id="861c0-119">运行发布目标并发布 `osx.10.11-x64` RID：</span><span class="sxs-lookup"><span data-stu-id="861c0-119">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- <span data-ttu-id="861c0-120">请参阅包含 SDK 添加的所有目标的整个项目：</span><span class="sxs-lookup"><span data-stu-id="861c0-120">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
