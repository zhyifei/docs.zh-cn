---
title: dotnet msbuild 命令 - .NET Core CLI
description: dotnet msbuild 命令可提供对 MSBuild 命令行的访问权限。
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 9e6f8b3063b4cd2a3a36cae8839d6f83e0466e03
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="f3806-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="f3806-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="f3806-104">name</span><span class="sxs-lookup"><span data-stu-id="f3806-104">Name</span></span>

<span data-ttu-id="f3806-105">`dotnet msbuild` - 生成项目及其所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="f3806-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f3806-106">摘要</span><span class="sxs-lookup"><span data-stu-id="f3806-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="f3806-107">描述</span><span class="sxs-lookup"><span data-stu-id="f3806-107">Description</span></span>

<span data-ttu-id="f3806-108">`dotnet msbuild` 命令允许访问功能完备的 MSBuild。</span><span class="sxs-lookup"><span data-stu-id="f3806-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="f3806-109">该命令与现有的 MSBuild 命令行客户端具有完全相同的功能。</span><span class="sxs-lookup"><span data-stu-id="f3806-109">The command has the exact same capabilities as existing MSBuild command-line client.</span></span> <span data-ttu-id="f3806-110">选项一致。</span><span class="sxs-lookup"><span data-stu-id="f3806-110">The options are all the same.</span></span> <span data-ttu-id="f3806-111">使用 [MSBuild 命令行引用](/visualstudio/msbuild/msbuild-command-line-reference)获取可用选项的信息。</span><span class="sxs-lookup"><span data-stu-id="f3806-111">Use the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) to obtain information on the available options.</span></span> 

## <a name="examples"></a><span data-ttu-id="f3806-112">示例</span><span class="sxs-lookup"><span data-stu-id="f3806-112">Examples</span></span>

<span data-ttu-id="f3806-113">生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="f3806-113">Build a project and its dependencies:</span></span>

`dotnet msbuild`

<span data-ttu-id="f3806-114">使用“发布”配置生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="f3806-114">Build a project and its dependencies using Release configuration:</span></span>

`dotnet msbuild /p:Configuration=Release`

<span data-ttu-id="f3806-115">运行发布目标并发布 `osx.10.11-x64` RID：</span><span class="sxs-lookup"><span data-stu-id="f3806-115">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

<span data-ttu-id="f3806-116">请参阅包含 SDK 添加的所有目标的整个项目：</span><span class="sxs-lookup"><span data-stu-id="f3806-116">See the whole project with all targets included by the SDK:</span></span>

`dotnet msbuild /pp`
