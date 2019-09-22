---
title: dotnet msbuild 命令
description: dotnet msbuild 命令可提供对 MSBuild 命令行的访问权限。
ms.date: 12/03/2018
ms.openlocfilehash: b83f1272cdd4c5fcdb6b1e34aef7692e9acc01cd
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117701"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="cb6a6-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="cb6a6-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="cb6a6-104">name</span><span class="sxs-lookup"><span data-stu-id="cb6a6-104">Name</span></span>

<span data-ttu-id="cb6a6-105">`dotnet msbuild` - 生成项目及其所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="cb6a6-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cb6a6-106">摘要</span><span class="sxs-lookup"><span data-stu-id="cb6a6-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="cb6a6-107">说明</span><span class="sxs-lookup"><span data-stu-id="cb6a6-107">Description</span></span>

<span data-ttu-id="cb6a6-108">`dotnet msbuild` 命令允许访问功能完备的 MSBuild。</span><span class="sxs-lookup"><span data-stu-id="cb6a6-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="cb6a6-109">该命令与仅适用于 SDK 样式项目的现有 MSBuild 命令行客户端具有完全相同的功能。</span><span class="sxs-lookup"><span data-stu-id="cb6a6-109">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style project only.</span></span> <span data-ttu-id="cb6a6-110">选项一致。</span><span class="sxs-lookup"><span data-stu-id="cb6a6-110">The options are all the same.</span></span> <span data-ttu-id="cb6a6-111">有关可用选项的详细信息，请参阅 [MSBuild 命令行参考](/visualstudio/msbuild/msbuild-command-line-reference)。</span><span class="sxs-lookup"><span data-stu-id="cb6a6-111">For more information about the available options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="cb6a6-112">[dotnet build](dotnet-build.md) 命令相当于 `dotnet msbuild -restore -target:Build`。</span><span class="sxs-lookup"><span data-stu-id="cb6a6-112">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="cb6a6-113">`dotnet build` 更常用于生成项目，但 `dotnet msbuild` 可使用户更好地进行控制。</span><span class="sxs-lookup"><span data-stu-id="cb6a6-113">`dotnet build` is more commonly used for building projects, but `dotnet msbuild` gives you more control.</span></span> <span data-ttu-id="cb6a6-114">例如，如果想要运行特定目标（而不运行生成目标），可能更倾向于使用 `dotnet msbuild`。</span><span class="sxs-lookup"><span data-stu-id="cb6a6-114">For example, if you have a specific target you want to run (without running the build target), you probably want to use `dotnet msbuild`.</span></span>

## <a name="examples"></a><span data-ttu-id="cb6a6-115">示例</span><span class="sxs-lookup"><span data-stu-id="cb6a6-115">Examples</span></span>

* <span data-ttu-id="cb6a6-116">生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="cb6a6-116">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

* <span data-ttu-id="cb6a6-117">使用“发布”配置生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="cb6a6-117">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -p:Configuration=Release
  ```

* <span data-ttu-id="cb6a6-118">运行发布目标并发布 `osx.10.11-x64` RID：</span><span class="sxs-lookup"><span data-stu-id="cb6a6-118">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64
  ```

* <span data-ttu-id="cb6a6-119">请参阅包含 SDK 添加的所有目标的整个项目：</span><span class="sxs-lookup"><span data-stu-id="cb6a6-119">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -pp
  ```
