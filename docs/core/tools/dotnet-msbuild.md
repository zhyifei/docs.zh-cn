---
title: dotnet msbuild 命令 - .NET Core CLI
description: dotnet msbuild 命令可提供对 MSBuild 命令行的访问权限。
ms.date: 12/03/2018
ms.openlocfilehash: 93471ded9614502ab89d5afb19dd9992f068ef80
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128042"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="6b013-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="6b013-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="6b013-104">name</span><span class="sxs-lookup"><span data-stu-id="6b013-104">Name</span></span>

<span data-ttu-id="6b013-105">`dotnet msbuild` - 生成项目及其所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="6b013-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6b013-106">摘要</span><span class="sxs-lookup"><span data-stu-id="6b013-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="6b013-107">说明</span><span class="sxs-lookup"><span data-stu-id="6b013-107">Description</span></span>

<span data-ttu-id="6b013-108">`dotnet msbuild` 命令允许访问功能完备的 MSBuild。</span><span class="sxs-lookup"><span data-stu-id="6b013-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="6b013-109">该命令与仅适用于 SDK 样式项目的现有 MSBuild 命令行客户端具有完全相同的功能。</span><span class="sxs-lookup"><span data-stu-id="6b013-109">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style project only.</span></span> <span data-ttu-id="6b013-110">选项一致。</span><span class="sxs-lookup"><span data-stu-id="6b013-110">The options are all the same.</span></span> <span data-ttu-id="6b013-111">有关可用选项的详细信息，请参阅 [MSBuild 命令行参考](/visualstudio/msbuild/msbuild-command-line-reference)。</span><span class="sxs-lookup"><span data-stu-id="6b013-111">For more information about the available options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="6b013-112">[dotnet build](dotnet-build.md) 命令相当于 `dotnet msbuild -restore -target:Build`。</span><span class="sxs-lookup"><span data-stu-id="6b013-112">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="6b013-113">`dotnet build` 更常用于生成项目，但 `dotnet msbuild` 可使用户更好地进行控制。</span><span class="sxs-lookup"><span data-stu-id="6b013-113">`dotnet build` is more commonly used for building projects, but `dotnet msbuild` gives you more control.</span></span> <span data-ttu-id="6b013-114">例如，如果想要运行特定目标（而不运行生成目标），可能更倾向于使用 `dotnet msbuild`。</span><span class="sxs-lookup"><span data-stu-id="6b013-114">For example, if you have a specific target you want to run (without running the build target), you probably want to use `dotnet msbuild`.</span></span>

## <a name="examples"></a><span data-ttu-id="6b013-115">示例</span><span class="sxs-lookup"><span data-stu-id="6b013-115">Examples</span></span>

* <span data-ttu-id="6b013-116">生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="6b013-116">Build a project and its dependencies:</span></span>

  ```console
  dotnet msbuild
  ```

* <span data-ttu-id="6b013-117">使用“发布”配置生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="6b013-117">Build a project and its dependencies using Release configuration:</span></span>

  ```console
  dotnet msbuild -p:Configuration=Release
  ```

* <span data-ttu-id="6b013-118">运行发布目标并发布 `osx.10.11-x64` RID：</span><span class="sxs-lookup"><span data-stu-id="6b013-118">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```console
  dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64
  ```

* <span data-ttu-id="6b013-119">请参阅包含 SDK 添加的所有目标的整个项目：</span><span class="sxs-lookup"><span data-stu-id="6b013-119">See the whole project with all targets included by the SDK:</span></span>

  ```console
  dotnet msbuild -pp
  ```