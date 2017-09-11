---
title: "dotnet-msbuild 命令 - .NET Core CLI"
description: "dotnet-msbuild 命令提供对 MSBuild 命令行的访问。"
keywords: "dotnet-msmsbuild, CLI, CLI 命令, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 05/24/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1f02dcd779b9ed249ebd2fedb973383b1dcd8963
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-msbuild"></a><span data-ttu-id="6e93c-104">dotnet-msbuild</span><span class="sxs-lookup"><span data-stu-id="6e93c-104">dotnet-msbuild</span></span>

## <a name="name"></a><span data-ttu-id="6e93c-105">名称</span><span class="sxs-lookup"><span data-stu-id="6e93c-105">Name</span></span>

<span data-ttu-id="6e93c-106">`dotnet-msbuild` - 生成项目及其所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="6e93c-106">`dotnet-msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6e93c-107">摘要</span><span class="sxs-lookup"><span data-stu-id="6e93c-107">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="6e93c-108">说明</span><span class="sxs-lookup"><span data-stu-id="6e93c-108">Description</span></span>

<span data-ttu-id="6e93c-109">`dotnet msbuild` 命令允许访问功能完备的 MSBuild。</span><span class="sxs-lookup"><span data-stu-id="6e93c-109">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="6e93c-110">该命令与现有的 MSBuild 命令行客户端具有完全相同的功能。</span><span class="sxs-lookup"><span data-stu-id="6e93c-110">The command has the exact same capabilities as existing MSBuild command-line client.</span></span> <span data-ttu-id="6e93c-111">选项一致。</span><span class="sxs-lookup"><span data-stu-id="6e93c-111">The options are all the same.</span></span> <span data-ttu-id="6e93c-112">使用 [MSBuild 命令行引用](/visualstudio/msbuild/msbuild-command-line-reference)获取可用选项的信息。</span><span class="sxs-lookup"><span data-stu-id="6e93c-112">Use the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) to obtain information on the available options.</span></span> 

## <a name="examples"></a><span data-ttu-id="6e93c-113">示例</span><span class="sxs-lookup"><span data-stu-id="6e93c-113">Examples</span></span>

<span data-ttu-id="6e93c-114">生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="6e93c-114">Build a project and its dependencies:</span></span>

`dotnet msbuild`

<span data-ttu-id="6e93c-115">使用“发布”配置生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="6e93c-115">Build a project and its dependencies using Release configuration:</span></span>

`dotnet msbuild /p:Configuration=Release`

<span data-ttu-id="6e93c-116">运行发布目标并发布 `osx.10.11-x64` RID：</span><span class="sxs-lookup"><span data-stu-id="6e93c-116">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

<span data-ttu-id="6e93c-117">请参阅包含 SDK 添加的所有目标的整个项目：</span><span class="sxs-lookup"><span data-stu-id="6e93c-117">See the whole project with all targets included by the SDK:</span></span>

`dotnet msbuild /pp`

