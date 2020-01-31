---
title: dotnet msbuild 命令
description: dotnet msbuild 命令可提供对 MSBuild 命令行的访问权限。
ms.date: 12/03/2018
ms.openlocfilehash: dae1e9f0ca355166d41c11fbafb80c7c9fb29748
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733198"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="8f20b-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="8f20b-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="8f20b-104">“属性”</span><span class="sxs-lookup"><span data-stu-id="8f20b-104">Name</span></span>

<span data-ttu-id="8f20b-105">`dotnet msbuild` - 生成项目及其所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="8f20b-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8f20b-106">摘要</span><span class="sxs-lookup"><span data-stu-id="8f20b-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="8f20b-107">描述</span><span class="sxs-lookup"><span data-stu-id="8f20b-107">Description</span></span>

<span data-ttu-id="8f20b-108">`dotnet msbuild` 命令允许访问功能完备的 MSBuild。</span><span class="sxs-lookup"><span data-stu-id="8f20b-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="8f20b-109">该命令与仅适用于 SDK 样式项目的现有 MSBuild 命令行客户端具有完全相同的功能。</span><span class="sxs-lookup"><span data-stu-id="8f20b-109">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="8f20b-110">选项一致。</span><span class="sxs-lookup"><span data-stu-id="8f20b-110">The options are all the same.</span></span> <span data-ttu-id="8f20b-111">有关可用选项的详细信息，请参阅 [MSBuild 命令行参考](/visualstudio/msbuild/msbuild-command-line-reference)。</span><span class="sxs-lookup"><span data-stu-id="8f20b-111">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="8f20b-112">[dotnet build](dotnet-build.md) 命令相当于 `dotnet msbuild -restore -target:Build`。</span><span class="sxs-lookup"><span data-stu-id="8f20b-112">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="8f20b-113">[dotnet build](dotnet-build.md) 更常用于生成项目，但由于它始终运行生成目标，因此不想生成项目时可以使用 `dotnet msbuild`。</span><span class="sxs-lookup"><span data-stu-id="8f20b-113">[dotnet build](dotnet-build.md) is more commonly used for building projects, but because it always runs the build target, you can use `dotnet msbuild` when you don't want to build the project.</span></span> <span data-ttu-id="8f20b-114">例如，如果想要运行特定目标而不生成项目，请使用 `dotnet msbuild` 指定目标。</span><span class="sxs-lookup"><span data-stu-id="8f20b-114">For example, if you have a specific target you want to run without building the project, use `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="8f20b-115">示例</span><span class="sxs-lookup"><span data-stu-id="8f20b-115">Examples</span></span>

* <span data-ttu-id="8f20b-116">生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="8f20b-116">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

* <span data-ttu-id="8f20b-117">使用“发布”配置生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="8f20b-117">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

* <span data-ttu-id="8f20b-118">运行发布目标并发布 `osx.10.11-x64` RID：</span><span class="sxs-lookup"><span data-stu-id="8f20b-118">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

* <span data-ttu-id="8f20b-119">请参阅包含 SDK 添加的所有目标的整个项目：</span><span class="sxs-lookup"><span data-stu-id="8f20b-119">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
