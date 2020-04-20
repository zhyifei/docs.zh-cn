---
title: dotnet msbuild 命令
description: dotnet msbuild 命令可提供对 MSBuild 命令行的访问权限。
ms.date: 02/14/2020
ms.openlocfilehash: 88e85868e2d7de564b2e4c90ce6e78bde4cb350e
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463628"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="5cc2f-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="5cc2f-103">dotnet msbuild</span></span>

<span data-ttu-id="5cc2f-104">**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="5cc2f-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="5cc2f-105">名称</span><span class="sxs-lookup"><span data-stu-id="5cc2f-105">Name</span></span>

<span data-ttu-id="5cc2f-106">`dotnet msbuild` - 生成项目及其所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="5cc2f-106">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5cc2f-107">摘要</span><span class="sxs-lookup"><span data-stu-id="5cc2f-107">Synopsis</span></span>

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

## <a name="description"></a><span data-ttu-id="5cc2f-108">说明</span><span class="sxs-lookup"><span data-stu-id="5cc2f-108">Description</span></span>

<span data-ttu-id="5cc2f-109">`dotnet msbuild` 命令允许访问功能完备的 MSBuild。</span><span class="sxs-lookup"><span data-stu-id="5cc2f-109">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="5cc2f-110">该命令与仅适用于 SDK 样式项目的现有 MSBuild 命令行客户端具有完全相同的功能。</span><span class="sxs-lookup"><span data-stu-id="5cc2f-110">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="5cc2f-111">选项一致。</span><span class="sxs-lookup"><span data-stu-id="5cc2f-111">The options are all the same.</span></span> <span data-ttu-id="5cc2f-112">有关可用选项的详细信息，请参阅 [MSBuild 命令行参考](/visualstudio/msbuild/msbuild-command-line-reference)。</span><span class="sxs-lookup"><span data-stu-id="5cc2f-112">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="5cc2f-113">[dotnet build](dotnet-build.md) 命令相当于 `dotnet msbuild -restore -target:Build`。</span><span class="sxs-lookup"><span data-stu-id="5cc2f-113">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="5cc2f-114">[dotnet build](dotnet-build.md) 更常用于生成项目，但由于它始终运行生成目标，因此不想生成项目时可以使用 `dotnet msbuild`。</span><span class="sxs-lookup"><span data-stu-id="5cc2f-114">[dotnet build](dotnet-build.md) is more commonly used for building projects, but because it always runs the build target, you can use `dotnet msbuild` when you don't want to build the project.</span></span> <span data-ttu-id="5cc2f-115">例如，如果想要运行特定目标而不生成项目，请使用 `dotnet msbuild` 指定目标。</span><span class="sxs-lookup"><span data-stu-id="5cc2f-115">For example, if you have a specific target you want to run without building the project, use `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="5cc2f-116">示例</span><span class="sxs-lookup"><span data-stu-id="5cc2f-116">Examples</span></span>

- <span data-ttu-id="5cc2f-117">生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="5cc2f-117">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

- <span data-ttu-id="5cc2f-118">使用“发布”配置生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="5cc2f-118">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- <span data-ttu-id="5cc2f-119">运行发布目标并发布 `osx.10.11-x64` RID：</span><span class="sxs-lookup"><span data-stu-id="5cc2f-119">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- <span data-ttu-id="5cc2f-120">请参阅包含 SDK 添加的所有目标的整个项目：</span><span class="sxs-lookup"><span data-stu-id="5cc2f-120">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
